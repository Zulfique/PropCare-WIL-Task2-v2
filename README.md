#  PropCare — Smart Property Maintenance Management

##  GROUP 2 - 5IVE BYTE 

---

#  Authors

This project was collaboratively developed by:

**ST10404539 — Neville Kabamba**  
**ST10403582 — Zulfique Jattiem**  
**ST10445479 — Connor Bettridge**  
**ST10283036 — Ayakha Ntsomi**  
**ST10439005 — Kwanda Zulu**

---

---

## Academic Information

**Module:** Information Systems 3E – Work Integrated Learning  
**Module Code:** INSY7315  
**Assessment:** Task 2 – Code and Implementation  

---

#  Useful Links

| Resource | Link |
|---|---|
| 🌐 Live Application | https://propcare-wil-task2.onrender.com/ |
| ❤️ API Health Check | https://propcare-wil-task2.onrender.com/api/health |
| 🔌 API Endpoint List | https://propcare-wil-task2.onrender.com/api |
| 💻 GitHub Repository | https://github.com/Zulfique/PropCare-WIL-Task2-v2 |
| 🧪 GitHub Actions | https://github.com/Zulfique/PropCare-WIL-Task2-v2/actions |
| 🖼️ Task 1 Prototype | https://zulfique.github.io/PropCare-WIL-Task2-v2/ |

---

##  About PropCare

PropCare is a full-stack property maintenance management system developed for **Obs Realty Group**.

The system makes it easier for tenants, property managers, technicians and administrators to manage property maintenance requests from one platform.

Tenants can report problems, property managers can review and assign maintenance requests, technicians can complete jobs, and administrators can manage users and system settings.

The project includes the Task 2 working application as well as the original Task 1 prototype.

---

##  Live Application

**Live Application:**  
https://propcare-wil-task2.onrender.com/

**API Health Check:**  
https://propcare-wil-task2.onrender.com/api/health

**API Information:**  
https://propcare-wil-task2.onrender.com/api

**GitHub Repository:**  
https://github.com/Zulfique/PropCare-WIL-Task2-v2

**Task 1 Prototype:**  
https://zulfique.github.io/PropCare-WIL-Task2-v2/

---

#  Main Features

## Tenant Features

Tenants can:

- Report maintenance issues
- Select a maintenance category
- Set the urgency of a request
- Add information about the problem
- Upload photos
- Track maintenance requests
- Add comments
- Confirm completed work
- Rate completed maintenance

##  Property Manager Features

Property managers can:

- View maintenance requests
- Search and filter requests
- Review and prioritise issues
- Assign technicians
- Monitor maintenance progress
- View property information
- View reports
- Monitor their property portfolio

##  Technician Features

Technicians can:

- View assigned jobs
- Accept maintenance requests
- Update request status
- Place requests on hold
- Resume work
- Add notes
- Upload photos
- Complete maintenance jobs

##  Administrator Features

Administrators can:

- Manage users
- Manage user roles
- Manage categories
- Manage tenants
- Manage notifications
- Manage system settings
- View reports

---

#  Technology Stack

## Front End

- HTML
- CSS
- Vanilla JavaScript
- Responsive CSS
- Single Page Application (SPA)

## Back End

- Node.js
- Express.js
- REST API
- JWT authentication
- bcrypt password hashing

## Database

- SQLite
- Node.js `node:sqlite`

## Testing

- Jest
- Supertest
- Puppeteer

## Development and Deployment

- Git
- GitHub
- GitHub Actions
- Render

---

#  System Architecture

PropCare uses a layered application structure:

```text
User
  ↓
Front End
  ↓
REST API
  ↓
Routes
  ↓
Services
  ↓
Repositories
  ↓
SQLite Database
```

This structure separates the different responsibilities of the application and makes the system easier to maintain, test and update.

---

#  Design Patterns

The project uses two main design patterns.

## Repository Pattern

The Repository Pattern separates database operations from the rest of the application.

Database queries are handled through repository classes instead of being placed directly inside routes.

Examples include:

- `BaseRepository`
- `RequestRepository`
- `NotificationRepository`
- `UserRepository`
- `ReferenceRepository`

This makes the application easier to test and allows the storage system to be changed more easily.

## Observer Pattern

The Observer Pattern is used for notifications.

When important events occur, the system can notify the appropriate users.

Examples include:

- A maintenance request being created
- A technician being assigned
- A request status changing
- A new user registering

The notification observers are separated from the main request-processing logic.

---

# Database

PropCare uses SQLite for data storage.

The database contains **12 tables**:

1. `users`
2. `properties`
3. `units`
4. `categories`
5. `technicians`
6. `requests`
7. `request_photos`
8. `comments`
9. `history`
10. `notifications`
11. `ratings`
12. `settings`

The database uses:

- Primary keys
- Foreign keys
- Unique constraints
- Check constraints
- Database indexes

These features help maintain data integrity and improve query performance.

---

# Security

Several security features have been implemented in PropCare.

These include:

- JWT authentication
- Password hashing with bcrypt
- Role-based access control
- Object-level access checks
- Input validation
- Rate limiting
- Helmet security headers
- CORS configuration
- Request body-size limits
- Photo upload validation
- Secure error responses

Passwords are never stored as plain text.

---

#  Demo Accounts

The application includes four demo accounts representing the main user roles.

| Role | Email | Main Responsibilities |
|---|---|---|
| **Tenant** | `sarahwilliams@example.com` | Report and track maintenance |
| **Property Manager** | `michael.jacobs@obsrealty.co.za` | Review, assign and monitor requests |
| **Technician** | `johan.vdm@obsrealty.co.za` | Accept and complete maintenance jobs |
| **Administrator** | `admin@obsrealty.co.za` | Manage users and system settings |

### Demo Password

```text
PropCare123!
```

> These are demonstration accounts and should not be used as production credentials.

---

# 💻 Running PropCare Locally

## Requirements

Before running the project locally, install:

- Node.js **22.5 or newer**
- Git
- npm

Node.js 22.5+ is required because the application uses the built-in `node:sqlite` module.

## 1. Clone the Repository

```bash
git clone https://github.com/Zulfique/PropCare-WIL-Task2-v2.git
```

Move into the project directory:

```bash
cd PropCare-WIL-Task2-v2
```

## 2. Install Dependencies

```bash
npm ci
```

## 3. Create the Environment File

Linux/macOS:

```bash
cp .env.example .env
```

Windows PowerShell:

```powershell
Copy-Item .env.example .env
```

The `.env` file is optional because the application has working defaults.

## 4. Start the Application

```bash
npm start
```

The application will run at:

```text
http://localhost:8124
```

Open the address in your browser and log in using one of the demo accounts.

---

# 🧪 Testing

The project contains automated tests for the application's main functionality.

Run the complete test suite:

```bash
npm test
```

### Current Test Result

```text
129 / 129 tests passing
```

Other available commands:

```bash
npm run check
```

Checks the JavaScript syntax.

```bash
npm audit
```

Checks project dependencies for known vulnerabilities.

```bash
npm run test:browser
```

Runs the browser-based tests using Puppeteer.

---

#  Test Results

| Test | Result |
|---|---|
| Jest + Supertest | ✅ 129 / 129 passing |
| JavaScript syntax check | ✅ Passed |
| GitHub Actions CI | ✅ Passed |
| API health check | ✅ Passed |
| Live Render deployment | ✅ Working |
| GitHub Pages prototype | ✅ HTTP 200 |

The automated tests cover:

- Authentication
- Role-based access control
- Maintenance requests
- Request status changes
- Comments
- Photos
- Ratings
- Notifications
- Reports
- Security
- Repository Pattern
- Observer Pattern

---

#  REST API

The PropCare REST API is available under:

```text
/api
```

## Authentication

```text
POST /api/auth/login
GET  /api/auth/me
POST /api/auth/logout
```

## Users

```text
GET  /api/users
POST /api/users
GET  /api/users/me
PUT  /api/users/me
PUT  /api/users/:id/status
```

## Maintenance Requests

```text
GET  /api/requests
POST /api/requests
GET  /api/requests/:id
```

## Request Actions

```text
POST /api/requests/:id/status
POST /api/requests/:id/assign
POST /api/requests/:id/comments
POST /api/requests/:id/photos
POST /api/requests/:id/rate
```

## Properties, Technicians and Categories

```text
GET /api/properties
GET /api/properties/:id
GET /api/technicians
GET /api/categories
GET /api/categories/:id
GET /api/statuses
GET /api/urgencies
```

## Notifications

```text
GET  /api/notifications
POST /api/notifications/read-all
```

## Administration and Reports

```text
GET /api/settings
PUT /api/settings
GET /api/reports/summary
```

## Health Check

```text
GET /api/health
```

---

#  Responsive Design

PropCare is designed to work across:

- 💻 Desktop computers
- 💻 Laptops
- 📱 Tablets
- 📱 Mobile devices

The application includes responsive layouts and mobile navigation.

Accessibility has also been considered through:

- Keyboard navigation
- Visible focus states
- Accessible control names
- Loading feedback
- Error feedback
- Success messages

---

#  Deployment

PropCare is deployed using **Render's Free plan**.

The deployment uses:

- Node.js
- Express
- SQLite
- Render
- GitHub
- GitHub Actions

The application automatically creates and seeds the database when required.

## Render Free Plan

The Free Render deployment has some limitations.

The service can go to sleep after approximately 15 minutes without traffic. When this happens, the first request may take approximately **30–60 seconds** while the application starts again.

The filesystem is also ephemeral, meaning data created during a demonstration may not survive a restart or redeployment.

The application therefore recreates the demo data when the service starts again.

---

#  Git Workflow

The project follows a Gitflow-style workflow.

```text
main
  ↓
develop
  ↓
feature/*
```

### Branches

- `main` — stable and releasable version
- `develop` — integration branch
- `feature/*` — branches used for individual features

Feature branches used during development included:

```text
backend-api
frontend-app
tests-pipeline
hosting-docs
a11y-robustness
rate-limits-and-diag
deploy-readiness
deploy-verify
fix-browser-test
```

The project uses Conventional Commit messages such as:

```text
feat:
fix:
docs:
ci(cd):
chore(deploy):
```

---

#  CI/CD

GitHub Actions is used to automate project checks.

The workflows perform tasks such as:

- Syntax checking
- Automated testing
- Dependency auditing
- Building
- Deployment verification

The project contains the following workflows:

| Workflow | Purpose |
|---|---|
| `ci.yml` | Testing, syntax checks and dependency audit |
| `build.yml` | Build and publish the Task 1 prototype |
| `deploy.yml` | Verify the live Render deployment |

---

#  Screens and Functionality

The application includes:

- Dashboard
- Maintenance request list
- Request search and filtering
- Request details
- Request timeline
- Request conversation
- Report-an-issue wizard
- Properties
- Technicians
- Tenants
- Reports
- CSV export
- Notifications
- Users
- Roles
- Categories
- Profile
- Settings
- Design gallery

---

# Requirements Alignment

| Requirement | Implementation |
|---|---|
| Tenant reports an issue | Request creation and report wizard |
| Tenant uploads a photo | Request photo upload |
| Manager reviews requests | Request list, search and filtering |
| Manager assigns technician | Technician assignment |
| Technician accepts work | Request status actions |
| Technician completes work | Completion workflow |
| Users communicate | Request comments |
| Tenant rates completed work | Rating system |
| Admin manages users | User management |
| Admin manages categories | Category management |
| Manager views reports | Reports and CSV export |
| Users receive notifications | Notification Observer system |
| Secure authentication | JWT authentication |
| Role-based access | RBAC and object-level checks |
| Mobile support | Responsive design and mobile navigation |
| Accessibility | Keyboard and accessible controls |
| Live system | Render deployment |

---

#  Design

The PropCare interface uses the Obs Realty Group branding.

Main design colours include:

```text
Navy:  #101d31
Teal:  #2fc4ac
Mint:  #a9e7d2
```

The application uses vanilla HTML, CSS and JavaScript without a front-end framework or build step.

This keeps the application lightweight and easy to run.

---

#  Security Audit

The project has been checked for dependency vulnerabilities.

The current audit reports:

```text
0 vulnerabilities
```

Puppeteer was also upgraded to address previously identified high-severity advisories in its browser tooling.

The application does not print the demo password to the application logs.

---

#  Task 1 Prototype

The original Task 1 static prototype is included in:

```text
prototype/
```

It contains the original HTML, CSS, JavaScript and mockups.

To run the prototype locally:

```bash
cd prototype
python -m http.server 8124
```

Then open:

```text
http://localhost:8124
```



#  Project Status

**Status: Completed and deployed**

PropCare includes:

- ✅ Full-stack web application
- ✅ REST API
- ✅ SQLite database
- ✅ JWT authentication
- ✅ Role-based access control
- ✅ Maintenance request management
- ✅ Notifications
- ✅ Reporting
- ✅ Automated testing
- ✅ CI/CD
- ✅ Responsive design
- ✅ Accessibility support
- ✅ Live deployment



##  Thank You

Thank you for reviewing the **PropCare – Smart Property Maintenance Management System**.

Developed for  ** IIE EMERIS, INSY7315 Information Systems 3E – Work Integrated Learning Task 2** .

