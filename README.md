# FreshFold Laundry Shop Management System

A beginner-friendly Django web application with user registration/login, dashboard, POS, customers, services/rates, order management, SQLite database, and printable order receipt.

## Requirements
- Python 3.10 or newer
- Visual Studio Code (recommended)

## Windows setup
1. Extract `FreshFold_Laundry_System.zip`.
2. Open the extracted `FreshFold` folder in VS Code.
3. Open Terminal → New Terminal.
4. Create a virtual environment:
   ```powershell
   py -m venv venv
   ```
5. Activate it:
   ```powershell
   .\venv\Scripts\Activate.ps1
   ```
   If PowerShell blocks activation, run `Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass` and activate again.
6. Install Django:
   ```powershell
   python -m pip install -r requirements.txt
   ```
7. Create database tables:
   ```powershell
   python manage.py migrate
   ```
8. (Optional) Create an admin account:
   ```powershell
   python manage.py createsuperuser
   ```
9. Start the website:
   ```powershell
   python manage.py runserver
   ```
10. Open `http://127.0.0.1:8000/` in your browser and click **Create an account**.

## First use
1. Register a staff/owner account from the registration page.
2. Sign in.
3. Add at least one customer from Customers.
4. Add a service and its price per kg from Services & Rates (example: Wash & Fold, 35.00).
5. Open New POS Sale, select customer and service, enter weight, choose payment/status, then save.
6. Update order status as the laundry moves through Received → Washing → Drying → Ready → Completed.
7. Dashboard shows customer count, order count, today's orders, paid revenue and recent orders.

## Database
SQLite is used by default. Django creates `db.sqlite3` in the project folder after `migrate`. For a class project this is easy to run without MySQL/XAMPP. The Django admin is at `/admin/`.

## Important
- The first registered account is not automatically a superuser. Use `createsuperuser` if you need Django admin access.
- This is a local development setup. Before public deployment, set `DEBUG=False`, use a secure environment-based `SECRET_KEY`, configure `ALLOWED_HOSTS`, HTTPS, backups and a production database.
- GCash is represented as a selectable payment method only; this starter does not connect to a real GCash payment gateway.
- The responsive website works in mobile browsers. A native Android application is not included in this Django web project.
