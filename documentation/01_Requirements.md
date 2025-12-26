# User Requirements & Stories

## 🎭 User Personas
*   **Employee**: The individual undergoing the transition (Onboarding/Offboarding/Transfer).
*   **Department Manager**: Responsible for approving role changes and resource allocation.
*   **HR Manager**: Oversees compliance, documentation, and final approval.
*   **IT Admin**: Manages system access, hardware provisioning, and de-provisioning.
*   **Finance**: Handles payroll updates and final settlements.

## 📖 User Stories

| ID | Persona | Story | Acceptance Criteria |
| :--- | :--- | :--- | :--- |
| **US-01** | Employee | As an employee, I want to submit a transition request online so that I don't have to fill out paper forms. | Form submits validation; Tracker ID generated. |
| **US-02** | Manager | As a manager, I want to view all pending requests for my team so that I can approve them quickly. | Dashboard shows pending items; "Approve/Reject" buttons work. |
| **US-03** | HR | As an HR manager, I want to receive alerts when a manager approves a request so I can start my compliance checks. | Email/Slack notification triggered within 5 mins of manager action. |
| **US-04** | IT | As an IT admin, I want a checklist of assets to recover during offboarding so nothing is lost. | Asset list generated based on employee ID; "Return" status updates DB. |

## ✅ Functional Requirements (FR)
1.  **Submission**: System must allow initiating requests for Onboarding, Offboarding, and Role Change.
2.  **Workflow**: Must support a multi-tiered approval flow (`Manager` -> `HR` -> `IT` -> `Finance`).
3.  **Notifications**: Automated emails sent at each state transition.
4.  **Audit**: Every action (submit, approve, reject) must be logged with timestamp and User ID.

## 🚀 Non-Functional Requirements (NFR)
1.  **Security**: Role-Based Access Control (RBAC) to ensure managers only see their team's data.
2.  **Performance**: Dashboards must load within 2 seconds.
3.  **Compliance**: All offboarding records must be retained for 7 years (Audit Trail).
