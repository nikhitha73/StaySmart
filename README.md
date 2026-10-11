# StaySmart — AI-Powered Hotel Discovery & Booking Aggregator

StaySmart is a hotel discovery and booking web application designed to help users find suitable stays based on their preferences and travel needs. It combines a modern web interface with AI-assisted discovery to make hotel exploration more intuitive.

## Live Demo

- **Frontend:** https://staysmart-ie62.onrender.com/
- **Backend:** https://backend-nj1y.onrender.com/
- **GitHub Repository:** https://github.com/nikhitha73/StaySmart

> Note: The backend URL is an API service. Opening its root URL should display a simple backend health message.

## Key Features

- **User authentication:** Register and log in to the application.
- **Hotel discovery:** Browse available hotel listings and view hotel information.
- **Hotel search:** Search for hotels based on the options supported by the application.
- **AI-assisted recommendations:** Explore hotel suggestions using the application's AI recommendation feature.
- **Booking workflow:** Select a hotel and create a booking.
- **Persistent bookings:** Booking information is stored in the backend database and remains available after refreshing or signing in again.
- **Responsive interface:** Use the application on desktop and mobile-sized screens.

## Technology Stack

| Layer | Technologies |
|---|---|
| Frontend | React, Vite, JavaScript, CSS |
| Backend | Node.js, Express.js |
| Database | MongoDB Atlas, Mongoose |
| Authentication | JSON Web Tokens (JWT), bcryptjs |
| AI integration | Google Gemini API |
| Deployment | Render |
| Version control | Git, GitHub |

The project concept also explores semantic hotel discovery using retrieval-augmented generation (RAG) and vector search. Include Pinecone in the implemented stack only if it is configured and used in the current codebase.

## Architecture Overview

1. The user interacts with the React frontend.
2. The frontend sends API requests to the Express backend.
3. The backend handles authentication, hotel-related requests, bookings, and AI requests.
4. MongoDB Atlas stores application data.
5. The AI integration supports the application's recommendation experience.

## Run Locally

### Prerequisites

- Node.js and npm installed
- A MongoDB Atlas database or another supported MongoDB instance
- Required API credentials for the integrations you use

### 1. Clone the repository

```bash
git clone https://github.com/nikhitha73/StaySmart.git
cd StaySmart
```

### 2. Set up the backend

```bash
cd backend
npm install
```

Create a `.env` file inside the `backend` directory. Add your own values locally:

```env
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_long_random_secret
JWT_EXPIRES_IN=your_configured_expiration
GEMINI_API_KEY=your_gemini_api_key
```

Do not commit this file or share its contents. The exact environment variables required depend on the current backend code and configuration.

Start the backend:

```bash
npm start
```

The backend uses `process.env.PORT` when supplied by the hosting platform and otherwise defaults to port `5000`.

### 3. Set up the frontend

Open a second terminal:

```bash
cd frontend
npm install
npm run dev
```

Open the local URL printed by Vite in the terminal. The current Vite configuration uses port `3000` and proxies `/api` requests to the local backend on port `5000`.

For production, the frontend must use the deployed backend URL. In the current configuration, `frontend/src/main.jsx` sets the Axios base URL for production.

## Deployment

The application is deployed on Render:

- Frontend service: https://staysmart-ie62.onrender.com/
- Backend service: https://backend-nj1y.onrender.com/

Configure backend secrets through the hosting provider's environment-variable settings. Do not add credentials to source code, screenshots, README files, or Git history.

## Suggested Demo Flow

1. Open the live frontend.
2. Register or log in.
3. Browse hotel listings and try a search.
4. Try the AI hotel recommendation feature.
5. Create a booking.
6. Open the bookings section and refresh or sign in again to verify persistence.

Use a test account and test data for demonstrations.

## Security Notes

- Keep `.env` files out of Git.
- Use strong, unique secrets for JWT signing.
- Restrict database access appropriately and rotate any credential that may have been exposed.
- Never put private API keys in frontend code; frontend code is visible to users.
- Review authentication, authorization, input validation, and error handling before using the application with real users.

## Future Improvements

- Add filters for price, location, amenities, and ratings where supported by the data.
- Improve recommendation explanations and personalization.
- Add booking status management and cancellation workflows.
- Add automated tests for API routes and user flows.
- Add monitoring and clearer user-facing error messages.

## Author / Contributors

Add your project team's names and roles here.

---

If you find an issue or have a suggestion, open an issue in the GitHub repository.
