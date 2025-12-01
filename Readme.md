# Plan de Charge Backend API

## Overview

This is the backend API for the Plan de Charge system, built with Node.js, Express, and PostgreSQL. The API provides endpoints for managing users, teams, subjects, and administrative tasks.

## Features

- RESTful API with comprehensive endpoints
- JWT-based authentication
- PostgreSQL database integration
- Comprehensive error handling
- API documentation

## Project Structure

```
back/
├── .env                  # Environment variables
├── sql/                  # SQL scripts for database setup
├── src/                  # Source code
│   └── index.ts          # Main server file
├── package.json          # Project dependencies and scripts
├── tsconfig.json         # TypeScript configuration
└── README.md             # Project documentation
```

## Getting Started

### Prerequisites

- Node.js (v16 or later)
- npm (v6 or later)
- PostgreSQL database

### Installation

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd back
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Set up environment variables:
   Create a `.env` file in the root directory with the following content:
   ```
   DATABASE_URL=postgresql://username:password@localhost:5432/database_name
   JWT_SECRET=your_secret_key
   PORT=5001
   ```

### Database Setup

1. Create a PostgreSQL database
2. Run the SQL scripts in the `sql/` directory to set up the database schema and initial data:
   ```bash
   psql -U your_username -d your_database -f sql/10_create_tables.sql
   psql -U your_username -d your_database -f sql/99_01_truncate_tables.sql
   psql -U your_username -d your_database -f sql/99_02_insert_t_pers.sql
   psql -U your_username -d your_database -f sql/99_03_0_insert_t_subject_types.sql
   psql -U your_username -d your_database -f sql/99_03_1_insert_t_subjects.sql
   psql -U your_username -d your_database -f sql/99_04_insert_t_comment.sql
   psql -U your_username -d your_database -f sql/99_05_color_mapping.sql
   psql -U your_username -d your_database -f sql/99_07_insert_t_teams.sql
   psql -U your_username -d your_database -f sql/99_08_update_t_pers.sql
   psql -U your_username -d your_database -f sql/99_10_insert_t_admin.sql
   psql -U your_username -d your_database -f sql/99_12_insert_t_pdc.sql
   ```

### Running the Server

1. Start the server:
   ```bash
   npm start
   ```

2. The API will be available at [http://localhost:5001](http://localhost:5001)

## API Documentation

The API provides endpoints for managing various aspects of the Plan de Charge system. The existing API documentation is included in this README file.

## Environment Variables

The application uses the following environment variables:

- `DATABASE_URL`: PostgreSQL connection string
- `JWT_SECRET`: Secret key for JWT token generation
- `PORT`: Server port (default: 5001)

## Contributing

1. Fork the repository
2. Create a new branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -am 'Add your feature'`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Create a new Pull Request

## License

This project is licensed under the ISC License. See the LICENSE file for details.

## Acknowledgments

- Built with Express.js and TypeScript
- Uses PostgreSQL for database storage
- JWT for authentication
- CORS for cross-origin resource sharing
