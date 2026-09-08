# FastAPI Social CRUD

A lightweight, high-performance social media backend and frontend application built with FastAPI, SQLAlchemy, Pydantic, and Streamlit, managed using `uv`.

## Features

* **User Authentication:** Secure user registration, login, and token-based authentication.
* **Full CRUD Operations:** Create, read, update, and delete posts and user profiles.
* **Media Uploads:** Handle image and file uploads for social posts.
* **Robust Validation:** Automatic input validation and parsing via Pydantic.
* **Interactive Frontend:** Streamlit-powered dashboard interface for interacting with the API.

## Tech Stack

* **Backend:** FastAPI, Python
* **Frontend:** Streamlit
* **Database/ORM:** SQLAlchemy (SQLite by default)
* **Validation:** Pydantic
* **Package Management:** `uv`

## Project Structure

```text
├── app/
│   ├── app.py          # Core application logic / router integration
│   ├── db.py           # Database connection and session management
│   ├── frontend.py     # Streamlit frontend application
│   ├── images.py       # Media and image upload handling
│   ├── schemas.py      # Pydantic data models and schemas
│   └── users.py        # Authentication and user management logic
├── src/
│   └── fastapi_project/ # Package root directory
├── main.py             # FastAPI entry point
├── pyproject.toml      # Project metadata and dependencies
├── uv.lock             # Locked dependency versions
└── README.md
```

## Prerequisites

Ensure you have [uv](https://github.com/astral-sh/uv) installed on your system:

```bash
curl -sSf https://astral.sh/uv/install.sh | sh
```

## Setup & Installation

1. Clone the repository and navigate into the project directory:
```bash
git clone https://github.com/cha-sris/fastapi-crud.git
cd fastapi-crud
```


2. Create a virtual environment and sync dependencies using `uv`:
```bash
uv venv
source .venv/bin/activate
uv sync
```

3. Get your Imagekit API keys:
[imagekit.io](https://imagekit.io/)

4. Create your secret JWT token:
```bash
python -c "import secrets; print(secrets.token_hex(32))"
```

5. Create a `.env` file in the root directory and configure your environment variables:
```env
IMAGEKIT_PRIVATE_KEY=your_imagekit_private_key
IMAGEKIT_PUBLIC_Key=your_imagekit_public_key
IMAGEKIT_URL=your_imagekit_url_endpoint

JWT_SECRET_KEY=your_jwt_secret_key
```



## Running the Application

### 1. Start the FastAPI Backend

Run the backend server using `uv` and Uvicorn:

```bash
uv run uvicorn main:app --reload
```

- API Endpoint: [localhost:8000](http://127.0.0.1:8000)
- Interactive Documentation (Swagger UI): [localhost:8000/docs](http://127.0.0.1:8000/docs)

### 2. Start the Streamlit Frontend

In a separate terminal window (with your virtual environment active), launch the Streamlit frontend:

```bash
uv run streamlit run app/frontend.py
```

The frontend dashboard will open in your default browser at [localhost:8501](http://127.0.0.1:8501)