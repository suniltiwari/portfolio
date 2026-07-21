# Background Verification System

A workflow application for managing employee background checks — candidate onboarding, document collection, employer/education verification tracking, and audit-ready reports for HR teams and verification agencies.

<p>
  <img src="https://img.shields.io/badge/ASP.NET-512BD4?style=flat-square&logo=dotnet&logoColor=white" alt="ASP.NET">
  <img src="https://img.shields.io/badge/C%23-239120?style=flat-square&logo=c-sharp&logoColor=white" alt="C#">
  <img src="https://img.shields.io/badge/SQL_Server-CC2927?style=flat-square&logo=microsoftsqlserver&logoColor=white" alt="SQL Server">
  <img src="https://img.shields.io/badge/REST_API-512BD4?style=flat-square&logo=dotnet&logoColor=white" alt="REST API">
</p>

## Overview

Most companies still run background verification over email and spreadsheets — a candidate's documents in one inbox, verification calls tracked in Excel, and no single view of where a case stands. This project replaces that with a structured workflow: one record per candidate, a clear verification status per check, and a report HR can hand to a hiring manager without chasing anyone.

## Features

- Candidate profile with document upload (ID proof, address proof, education certificates, previous employment letters)
- Per-check verification workflow: Employment, Education, Address, Identity — each with its own status (Pending → In Progress → Verified → Discrepancy)
- Case assignment to HR staff or an external verification agency
- Audit trail of every status change, with timestamp and actor
- Auto-generated PDF verification report for closed cases
- Role-based access: Candidate, HR, Verification Agency, Admin
- REST API layer so the workflow can be triggered from an existing HRMS/ATS instead of used as a standalone portal

## Tech Stack

- **Backend:** ASP.NET, C#
- **Database:** SQL Server (case records, audit log, document metadata)
- **API:** ASP.NET Web API for HRMS/ATS integration
- **Frontend:** Bootstrap, JavaScript
- **Documents:** File storage for uploaded proofs, PDF generation for final reports

## Screenshots

> _Add screenshots here — `/screenshots/candidate-dashboard.png`, `/screenshots/case-status.png`, `/screenshots/report.png`_

## Getting Started

### Prerequisites

- Visual Studio 2019 or later
- SQL Server 2016+ (or LocalDB)

### Installation

```bash
git clone https://github.com/suniltiwari/background-verification-system.git
cd background-verification-system
```

1. Open the solution in Visual Studio
2. Run `Database/schema.sql` to create the case, document, and audit-log tables
3. Update the connection string and file-storage path in `Web.config`
4. Run the project (`F5`)

## Project Structure

```
BackgroundVerificationSystem/
├── Database/
│   └── schema.sql
├── BackgroundVerificationSystem.Web/
│   ├── Candidate/
│   ├── HR/
│   ├── Agency/
│   ├── Api/
│   ├── App_Code/
│   └── Web.config
└── README.md
```

## License

MIT — free to use as a reference or starting point.

## Contact

Sunil Tiwari — suniltiwari1@gmail.com
Available for freelance/contract work building or extending BGV and HR-tech workflow systems.
