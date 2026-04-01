Trello API Testing Project
Overview

This project shows how I tested the Trello API using Postman.

I created a simple workflow where I work with boards, lists, and cards, and I validate the responses using test scripts.

What I Did
Boards
Create a new board
Get all boards
Delete a board
Check the behavior after deletion
Lists
Create a TODO list
Create a DONE list
Check that the list is created on the correct board
Cards
Create a card
Move a card from TODO to DONE
How It Works

This project uses collection variables to pass data between requests.

For example:

I get all board IDs
I store them in a variable
I use one of them in the next requests
Workflow
Get all boards
Save board IDs
Choose a board
Create lists
Create and move cards
Delete the board
Testing

I added tests in Postman to check:

Status code (200 OK)
If the correct data is returned
If lists and cards belong to the correct board
Dynamic Data

I used collection variables such as:

lastBoardId
boardsIds
lastListId

I also worked with arrays to handle multiple boards and updated variables after each request.

Notes
API keys are not included
Placeholder values are used (example: INVALID_KEY)
How to Run
Import the Postman collection
Add your Trello API key and token
Run the collection
Future Improvements
Add more negative tests
Use environment variables
Run tests using Newman
Author

QA Engineer (API Testing)
