# Python Application CI/CD Automation

A Python Flask application demonstrating a complete **CI/CD pipeline using GitHub, Jenkins, Pytest, and SonarQube**. The project automates dependency installation, testing, code quality analysis, and application validation whenever changes are pushed to the repository.

## íº€ Project Overview

This project demonstrates how a Python application can be integrated into a CI/CD workflow using Jenkins.

The pipeline automatically:

1. Checks out the source code from GitHub
2. Installs Python dependencies
3. Runs automated tests using Pytest
4. Performs static code analysis using SonarQube
5. Validates the Python source by compiling the application

### CI/CD Workflow

```text
Developer
    â”‚
    â–¼
  Git
    â”‚
    â–¼
 GitHub
    â”‚
    â–¼
 Jenkins
    â”‚
    â”œâ”€â”€ Checkout
    â”‚
    â”œâ”€â”€ Install Dependencies
    â”‚
    â”œâ”€â”€ Run Pytest
    â”‚
    â”œâ”€â”€ SonarQube Analysis
    â”‚
    â””â”€â”€ Build / Compile Validation
    â”‚
    â–¼
 Successful Pipeline
```

---

## í» ï¸ Technologies Used

| Technology | Purpose                   |
| ---------- | ------------------------- |
| Python     | Application development   |
| Flask      | Web application framework |
| Git        | Version control           |
| GitHub     | Source code repository    |
| Jenkins    | CI/CD automation          |
| Pytest     | Automated testing         |
| SonarQube  | Static code analysis      |
| Maven      | Not used                  |
| Docker     | Not used                  |

---

## í³ Project Structure

```text
Python_app_CICD/
â”‚
â”œâ”€â”€ app.py
â”œâ”€â”€ Jenkinsfile
â”œâ”€â”€ requirements.txt
â”œâ”€â”€ sonar-project.properties
â”œâ”€â”€ .gitignore
â”œâ”€â”€ README.md
â”‚
â””â”€â”€ tests/
    â””â”€â”€ test_app.py
```

---

## í²» Application

The application is a simple Flask REST-style web application with two endpoints.

### Home Endpoint

```text
GET /
```

Response:

```json
{
    "message": "Python CI/CD Demo Application",
    "status": "Application is running"
}
```

### Health Check Endpoint

```text
GET /health
```

Response:

```json
{
    "status": "UP"
}
```

The `/health` endpoint can be used to verify whether the application is running correctly.

---

## í´„ Jenkins Pipeline

The Jenkins pipeline is defined in the `Jenkinsfile`.

### Pipeline Stages

#### 1. Checkout

Jenkins checks out the latest source code from the `main` branch of the GitHub repository.

#### 2. Install Dependencies

Python dependencies are installed using:

```bash
python -m pip install -r requirements.txt
```

#### 3. Test

Automated tests are executed using Pytest:

```bash
python -m pytest
```

The current test suite validates:

* Home endpoint response
* Health endpoint response
* HTTP status codes
* JSON response values

#### 4. SonarQube Analysis

SonarQube performs static code analysis to identify potential code quality issues and maintainability problems.

The project configuration is defined in:

```text
sonar-project.properties
```

#### 5. Build / Validation

The pipeline validates Python source files using:

```bash
python -m compileall .
```

This ensures that the Python source code can be successfully compiled.

---

## í·ª Testing

Tests are written using **Pytest**.

Run the tests locally:

```bash
python -m pytest
```

Expected result:

```text
2 passed
```

---

## âš™ï¸ Local Setup

### Prerequisites

Make sure the following are installed:

* Python 3.12+
* Git

### 1. Clone the Repository

```bash
git clone https://github.com/samarthgarde/Python_app_CICD.git
```

### 2. Navigate to the Project

```bash
cd Python_app_CICD
```

### 3. Install Dependencies

```bash
python -m pip install -r requirements.txt
```

### 4. Run the Application

```bash
python app.py
```

The application runs on:

```text
http://localhost:5000
```

Health check:

```text
http://localhost:5000/health
```

---

## í´§ Jenkins Configuration

The Jenkins job uses **Pipeline from SCM**.

### SCM Configuration

```text
SCM: Git
Branch: main
Script Path: Jenkinsfile
Repository: Python_app_CICD
```

Jenkins automatically retrieves the latest code from GitHub and executes the pipeline defined in the `Jenkinsfile`.

---

## í³Š SonarQube Integration

SonarQube is integrated into the Jenkins pipeline for automated static code analysis.

The project uses:

```text
sonar-project.properties
```

The configuration includes the project key, project name, source directory, test directory, and Python version.

The SonarQube analysis runs automatically as part of the Jenkins pipeline.

---

## âœ… Pipeline Result

The complete pipeline has been successfully executed with the following stages:

```text
âœ“ Checkout
âœ“ Install Dependencies
âœ“ Run Tests
âœ“ SonarQube Analysis
âœ“ Build / Compile Validation
```

Automated tests:

```text
2 passed
```

---

## í¾¯ Learning Objectives

This project was created to gain practical experience with:

* Python web application development
* Git and GitHub workflows
* Jenkins pipeline automation
* Continuous Integration
* Automated testing with Pytest
* Static code analysis with SonarQube
* Jenkinsfile configuration
* CI/CD troubleshooting
* Build validation

---

## í´® Future Improvements

Possible future enhancements include:

* Add code coverage using `pytest-cov`
* Add deployment to a cloud platform
* Add Docker containerization
* Add GitHub Webhook-based automatic Jenkins triggering
* Add automated release/versioning
* Add security scanning
* Add production WSGI server such as Gunicorn

---

## í±¨â€í²» Author

**Samarth Garde**

Computer Science Engineer | Python | Cloud & AWS | CI/CD

GitHub:
https://github.com/samarthgarde

LinkedIn:
https://linkedin.com/in/samarthgarde

