# REST API Demo

A token-authenticated CRUD service built on ASP.NET Web API, consumed by a Bootstrap front end with paginated data grids.

<p>
  <img src="https://img.shields.io/badge/ASP.NET_Web_API-512BD4?style=flat-square&logo=dotnet&logoColor=white" alt="ASP.NET Web API">
  <img src="https://img.shields.io/badge/C%23-239120?style=flat-square&logo=c-sharp&logoColor=white" alt="C#">
  <img src="https://img.shields.io/badge/SQL_Server-CC2927?style=flat-square&logo=microsoftsqlserver&logoColor=white" alt="SQL Server">
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black" alt="JavaScript">
</p>

## Overview

A reference implementation of a REST API layer in front of a SQL Server database — the pattern I use when connecting internal enterprise systems to third-party services or newer front ends.

## Features

- Full CRUD endpoints (`GET`, `POST`, `PUT`, `DELETE`) with proper HTTP status codes
- Token-based authentication (JWT bearer tokens)
- Request validation with meaningful error responses
- Server-side pagination, filtering, and sorting
- Swagger / OpenAPI documentation for all endpoints
- Bootstrap front end demonstrating consumption of the API

## Tech Stack

- **Backend:** ASP.NET Web API, C#
- **Database:** SQL Server, ADO.NET
- **Auth:** JWT Bearer tokens
- **Frontend (demo consumer):** JavaScript (fetch API), Bootstrap
- **Docs:** Swashbuckle (Swagger)

## API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| GET | `/api/items` | List items (paginated, filterable) |
| GET | `/api/items/{id}` | Get a single item |
| POST | `/api/items` | Create a new item |
| PUT | `/api/items/{id}` | Update an existing item |
| DELETE | `/api/items/{id}` | Delete an item |
| POST | `/api/auth/login` | Authenticate and receive a JWT |

## Getting Started

### Prerequisites

- Visual Studio 2019 or later
- SQL Server 2016+ (or LocalDB)

### Installation

```bash
git clone https://github.com/suniltiwari/rest-api-demo.git
cd rest-api-demo
```

1. Open the solution in Visual Studio
2. Run `Database/schema.sql` to create the demo schema
3. Update the connection string and JWT secret in `Web.config` / `appsettings.json`
4. Run the project — Swagger UI is available at `/swagger`
5. Open `Client/index.html` to see the Bootstrap demo consumer in action

## Project Structure

```
RestApiDemo/
├── Database/
│   └── schema.sql
├── RestApiDemo.Api/
│   ├── Controllers/
│   ├── Models/
│   └── Web.config
├── Client/
│   └── index.html
└── README.md
```

## License

MIT — free to use as a reference or starting point.

## Contact

Sunil Tiwari — suniltiwari1@gmail.com
