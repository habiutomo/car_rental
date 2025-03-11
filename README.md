# Car Rental Application

A modern web application for car rental services built with React, TypeScript, Node.js, and Express.

## Features

### Customer Features
- **Home Page**: Browse featured cars and categories
- **Car Search**: Find cars by location, type, and date
- **Detailed Car Listings**: View comprehensive car information and images
- **Booking System**: Complete reservation process with date selection
- **User Authentication**: Register, login, and manage your profile
- **Booking Management**: View and manage your bookings
- **Reviews & Ratings**: Leave reviews for cars you've rented

### Admin Features
- **Dashboard**: Overview of bookings, cars, and statistics
- **Car Management**: Add, edit, and delete car listings
- **Booking Management**: View, approve, or reject bookings
- **User Management**: Manage user accounts

## Technology Stack

### Frontend
- **React**: UI library for building the user interface
- **TypeScript**: Type-safe JavaScript
- **TailwindCSS**: Utility-first CSS framework
- **ShadcnUI**: UI component library
- **Wouter**: Lightweight routing library
- **Tanstack Query**: Data fetching and state management
- **React Hook Form**: Form handling
- **Zod**: Schema validation
- **Lucide React**: Icon library

### Backend
- **Node.js**: JavaScript runtime
- **Express**: Web framework
- **Drizzle ORM**: Database ORM
- **PostgreSQL**: Database (configurable in-memory storage for development)
- **Passport.js**: Authentication middleware

## Getting Started

### Prerequisites
- Node.js 20 or later
- npm or yarn

### Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd car-rental-app
```

2. Install dependencies:
```bash
npm install
```

3. Start the development server:
```bash
npm run dev
```

This will start both the frontend and backend servers. The application will be available at http://localhost:5000.

## Project Structure

```
.
├── client/                   # Frontend code
│   ├── src/
│   │   ├── components/       # Reusable UI components
│   │   ├── hooks/            # Custom React hooks
│   │   ├── lib/              # Utility functions and shared logic
│   │   ├── pages/            # Page components
│   │   ├── App.tsx           # Main application component
│   │   └── main.tsx          # Entry point
├── server/                   # Backend code
│   ├── auth.ts               # Authentication logic
│   ├── index.ts              # Server entry point
│   ├── routes.ts             # API routes
│   ├── storage.ts            # Data storage interface
│   └── vite.ts               # Vite configuration
├── shared/                   # Shared code between frontend and backend
│   └── schema.ts             # Database schema and types
├── package.json
└── README.md
```

## Authentication

The application uses a session-based authentication system with the following endpoints:

- `POST /api/register`: Register a new user
- `POST /api/login`: Login an existing user
- `POST /api/logout`: Logout the current user
- `GET /api/user`: Get the current user information

## API Endpoints

### Cars
- `GET /api/cars`: Get all cars
- `GET /api/cars/:id`: Get a specific car
- `GET /api/cars/search`: Search cars by criteria
- `POST /api/cars`: Create a new car (admin only)
- `PUT /api/cars/:id`: Update a car (admin only)
- `DELETE /api/cars/:id`: Delete a car (admin only)

### Bookings
- `GET /api/bookings`: Get all bookings (admin only)
- `GET /api/bookings/:id`: Get a specific booking
- `GET /api/bookings/user`: Get current user's bookings
- `POST /api/bookings`: Create a new booking
- `PATCH /api/bookings/:id/status`: Update a booking status (admin only)

### Reviews
- `GET /api/reviews/:carId`: Get reviews for a specific car
- `POST /api/reviews`: Create a new review

## Development Guidelines

1. **Component Organization**: Components are organized by feature/page in the `/components` directory.
2. **State Management**: Use TanStack Query for server state and React Context for global UI state.
3. **Routing**: Use the `wouter` library for routing. All routes are defined in `App.tsx`.
4. **Forms**: Use React Hook Form with Zod validation for all forms.
5. **API Requests**: Use the `apiRequest` function from `lib/queryClient` for all API requests.

## License

This project is licensed under the MIT License - see the LICENSE file for details.