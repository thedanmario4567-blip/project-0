A lightweight FastAPI application that exposes a /me endpoint returning your profile information along with a dynamic cat fact fetched from the Cat Facts API.

This project demonstrates how to:

Build RESTful endpoints with FastAPI

Consume third-party APIs using Requests

Organize code using a clean and scalable folder structure

📁 Project Structure
fastapi_profile_api/
│
├── app/
│   ├── __init__.py
│   ├── main.py                # Entry point for FastAPI app
│   ├── api/
│   │   ├── __init__.py
│   │   └── routes_me.py       # /me endpoint implementation
│   ├── core/
│   │   ├── __init__.py
│   │   ├── config.py          # Configuration, environment variables
│   │   └── utils.py           # Utility functions (e.g., timestamp formatting)
│   ├── services/
│   │   ├── __init__.py
│   │   └── cat_facts.py       # Handles Cat Facts API integration
│   └── tests/
│       ├── __init__.py
│       └── test_me_endpoint.py  # Unit test for /me endpoint
│
├── .env                        # Environment variables (optional)
├── requirements.txt             # Dependencies list
├── README.md                    # Documentation
└── run.py                       # App launcher script

🚀 Features

GET /me: Returns a JSON response containing:

Your name, email, and tech stack

A dynamically fetched cat fact

A timestamp for when the data was generated

Sample Response

{
  "status": "success",
  "user": {
    "email": "youremail@example.com",
    "name": "Your Full Name",
    "stack": "Python / FastAPI"
  },
  "timestamp": "2025-10-16T11:43:29",
  "fact": "Cats sleep for 70% of their lives."
}

🧩 Tech Stack

FastAPI – for building the REST API

Uvicorn – ASGI server for running the app

Requests – for consuming the Cat Facts API

Python 3.10+

⚙️ Setup & Installation
1. Clone the repository
git clone https://github.com/yourusername/fastapi_profile_api.git
cd fastapi_profile_api

2. Create and activate a virtual environment
python -m venv venv
venv\Scripts\activate  # on Windows
# or
source venv/bin/activate  # on macOS/Linux

3. Install dependencies
pip install -r requirements.txt

4. Run the application
uvicorn app.main:app --host 0.0.0.0 --port 8000 --reload

5. Test it

Open your browser and go to:

http://127.0.0.1:8000/me

🧪 Running Tests

You can run tests with:

pytest

🧠 Environment Variables (optional)

If you have API keys or config values, add them in the .env file like this:

API_BASE_URL=https://catfact.ninja/fact

📜 License

This project is open-source and available under the MIT License
.
