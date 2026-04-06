# 🚀 Employee API Platform (MuleSoft | APIKit | OAuth 2.0 | Enterprise Integration)

## 🌟 Overview

This project demonstrates a **production-grade, enterprise integration API** built using **MuleSoft**. It showcases **API-led connectivity**, **secure API exposure**, and **scalable system integration** using modern best practices.

The solution exposes a **RESTful Employee API** that supports full **CRUD operations** and integrates with backend systems using **database stored procedures**.

🔐 Secured using **OAuth 2.0** via API Gateway policies
⚙️ Designed using **API-first (RAML) approach**
🏗️ Built with **scalability, reusability, and governance in mind**

---

## 🧠 Key Highlights (What Makes This Stand Out)

* ✅ API-led architecture principles (Experience layer implementation)
* ✅ APIKit (RAML-driven development)
* ✅ OAuth 2.0 security via API Manager (policy-based enforcement)
* ✅ Clean separation of concerns (routing, transformation, system interaction)
* ✅ Database integration using stored procedures (enterprise pattern)
* ✅ Structured error handling with reusable strategy
* ✅ Production-ready design (logging, extensibility, governance-ready)

---

## 🏗️ Architecture (Enterprise View)

```id="bq3w4h"
                 ┌──────────────────────────┐
                 │   Client Applications    │
                 │ (Web / Mobile / Postman)│
                 └────────────┬─────────────┘
                              │
                              │  OAuth 2.0 (Bearer Token)
                              ▼
                 ┌──────────────────────────┐
                 │   API Gateway Layer      │
                 │ (API Manager Policies)   │
                 │  - OAuth Enforcement     │
                 │  - Traffic Management    │
                 └────────────┬─────────────┘
                              ▼
                 ┌──────────────────────────┐
                 │ Experience API (MuleSoft)│
                 │  - APIKit Router         │
                 │  - Request Validation    │
                 │  - Error Handling        │
                 └────────────┬─────────────┘
                              ▼
                 ┌──────────────────────────┐
                 │ System Integration Layer │
                 │  - Stored Procedures     │
                 │  - DB Connector          │
                 └──────────────────────────┘
```

---

## 🧩 Technology Stack

| Layer          | Technology                       |
| -------------- | -------------------------------- |
| API Design     | RAML 1.0                         |
| Runtime        | Mule 4                           |
| Routing        | APIKit                           |
| Security       | OAuth 2.0 (API Manager Policy)   |
| Transformation | DataWeave 2.0                    |
| Integration    | DB Connector (Stored Procedures) |
| Deployment     | CloudHub / Runtime Fabric        |
| Testing        | Postman / cURL                   |

---

## 📜 API Endpoints

| Method | Endpoint        | Description       |
| ------ | --------------- | ----------------- |
| POST   | `/api/employee` | Create employee   |
| PUT    | `/api/employee` | Update employee   |
| GET    | `/api/employee` | Retrieve employee |
| DELETE | `/api/employee` | Delete employee   |

---

## 🔐 Security Implementation

This API is secured using **OAuth 2.0 Access Token Enforcement** via MuleSoft API Manager.

### 🔑 Flow

1. Client obtains access token from OAuth provider
2. Token passed in request header:

   ```
   Authorization: Bearer <access_token>
   ```
3. API Gateway validates token before routing request

👉 No security logic is hardcoded in flows (policy-driven security)

---

## 🔄 Data Transformation Strategy

* Input payload validated via RAML schema
* Transformed using **DataWeave 2.0**
* Converted into DB-compatible parameter object

```dw id="rdr4s9"
%dw 2.0
output application/java
---
{
    emp_id: payload.empId,
    first_name: payload.firstName,
    last_name: payload.lastName,
    email: payload.email,
    salary: payload.salary
}
```

---

## 🗄️ Backend Integration

Each API operation maps to a **dedicated stored procedure**:

* `insert_employee`
* `update_employee`
* `get_employee`
* `delete_employee`

📌 This approach:

* Improves performance
* Encapsulates DB logic
* Aligns with enterprise DB governance

---

## ❗ Error Handling Strategy

* Implemented using **Try Scope**
* Centralized error responses
* Clean JSON error format

```json id="nlws6k"
{
  "status": "ERROR",
  "message": "Detailed error message"
}
```

✔ Supports:

* Business errors
* System errors
* Security errors (401 / 403)

---

## 📂 Project Structure

```id="bqf31f"
employee-api/
│
├── api/                # RAML definitions
├── flows/              # APIKit + CRUD flows
├── dwl/                # DataWeave scripts
├── config/             # Environment configs
├── pom.xml
└── README.md
```

---

## ▶️ Running the Project

### Prerequisites

* Mule Runtime 4.x
* Anypoint Studio
* Database instance
* API Manager access (for OAuth)

### Steps

1. Import project into Anypoint Studio
2. Configure DB properties
3. Deploy to runtime
4. Apply OAuth policy via API Manager
5. Test using Postman

---

## 🧪 Sample Request

```bash id="q9cg3o"
curl -X POST http://localhost:8081/api/employee \
-H "Authorization: Bearer <token>" \
-H "Content-Type: application/json" \
-d '{
  "empId": 101,
  "firstName": "John",
  "lastName": "Doe",
  "email": "john@test.com",
  "salary": 5000
}'
```

---

## 📈 Future Enhancements (Roadmap)

* 🔹 Full API-led architecture (Experience + Process + System APIs)
* 🔹 Client ID Enforcement & SLA tiers
* 🔹 Rate limiting & throttling policies
* 🔹 CI/CD pipeline (Azure DevOps / GitHub Actions)
* 🔹 Observability (logging, tracing, monitoring)
* 🔹 Secure properties & secrets management
* 🔹 JWT validation (Azure AD / Okta integration)

---

## 💼 Why This Project Matters

This project demonstrates:

* Real-world **enterprise integration patterns**
* Strong understanding of **MuleSoft architecture**
* Ability to design **secure, scalable APIs**
* Experience with **API governance and policies**
* Readiness for **Lead / Architect-level roles**

---

## 👨‍💻 Author

**WAQAR AHMED**
Lead Integration Engineer | MuleSoft | Azure | API Architecture

---

## ⭐ If you found this useful

Give it a star ⭐ and feel free to connect!
