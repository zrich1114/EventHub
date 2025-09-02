# EventHub

EventHub is a full-stack web application for creating and managing events, designed as a demonstration of modern web development practices. It's configured for ephemeral cloud development environments on [Gitpod](https://www.gitpod.io/) and showcases a complete CRUD application with React, Node.js, Express, and PostgreSQL.

## Tech Stack

- **Frontend**: React 18, React Router DOM, Axios
- **Backend**: Node.js, Express.js, PostgreSQL
- **Development**: Gitpod, Dev Containers, Create React App

## Project Structure

```
EventHub/
├── client/                 # React frontend application
│   ├── src/
│   │   ├── App.js         # Main app component with routing
│   │   ├── HomePage.js    # Event listing page
│   │   ├── EventPage.js   # Individual event details
│   │   ├── CreateEventPage.js # Event creation form
│   │   └── index.js       # React app entry point
│   ├── public/            # Static assets
│   └── package.json       # Frontend dependencies
├── server.js              # Express API server (main backend entry)
├── db.js                  # PostgreSQL connection configuration
├── init-db.sh            # Database initialization script
├── package.json          # Backend dependencies
├── .gitpod.yml           # Gitpod workspace configuration
└── .devcontainer/        # Dev Container configuration
```

## Features

- **Event Management**: Create, view, and list events
- **RESTful API**: Clean API endpoints for event operations
- **Responsive UI**: React-based frontend with routing
- **Database Integration**: PostgreSQL for persistent data storage
- **Cloud Development**: Pre-configured for Gitpod environments

## API Endpoints

- `GET /` - Health check
- `GET /events` - Fetch all events
- `GET /events/:id` - Fetch single event by ID
- `POST /events` - Create new event

## Database Schema

```sql
CREATE TABLE events (
    id SERIAL PRIMARY KEY,
    title VARCHAR(255) NOT NULL,
    description TEXT NOT NULL
);
```

## Quick Start with Gitpod

Click the button below to start a new cloud development environment:

[![Open in Gitpod](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io/#https://github.com/gitpod-samples/EventHub)

The Gitpod environment will automatically:
- Install all dependencies
- Initialize the PostgreSQL database
- Start the backend server on port 3001
- Start the frontend development server on port 3000
- Configure environment variables

## Local Development Setup

If you prefer to run locally instead of using Gitpod:

### Prerequisites
- Node.js (v14 or higher)
- PostgreSQL
- npm or yarn

### Setup Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/gitpod-samples/EventHub.git
   cd EventHub
   ```

2. **Install backend dependencies**
   ```bash
   npm install
   ```

3. **Install frontend dependencies**
   ```bash
   cd client
   npm install
   cd ..
   ```

4. **Setup PostgreSQL database**
   ```bash
   # Create database and tables
   ./init-db.sh
   ```

5. **Configure environment variables**
   ```bash
   # In the client directory, create .env file
   cd client
   echo "REACT_APP_API_URL=http://localhost:3001" > .env
   cd ..
   ```

6. **Start the application**
   ```bash
   # Terminal 1: Start backend server
   npm start
   
   # Terminal 2: Start frontend development server
   cd client
   npm start
   ```

7. **Access the application**
   - Frontend: http://localhost:3000
   - Backend API: http://localhost:3001

## Development

### Backend Development
- Main server file: `server.js`
- Database configuration: `db.js`
- Uses Express.js with async/await patterns
- PostgreSQL with connection pooling

### Frontend Development
- Built with Create React App
- Uses functional components and React hooks
- React Router for client-side routing
- Axios for API communication

### Adding New Features
1. **Backend**: Add new routes in `server.js`
2. **Frontend**: Create new components in `client/src/`
3. **Database**: Update schema in `init-db.sh` if needed

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## License

This project is open source and available under the [MIT License](LICENSE).
