
# 🧪 Lab: Using GitHub Copilot for Automation Testing (.NET, UI & API)

## 🎯 Objective
Learn how to use GitHub Copilot (Ask, Edit, Chat) to accelerate automation testing by generating:
- Unit tests  
- UI tests using Playwright  
- API tests  
- Page Object Model (POM)  
- Mocking and data-driven tests  

---

# ------------------------------------------------------------
# SECTION 1 — Prerequisites
# ------------------------------------------------------------

### ✔ Tools Required
- Visual Studio 2022 **or** VS Code  
- .NET 8 SDK  
- GitHub Copilot Chat / Copilot Enterprise  
- Playwright for .NET (`dotnet tool install --global playwright`)  
- Sample Application (Any Web/API project)

---

# ------------------------------------------------------------
# SECTION 2 — Setup & Repo Structure
# ------------------------------------------------------------

### Create a new solution

```
dotnet new sln -n AutomationCopilotLab
dotnet new webapi -n SampleAPI
dotnet new nunit -n AutomationTests
dotnet sln add SampleAPI/SampleAPI.csproj
dotnet sln add AutomationTests/AutomationTests.csproj
```

### Install Playwright

```
cd AutomationTests
dotnet add package Microsoft.Playwright.NUnit
playwright install
```

### Repo Structure

```
AutomationCopilotLab/
│── SampleAPI/          # API for testing
│── AutomationTests/    # UI & API Tests
└── README.md
```

---

# ------------------------------------------------------------
# SECTION 3 — Lab Activities Using GitHub Copilot
# ------------------------------------------------------------

## ✅ Activity 1: Generate Unit Tests Using Copilot

### Goal
Use Copilot to automatically generate unit tests for API methods.

### Steps
1. Open **SampleAPI → Controllers → WeatherForecastController.cs**  
2. Highlight the action method.  
3. Right-click → **GitHub Copilot → Generate Tests**  
4. Copilot will generate NUnit tests such as:
   - `Should_Return_Weather_Data`  
   - `Should_Return_5_Items`  
   - `Should_Handle_Empty_Response`  

---

## ✅ Activity 2: Generate API Tests with Copilot Ask

### Goal
Use Copilot Ask to create API tests using HttpClient.

### Steps
Open Copilot Chat and run:

```
Generate API test methods in NUnit to test the GET /weatherforecast endpoint using HttpClient.
```

---

## ✅ Activity 3: Auto-Create a Playwright Page Object Model (POM)

### Goal
Use Copilot to generate a full POM class.

### Steps
Create file:  
`AutomationTests/Pages/LoginPage.cs`

Add:

```csharp
// Create a Playwright POM for Login Page with methods: EnterUser, EnterPassword, ClickLogin, AssertDashboardVisible
```

---

## ✅ Activity 4: Generate UI Test Cases Using Copilot

### Steps
Create file:

`AutomationTests/Tests/LoginUITests.cs`

Prompt Copilot:

```
Write a Playwright NUnit UI test using the LoginPage POM to validate successful login. Include setup and teardown.
```

---

# ------------------------------------------------------------
# SECTION 4 — Mocking & Stubbing with Copilot
# ------------------------------------------------------------

### Goal
Use Copilot to generate mocks using Moq.

### Steps
Run in Copilot Chat:

```
Generate NUnit + Moq tests for WeatherService where GetForecast depends on IExternalAPI. Mock IExternalAPI to return dummy data.
```
