# Backend Application

This directory contains the backend application built with Python and Flask. The backend is designed to interact with a PostgreSQL database and serves as the API for the frontend application.

## Setup Instructions

1. **Clone the Repository**
   ```bash
   git clone <repository-url>
   cd my-fullstack-app/backend
   ```

2. **Install Dependencies**
   Ensure you have Python and pip installed. Then, install the required packages:
   ```bash
   pip install -r requirements.txt
   ```

3. **Database Setup**
   Make sure you have PostgreSQL installed and running. You can initialize the database using the SQL commands in `db/init.sql`.

4. **Running the Application**
   You can run the application locally using:
   ```bash
   python app.py
   ```

5. **Docker Setup**
   To run the backend in a Docker container, build the Docker image and run it:
   ```bash
   docker build -t my-backend .
   docker run -p 5002:5000 my-backend
   ```

## Usage

The backend API provides various endpoints to interact with the application. You can access the API at `http://localhost:5000`.

## Contributing

Feel free to submit issues or pull requests if you have suggestions or improvements for the backend application.