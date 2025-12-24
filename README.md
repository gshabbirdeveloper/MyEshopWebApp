# MyEshopWebApp – ASP.NET Core Reference Application

**Overview:**
**MyEshopWebApp** is a **sample ASP.NET Core application** demonstrating **Clean Architecture principles** and a single-process (monolithic) architecture. It’s designed for learning **modern web application patterns** with ASP.NET Core, EF Core, and Identity.

---

## Features

* **Clean Architecture & Layered Design** – Separation of concerns for maintainability.
* **EF Core Integration** – Catalog, shopping cart, and identity management.
* **Admin Interface** – Manage products and orders via Blazor WebAssembly.
* **Docker & Dev Container Support** – Run without installing all tools locally.
* **Sample Data** – Preloaded demo users and products for quick experimentation.

---

## Getting Started

### Clone & Restore

```bash
git clone <your-repo-url>
cd MyEshopWebApp
dotnet restore
dotnet tool restore
```

### Configure Database

In `Web/appsettings.json` you can choose an in-memory database:

```json
{
   "UseOnlyInMemoryDatabase": true
}
```

For SQL Server, update the connection strings and run EF Core migrations:

```bash
dotnet ef database update -c catalogcontext -p ../Infrastructure/Infrastructure.csproj -s Web.csproj
dotnet ef database update -c appidentitydbcontext -p ../Infrastructure/Infrastructure.csproj -s Web.csproj
```

### Run Application

```bash
dotnet run --launch-profile Web
```

Admin page is accessible at `https://localhost:5001/admin` using the demo user: `demouser@microsoft.com`.

---

### Running with Docker

```bash
docker-compose build
docker-compose up
```

* Web project: `localhost:5106`
* Public API: `localhost:5200`

---

## Community Extensions

* **VB.NET Version:** eShopOnWeb VB.NET
* **F# Version:** FShopOnWeb

---
