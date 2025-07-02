# 🧪 Detailed Test Plan Document for  CleanCity - Waste Pickup Scheduler Web Application

## 1. Test Plan Identifier

**Document ID:** QA-CC-WEB-TP-001  
**Version:** 1.0  
**Date:** 2025-06-28  
**Application:** CleanCity – Waste Pickup Scheduler Web App

---

## 2. Introduction

The CleanCity application is designed to help users schedule waste pickups, report issues, and access educational content about environmental sustainability. This Test Plan provides a structured and detailed approach to verify the correctness, performance, and usability of the application. It ensures that the solution meets business, functional, and technical requirements before going live.

---

## 3. Test Items

**Functional Areas to Be Tested:**

- User Registration: Validations, error messages, password rules
- Login/Logout: Authentication, session management, error handling
- Pickup Request Form: Mandatory fields, input validation, success feedback
- Feedback Submission: Link to valid request ID, select reason, submit comments
- Admin Panel:
  - Update pickup request status
  - View all requests
  - View request statistics
- Dashboard View:
  - Filter by location and status
  - Accurate request display
- Awareness Section:
  - Content visibility
  - Educational resources and images
- Navigation:
  - Conditional rendering of menu links (auth vs guest)
  - Mobile hamburger navigation
- Responsive Design:
  - All pages adapting correctly to different screen sizes

---

## 4. Features to be Tested

| Feature                         | Objective                                                     |
|---------------------------------|---------------------------------------------------------------|
| Registration                    | All fields must be validated; error shown on mismatch         |
| Login/Logout                    | Valid/invalid login flows, session clear on logout            |
| Pickup Form                     | Accurate form submission; all waste types selectable          |
| Preferred Date                  | Optional input but parsed and stored when present             |
| Feedback Submission             | Match request ID; show success message                        |
| Role Access                     | Admin features must be restricted to admin users only         |
| Filtering                       | Status and location filtering must be correct and independent |
| Admin Panel Controls            | Only Admin can update statuses; fields must update live table |
| Responsive UI                   | All views on mobile/tablet must maintain usability            |
| Awareness Education             | Static content should render with images and lists intact     |

---

## 5. Features Not to Be Tested

- SMTP/email verification (not part of frontend)
- Direct backend validations (only frontend calls will be tested)
- Third-party analytics or logs
- DB-level transaction performance

---

## 6. Approach

- **Black-Box Functional Testing:** Based solely on user input/output, without code-level insight
- **Manual Testing Focus:**
  - UI validation for all visible elements and interactivity
  - Data-driven testing for different pickup requests and filters
  - Cross-role testing for permissions
- **Test Case Design Techniques:**
  - Equivalence Partitioning for valid/invalid form inputs
  - Boundary Value Analysis for date, password length, and dropdowns
  - Decision Table Testing for admin status transitions
- **Responsive Testing:**
  - Use Chrome DevTools to simulate devices
  - Test real devices: Android (Chrome), iOS (Safari), Windows/macOS

---

## 7. Entry and Exit Criteria

**Entry Criteria:**

- Build deployed on staging environment
- All APIs integrated and functioning
- Test accounts (regular and admin) created
- Test environment is stable and accessible

**Exit Criteria:**

- All major features validated manually
- 100% of planned test cases executed
- All critical/high severity defects resolved and retested
- Test summary report completed and reviewed

---

## 8. Suspension & Resumption Criteria

**Suspension Triggers:**

- Major environment instability (site not loading)
- Deployment delays or failure to integrate backend APIs
- Critical blocking defects identified in early phases

**Resumption Conditions:**

- Environment restored with access
- Dependencies (APIs, data) are fully functional
- Test cases reevaluated to accommodate blockers

---

## 9. Test Deliverables

- Detailed Test Plan (this document)
- Functional and Regression Test Case Spreadsheet
- Daily Execution Report (Excel or Notion)
- Bug Reports in JIRA with complete traceability
- Final QA Sign-Off Report
- Optional: Test Automation Script Suite (future scope)

---

## 10. Testing Tasks

| Task                                    | Description                                                |
|-----------------------------------------|------------------------------------------------------------|
| Requirement Analysis                    | Identify testable items and business logic                 |
| Test Design                             | Write test cases using scenarios from UI and requirements |
| Test Case Review                        | Peer-reviewed for coverage and accuracy                   |
| Environment Setup                       | Browser/device setup; credentials ready                   |
| Test Execution                          | Execute all manual tests; log outcomes                    |
| Defect Logging and Tracking             | Document in JIRA with reproduction steps                  |
| Retesting and Regression                | Re-execute fixed cases + high-impact flows                |
| Final Reporting                         | Compile execution results into test summary               |

---

### 11. Testing Tools

| Tool            | Purpose                               |
|-----------------|---------------------------------------|
| JIRA            | Test case tracking and defect logging |
| Chrome DevTools | Responsive & performance testing      |
| Jest            | Unit testing for JS components        |
| Postman         | (Optional) API sanity checks          |
| GitHub Issues   | Lightweight bug tracking              |

---

## 12. Environmental Needs

**Test URL:** `https://staging.cleancity.gov.ke`

**Supported Browsers:**

- Google Chrome (latest stable)
- Mozilla Firefox (latest stable)
- Safari on iOS (14+)
- Microsoft Edge (Chromium based)

**Devices:**

- Android smartphone
- iPhone (Safari & Chrome)
- iPad/tablet
- Windows 10+ laptop
- MacOS laptop (Safari and Chrome)

**Other Needs:**

- User data: Admin and standard users
- Browser dev tools enabled for debugging
- Internet speed: Minimum 10 Mbps recommended

---

## 13. Test Data Strategy

Test data is essential to validate real-world user flows, especially for form-based and admin operations.

**Test Data Needs:**

- Registered Users (Admin and Standard)
- Pickup Request Records (REQ001–REQ005)
- Feedback IDs tied to real request IDs
- Awareness content mock data (static)

**Data Preparation Approach:**

- Use SQL scripts or frontend input to generate seed data
- For automation: JSON fixtures or data factories
- Reset data before each test cycle (if applicable)

---

## 14. Responsibilities

| Role             | Assigned To         | Responsibility                                             |
|------------------|---------------------|------------------------------------------------------------|
| QA Lead          | Bednah/ Ian / Wisani| Approval, monitoring, reporting, test strategy alignment   |
| Test Engineer    | Bednah/ Ian / Wisani| Write, execute, and maintain test cases and log defects    |
| Bug Triage       | Bednah/ Ian / Wisani| Support bug triage, fix bugs, clarify behavior             |
| Product Owner    | Bednah/ Ian / Wisani| Review and validate final product behavior                 |

---

## 15. Schedule

| Phase                      | Start Date  | End Date    | Description                                 |
|----------------------------|-------------|-------------|---------------------------------------------|
| Planning & Setup           | 2025-06-28  | 2025-06-29  | Analyze requirements, test scope            |
| Test Case Design           | 2025-06-30  | 2025-07-01  | Prepare and review all test cases           |
| Test Execution             | 2025-07-02  | 2025-07-06  | Functional, UI, regression, responsive tests|
| Retesting & Regression     | 2025-07-07  | 2025-07-08  | Retest failed and impacted test cases       |
| Final Sign-Off & Reporting | 2025-07-09  | 2025-07-09  | Prepare test summary and obtain approvals   |

---

## 16. Requirements Traceability Matrix

| Requirement ID | Description                          | Test Case ID(s)    | Status     |
|----------------|--------------------------------------|--------------------|------------|
| REQ-001        | User Registration with validation    | TC-REG-001 to 004  | Covered    |
| REQ-002        | User Login and Logout                | TC-AUTH-001 to 003 | Covered    |
| REQ-003        | Schedule Pickup Request              | TC-REQ-001 to 005  | Covered    |
| REQ-004        | Admin updates pickup status          | TC-ADM-001 to 003  | Covered    |
| REQ-005        | View awareness content               | TC-STA-001         | Covered    |
| REQ-006        | Feedback submission linked to ID     | TC-FDB-001 to 002  | Covered    |

---

## 17. Risks and Mitigation

| Risk                                | Likelihood | Impact | Risk   | Mitigation Strategy                              |
|-------------------------------------|------------|--------|--------|--------------------------------------------------|
| Feature delivery delays             | Medium     | High   | High   | Parallelize test case writing with dev work      |
| Browser incompatibility             | High       | Medium | High   | Test early and often on all target browsers      |
| Unclear acceptance criteria         | Medium     | High   | High   | Conduct frequent QA-PO review syncs              |
| Bug resolution delays               | Medium     | High   | High   | Maintain a clear priority-based triage log       |
| Incomplete validation or error flows| High       | Medium | High   | Exhaustive form testing and input combinations   |

---

## 18. Approvals

This document must be reviewed and approved by the following:

| Name                            | Role             | Status  |
|---------------------------------|------------------|---------|
| Quality Assurance(QA) Lead      | Ian              | Pending |
| Quality Assurance Engineers     | Bednah/Wisani    | Pending |

---

**Prepared by:**  Bednah QA, CleanCity  
**Reviewed by:** Ian , Wisani QA's CleanCity  
**Version:** 1.0  
**Status:** Final
