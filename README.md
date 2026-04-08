## ECommerceSite (Using Python Django)

A simple e-commerce web application built with Python Django. It supports two roles — Admin and Customer with product management, cart/checkout, order tracking, and invoice downloads.

## Project Overview

This is a simple full‑stack e‑commerce web application built with Django. This project is a learning-friendly e-commerce site where:

- Visitors can browse products, search, and add items to a cart.
- Customers can sign up, log in, place orders, view order history, and download invoices.
- Admin users can manage products, customers, and order statuses.

## Project Details

# Modules / Apps

- `ecommerce/` – Django project (settings, URLs, WSGI/ASGI)
- `ecom/` – Main Django app (models, forms, views)
- `templates/ecom/` – HTML templates for admin + customer + public pages
- `static/` – Static assets and uploaded media (product images, profile pictures)

# Database

- Uses **SQLite** by default (`db.sqlite3`).

# Key Models

- **Customer**: user profile (address, mobile, profile pic)
- **Product**: name, price, description, image
- **Orders**: customer + product + shipping contact info + status
- **Feedback**: name + feedback message + date

# Authentication / Roles

- Uses Django’s built-in `User`.
- Customers are assigned to the `CUSTOMER` group.
- Admin uses Django admin/superuser login.

##  Project Features

# Public (no login)

- View product list (home page)
- Search products by name
- Add/remove products to cart (cart stored in browser cookies)
- Send feedback
- Contact-us email form

# Customer

- Signup / login
- View products
- Cart → address form → payment success flow
- View “My Orders”
- Download invoice PDF for an order
- View and edit profile

# Admin

- Dashboard with counts (customers/products/orders)
- View/update/delete customers
- Add/update/delete products
- View orders and update order status (Pending → Delivered)
- View feedback

##  Project Setup Requirements

# Requirements

- Python (commonly works with Python 3.7+ for Django 3.x)
- pip
- (Recommended) virtual environment: `venv`

Python packages are listed in `requirements.txt`.

# Installation & Run

```bash
# 1) Clone
git clone https://github.com/ijanan/ECommerceSite-Python-Django.git
cd ECommerceSite-Python-Django

# 2) Create & activate venv (Windows PowerShell)
python -m venv .venv
.\.venv\Scripts\Activate.ps1

# 3) Install dependencies
pip install -r requirements.txt

# 4) Migrations
python manage.py makemigrations
python manage.py migrate

# 5) Create admin user
python manage.py createsuperuser

# 6) Run
python manage.py runserver
```

Open:

- App: http://127.0.0.1:8000/
- Admin: http://127.0.0.1:8000/admin/


### Notes

- **Images / `ImageField`:** Django image uploads require the `Pillow` package.
- **Contact-us email:** SMTP settings are in `ecommerce/settings.py`.
  - Don’t commit real passwords.
  - For Gmail, you may need an **App Password** (recommended) instead of “less secure apps”.


