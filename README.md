# Histoires Magiques

This project is a fullstack application built with a Vue.js frontend, a Python backend using Flask, and a PostgreSQL database. The application is designed to demonstrate a complete development setup with Docker.

## Project Structure

```
my-fullstack-app
├── backend          # Contains the backend application
│   ├── app.py      # Main entry point for the Flask app
│   ├── requirements.txt  # Python dependencies
│   ├── Dockerfile   # Dockerfile for the backend
│   └── README.md    # Documentation for the backend
├── frontend         # Contains the Vue.js frontend application
│   ├── src
│   │   ├── App.vue  # Main Vue component
│   │   └── main.js   # Entry point for the Vue application
│   ├── package.json  # Configuration for npm
│   └── README.md     # Documentation for the frontend
├── db               # Contains database initialization scripts
│   └── init.sql     # SQL commands to initialize the PostgreSQL database
├── docker-compose.yml # Docker Compose file to manage services
└── README.md        # General documentation for the entire project
```

## Getting Started

### Prerequisites

- Docker
- Docker Compose

### Installation

1. Clone the repository:
   ```
   git clone <repository-url>
   cd my-fullstack-app
   ```

2. Build and run the application using Docker Compose:
   ```
   docker-compose up --build
   ```

### Usage

- The backend will be accessible at `http://localhost:5002`.
- The frontend will be accessible at `http://localhost:8080`.

### Contributing

Contributions are welcome! Please open an issue or submit a pull request for any improvements or bug fixes.

### License

This project is licensed under the MIT License.