# 🧪 Trello API Testing Project

# 📌 Overview

This project shows how I tested the Trello API using Postman.

I created a simple workflow where I work with boards, lists, and cards, and I validate the responses using test scripts.

---

# 🚀 Project Coverage

## 🧩 Boards
- 🟢 Create a new board  
- ✏️ Update board  
- 🔍 Get board  
- 🔍 Get all boards  
- ❌ Delete board  

---

## 📋 Lists
- 🟢 Create list
- 🔄 Update list
- ❌ Delete list  

---

## 🃏 Cards
- 🟢 Create card  
- 🔄 Move card (TODO → DONE)  
- ❌ Delete card  

---

## ❌ Invalid Requests

### 🧩 Board
- ❌ Create board with missing required fields  
- ❌ Get non-existent board  
- ❌ Delete already deleted board  

### 📋 List
- ❌ Create list with invalid data  
- ❌ Delete non-existent list  

### 🃏 Card
- ❌ Create card with missing data  
- ❌ Move card to invalid list  
- ❌ Delete non-existent card  

---


# ⚙️ How it works

This project uses collection variables to pass data between requests.

For example:

* I get all board IDs
* I store them in a variable
* I use one of them in the next requests

# 🔄 Project Structure and Workflow

## 📌 Main Functional Workflow

1️⃣ Create new board  
2️⃣ Update board  
3️⃣ Get board  

  ↳ 4️⃣ Create TODO list  
  ↳ 5️⃣ Create DONE list  
  ↳ 6️⃣ Update list  
  ↳ 7️⃣ Get lists  

    ↳ 8️⃣ Create new card  
    ↳ 9️⃣ Move card (TODO → DONE)  

      ↳ 🔟 Delete card  
      ↳ 1️⃣1️⃣ Get deleted card  

  ↳ 1️⃣2️⃣ Delete list  
  ↳ 1️⃣3️⃣ Get deleted list  

1️⃣4️⃣ Delete board  
1️⃣5️⃣ Get deleted board  

<small>
⚠️ Important Dependency Note<br><br>

- Lists must be created under an existing board<br>
- Cards must exist within a list<br>
- Deleting a board removes all associated lists and cards<br>
</small>


## 🛠️ Maintenance

1️⃣ Get all boards  

## ❌ Invalid Cases

1️⃣ Create new board with invalid token  
2️⃣ Create new board with invalid API endpoint  

3️⃣ Create new list without providing a board ID  
4️⃣ Create new card without providing a list ID  

---

# 🧪 Testing

I added tests in Postman to check:

* Status code (200 OK)
* If the correct data is returned
* If lists and cards belong to the correct board

---

# 🔄 Dynamic Data

I used collection variables such as:

* `lastBoardId`
* `boardsIds`
* `lastListId`

I also worked with arrays to handle multiple boards and updated variables after each request.

---

# ⚠️ Notes

* API keys are not included
* Placeholder values are used (example: `INVALID_KEY`)

---

# ▶️ How to run

1. Import the Postman collection
2. Add your Trello API key and token
3. Run the collection

---

# 📈 Future Improvements

* Add more negative tests
* Use environment variables
* Run tests using Newman

---

# 👨‍💻 Author

QA Engineer (API Testing)
