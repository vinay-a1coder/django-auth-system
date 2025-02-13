# Django Authentication System

## Overview
This project is a Django-based authentication system that provides user registration, login, password reset, and profile management functionalities using Django's built-in authentication system.

## Features
- User authentication with email or username and password.
- Pages for login, signup, forgot password, change password, dashboard, and profile.
- Restrict access to certain pages based on authentication status.
- Secure password reset functionality via email.
- Styled templates using Bootstrap.

## Installation & Setup
### 1. Clone the Repository
```sh
git clone https://github.com/yourusername/django-auth-system.git
cd django-auth-system
```

### 2. Create a Virtual Environment (Optional but Recommended)
```sh
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

### 3. Install Dependencies
```sh
pip install -r requirements.txt
```

### 4. Configure Database
Apply migrations to set up the database:
```sh
python manage.py migrate
```

### 5. Create a Superuser
To access the admin panel:
```sh
python manage.py createsuperuser
```
Follow the prompts to enter a username, email, and password.

### 6. Run the Development Server
```sh
python manage.py runserver
```
Visit `http://127.0.0.1:8000/` in your browser.

## Configuration
### Email Settings for Password Reset
For password reset functionality, update your `settings.py` with SMTP settings.

#### Option 1: Console Backend (For Development)
Emails will be printed to the console instead of being sent.
```python
EMAIL_BACKEND = 'django.core.mail.backends.console.EmailBackend'
```

#### Option 2: Gmail SMTP (For Real Emails)
1. Enable **2-Step Verification** in your Google account.
2. Generate an **App Password** from [Google App Passwords](https://myaccount.google.com/apppasswords).
3. Update `settings.py`:
```python
EMAIL_BACKEND = 'django.core.mail.backends.smtp.EmailBackend'
EMAIL_HOST = 'smtp.gmail.com'
EMAIL_PORT = 587
EMAIL_USE_TLS = True
EMAIL_HOST_USER = 'your_email@gmail.com'
EMAIL_HOST_PASSWORD = 'your_app_password'
DEFAULT_FROM_EMAIL = EMAIL_HOST_USER
```


## Usage
### Available Pages:
- **Login Page:** `http://127.0.0.1:8000/accounts/login/`
- **Signup Page:** `http://127.0.0.1:8000/accounts/signup/`
- **Forgot Password Page:** `http://127.0.0.1:8000/accounts/forgot-password/`
- **Change Password Page:** `http://127.0.0.1:8000/accounts/change-password/`
- **Dashboard:** `http://127.0.0.1:8000/accounts/dashboard/`
- **Profile Page:** `http://127.0.0.1:8000/accounts/profile/`

## Troubleshooting
- **Template Not Found Error**: Ensure `base.html` is in `templates/` and `TEMPLATES['DIRS']` in `settings.py` is correctly set.
- **NoReverseMatch for Password Reset**: Ensure `password_reset_confirm` is included in `urls.py`.
- **Email Not Sending**: If using Gmail, make sure **App Password** is correctly configured.
- **Database Issues**: Run `python manage.py migrate` to apply migrations.


---


