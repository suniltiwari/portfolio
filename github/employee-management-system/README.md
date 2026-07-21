# Employee Management System

A complete HR module for managing employee records, leave requests, and payroll exports — built on ASP.NET Web Forms with a normalized SQL Server schema.

<p>
  <img src="https://img.shields.io/badge/ASP.NET_Web_Forms-512BD4?style=flat-square&logo=dotnet&logoColor=white" alt="ASP.NET Web Forms">
  <img src="https://img.shields.io/badge/C%23-239120?style=flat-square&logo=c-sharp&logoColor=white" alt="C#">
  <img src="https://img.shields.io/badge/SQL_Server-CC2927?style=flat-square&logo=microsoftsqlserver&logoColor=white" alt="SQL Server">
  <img src="https://img.shields.io/badge/Bootstrap-7952B3?style=flat-square&logo=bootstrap&logoColor=white" alt="Bootstrap">
</p>

## Overview

This project models a typical mid-size company's HR workflow: onboarding an employee, tracking their leave balance, and generating monthly payroll exports — the kind of system most enterprises run internally rather than buy off the shelf.

## Features

- Employee CRUD with department, designation, and reporting-manager hierarchy
- Leave request workflow (apply → manager approval → balance deduction)
- Attendance summary per pay cycle
- Payroll export to Excel/CSV with configurable pay components
- Role-based views for Employee, Manager, and HR Admin
- Server-side validation and audit logging on all record changes

## Tech Stack

- **Backend:** ASP.NET Web Forms, C#
- **Database:** SQL Server (stored procedures for all data access)
- **Frontend:** Bootstrap, jQuery
- **Data Access:** ADO.NET

## Screenshots

> _Add screenshots here — `/screenshots/dashboard.png`, `/screenshots/leave-request.png`, etc._

## Getting Started

### Prerequisites

- Visual Studio 2019 or later
- SQL Server 2016+ (or LocalDB for development)
- IIS Express (bundled with Visual Studio) or full IIS

### Installation

```bash
git clone https://github.com/suniltiwari/employee-management-system.git
cd employee-management-system
```

1. Open `EmployeeManagementSystem.sln` in Visual Studio
2. Restore NuGet packages (Visual Studio does this automatically on build)
3. Run the database script: `Database/schema.sql` against your SQL Server instance
4. Update the connection string in `Web.config`:
   ```xml
   <connectionStrings>
     <add name="EMSConnection" connectionString="Data Source=.;Initial Catalog=EmployeeManagementDB;Integrated Security=True" />
   </connectionStrings>
   ```
5. Press `F5` to run

## Project Structure

```
EmployeeManagementSystem/
├── Database/
│   └── schema.sql
├── EmployeeManagementSystem.Web/
│   ├── Pages/
│   ├── App_Code/
│   └── Web.config
└── README.md
```

## License

MIT — free to use as a reference or starting point.

## Contact

Sunil Tiwari — suniltiwari1@gmail.com
