
# E-Commerce Back End

This project provides a backend for an e-commerce website using Express.js, Sequelize, and PostgreSQL. It features a RESTful API for managing categories, products, tags, and product-tag associations.

## Table of Contents

- [Project Overview](#project-overview)
- [Technologies Used](#technologies-used)
- [Getting Started](#getting-started)
- [Configuration](#configuration)
- [Database Setup](#database-setup)
- [Seeding Data](#seeding-data)
- [Running the Application](#running-the-application)
- [API Endpoints](#api-endpoints)
  - [Categories](#categories)
  - [Products](#products)
  - [Tags](#tags)
- [Testing](#testing)
- [Contributing](#contributing)
- [License](#license)

## Project Overview

This backend API allows management of an e-commerce store's categories, products, and tags. It uses Sequelize to interact with a PostgreSQL database, and Express.js to handle HTTP requests.

## Technologies Used

- **Node.js**: JavaScript runtime for building server-side applications.
- **Express.js**: Web framework for building RESTful APIs.
- **Sequelize**: Promise-based ORM for Node.js to interact with PostgreSQL.
- **PostgreSQL**: Relational database system.
- **dotenv**: Module for loading environment variables from a `.env` file.

## Getting Started

### Prerequisites

- Node.js and npm installed.
- PostgreSQL installed and running.

### Installation

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd <project-directory>
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Create a `.env` file based on the `.env.EXAMPLE` template provided:
   ```bash
   cp .env.EXAMPLE .env
   ```

4. Update the `.env` file with your PostgreSQL database credentials:
   ```plaintext
   DB_NAME='your_database_name'
   DB_USER='your_database_user'
   DB_PASSWORD='your_database_password'
   ```

## Configuration

### Database Configuration

Make sure PostgreSQL is installed and running. Update the `.env` file with your database credentials. The `config/connection.js` file uses these credentials to connect to the database.

## Database Setup

1. Create the database using the schema file:
   ```bash
   psql -U <your-username> -f db/schema.sql
   ```

## Seeding Data

1. Run the seed script to populate the database with initial data:
   ```bash
   npm run seed
   ```

## Running the Application

1. Start the server:
   ```bash
   npm start
   ```

2. Or, for development with automatic restarts:
   ```bash
   npm run watch
   ```

The server will run on port 3001 by default, or you can set the `PORT` environment variable.

## API Endpoints

### Categories

- **GET** `/api/categories` - Retrieve all categories with associated products.
- **GET** `/api/categories/:id` - Retrieve a single category by ID with associated products.
- **POST** `/api/categories` - Create a new category.
- **PUT** `/api/categories/:id` - Update a category by ID.
- **DELETE** `/api/categories/:id` - Delete a category by ID.

### Products

- **GET** `/api/products` - Retrieve all products with associated category and tags.
- **GET** `/api/products/:id` - Retrieve a single product by ID with associated category and tags.
- **POST** `/api/products` - Create a new product. Includes `tagIds` in the request body to associate tags.
- **PUT** `/api/products/:id` - Update a product by ID. Update tags using `tagIds`.
- **DELETE** `/api/products/:id` - Delete a product by ID.

### Tags

- **GET** `/api/tags` - Retrieve all tags with associated products.
- **GET** `/api/tags/:id` - Retrieve a single tag by ID with associated products.
- **POST** `/api/tags` - Create a new tag.
- **PUT** `/api/tags/:id` - Update a tag's name by ID.
- **DELETE** `/api/tags/:id` - Delete a tag by ID.

## Testing

Test your API endpoints using tools like [Insomnia](https://insomnia.rest/) or [Postman](https://www.postman.com/). You can also write unit tests for your models and routes using a testing framework like [Jest](https://jestjs.io/) if desired.

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request with your changes. Ensure that your code adheres to the project's coding standards and includes relevant tests.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

Feel free to adjust the content and structure according to your specific needs or preferences. This template provides a comprehensive overview and instructions for setting up and using your e-commerce backend project.
