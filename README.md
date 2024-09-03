# Django Customer API

This is a simple Django REST API for managing customer data. The API allows you to create, retrieve, update, and delete customer records. It uses Django 4.2, Django REST Framework, and MySQL as the database.

## Features

- Create, retrieve, update, and delete customers
- Uses Django REST Framework for API handling
- Configured to use MySQL as the database backend

## Requirements

- Python 3.12.4
- Django 4.2 or newer
- MySQL 10.5 or newer

## Installation

### 1. Clone the repository

First, clone this repository to your local machine:

```bash
git clone https://github.com/your-username/django_simple_api.git
cd django_simple_api
```

### 2. Set up the virtual environment

It's recommended to use a virtual environment to manage dependencies:

```bash
python -m venv venv
```

Activate the virtual environment:

- On Windows:
  ```bash
  venv\Scripts\activate
  ```
- On macOS/Linux:
  ```bash
  source venv/bin/activate
  ```

### 3. Install the dependencies

Install the required Python packages:

```bash
pip install -r requirements.txt
```

### 4. Set up the database

This project uses MySQL. You need to create a database and configure it in your Django settings.

1. **Create the MySQL database:**

   ```sql
   CREATE DATABASE your_db_name;
   ```

2. **Configure the database in Django:**

   Open `your_project/settings.py` and configure the `DATABASES` section:

   ```python
   DATABASES = {
       'default': {
           'ENGINE': 'django.db.backends.mysql',
           'NAME': 'your_db_name',
           'USER': 'your_db_user',
           'PASSWORD': 'your_db_password',
           'HOST': 'localhost',
           'PORT': '3306',
       }
   }
   ```

### 5. Apply database migrations

Apply the initial database migrations to set up the database schema:

```bash
python manage.py migrate
```

### 6. Run the development server

Start the Django development server:

```bash
python manage.py runserver
```

You can now access the API at `http://127.0.0.1:8000/`.

## API Endpoints

- `GET /api/customers/` - List all customers
- `POST /api/customers/` - Create a new customer
- `GET /api/customers/<id>/` - Retrieve a customer by ID
- `PUT /api/customers/<id>/` - Update a customer by ID
- `DELETE /api/customers/<id>/` - Delete a customer by ID

## Folder Structure

The project follows an atomic design pattern for organizing code, ensuring that the application remains maintainable as it grows.

```
your_project/
├── manage.py
├── simple_api/
│   ├── __init__.py
│   ├── settings.py
│   ├── urls.py
│   ├── asgi.py
│   ├── wsgi.py
│   └── ...
├── customers/
│   ├── migrations/
│   ├── admin.py
│   ├── apps.py
│   ├── models.py
│   ├── serializers.py
│   ├── tests.py
│   ├── urls.py
│   ├── views.py
│   └── ...
└── README.md
```

- **models.py:** Defines the database models.
- **serializers.py:** Handles serialization of the models for the API.
- **views.py:** Contains the view logic for handling API requests.
- **services/:** Contains business logic, separated from the views.
- **repositories/:** Encapsulates database access logic.
