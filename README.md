# 📦 ECommerce - ASP.NET Core Reference Application

---

## ✨ Features

- Monolithic architecture using ASP.NET Core MVC
- Clean separation: UI, Application Core, Infrastructure
- Admin panel built with Blazor WebAssembly
- Entity Framework Core with SQL Server (or in-memory)
- Dependency injection, logging, and validation
- Public API (Minimal API) for client apps
- Unit & functional tests
- Docker support
- Easy deployment to Azure using Azure Developer CLI (`azd`)

---

## 📐 Architecture Overview

Solution
├── Web # ASP.NET Core MVC frontend
├── ApplicationCore # Business logic, interfaces, domain entities
├── Infrastructure # Data access (EF Core), external services
├── PublicApi # API endpoints for Blazor / external clients
├── UnitTests # Business logic unit tests
└── FunctionalTests # End-to-end functional tests

yaml
Copy
Edit

---

## 🏁 Quick Start

### ✅ Prerequisites

- [.NET 8 SDK](https://dotnet.microsoft.com/download)
- (Optional) [Docker](https://www.docker.com/)
- (Optional) [Azure Developer CLI (azd)](https://aka.ms/azure-dev/install)
- SQL Server (local or container) — or use in-memory database

---

### 🖥️ Running locally

Clone repository:

```bash
git clone https://github.com/AtharvaAnbhule/ECommerce.git
cd eShopOnWeb
Install dependencies & tools:

bash
Copy
Edit
dotnet restore
dotnet tool restore
Apply EF Core migrations (for SQL Server):

bash
Copy
Edit
cd src/Web
dotnet ef database update -c catalogcontext -p ../Infrastructure/Infrastructure.csproj -s Web.csproj
dotnet ef database update -c appidentitydbcontext -p ../Infrastructure/Infrastructure.csproj -s Web.csproj
Run applications:

bash
Copy
Edit
# Start PublicApi project (API for Blazor admin)
cd src/PublicApi
dotnet run
In a separate terminal:

bash
Copy
Edit
# Start main Web project
cd src/Web
dotnet run --launch-profile Web
Browse to: https://localhost:5001

🐳 Running with Docker
bash
Copy
Edit
docker-compose build
docker-compose up
Browse:

Web frontend: http://localhost:5106

Public API: http://localhost:5200

☁ Deploying to Azure
Requires Azure Developer CLI (azd)

bash
Copy
Edit
azd auth login
azd init -t dotnet-architecture/ECommerce 
azd up
📚 Learn More
This project is inspired by modern .NET architecture patterns, clean code principles, and the free eBook on architecting ASP.NET Core web apps.

You can also explore related community projects:

eShopOnContainers - microservices architecture

Community forks in VB.NET and F#

🙌 Contributing
Pull requests and improvements are welcome!
Open an issue or submit a PR if you'd like to help.




If you want,
📌 I can also add:
✅ Badges (build, license, stars)
✅ Project logo / screenshot
✅ Fancy header


