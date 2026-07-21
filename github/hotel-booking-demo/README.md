# Hotel Booking Demo

A room inventory and booking calendar application with real-time availability logic and conflict-safe reservation writes.

<p>
  <img src="https://img.shields.io/badge/ASP.NET_Web_Forms-512BD4?style=flat-square&logo=dotnet&logoColor=white" alt="ASP.NET Web Forms">
  <img src="https://img.shields.io/badge/C%23-239120?style=flat-square&logo=c-sharp&logoColor=white" alt="C#">
  <img src="https://img.shields.io/badge/SQL_Server-CC2927?style=flat-square&logo=microsoftsqlserver&logoColor=white" alt="SQL Server">
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black" alt="JavaScript">
</p>

## Overview

The interesting part of a booking system isn't the form — it's making sure two people can't book the same room for overlapping dates. This project focuses on that: safe concurrent writes, an availability calendar, and a straightforward booking flow.

## Features

- Room inventory management (room types, rates, amenities)
- Interactive availability calendar (date-range picker)
- Conflict-safe booking writes using SQL Server transactions and row locking
- Booking confirmation, modification, and cancellation flow
- Admin dashboard for occupancy and upcoming check-ins/check-outs

## Tech Stack

- **Backend:** ASP.NET Web Forms, C#
- **Database:** SQL Server (transactions, row-level locking for booking integrity)
- **Frontend:** JavaScript, Bootstrap, a date-range picker component

## How Availability Conflicts Are Prevented

Booking writes run inside a SQL Server transaction that checks for overlapping date ranges on the target room with a `SELECT ... WITH (UPDLOCK, HOLDLOCK)` before inserting, preventing two simultaneous requests from double-booking the same room.

## Getting Started

### Prerequisites

- Visual Studio 2019 or later
- SQL Server 2016+ (or LocalDB)

### Installation

```bash
git clone https://github.com/suniltiwari/hotel-booking-demo.git
cd hotel-booking-demo
```

1. Open the solution in Visual Studio
2. Run `Database/schema.sql` to create `Rooms`, `Bookings`, and `Guests` tables
3. Update the connection string in `Web.config`
4. Run the project (`F5`) and open the Booking Calendar page

## Project Structure

```
HotelBookingDemo/
├── Database/
│   └── schema.sql
├── HotelBookingDemo.Web/
│   ├── Booking/
│   ├── Admin/
│   ├── App_Code/
│   └── Web.config
└── README.md
```

## License

MIT — free to use as a reference or starting point.

## Contact

Sunil Tiwari — suniltiwari1@gmail.com
