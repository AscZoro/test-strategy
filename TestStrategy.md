# Test Strategy Document

## Section 1: Scope

### In-Scope
- Single high-resolution image upload by authenticated users.
- Upload interface is only available to users with an active session.
- Uploads are processed through a secure API Gateway.
- Server-side only image optimization and compression.
- Synchronous virus scanning and file validation before storage.
- Images are stored in AWS S3 buckets.
- Uploaded images instantly update the user's public portfolio grid.

### Out-of-Scope
- Client-side image optimization or pre-processing.
- Support for non-image files or formats (WebP, GIF, SVG, TIFF, etc.).
- Batch or multi-file uploads.
- Storage using internal file servers or non-AWS S3 providers.

### Constraints
- Maximum individual file size is 10MB.
- Only PNG and JPEG formats are supported.
- Strict backend header byte validation to prevent spoofed extensions.
- End-to-end upload, processing, and rendering must complete within 2.5 seconds on a standard 4G network.
- Single-file uploads only; no batch or multi-file uploads.
- No client-side image optimization or pre-processing.
- No support for non-image files or formats other than PNG/JPEG.
- Storage is limited to AWS S3; no other providers.

## Section 2: Test Approach

### Testing Levels
- UI / Front-End Component Level (Upload button visibility, authentication gating, grid update rendering)
- API Gateway / Backend Integration Level (Upload endpoint, file validation, virus scanning, image optimization)
- Cloud Storage Verification Level (AWS S3 bucket write/read validation)
- End-to-End System Integration Level (Full upload-to-public-grid workflow, including SLA timing)

### Testing Types
- Functional Testing (Authentication gating, file upload, grid update)
- Boundary Value & Negative Testing (File size limits, unsupported formats, session expiry)
- Security Testing (Virus scanning, header byte validation, session enforcement)
- Performance & SLA Latency Testing (End-to-end upload and rendering within 2.5 seconds on 4G)
- Data Integrity Testing (Image persistence and grid synchronicity)

### Test Design Techniques
- Boundary Value Analysis (File size acceptance at 10.00MB, rejection at 10.01MB and above)
- Equivalence Partitioning (Supported vs. unsupported file types: PNG/JPEG vs. others)
- State Transition Testing (Session state changes: authenticated, expired, unauthenticated)
- Negative Testing (Spoofed file extensions, invalid payloads, multi-file attempts)
- Timing Analysis (Measuring total workflow duration under network constraints)
- Security Payload Injection (Malicious file content, virus signature simulation)

### Environments Needed
- Staging environment with user authentication and session management enabled
- API Gateway endpoint with logging and request tracing
- Mocked and real AWS S3 buckets for storage validation
- Backend microservices for virus scanning and file validation (with toggles for simulating scan outcomes)
- Network shaping tools to simulate standard 4G mobile bandwidth and latency
- Test data sheets: Valid PNG/JPEG files at 9.99MB, 10.00MB, 10.01MB; invalid file types (e.g., GIF, SVG); files with spoofed extensions; files with embedded test viruses
- Automated UI test harness for real-time grid update verification (with DOM mutation observers)

### Automation Frameworks & Tools
- **Playwright**: For UI automation (upload button visibility, grid update, DOM mutation observation)
- **PyTest**: For backend API, file validation, and security payload injection
- **Locust**: For simulating concurrent uploads and SLA timing under network constraints
- **Moto (AWS Mocking)**: For S3 bucket integration testing
- **Charles Proxy / Network Link Conditioner**: For 4G network simulation

## Section 3: Risk Management Matrix

| Risk Area | Description | Severity | Mitigation Action |
|-----------|-------------|----------|-------------------|
| 1. Network Latency Breaches | Upload-to-render time may exceed 2.5s SLA under real 4G conditions | High | Use network shaping tools in CI; run Locust-based load/SLA tests; alert on SLA breach |
| 2. Spoofed File Extensions | Malicious files may bypass extension checks | High | Enforce backend magic number validation; negative tests with spoofed files via PyTest |
| 3. Virus Scanning Microservice Failure | Inline virus scan may fail open, allowing unsafe files | Critical | Simulate scan failures; require hard fail on scan error; monitor logs for scan bypass |
| 4. S3 Write Latency or Outage | Delayed or failed image persistence impacts grid sync | Medium | Use Moto for S3 outage simulation; alert on write failures; retry logic in backend |
| 5. Session Expiry Race Conditions | Uploads may be accepted after session expiry | Medium | State transition tests; enforce session validation at API gateway; automate expiry scenarios |

### Resource & Timeline Estimate
- **Test Automation Engineer**: 1 FTE, 2 weeks (framework setup, Playwright/PyTest scripting, CI integration)
- **Manual QA Analyst**: 0.5 FTE, 1 week (exploratory, negative, and edge case validation)
- **DevOps/Infra Support**: 0.2 FTE, 1 week (network shaping, S3/microservice toggling, CI pipeline config)
- **Total Duration**: 2.5 weeks (including parallelization and review buffer)
