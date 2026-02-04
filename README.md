# INTERNSHIP-EXPERIENCE

During this period, I had the opportunity to actively contribute to the development of web-
based applications focused on improving the internal operations of the Sales and Human
Resources (HR) departments that strengthened both my technical and problem-solving skills.
While developing these projects, I adhered to the company’s standard development practices and followed a structured architecture that was applied consistently across all
tools. 

## Use of APIs
All backend systems were developed using ASP.NET Core Web APIs. These APIs exposed structured endpoints for CRUD operations, validations, and data transfer. 
On the client side, Blazor WebAssembly consumed these APIs through dedicated client services.
To ensure secure and efficient communication, DTOs (Data Transfer Objects) were used
to decouple database entities from client-side models.

## Architecture Adopted
The overall architecture included the following layers:
- Workspace → Core business features (entities, services, endpoints).
- Workspace.Api → API gateway layer exposing services to clients.
- Workspace.Client → Blazor WASM frontend application.
- Workspace.UI → Shared presentation layer (layouts, themes, reusable UI).
- Workspace.Test → Testing layer, containing client- and service-level test implementations.
  
This architecture promoted modularity, reusability, testability, and maintainability, while also ensuring that teams could work in parallel on different layers.

## Common Folder Structure

### Workspace
```text
Workspace
├── Features
│   ├── Data44
│   ├── [FeatureName]
│   │   ├── Endpoints/        # API endpoints (Controllers)
│   │   ├── Entities/         # Business / domain entities
│   │   ├── Services/         # Business logic and core services
```

### Workspace.Api
```text
├── Features
│ ├── [FeatureName]
├── EndPoints/ # API controllers exposed to external clients
├── Data/ # EF Core DbContext, repositories, migrations
├── Program.cs # Startup configuration
└── appsettings.json # API settings and database connection
```

### Workspace.Client
```text
├── Features
│ ├── [FeatureName]
│ │ ├── Components/ # Blazor UI components
│ │ ├── DTOs/ # Data Transfer Objects for API communication
│ │ ├── Services/ # Client-side API call services
```

### Workspace.Test
```text
├── Client
├── Workspace
└── WorkspaceClient
```

### Workspace.UI
```text
├── Shared/ # Shared layouts and components
├── Theme/ # UI styling (Tailwind, MudBlazor, etc.)
└── Pages/ # High-level application pages
```

## Roles of Each Layer

Workspace (Core Layer)
- Contains Entities that represent database models.
- Defines Services that implement the core business rules.
- Includes Endpoints (controllers) that connect business logic to APIs.

Workspace.Api (API Layer)
- Provides RESTful APIs for CRUD operations and system integrations.
- Configures middleware, dependency injection, and authentication.
- Acts as the gateway between the database and the client.

Workspace.Client (Frontend Layer)
- Built using Blazor WASM.
- Implement UI components for user interaction.
- Uses DTOs and Client Services to securely call backend APIs.

Workspace.UI (Presentation Layer)
- Maintains global layouts, navigation bars, themes, and reusable UI elements.
- Provides consistency across multiple applications/tools.

Workspace.Test (Testing Layer)
- Provides unit tests for Workspace services and entities.
- Includes integration tests for verifying API responses.
- Contains end-to-end (E2E) tests for Workspace.Client to ensure correct interaction between client and backend.
- Helps maintain code quality, reliability, and regression testing46

## Tools / Technologies / Framework
During my training, I was able to work with a wide range of technologies, tools,
and frameworks. Each of them contributed to my technical skill development and
professional growth in different ways. The following is a detailed explanation of each:

### 1. Blazor
Blazor is a web framework developed by Microsoft that allows building interactive web
applications using C# and .NET, instead of relying solely on JavaScript. It supports both
Blazor Server and Blazor WebAssembly (WASM) models.
During training, I practiced creating components, routing, data binding, form validation,
and CRUD operations. I also explored rendering modes (SSR, WASM, Auto) and learned
when to choose each based on project requirements. This framework helped me
understand how frontend and backend can be integrated seamlessly with .NET
technologies.

<img width="1332" height="727" alt="6" src="https://github.com/user-attachments/assets/53a78707-1a40-4432-a994-3a01e77f430b" />

#### Table 1: Comparison between Blazor and React

| Feature / Aspect        | Blazor                     | React                                  |
|-------------------------|----------------------------|----------------------------------------|
| Developed By            | Microsoft                  | Facebook                               |
| Language                | C#                         | JavaScript                             |
| Ecosystem               | .NET ecosystem             | JavaScript ecosystem                  |
| UI Rendering            | Server-side and client-side| Client-side                            |
| Data Binding            | Two-way data binding       | One-way data binding                  |
| Templating              | Razor syntax               | JSX                                    |
| Performance             | Good                       | Excellent                              |
| Server-Side Rendering   | Possible with Blazor Server| Possible with Next.js or other SSR solutions |

---

#### Table 2: Differences between the Blazor Rendering Modes

| Feature / Aspect        | Blazor Server              | Blazor WebAssembly (WASM) | Blazor SSR (Server-Side Rendering) | Blazor Auto (Hybrid)              |
|-------------------------|----------------------------|---------------------------|-----------------------------------|----------------------------------|
| Rendering Location      | Server                     | Client (Browser)          | Initially Server, then Client     | Auto-selects based on platform   |
| Initial Load            | Fast                       | Slow (due to WASM)        | Fast (server-rendered)            | Optimized for platform           |
| Interactivity           | Depends on SignalR         | Full client-side          | Hybrid (Server + Client)          | Adapts to platform               |
| Network Dependency      | Constant connection needed | No ongoing connection     | Server-dependent initially        | Auto-switches by environment     |
| SEO Friendly            | No                         | Limited                   | Yes                               | Depends on platform              |

### 2. Tailwind CSS
Tailwind CSS is a utility-first CSS framework that allows rapid UI development
by using predefined classes. Instead of writing long custom CSS files, developers can
directly apply Tailwind classes to HTML elements, making the design process faster and
more consistent.
In my projects, Tailwind was particularly useful for creating responsive layouts,
typography, spacing, and color schemes. I also learned how to integrate Tailwind into
Blazor applications, which gave me hands-on experience in modern styling practices
widely used in industry.

### 3. MudBlazor
MudBlazor is a Blazor component library based on Material Design principles. It
provides pre-built components like buttons, dialogs, navigation menus, data tables, and
charts.
Although I initially faced challenges integrating MudBlazor, I learned how to install the
required packages, configure them in `Program.cs`, and import styles/scripts into
`wwwroot/index.html`. Using MudBlazor improved my ability to create professional-
looking UIs without writing everything from scratch.

### 4. Entity Framework (EF) Core
Entity Framework Core is an Object-Relational Mapper (ORM) for .NET, which
allows developers to interact with databases using C# objects instead of raw SQL queries.
I practiced creating DbContext classes, migrations, and CRUD operations. For example,
in the Meal Management App, I used EF Core to define the EmployeeMeal entity, set up
the database schema, and query/filter data. EF Core simplified database interactions and
demonstrated the benefits of using an ORM for maintainability and productivity.

### 5. Microsoft Azure
Azure is Microsoft’s cloud computing platform, offering services like hosting,
storage, and identity management. I explored the Azure Fundamentals course, where I
learned about different service models (IaaS, PaaS, SaaS) and deployment types (public,
private, hybrid, multi-cloud).
This knowledge highlighted the importance of cloud scalability, availability, and security.
It also showed me how applications like Blazor web apps can be deployed and scaled
efficiently on Azure.

### 6. Visual Studio
Visual Studio was the primary IDE used during training. It provided integrated
tools for coding, debugging, Git version control, package management, and testing.
Through Visual Studio, I was able to set up projects, configure NuGet packages (such as
EF Core and MudBlazor), and debug both client-side and server-side code effectively.
This IDE played a crucial role in my ability to build structured and error-free applications.

### 7. Jira
Jira is an agile project management tool used for tracking tasks, sprints, and issues.
At the organization, Jira was used to assign development tasks, track progress, and manage
workflows.
Using Jira taught me how professional teams collaborate in Agile environments. It also
improved my ability to plan, prioritize, and deliver tasks within deadlines while
maintaining clear communication with supervisors and teammates.

### 8. Draw\.io
Draw\.io is a web-based diagramming tool used for creating flowcharts, system
diagrams, and architecture diagrams. I used it to design project flow diagrams, entity-
relationship diagrams, and clean architecture models.
This tool helped me improve my visual representation of systems, making it easier to
explain project structures to supervisors and peers.

### 9. Power BI
Power BI is a business intelligence and data visualization tool. Although my usage
was limited, I explored how it can be used to transform raw data into interactive
dashboards and reports.
Learning Power BI gave me an understanding of how data analytics is applied in industry
to support decision-making and reporting.

### 10. SQL Server
SQL Server was the database management system used during the projects. It
provided reliable data storage for applications such as the Meal Management App.
I practiced writing queries, creating schemas, and linking EF Core with SQL Server to
manage data. SQL Server also exposed me to concepts like connection strings, migrations,
and database security practices

## Challenges Faced and How I overcome them

1. Adapting from academic programming to frameworks like Blazor, Tailwind CSS, and MudBlazor was difficult at the beginning.

Solution: I followed self-learning through documentation and tutorials and also took guidance from senior developers to understand real-world development practices.

2. The application faced 500 internal server errors and failed API responses during development.

Solution: I fixed the issue by correctly registering dependencies in Program.cs and verifying service configurations.

3. The frontend sometimes failed to retrieve or display data from the backend API.

Solution: I resolved this by checking dependency injection, service lifetimes, and API routing.

4. Incorrect selection of Blazor rendering modes caused performance and responsiveness issues.

Solution: I tested different modes such as Server, WASM, SSR, and Auto (Hybrid) and selected them based on project requirements.

6. MudBlazor components did not render properly due to configuration and dependency issues.

Solution:

> MudBlazor Weakness (in this situation):
MudBlazor has a heavy dependency on correct configuration. If services, themes, or providers are not properly registered, components fail to render.
It also has a learning curve, and debugging UI issues can be time-consuming during early project stages.

> Why Tailwind CSS Was Used:
Tailwind CSS is lightweight and configuration-friendly. It does not depend on complex service registrations or providers.
Using Tailwind allowed me to continue UI development without blocking the project timeline while MudBlazor issues were being resolved.

| Aspect              | MudBlazor                         | Tailwind CSS                |
| ------------------- | --------------------------------- | --------------------------- |
| Type                | UI Component Library              | Utility-first CSS framework |
| Configuration       | Requires service & provider setup | Minimal setup               |
| Dependencies        | Heavy (.NET & Blazor services)    | Very lightweight            |
| Learning Curve      | Medium to high                    | Easy to learn               |
| Debugging UI Issues | Can be complex                    | Simple and fast             |
| Best Use Case       | Enterprise-level UI               | Rapid, flexible UI design   |

8. Large data sets caused slow UI rendering and poor performance.

Solution: I added pagination and virtualization to improve UI performance.

> Pagination divides large dataset into smaller pages (only one page loads at a time instead of thousands of records), so app loads faster and uses less memory

> Virtualization : it loads only the rows currently visible on the screen (browser doesn’t have to render all items at once.)


## Summarization

### Key Project Contributions :
- Meal Management System
- Logistics Tool Documentation
- Shop Floor Project
- Customer List Tool
- Production Efficiency Bonus Tool
- Traffic Monitoring Dashboard
- WS Components (Date picker, rating, pagination, progress, time picker, input field) Development and Documentation
 
### Technical Skills & Experience Gained :
- Developed web applications using Blazor (WASM, Server).
- Implemented CRUD operations using ASP.NET Core Web APIs.
- Worked with Entity Framework Core for database design, migrations, and data handling.
- Used SQL Server for structured data storage and querying.
- Designed responsive user interfaces using Tailwind CSS and MudBlazor.
- Developed reusable UI components such as date picker, pagination, rating, progress bar, time picker, and input fields.
- Integrated SAP APIs and implemented data caching mechanisms.
- Applied pagination and virtualization techniques to handle large datasets efficiently.
- Created technical documentation for system logics.
- Used Git and GitHub for version control and Jira for task and sprint management.
 
### Professional Skills Developed :
- Worked effectively in a team-based agile development environment.
- Demonstrated strong problem-solving and debugging skills.
- Improved communication skills through team discussions and documentation.
- Managed tasks efficiently with good time management and responsibility.
- Adapted quickly to new technologies and project requirements.
- Developed a strong sense of professional discipline and work ethics.
