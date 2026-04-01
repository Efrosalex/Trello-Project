# 🧪 Trello API Testing Project

## 📌 Overview
This project demonstrates API testing using Trello REST API in Postman.

The goal of this project was to simulate real-life API testing scenarios, including working with dynamic data, validating responses, and creating a complete workflow.

---

## 🚀 What I Tested

### 🧩 Board Management
- Created new boards
- Retrieved all existing boards
- Deleted boards
- Verified behavior after deletion

### 📋 List Management
- Created TODO and DONE lists
- Verified lists are assigned to the correct board

### 🃏 Card Management
- Created cards
- Moved cards between lists (TODO → DONE)

---

## ⚙️ How the Logic Works

The project uses dynamic variables and request chaining:

- Extract data from responses (e.g. board IDs)
- Store them in collection variables
- Reuse them in the next requests

Example flow:
1. Get all boards
2. Extract board IDs
3. Select a board dynamically
4. Create lists inside that board
5. Perform actions on cards
6. Delete the board

---

## 🧪 Testing Approach

I implemented automated tests in Postman to validate:

- Status codes (e.g. 200 OK)
- Response structure and data
- Correct assignment of lists and cards

---

## 🔄 Dynamic Data Handling

This project includes:

- Collection variables (board ID, list ID, etc.)
- Dynamic selection of resources
- Handling multiple boards using arrays
- Updating variables between requests

---

## 🧠 What I Learned

- How to work with REST APIs in a real scenario
- Writing test scripts in Postman using JavaScript
- Handling dynamic data between requests
- Validating API responses
- Structuring an API testing project

---

## ▶️ How to Run

1. Import the Postman Collection
2. Import the Environment file
3. Add your Trello API key and token
4. Run the collection using Postman Runner

---

## 📈 Future Improvements

- Add negative test scenarios
- Run tests using Newman (CLI)
- Integrate with CI/CD (GitHub Actions)

---

## 👨‍💻 Author
QA Engineer (API Testing)
