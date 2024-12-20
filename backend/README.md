# Insurance Recommendation App - Backend

## Table of Contents
1. [Getting Started](#getting-started)
2. [Running Tests](#running-tests)
3. [Building for Production](#building-for-production)
4. [Docker](#docker)
5. [Tech Stack](#tech-stack)
6. [License](#license)

## Getting Started

1. Clone the repository:
    ```sh
    git clone https://github.com/yourusername/insurance-recommendation-app.git
    ```

2. Navigate to the backend directory:
    ```sh
    cd insurance-recommendation-app/backend
    ```

3. Install dependencies:
    ```sh
    pnpm install
    ```

4. Create a `.env` file in the backend directory and add the necessary environment variables:
    ```env
    PORT=3001
    DATABASE_URL=your_database_url
    ```

5. Run the development server:
    ```sh
    pnpm run dev
    ```

6. The backend service should now be running on `http://localhost:3001`.

## Running Tests

To run the tests, use the following command:
```sh
pnpm test
```

## Building for Production

To build the project for production, use the following command:
```sh
pnpm run build
```

This will generate the compiled JavaScript files in the `dist` directory.

## Docker

To run the backend service using Docker, follow these steps:

1. Build the Docker image:
    ```sh
    docker build -t insurance-backend .
    ```

2. Run the Docker container:
    ```sh
    docker run -p 3001:3001 --env-file .env insurance-backend
    ```

The backend service should now be running on `http://localhost:3001`.

## Tech Stack

- **Node.js**: JavaScript runtime
- **Express.js**: Web framework for Node.js
- **PostgreSQL**: Relational database
- **Prisma**: ORM for database management
- **pnpm**: Fast, disk space efficient package manager
- **Docker**: Containerization platform

## License

This project is licensed under the MIT License.