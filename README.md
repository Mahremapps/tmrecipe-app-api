# Turkmen Cuisine Recipe API

A **Django REST API** for sharing Turkmen cuisine recipes. This project follows **Test‑Driven Development (TDD)** and includes **Docker**, **docker-compose**, **GitHub Actions CI**, and automated tests.

---

## 🚀 Features
- Django + Django REST Framework
- Recipe CRUD (create, list, update, delete)
- TDD using `pytest` or Django's `manage.py test`
- Dockerized development & production setup
- GitHub Actions CI for running tests automatically
- Environment-based configuration

---

## 📁 Project Structure (example)
```
project/
│   docker-compose.yml
│   Dockerfile
│   README.md
│   requirements.txt
│
├── app/
│   ├── manage.py
│   ├── app/
│   ├── recipes/
│   ├── tests/
```

---

## 🛠 Requirements
- Docker & Docker Compose
- Git
- VSCode
---

## 🐳 Running the Project with Docker
### 1. Build containers
```
docker-compose build
```

### 2. Run development server
```
docker-compose up
```
The API will be available at:
```
http://localhost:8000
```

### 3. Apply migrations
```
docker-compose exec app python manage.py migrate
```

### 4. Create superuser
```
docker-compose exec app python manage.py createsuperuser
```

---

## 🧪 Running Tests
### Using Docker-compose
Tests may be executed as part of CI or inside Dockerfile:
```
docker-compose --rm app sh -c "python manage.py test"
```

---

## 🧑‍💻 Local Development (Without Docker)
If needed:
```
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver
```

---

## 🔄 GitHub Actions CI
This project uses GitHub Actions to:
- build Docker image
- run tests
- validate code formatting

---

## 🚀 Deployment Guide
### 1. Build production image
```
docker build -t recipes-api .
```

### 2. Run container
```
docker run -p 8000:8000 recipes-api
```

### 3. Environment variables
```
DJANGO_SECRET_KEY=your_secret
DEBUG=False
DATABASE_URL=postgres://user:pass@db:5432/recipes
```

### 4. Production server command
Usually via gunicorn:
```
gunicorn app.wsgi:application --bind 0.0.0.0:8000
```

---

## 📖 API Endpoints (example)
```
GET /api/recipes/
POST /api/recipes/
GET /api/recipes/<id>/
PUT /api/recipes/<id>/
DELETE /api/recipes/<id>/
```

---

## 🤝 Contributing
1. Fork repo
2. Create feature branch
3. Add tests first (TDD!)
4. Implement feature
5. Submit a pull request

---

## 📜 License
MIT License

---

## 💬 Contact
Feel free to open issues or suggestions.
