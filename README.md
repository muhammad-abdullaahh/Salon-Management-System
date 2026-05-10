# Salon Management System ✂️💇‍♀️

![.NET](https://img.shields.io/badge/.NET-5C2D91?style=for-the-badge&logo=.net&logoColor=white)
![C#](https://img.shields.io/badge/C%23-239120?style=for-the-badge&logo=c-sharp&logoColor=white)
![ASP.NET Core MVC](https://img.shields.io/badge/ASP.NET_Core_MVC-512BD4?style=for-the-badge&logo=asp.net&logoColor=white)
![SQL Server](https://img.shields.io/badge/SQL_Server-CC2927?style=for-the-badge&logo=microsoft-sql-server&logoColor=white)

A comprehensive, role-based Web Application built with **ASP.NET Core MVC** and **C#** for managing daily salon operations. The system provides separate portals for Administrators, Staff members, and Clients to streamline appointment booking, billing, staff management, and inventory tracking.

---

## ✨ Features

The application is structured into three main roles with dedicated dashboards and permissions:

### 👑 Administrator
- **Dashboard Analytics:** View real-time metrics including today's sales, daily appointments, and available staff.
- **Graphical Reports:** Interactive charts for Weekly Sales and Monthly Comparisons.
- **Service Management:** Add new salon services and manage their active/inactive status.
- **Staff Management:** Onboard new staff members and update their employment status.
- **Inventory Management:** Add new product brands and products, set pricing (cost & selling price), and manage stock quantities.

### 👥 Staff
- **Attendance Tracking:** Check-in and check-out functionality to log daily attendance.
- **Appointment Booking:** Schedule appointments for clients, select services, and assign staff members.
- **Billing & Invoicing:** Generate professional bills for completed services and record payment methods.
- **Staff Dashboard:** View personal attendance charts and today's appointment schedules.

### 👤 Client
- **Client Portal:** Dedicated interface for clients to interact with the salon.
- **Authentication:** Secure login and session management for all user types.

---

## 🛠️ Technology Stack

- **Framework:** ASP.NET Core MVC (.NET SDK)
- **Language:** C#
- **Database:** Microsoft SQL Server
- **Data Access:** ADO.NET (`Microsoft.Data.SqlClient`)
- **Frontend:** HTML5, CSS3, JavaScript (with AJAX for dynamic charts and pricing)

---

## 🚀 Getting Started

### Prerequisites

To run this project locally, ensure you have the following installed:
1. [.NET SDK](https://dotnet.microsoft.com/download) (Compatible with the version specified in the `.csproj` file, e.g., .NET 8.0 or 10.0)
2. [Visual Studio 2022](https://visualstudio.microsoft.com/) or [Visual Studio Code](https://code.visualstudio.com/)
3. [Microsoft SQL Server](https://www.microsoft.com/en-us/sql-server/sql-server-downloads) (Express or Developer Edition)
4. [SQL Server Management Studio (SSMS)](https://learn.microsoft.com/en-us/sql/ssms/download-sql-server-management-studio-ssms) (Optional but recommended for database management)

### Installation & Setup

1. **Clone or Extract the Project**
   Open the project folder `SalonManagementSystem` in Visual Studio or VS Code.

2. **Configure the Database Connection**
   Open `appsettings.json` in the root directory and update the `ConnectionStrings` to match your local SQL Server instance:
   ```json
   "ConnectionStrings": {
     "SalonDB": "Server=YOUR_SERVER_NAME;Database=salonmanagementsystem;Trusted_Connection=True;TrustServerCertificate=True;"
   }
   ```
   *(Note: The default connection string uses `Server=.;`, which connects to the local default SQL Server instance).*

3. **Database Setup**
   Ensure your SQL Server is running and the database `salonmanagementsystem` is created with the required tables (`users`, `clients`, `staff`, `salonservices`, `appointments`, `bills`, `attendance`, `brands`, `products`).
   
   *(If you have a `.sql` script file provided with the project, run it in SSMS to generate the schema).*

4. **Build and Run**
   - **Using Visual Studio:** Press `F5` or click the "Start" button to build and run the project.
   - **Using .NET CLI:** Open a terminal in the project directory and run:
     ```bash
     dotnet build
     dotnet run
     ```

5. **Access the Application**
   Once running, the application will launch in your default web browser (typically at `https://localhost:5001` or `http://localhost:5000`). The default landing page is the Login screen.

---

## 📁 Project Structure

```plaintext
SalonManagementSystem/
│
├── Controllers/       # Handles incoming HTTP requests and application logic (Admin, Staff, Client, Login)
├── Models/            # Defines data structures and ViewModels (DashboardModel, BillViewModel, etc.)
├── Views/             # UI templates written in Razor syntax (.cshtml)
├── DAL/               # Data Access Layer classes (e.g., DBHelper)
├── wwwroot/           # Static assets (CSS, JS, images, libraries)
├── appsettings.json   # Configuration settings including Database Connection Strings
├── Program.cs         # Application entry point and middleware pipeline configuration
└── SalonManagementSystem.csproj # Project configuration and dependencies
```

---

## 🔒 Security & Architecture

- **Session Management:** Utilizes ASP.NET Core built-in session state (`builder.Services.AddSession()`) for maintaining user login states across different roles.
- **Direct Database Access:** Uses raw SQL queries via `SqlConnection` and `SqlCommand` for optimized performance and direct database interaction.
- **SQL Parameterization:** Protects against SQL Injection by utilizing parameterized queries (`@param`) across all database insert/update operations.

---

## 📝 License
This project is developed as an academic/professional DBMS implementation. Feel free to fork, modify, and use it for learning purposes.
