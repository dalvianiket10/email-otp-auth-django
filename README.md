# email-otp-auth-django

# Grexa AI - User Authentication API

This project implements a simple user authentication system using email and OTP, built with Django and JWT.

## 🔧 Tech Stack

- **Backend Framework**: Django
- **Database**: SQLite
- **Authentication**: OTP + JWT
- **Mock Email**: Printed to console
- **API Tool**: Postman

---

## 📁 Setup Instructions

### 1. Clone or Download

Download and unzip the project folder or clone the repository (if applicable).

### 2. Create Virtual Environment (if not already created)

```bash
python -m venv venv

3. Activate Virtual Environment

Windows:

venv\Scripts\activate

4. Install Dependencies

pip install -r requirements.txt

5. Run Migrations

python manage.py makemigrations
python manage.py migrate

6. Start the Server

python manage.py runserver
📬 API Endpoints
Base URL: http://127.0.0.1:8000/api/

1. Register (Send OTP)
Endpoint: /register/

Method: POST

Body (JSON):

{
  "email": "test@example.com"
}

✅ Returns 201 Created and sends mock OTP to console.


2. Request OTP (again)
Endpoint: /request-otp/

Method: POST

Body (JSON):

{
  "email": "test@example.com"
}

✅ Prints new OTP to console (mock email).


3. Verify OTP
Endpoint: /verify-otp/

Method: POST

Body (JSON):

{
  "email": "test@example.com",
  "otp": "123456"
}

✅ Returns JWT token if OTP is correct and not expired:


{
  "message": "OTP verified",
  "token": "your_jwt_token_here"
}

🧪 Postman Collection

Use the provided Postman collection file:
➡️ grexa_auth_api.postman_collection.json
Import it into Postman to test all 3 endpoints.

🔐 Notes

OTP is valid for 5 minutes

OTP and email are stored in the SQLite database

Token is generated using PyJWT and returned upon successful verification

