# SQL Utility Library

Reusable ADO.NET data-access helpers — stored-procedure wrappers, connection pooling, and retry logic — for cutting boilerplate out of SQL Server-backed .NET projects.

<p>
  <img src="https://img.shields.io/badge/C%23-239120?style=flat-square&logo=c-sharp&logoColor=white" alt="C#">
  <img src="https://img.shields.io/badge/ADO.NET-512BD4?style=flat-square&logo=dotnet&logoColor=white" alt="ADO.NET">
  <img src="https://img.shields.io/badge/SQL_Server-CC2927?style=flat-square&logo=microsoftsqlserver&logoColor=white" alt="SQL Server">
</p>

## Overview

After writing the same `SqlConnection` / `SqlCommand` boilerplate across enough projects, I pulled the common pieces into a small reusable library: stored-procedure execution helpers, safe parameter binding, and transient-fault retry logic for SQL Server.

## Features

- `SqlHelper` class with `ExecuteScalar`, `ExecuteNonQuery`, `ExecuteReader`, and `ExecuteDataTable` wrappers
- Strongly-typed parameter builder (no more manual `SqlParameter` construction)
- Automatic retry with exponential backoff for transient SQL Server errors (timeouts, deadlocks)
- Connection pooling configuration helpers
- Lightweight — no external dependencies beyond `System.Data.SqlClient`

## Tech Stack

- **Language:** C#
- **Data Access:** ADO.NET
- **Target:** .NET Framework 4.7+ (compatible with ASP.NET Web Forms and Web API projects)

## Usage Example

```csharp
var helper = new SqlHelper(connectionString);

// Execute a stored procedure with parameters
DataTable result = helper.ExecuteDataTable(
    "usp_GetEmployeesByDepartment",
    new SqlParameterBuilder()
        .Add("@DepartmentId", departmentId)
        .Build()
);

// Automatic retry on transient failures
int rowsAffected = helper.ExecuteNonQueryWithRetry(
    "usp_UpdateLeaveBalance",
    parameters,
    maxRetries: 3
);
```

## Getting Started

### Prerequisites

- .NET Framework 4.7+ or Visual Studio 2019+
- SQL Server 2016+ for testing

### Installation

```bash
git clone https://github.com/suniltiwari/sql-utility-library.git
```

Add a project reference to `SqlUtilityLibrary.csproj`, or copy the `SqlHelper.cs` and `SqlParameterBuilder.cs` files directly into your project.

## Project Structure

```
SqlUtilityLibrary/
├── SqlUtilityLibrary/
│   ├── SqlHelper.cs
│   ├── SqlParameterBuilder.cs
│   └── RetryPolicy.cs
├── SqlUtilityLibrary.Tests/
└── README.md
```

## License

MIT — free to use in personal or commercial projects.

## Contact

Sunil Tiwari — suniltiwari1@gmail.com
