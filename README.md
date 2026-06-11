# Pedro Sánchez Lucio
**Software Engineer | Backend Developer**

Ingeniero de software especializado en el desarrollo de sistemas backend, arquitecturas de integración y manejo de bases de datos. Trabajo resolviendo problemas técnicos complejos, desde la estructuración de APIs web con arquitecturas multi-tenant, hasta el desarrollo de motores lógicos y soluciones empresariales.

---

### 🛠 Stack Tecnológico

- **Ecosistema .NET:** C#, ASP.NET Core (.NET 10), Entity Framework Core, WinForms, Win32 API
- **Backend & APIs:** REST, JWT (con refresh-token rotation), FluentValidation, Hangfire, Serilog, Swagger/OpenAPI
- **Python & Web:** Python, Django, JavaScript
- **Java & Otros:** Java, Spring Boot
- **Bases de Datos:** SQL Server (T-SQL, Window Functions, Stored Procedures), Oracle APEX, SQLite
- **Arquitectura & Herramientas:** SaaS Multi-Tenant, Service Layer, Optimistic Concurrency (`RowVersion`), Git, GitHub Actions (CI/CD), Docker, Unity

---

### 🚀 Proyectos Destacados

#### [MediCore - API SaaS Multi-Tenant](https://github.com/PedroSL0904/MediCore) | `C#` `ASP.NET Core 10` `EF Core 10` `SQL Server` `Docker`
API RESTful para la gestión de clínicas médicas construida con arquitectura por capas y endurecida para producción.

- **Aislamiento multi-tenant estricto** mediante `HasQueryFilter` global por `ClinicaId` y middleware de coherencia JWT↔ruta.
- **Refresh tokens con token family**: rotación atómica, detección de reúso con revocación de familia completa, transacciones serializables contra TOCTOU.
- **Concurrencia optimista** con `[Timestamp] RowVersion` en entidades críticas + mapeo de `DbUpdateConcurrencyException` a HTTP 409.
- **Auditoría** vía `SaveChangesInterceptor` que serializa cada cambio a JSON (con redacción de campos sensibles) en una tabla `AuditLog` indexada.
- **Versionado de API** (`Asp.Versioning.Mvc`) con Swagger multi-versión y default `v1.0`.
- **Background jobs** con Hangfire (dashboard protegido por rol SuperAdmin) sobre SQL Server.
- **Resiliencia**: `EnableRetryOnFailure(5, 30s)` para arranques contra Docker; fail-fast al detectar `Jwt:Key` placeholder.
- **CI/CD**: pipeline en GitHub Actions para .NET 10, `Dockerfile` multi-stage con `dotnet test` embebido, `docker-compose.yml` con healthcheck para SQL Server 2022.
- **Cobertura de tests**: xUnit + Moq + FluentAssertions + EF InMemory.

#### [FleetPro - Sistema de Gestión de Flotillas](https://github.com/PedroSL0904/fleet-management-system) | `Python` `Django` `CI/CD`
Aplicación web integral (SSR) orientada a la administración de activos vehiculares.

- Estructurada bajo el patrón *Service Layer* para desacoplar y proteger la lógica de negocio de las vistas.
- Control de Acceso Basado en Roles (RBAC) personalizado mediante decoradores y Mixins de seguridad.
- Pipeline de CI/CD automatizado con GitHub Actions y pruebas unitarias (`pytest`) para validación de servicios.

#### [PvZ Fusion Engine](https://github.com/PedroSL0904/PvZ_Fusion_Engine) | `C#` `Unity 6`
Motor 2D tipo tower-defense construido desde cero con un enfoque en arquitectura de software escalable.

- Implementa un motor de fusiones de entidades con complejidad algorítmica `O(1)` basado en diccionarios de tuplas.
- Diseñado con una separación estricta entre la matriz lógica y la representación visual mediante hitboxes delegadas y polimorfismo.

---

### 📫 Contacto

- **LinkedIn:** [in/pedro-sánchez-lucio](https://www.linkedin.com/in/pedro-s%C3%A1nchez-lucio-1932b6230)
- **Email:** [pedrolucio.0904@gmail.com](mailto:pedrolucio.0904@gmail.com)
