# Test Strategy Document

**Issue ID:** AD-101

---

## Section 1: Scope

### Business Requirements & Boundaries
- Authenticated users can upload high-resolution images to their profile gallery.
- Uploaded images are displayed in the user's public portfolio grid.
- Upload button is accessible only to logged-in users.

### Constraints
- Maximum file size for uploads is 10MB.
- Only PNG and JPEG file formats are supported.
- Upload processing, virus scanning, and rendering must complete within 2.5 seconds on a standard 4G mobile network.
- Images are stored in AWS S3 via a secure API gateway.
- Image optimization/compression is performed server-side.

### In Scope
- Profile gallery image upload functionality.
- Authentication checks for upload access.
- File size and format validation.
- Upload processing, virus scanning, and rendering performance.
- AWS S3 storage integration.
- Server-side image optimization/compression.
- Portfolio grid synchronization.

### Out of Scope
- Client-side image optimization/compression.
- Support for file formats other than PNG and JPEG.
- Uploads by unauthenticated users.
- Storage solutions other than AWS S3.

---

## Section 2: Test Approach

### Testing Levels
- UI / Front-End Component Level (Upload button visibility, file picker, portfolio grid rendering)
- API / Backend Integration Level (Upload endpoint, authentication enforcement, virus scanning, S3 storage, server-side optimization)
- End-to-End System Integration Level (Full upload-to-portfolio sync workflow, including network latency simulation)

### Testing Types
- Functional Testing (Authentication gating, file format/size validation, upload success/failure flows)
- Negative Testing (Oversized files, unsupported formats, unauthenticated access attempts)
- Performance & SLA Latency Testing (Upload, virus scan, and rendering within 2.5 seconds on 4G network simulation)
- Integration Testing (AWS S3 storage, server-side optimization, and portfolio grid sync)

### Test Design Techniques
- Boundary Value Analysis (File size at 10MB limit, min/max image dimensions, edge-case file names)
- Equivalence Partitioning (Valid PNG/JPEG vs. invalid formats, authenticated vs. unauthenticated users)
- State Transition Testing (User authentication state changes affecting upload button visibility and access)
- Decision Table Testing (Combinations of file size, format, and authentication status for upload acceptance/rejection)
- Performance Profiling (Measuring end-to-end upload-to-render time under simulated 4G conditions)

### Environments Needed
- Staging environment with production-like AWS S3 buckets (isolated for test data cleanup)
- Mock authentication provider or seeded test user accounts for positive/negative access scenarios
- Network virtualization tools (e.g., 4G mobile network simulation for latency and bandwidth constraints)
- Test data matrix of image files (PNG/JPEG at various sizes, including boundary and invalid cases)
- Backend monitoring/logging hooks to validate virus scan, optimization, and S3 storage events
- Portfolio grid UI test harness for instant sync verification

### Automation Frameworks & Tools
- **Playwright**: For UI automation (upload button gating, file picker, portfolio grid sync).
- **PyTest**: For API and backend validation (upload endpoint, authentication, S3 storage, server-side optimization).
- **JMeter**: For performance and SLA latency testing (simulating 4G network, measuring end-to-end upload-to-render time).
- **LocalStack**: For AWS S3 integration testing in isolated environments.
- **WireMock**: For simulating authentication and backend services.

---

## Section 3: Risk Management Matrix

| Risk Area | Description | Severity | Mitigation Action |
|-----------|-------------|----------|-------------------|
| 1. Network Latency/Instability | Uploads may exceed 2.5s SLA due to real-world 4G variability | High | Use JMeter to simulate worst-case 4G conditions; set up alerting for SLA breaches; run tests during peak/off-peak hours |
| 2. S3/API Gateway Integration Failures | Intermittent S3 or API gateway outages may block uploads | High | Mock S3 with LocalStack for integration tests; implement retry logic and monitor AWS health dashboards |
| 3. Virus Scan Engine Bottlenecks | Virus scanning may introduce unpredictable delays | Medium | Profile scan times with PyTest; use test files with/without embedded threats; monitor backend logs for scan queue times |
| 4. File Format/Size Validation Bypass | Edge-case files may bypass validation logic | Medium | Apply boundary value and equivalence partitioning tests; automate negative test cases for all invalid scenarios |
| 5. Portfolio Grid Sync Delay | Images may not appear instantly due to async sync issues | Medium | Use Playwright to validate UI sync; monitor backend event logs; add retry checks for grid update |

---

## Resource & Timeline Estimate
- **Test Automation Engineer**: 1 FTE, 5 days (framework setup, scripting, and execution)
- **Manual QA Analyst**: 0.5 FTE, 3 days (exploratory, negative, and edge-case validation)
- **DevOps/Infra Support**: 0.25 FTE, 2 days (environment setup, S3/LocalStack, network simulation)
- **Total Duration**: ~7 calendar days (including parallelization and review cycles)

---

## Traceability Matrix
| Objective | Test Type | Automation Tool |
|-----------|-----------|----------------|
| Authenticated upload access | Functional | Playwright, PyTest |
| PNG/JPEG upload ≤10MB | Functional/Boundary | Playwright, PyTest |
| Oversized/invalid format rejection | Negative | PyTest |
| SLA (2.5s) validation | Performance | JMeter |
| Portfolio grid sync | Integration/UI | Playwright |
| S3 storage/optimization | Integration | PyTest, LocalStack |
