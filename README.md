# 📚 Library Lending System

A full-stack Library Lending System built using:

- **Frontend:** React + Vite
- **Backend:** Express.js
- **Database:** MongoDB Atlas (Mongoose)

The application allows librarians to manage books and lending operations, including adding books, borrowing, returning, searching, and tracking overdue loans.

---

# Features

## Book Management

- Add new books
- Unique ISBN validation
- Search books by title or author
- Pagination
- Delete books
- Prevent deletion if currently borrowed

## Lending Management

- Borrow books
- Automatic available copies update
- Return books
- Active loan tracking
- Status filter
- Overdue loan detection

---

# Tech Stack

## Backend

- Node.js
- Express.js
- Mongoose
- MongoDB Atlas
- CORS

## Frontend

- React
- Vite
- CSS

---

# Project Structure

```
project/

│
├── backend/
│   └── index.js
│
├── frontend/
│   └── src/
│       ├── App.jsx
│       └── App.css
│
└── postman/
    ├── Library-Lending-API.postman_collection.json
    └── Library-Lending.postman_environment.json
```

---

# MongoDB Atlas Setup

Open **backend/index.js**

Replace the placeholder connection string:

```javascript
const MONGODB_URI =
'mongodb+srv://<username>:<password>@<cluster-host>/library_lending?retryWrites=true&w=majority';
```

with your own MongoDB Atlas credentials.

Example:

```javascript
const MONGODB_URI =
'mongodb+srv://myUser:myPassword@cluster0.mongodb.net/library_lending?retryWrites=true&w=majority';
```

---

# Install Dependencies

Backend

```bash
cd backend
npm install
```

Frontend

```bash
cd frontend
npm install
```

---

# Run the Backend

```bash
cd backend
node index.js
```

Expected output:

```
Connected to MongoDB Atlas
Server running on http://localhost:5000
```

---

# Run the Frontend

```bash
cd frontend
npm run dev
```

The application will usually open at

```
http://localhost:5173
```

---

# API Endpoints

## Books

### Add Book

```
POST /books
```

### List Books

```
GET /books
```

Supports:

- page
- limit
- search

Example

```
GET /books?page=1&limit=10&search=harry
```

---

### Get Book

```
GET /books/:id
```

---

### Delete Book

```
DELETE /books/:id
```

---

## Loans

### Borrow Book

```
POST /loans
```

---

### List Loans

```
GET /loans
```

Supports

- page
- limit
- status

Example

```
GET /loans?page=1&status=Borrowed
```

---

### Overdue Loans

```
GET /loans/overdue
```

---

### Return Loan

```
PUT /loans/:id/return
```

---

# Sample Book JSON

```json
{
    "title": "Clean Code",
    "author": "Robert C. Martin",
    "isbn": "9780132350884",
    "totalCopies": 5
}
```

---

# Sample Loan JSON

```json
{
    "bookId": "BOOK_ID",
    "borrowerName": "John Doe",
    "dueDate": "2026-08-15"
}
```

---

# Importing Postman

Import:

```
postman/
├── Library-Lending-API.postman_collection.json
└── Library-Lending.postman_environment.json
```

Select the environment:

```
Library Lending - Local
```

Update:

- `book_id`
- `loan_id`

after creating resources.

---

# Validation

### Books

- Required fields
- ISBN must be unique
- totalCopies must be greater than zero

### Loans

- Cannot borrow unavailable books
- Cannot return an already returned loan
- Cannot delete a borrowed book

---

# Screens

The React frontend includes

- Add Book
- Search Catalog
- Borrow Books
- Delete Books
- Active Loans
- Return Books
- Pagination
- Status Filtering
- Overdue Indicators

---

# Future Improvements

- User authentication
- Role-based access
- Fine calculations
- Reservation system
- Email reminders
- Barcode scanning
- Dashboard analytics

---

# Author

Library Lending System

Built with ❤️ using Express, React and MongoDB Atlas.
