# Authentication System

A role-based authentication module for enterprise portals — session management, salted password hashing, and account lockout policies, built with ASP.NET and SQL Server.

<p>
  <img src="https://img.shields.io/badge/ASP.NET-512BD4?style=flat-square&logo=dotnet&logoColor=white" alt="ASP.NET">
  <img src="https://img.shields.io/badge/C%23-239120?style=flat-square&logo=c-sharp&logoColor=white" alt="C#">
  <img src="https://img.shields.io/badge/SQL_Server-CC2927?style=flat-square&logo=microsoftsqlserver&logoColor=white" alt="SQL Server">
</p>

## Overview

Most internal tools need the same thing: a login screen that's actually secure. This project is a self-contained authentication module — login, registration, password reset, and role-based access — designed to be dropped into a larger ASP.NET application.

## Features

- Salted + hashed password storage (PBKDF2)
- Role-based authorization (Admin / Manager / User)
- Session timeout and sliding expiration
- Account lockout after repeated failed attempts
- Forgot-password flow with time-limited reset tokens
- Audit log of login attempts (success and failure)

## Tech Stack

- **Backend:** ASP.NET, C#
- **Database:** SQL Server
- **Security:** ASP.NET Forms Authentication, PBKDF2 password hashing

## Screenshots

> _Add screenshots here — `/screenshots/login.png`, `/screenshots/reset-password.png`_

## Getting Started

### Prerequisites

- Visual Studio 2019 or later
- SQL Server 2016+ (or LocalDB)

### Installation

```bash
git clone https://github.com/suniltiwari/authentication-system.git
cd authentication-system
```

1. Open the solution in Visual Studio
2. Run `Database/schema.sql` to create the `Users`, `Roles`, and `LoginAudit` tables
3. Update the connection string in `Web.config`
4. Set `machineKey` in `Web.config` for consistent hashing across environments
5. Run the project (`F5`)

## Project Structure

```
AuthenticationSystem/
├── Database/
│   └── schema.sql
├── AuthenticationSystem.Web/
│   ├── Account/
│   ├── App_Code/
│   │   └── PasswordHasher.cs
│   └── Web.config
└── README.md
```

## Security Notes

- Passwords are never stored or logged in plain text
- Reset tokens expire after 30 minutes and are single-use
- Consider adding CAPTCHA or rate-limiting in front of the login endpoint for production use

## License

MIT — free to use as a reference or starting point.

## Contact

Sunil Tiwari — suniltiwari1@gmail.com
