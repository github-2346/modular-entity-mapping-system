# Modular Entity Mapping System API

This project demonstrates backend architecture, modular app
design, and API development using **APIView endpoints** 

## Project Overview

The system manages four main entities:

Vendor → Product → Course → Certification

It also manages the relationships between them using mapping tables:

-   VendorProductMapping
-   ProductCourseMapping
-   CourseCertificationMapping

## Tech Stack

-   Python
-   Django
-   Django REST Framework
-   drf-yasg 
-   SQLite 

## Project Structure

```
modular_entity_mapping_system/
│
├── manage.py
├── requirements.txt
├── README.md
│
├── modular_api_project/
│   ├── __init__.py
│   ├── settings.py
│   ├── urls.py
│   ├── asgi.py
│   └── wsgi.py
│
├── common/
│   ├── __init__.py
│   ├── models.py
│   └── utils.py
│
├── vendor/
│   ├── models.py
│   ├── serializers.py
│   ├── views.py
│   ├── urls.py
│   └── admin.py
│
├── product/
│   ├── models.py
│   ├── serializers.py
│   ├── views.py
│   ├── urls.py
│   └── admin.py
│
├── course/
│   ├── models.py
│   ├── serializers.py
│   ├── views.py
│   ├── urls.py
│   └── admin.py
│
├── certification/
│   ├── models.py
│   ├── serializers.py
│   ├── views.py
│   ├── urls.py
│   └── admin.py
│
├── vendor_product_mapping/
│   ├── models.py
│   ├── serializers.py
│   ├── views.py
│   ├── urls.py
│   └── admin.py
│
├── product_course_mapping/
│   ├── models.py
│   ├── serializers.py
│   ├── views.py
│   ├── urls.py
│   └── admin.py
│
└── course_certification_mapping/
    ├── models.py
    ├── serializers.py
    ├── views.py
    ├── urls.py
    └── admin.py
```

Each app contains:

    models.py
    serializers.py
    views.py
    urls.py
    admin.py

## Features

### Core Features

-   Modular Django application architecture
-   CRUD APIs for all entities
-   Mapping APIs for relationships
-   Query filtering
-   Soft delete using `is_active`

## API Endpoints

### Master Entities

    GET    /api/vendors/
    POST   /api/vendors/
    GET    /api/vendors/{id}/
    PUT    /api/vendors/{id}/
    PATCH  /api/vendors/{id}/
    DELETE /api/vendors/{id}/

    GET    /api/products/
    POST   /api/products/
    GET    /api/products/{id}/
    PUT    /api/products/{id}/
    PATCH  /api/products/{id}/
    DELETE /api/products/{id}/

    GET    /api/courses/
    POST   /api/courses/
    GET    /api/courses/{id}/
    PUT    /api/courses/{id}/
    PATCH  /api/courses/{id}/
    DELETE /api/courses/{id}/

    GET    /api/certifications/
    POST   /api/certifications/
    GET    /api/certifications/{id}/
    PUT    /api/certifications/{id}/
    PATCH  /api/certifications/{id}/
    DELETE /api/certifications/{id}/


### Mapping APIs

Vendor → Product

    GET    /api/vendor-product-mappings/
    POST   /api/vendor-product-mappings/
    GET    /api/vendor-product-mappings/{id}/
    PUT    /api/vendor-product-mappings/{id}/
    PATCH  /api/vendor-product-mappings/{id}/
    DELETE /api/vendor-product-mappings/{id}/

Product → Course

    GET    /api/product-course-mappings/
    POST   /api/product-course-mappings/
    GET    /api/product-course-mappings/{id}/
    PUT    /api/product-course-mappings/{id}/
    PATCH  /api/product-course-mappings/{id}/
    DELETE /api/product-course-mappings/{id}/

Course → Certification

    GET    /api/course-certification-mappings/
    POST   /api/course-certification-mappings/
    GET    /api/course-certification-mappings/{id}/
    PUT    /api/course-certification-mappings/{id}/
    PATCH  /api/course-certification-mappings/{id}/
    DELETE /api/course-certification-mappings/{id}/


## Setup Instructions

### 1. Clone the repository

    git clone https://github.com/github-2346/modular-entity-mapping-system.git
    cd modular_entity_mapping_system

### 2. Create virtual environment

    python -m venv venv
    source venv/bin/activate

### 3. Install dependencies

    pip install -r requirements.txt

### 4. Run migrations

    python manage.py makemigrations
    python manage.py migrate

### 5. Run the server

    python manage.py runserver


## API Documentation

Swagger UI

    http://127.0.0.1:8000/swagger/

ReDoc

    http://127.0.0.1:8000/redoc/

These pages allow you to test all APIs directly from the browser.


## Seed Sample Data

Populate the database with sample records:

    python manage.py seed_data


## Running Tests

    python manage.py test


## Example Request

Create a Vendor

    POST /api/vendors/

Request Body:

 json
{
  "name": "AWS",
  "code": "AWS01",
  "description": "Cloud provider"
}

