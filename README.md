🧪 Trello API Testing Project (Postman)
📌 Overview

This project demonstrates API testing using Trello REST API in Postman.

It includes:

CRUD operations
Dynamic variables (collection & environment)
Automated test scripts
Request chaining between endpoints
⚙️ Environment & Variables

The project uses Postman variables to manage dynamic data:

🔹 Environment Variables
base_url
api_key
token
🔹 Collection Variables
lastBoardId
boardsIds
lastListId
lastDoneListId
🔄 Workflow Logic
Get all boards → extract all board IDs
Select a board dynamically
Create lists inside selected board
Create card
Move card between lists
Delete board
🧪 Test Scripts & Validation
✅ Get All Boards
const response = pm.response.json();

pm.test("Status code 200", function() {
    pm.response.to.have.status(200);
});

// Verify new board exists
pm.test("New Board is found", function() {
    const newBoardFound = response.find(item => item.id === pm.collectionVariables.get("lastBoardId"));
    pm.expect(newBoardFound).to.be.an("object");
});

// Extract data
const totalBoards = response.length;

const boardsIds = [];
const boardsNames = [];

for (let i = 0; i < response.length; i++) {
    boardsIds.push(response[i].id);
    boardsNames.push(response[i].name);
}

pm.collectionVariables.set("boardsIds", boardsIds);
✅ Create DONE List
const response = pm.response.json();

pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

pm.test("List assigned to the correct board", function() {
    pm.expect(response.idBoard).to.eql(pm.collectionVariables.get("lastBoardId"));
});

pm.test("List name is correct", function() {
    pm.expect(response.name).to.eql("DONE");
});

pm.test("List is not closed", function() {
    pm.expect(response.closed).to.eql(false);
});

// Save IDs
pm.collectionVariables.set("lastDoneListId", response.id);
pm.collectionVariables.set("lastListId", response.id);
✅ Delete Board (Dynamic Selection)
const boardsIds = pm.collectionVariables.get("boardsIds");

let boardId;

if (boardsIds.length === 1)
    boardId = boardsIds;
else
    boardId = boardsIds.pop();

// Set selected board
if (boardId !== undefined)
    pm.collectionVariables.set("lastBoardId", boardId);

// Update remaining boards
pm.collectionVariables.set("boardsIds", boardsIds);
🧠 Key Testing Concepts Demonstrated
✔️ API chaining (dynamic IDs between requests)
✔️ Collection variables usage
✔️ Data extraction from responses
✔️ Response validation (status + body)
✔️ Dynamic test logic (array handling)
✔️ Basic data processing (loops, arrays)
⚠️ Edge Case Handling
Dynamic board selection from multiple boards
Handling last remaining board
Preventing undefined variables
▶️ How to Run
Import Postman Collection
Import Environment file
Add your Trello API credentials
Run collection using Collection Runner
📈 Future Improvements
Add negative test cases
Add Newman CLI execution
Integrate with GitHub Actions (CI/CD)
Extend validation coverage
👨‍💻 Author

QA Engineer (API Testing)
