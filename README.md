# FastAPI Production Starter

A production-ready FastAPI starter template with modern Python best practices, Docker support, and comprehensive testing setup.

![Python Version](https://img.shields.io/badge/Python-3.8+-blue.svg)
![FastAPI](https://img.shields.io/badge/FastAPI-0.100+-green.svg)
![License](https://img.shields.io/badge/License-MIT-blue.svg)

---

## 🚀 Features

- **FastAPI Framework** - Modern, fast (high-performance) web framework for building APIs
- **Docker Support** - Containerized deployment with Dockerfile included
- **GitHub Actions** - CI/CD pipeline for automated testing and deployment
- **Professional Structure** - Clean, scalable project architecture
- **Testing Ready** - pytest configuration for unit and integration tests
- **Environment Management** - Support for environment-specific configurations
- **Production-Grade** - Following FastAPI and Python best practices

---

## 🛠️ Prerequisites

- Python 3.8 or higher
- pip or poetry
- Docker (optional, for containerized deployment)
- Virtual environment (venv, poetry, or conda)

---

## 📦 Installation & Setup

### 1. Clone the Repository

```bash
git clone https://github.com/Hariom1441/fastapi-prod-starter.git
cd fastapi-prod-starter
```

### 2. Create Virtual Environment

```bash
# Using venv
python -m venv venv

# On Windows
venv\Scripts\activate

# On Linux/macOS
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the Application

```bash
# Using FastAPI development server
fastapi dev app/main.py

# Or using uvicorn directly
uvicorn app.main:app --reload --host 0.0.0.0 --port 8000
```

The API will be available at `http://localhost:8000`

### 5. Access API Documentation

- **Swagger UI**: http://localhost:8000/docs
- **ReDoc**: http://localhost:8000/redoc

---

## 🐳 Docker Deployment

### Build Docker Image

```bash
docker build -t fastapi-prod-starter:latest .
```

### Run Container

```bash
docker run -p 8000:8000 fastapi-prod-starter:latest
```

### Using Docker Compose

```bash
docker-compose up -d
```

---

## 🧪 Testing

Run tests using pytest:

```bash
# Run all tests
pytest

# Run with verbose output
pytest -v

# Run specific test file
pytest tests/test_main.py

# Run with coverage report
pytest --cov=app tests/

# Run with specific marker
pytest -m "unit"
```

The project includes `pytest.ini` configuration for test discovery and execution.

---

## 🔧 Configuration

### Environment Variables

Create a `.env` file in the root directory (if needed):

```bash
# Example configuration
ENVIRONMENT=development
DEBUG=True
DATABASE_URL=postgresql://user:password@localhost/dbname
SECRET_KEY=your-secret-key-here
```

Load environment variables in your application:

```python
from pydantic_settings import BaseSettings

class Settings(BaseSettings):
    environment: str = "development"
    debug: bool = True
    
    class Config:
        env_file = ".env"
```

---

## 📚 API Documentation

Once the application is running, interactive API documentation is available at:

- **Swagger UI** (default): `/docs`
- **ReDoc** (alternative): `/redoc`

These are automatically generated from your FastAPI route definitions.

---

## 🚀 CI/CD Pipeline

The project includes GitHub Actions workflows in `.github/workflows/`:

- **Continuous Integration**: Runs tests on every push
- **Code Quality**: Linting and formatting checks
- **Deployment**: Automated deployment on main branch updates

### Local Testing of GitHub Actions

```bash
# Using act (GitHub Actions emulator)
act -l                          # List available workflows
act push                        # Run workflows on push event
```

---

## 📝 Development Workflow

### Code Style & Formatting

```bash
# Format code with Black
black app/ tests/

# Sort imports with isort
isort app/ tests/

# Lint with flake8
flake8 app/ tests/

# Type checking with mypy
mypy app/
```

### Pre-commit Hooks (Optional)

```bash
pip install pre-commit
pre-commit install
```

---

## 🔐 Security Considerations

- Never commit `.env` files or secrets to version control
- Use environment variables for sensitive data
- Implement proper authentication (JWT, OAuth2)
- Add CORS configuration for frontend access
- Enable HTTPS in production
- Use strong database passwords
- Implement rate limiting for API endpoints

---

## 📦 Dependencies

Core dependencies (see `requirements.txt`):

- **fastapi**: Web framework
- **uvicorn**: ASGI server
- **pydantic**: Data validation using Python type annotations
- **sqlalchemy**: SQL toolkit and ORM (if using database)
- **python-dotenv**: Environment variable management (optional)

Development dependencies:

- **pytest**: Testing framework
- **black**: Code formatter
- **flake8**: Linter
- **mypy**: Type checker
- **isort**: Import sorter

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
---

