SateSoft Tenant Theming
A multi tenant theming application built with Spring Boot and React.it allow different tenants to use the same application with their own application with their own company 
branding,product names and theme colors.

project Overview 
The purpose of this project is to demonstrate how a frontend application can request tenant specific configuration from a backend API and dynamically display the application 
branding.

The application currently supports two tenants:
-> Default Store; the default tenant configuration.
->Acme Store; a separate tenant configuration with its own branding and colors.
if no tenant is specific or an unknown tenant is requesting, the application falls back to the Default tenant.

Technology used on this project
Backend
- Java 17
- Spring Boot
- Spring web
- Maven
Frontend
- React
- TypeScript
- Vite
- CSS
  HOW IT Works
  step 1 - A user open the React frontend.
  step 2 - React requests tenant configuration from the Spring Boot backend.
  step 3 - The frontend sends the selected tenant using the X - Tenant - Id HTTP request header.
   step 4 - Spring Boot identifies the tenant and return its configuration as JSON.
   step 5 - React  receives the configuration and display the company name, product name and theme colors.
   step 6 - When  the user switches tenants, React requests the new configuration and updates the webpage.
  
   API Endpoint
  Endpoint: GET /api/v1/tenant/config
  Header: X-Tenant-Id
  Example request for the Acme tenant
  GET / api/ v1/ tenant/ config
  X - Tenant -Id: acme

  The response contains the tenant's company name, product name, and theme configuration.
  The theme includes;
  - primary Color
  - secondary Color
  - backgroundColor
  - textColor
  - accentColor
  Running the Project Logically
Prerequisites
- Java 17 or later
- Node.js and npm
1. Open a terminal in the backend project directory and run:
.\mvnw.cmd spring-boot:run
Then backend runs on:
http: //Localhost :8080
2. Start the Frontend
Open a separate terminal and navigate to the frontend directory:
cd frontend
Start the development server:
npm.cmd run dev
Then frontend runs on:
http: //localhost :5173
   Open this address in your browser to use the applications
   Testing the API
   Test the Default tenant:
   Invoke-RestMethod http: //localhost:8080/api/v1/tenant/config

   Test the acme tenant:
   Invoke-RestMethod http://localhost:8080/api/v1/tenant/config -Headers @{"X-Tenant-Id"="acme"
   
  - Project Structure
   
   tenant-theming/
├── src/
│   └── main/
│       └── java/
│           └── com/satesoft/tenant_theming/
│               ├── TenantThemingApplication.java
│               ├── TenantconfigController.java
│               ├── TenantRegistry.java
│               ├── TenantProfile.java
│               └── ThemeConfig.java
│
├── frontend/
│   └── src/
│       ├── App.tsx
│       ├── App.css
│       └── main.tsx
│
├── pom.xml
└── README.md
   
   
  
