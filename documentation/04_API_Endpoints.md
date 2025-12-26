# API Specification

## 🔐 1. Authentication
*   **POST** `/api/auth/login`: Authenticate and receive JWT.

## 👤 2. Employee Management
*   **GET** `/api/employees`: List all employees (filterable by Dept).
*   **POST** `/api/employees`: Create a new employee profile (HR Only).

## 🔄 3. Transition Requests
*   **GET** `/api/transitions`: View requests. Managers see their team's; HR sees all.
*   **POST** `/api/transitions`: Submit a new Onboarding/Offboarding request.
    ```json
    {
      "employeeId": "emp_123",
      "type": "OFFBOARD",
      "reason": "Resignation",
      "lastWorkingDate": "2023-12-31"
    }
    ```
*   **PUT** `/api/transitions/{id}/approve`: Action a request.
    ```json
    {
      "action": "APPROVE",
      "comment": "Clearance received from IT."
    }
    ```

## 📂 4. Documents
*   **POST** `/api/documents/upload`: Upload clearance forms or contracts.
*   **GET** `/api/documents/{id}/download`: Secure download link.

## 📊 5. Analytics (KPIs)
*   **GET** `/api/analytics/tat`: Get Turn-Around-Time stats for transitions.
