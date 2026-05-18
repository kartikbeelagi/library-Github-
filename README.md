# 📚 Library Management System - REST API

A professional Django REST Framework-based Library Management System with a responsive web frontend for managing book inventory.

<img width="1376" height="655" alt="Screenshot 2026-05-18 111416" src="https://github.com/user-attachments/assets/d547b3b6-4c4d-4c1f-b470-ddd0dbc040e6" />



---

## 🤔 What is an API?

### Definition
An **API (Application Programming Interface)** is a set of protocols, rules, and tools that allows different software applications to communicate with each other. It defines the methods and data formats that applications can use to request and exchange information.

### Key Characteristics
- **Standardized Communication**: Enables seamless interaction between different systems
- **Data Exchange**: Facilitates sending and receiving data in structured formats (typically JSON)
- **Platform Independent**: Works across different programming languages and operating systems
- **Security**: Provides controlled access to backend resources through authentication mechanisms

### REST API Basics
**REST (Representational State Transfer)** is an architectural style for building web APIs. It uses standard HTTP methods:
- **GET**: Retrieve data
- **POST**: Create new data
- **PUT**: Update data (full replacement)
- **PATCH**: Partial update
- **DELETE**: Remove data

---

## 💼 API Applications & Use Cases

### Common Real-World Applications

1. **E-Commerce Platforms**
   - Product catalogs and inventory management
   - Shopping cart and order processing
   - Payment gateway integration

2. **Social Media Networks**
   - User profiles and authentication
   - Post creation and engagement
   - Notification systems

3. **Healthcare Systems**
   - Patient records management
   - Appointment scheduling
   - Medical data exchange

4. **Financial Services**
   - Banking transactions
   - Investment portfolio management
   - Real-time market data

5. **Travel & Booking**
   - Hotel and flight reservations
   - Availability checking
   - Booking confirmations

6. **Library Management** *(This Project)*
   - Book inventory tracking
   - Circulation management
   - Availability status

---

## 🎯 Project Overview

### About This Project
This Library Management System is a complete CRUD (Create, Read, Update, Delete) application that demonstrates modern web development practices with a professional REST API backend and responsive frontend.

### Technology Stack

| Component | Technology | Version |
|-----------|-----------|---------|
| **Backend Framework** | Django | 6.0.5 |
| **API Framework** | Django REST Framework | 3.14.0 |
| **Database** | SQLite3 | Built-in |
| **Frontend** | HTML5 + CSS3 + Vanilla JavaScript | Modern |
| **Authentication** | Django CSRF Token | Built-in |

---

## 🚀 Features

### Backend API Features
✅ **RESTful Endpoints**: Full CRUD operations for books  
✅ **JSON Response Format**: Standardized data exchange  
✅ **Error Handling**: Comprehensive error messages  
✅ **Database Persistence**: SQLite for reliable data storage  
✅ **Security**: CSRF protection for form submissions  

### Frontend Features
✅ **User-Friendly Interface**: Responsive design  
✅ **Real-time Updates**: Dynamic table with instant refresh  
✅ **Form Validation**: Client-side validation before submission  
✅ **Status Indicators**: Color-coded availability status  
✅ **CRUD Operations**: Full book management capabilities  

---

## 📋 API Endpoints Reference

### Base URL
```
http://localhost:8000/api/books/
```

### Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/api/books/` | List all books |
| `POST` | `/api/books/` | Create a new book |
| `GET` | `/api/books/{id}/` | Retrieve a specific book |
| `PUT` | `/api/books/{id}/` | Update entire book record |
| `PATCH` | `/api/books/{id}/` | Partially update book record |
| `DELETE` | `/api/books/{id}/` | Delete a book |

### Book Model Fields
```json
{
  "id": "integer",
  "title": "string - Book title",
  "author": "string - Author name",
  "isbn": "string - ISBN code",
  "publication_year": "integer - Year published",
  "is_available": "boolean - Availability status"
}
```

---

## 🛠️ Installation & Setup

### Prerequisites
- Python 3.8 or higher
- pip (Python package manager)
- Git

### Step 1: Clone/Navigate to Project
```bash
cd c:\Users\PC 04\Desktop\API-cc\library_project
```

### Step 2: Create Virtual Environment
```bash
# Windows
python -m venv venv

# macOS/Linux
python3 -m venv venv
```

### Step 3: Activate Virtual Environment
```bash
# Windows (PowerShell)
.\venv\Scripts\Activate.ps1

# Windows (Command Prompt)
venv\Scripts\activate.bat

# macOS/Linux
source venv/bin/activate
```

### Step 4: Install Dependencies
```bash
pip install -r requirements.txt
```

### Step 5: Run Migrations (if needed)
```bash
python manage.py migrate
```

---

## ▶️ Running the Project

### Start the Development Server
```bash
python manage.py runserver
```

### Access the Application
- **Frontend UI**: [http://localhost:8000/](http://localhost:8000/)
- **API Browser**: [http://localhost:8000/api/books/](http://localhost:8000/api/books/)

### Default Port
The application runs on `http://127.0.0.1:8000/` by default.

---

## 📊 Project Structure

```
library_project/
├── manage.py                      # Django management script
├── requirements.txt               # Project dependencies
├── db.sqlite3                    # SQLite database
├── README.md                     # This file
├── PROJECT_SUMMARY.md            # Detailed project summary
│
├── library_project/              # Project configuration
│   ├── settings.py              # Django settings
│   ├── urls.py                  # Main URL routing
│   ├── asgi.py                  # ASGI configuration
│   └── wsgi.py                  # WSGI configuration
│
└── books/                        # Main app
    ├── models.py                # Book database model
    ├── views.py                 # API views and logic
    ├── serializers.py           # Data serialization
    ├── urls.py                  # App URL routing
    ├── admin.py                 # Django admin config
    │
    ├── migrations/              # Database migrations
    │   └── 0001_initial.py
    │
    └── templates/
        └── books/
            └── index.html       # Frontend interface
```

---

## 🔌 API Usage Examples

### Get All Books
```bash
curl http://localhost:8000/api/books/
```

### Create a New Book
```bash
curl -X POST http://localhost:8000/api/books/ \
  -H "Content-Type: application/json" \
  -d '{
    "title": "The Great Gatsby",
    "author": "F. Scott Fitzgerald",
    "isbn": "978-0743273565",
    "publication_year": 1925,
    "is_available": true
  }'
```

### Retrieve a Specific Book
```bash
curl http://localhost:8000/api/books/1/
```

### Update a Book
```bash
curl -X PUT http://localhost:8000/api/books/1/ \
  -H "Content-Type: application/json" \
  -d '{
    "title": "The Great Gatsby",
    "author": "F. Scott Fitzgerald",
    "isbn": "978-0743273565",
    "publication_year": 1925,
    "is_available": false
  }'
```

### Delete a Book
```bash
curl -X DELETE http://localhost:8000/api/books/1/
```

---

## 🔐 Security Features

- **CSRF Protection**: All POST/PUT/PATCH/DELETE requests are CSRF-protected
- **Input Validation**: Server-side validation on all API endpoints
- **Database Safety**: ORM protection against SQL injection
- **Error Handling**: Secure error messages without exposing sensitive information

---

## 📝 Requirements

The project dependencies are listed in `requirements.txt`:
- **Django 6.0.5**: Web framework
- **Django REST Framework 3.14.0**: REST API toolkit

Install them with:
```bash
pip install -r requirements.txt
```

---

## 🤝 Contributing

To contribute to this project:
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

---

## 📞 Support

For issues or questions:
1. Check the PROJECT_SUMMARY.md for detailed documentation
2. Review the API Endpoints Reference section above
3. Ensure virtual environment is activated
4. Verify all dependencies are installed

---

## 📄 License

This project is provided as-is for educational purposes.

---

## ✨ Key Highlights

🎓 **Educational Purpose**: Demonstrates professional REST API development  
🔧 **Production-Ready Code**: Industry standard practices  
📱 **Responsive Design**: Works on desktop and mobile  
🚀 **Easy Deployment**: Simple setup and quick start  
💾 **Data Persistence**: Reliable SQLite database  

---

**Created**: May 2026  
**Framework**: Django 6.0.5 + Django REST Framework 3.14.0  
**Status**: ✅ Production Ready


