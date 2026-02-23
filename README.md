# E-Commerce REST API - Advanced Django Project

A robust, production-ready E-Commerce RESTful API built using Django REST Framework. 

## Key Features
- **Advanced Authentication:** Integrated **Djoser** and **SimpleJWT** for secure, token-based (Access/Refresh) authentication.
- **Background Tasks:** Used **Celery** with **Redis** as a message broker to handle asynchronous tasks like sending order confirmation emails.
- **Caching & Performance:** Implemented **Redis Caching** with **Django Signals** for automatic cache invalidation on product updates.
- **Scalable Architecture:**
  - **Nested Serializers** for complex Order-OrderItem relationships.
  - **Atomic Transactions** to ensure database integrity during order creation.
  - **Custom Filtering & Searching** using `django-filter` and custom backend filters.
- **Documentation:** Auto-generated **Swagger (OpenAPI 3.0)** documentation using `drf-spectacular`.
- **Reliability:** Comprehensive **API Test Cases** for products and authorization logic.

## Tech Stack
- **Backend:** Django, Django REST Framework
- **Task Queue:** Celery, Redis
- **Security:** JWT, Djoser
- **Database:** SQLite (Development)
- **Tools:** Swagger (Spectacular), Django-Silk (Profiling)

## API Endpoints
- `POST /auth/users/` - User Registration
- `POST /auth/jwt/create/` - User Login (Get Tokens)
- `GET /products/` - Product list with Filtering/Searching
- `POST /orders/` - Create Order (Triggers background email)

## Setup and Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/BalaUdayaBhaskar/E-Commerce-REST-API.git
   cd E-Commerce-REST-API

2. **Install dependencies:**

- pip install -r requirements.txt

3. **Database Setup & Population**:

To quickly test the API with sample data without manual entry, run the custom management command:

- python manage.py migrate
- python manage.py populate_db

This command creates a superuser (admin), sample products, and dummy orders.