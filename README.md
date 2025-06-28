# Postman Newman Tests

## Project Description  
This project contains a Postman collection and a GitHub Actions workflow for automated testing of a local API server using Newman.

---

## Daily Progress Report

### Day 1  
- Familiarized myself with the task requirements.  
- Studied articles about Postman, Curl, and REST API.  
- Downloaded the example repository.  
- Installed necessary dependencies (`npm install`).  

### Day 2  
- Started the local server using `npm run tern-on-api`.  
- Explored the routes `/products`, `/orders`, and `/users`.  
- Performed manual API testing using Postman.  
- Created the initial test collection.  

### Day 3  
- Developed integration tests in Postman including:  
  - Response status code checks (200, 201, etc.)  
  - Response time validation  
  - JSON schema validation of the response  
- Exported the collection as `store.collection.json`.  

### Day 4  
- Configured GitHub Actions workflow for running Newman tests automatically.  
- Added steps for installing Node.js, Newman, and running the local server in the background.  
- Fixed the issue with missing Newman HTML reporter.  

### Day 5  
- Resolved GitHub Actions errors related to repository permissions.  
- Updated the workflow to use the latest version of `actions/upload-artifact`.  
- Successfully tested the full pipeline with server startup and Newman tests.  
- Wrote this README with project description and usage instructions.  

---

## How to Run

### Important Notes  
The API server **must be running before executing the Newman tests**, otherwise tests will fail with connection errors (`ECONNREFUSED`). This is because Newman sends requests to `localhost:3000`.

### Local Setup Instructions

1. Install dependencies:

```bash
npm install
```

2. Start the local API server in a separate terminal window:

```bash
npm run tern-on-api
```

3. Open another terminal window and run the Newman tests:

```bash
newman run store.collection.json --reporters cli,html --reporter-html-export newman-report.html
```


