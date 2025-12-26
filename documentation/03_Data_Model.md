# Data Model & Schema

## 🗄️ Database Schema (ERD)

The system uses a relational database to track users, requests, and documents.

```mermaid
erDiagram
    USERS ||--o{ EMPLOYEES : "has_profile"
    EMPLOYEES ||--o{ TRANSITION_REQUESTS : "initiates"
    TRANSITION_REQUESTS ||--|{ APPROVALS : "requires"
    TRANSITION_REQUESTS ||--o{ DOCUMENTS : "contains"
    
    USERS {
        uuid id
        string email
        string role "Admin|HR|Manager|Employee"
    }

    EMPLOYEES {
        uuid id
        string full_name
        string department
        string designation
        date join_date
    }

    TRANSITION_REQUESTS {
        uuid id
        string type "ONBOARD|OFFBOARD|TRANSFER"
        string status "PENDING|APPROVED|REJECTED"
        date effective_date
    }
```

## 📋 Data Dictionary

| Table | Review | Description |
| :--- | :--- | :--- |
| **Users** | Core Auth | Stores login credentials and system roles. |
| **Employees** | Profile | HR-centric details (Department, Manager ID, etc.). |
| **Requests** | Transaction | The central entity linking an employee to a transition event. |
| **Approvals** | Audit | Logs who approved what and when. One request has multiple approval rows (Manager, HR, IT). |
| **Documents** | Assets | Links to uploaded files (Resignation Letter, Offer Letter, Clearance Form). |
