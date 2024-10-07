Jobly React Frontend
Welcome to the Jobly frontend! This application is the React-based front-end for Jobly, a job search platform where users can view jobs, apply to them, and manage their profiles. It communicates with a backend built with Express.js, using a PostgreSQL database. Below are setup instructions, key features, and deployment details.

Table of Contents
Features
Tech Stack
Installation
Backend Setup
Environment Variables
Running the App
File Structure
API
Deployment
License
Features
User Authentication: Users can sign up, log in, and log out.
Job Search & Apply: Browse jobs and apply to them if logged in.
Company Directory: View a list of companies and detailed information about each.
Profile Management: Update user profile information.
Route Protection: Protected routes for logged-in users.
Responsive Design: Built for mobile, tablet, and desktop devices.
Persistent Login: User authentication persists across sessions using localStorage.
Tech Stack
Frontend: React.js, React Router, Axios
Backend: Express.js, Node.js, PostgreSQL (handled separately)
Styling: CSS and Bootstrap
State Management: React hooks (useState, useEffect)
API Communication: Axios for HTTP requests
Deployment: Render for both backend and frontend
Installation
Clone the Repository:
Install Dependencies:

bash
Copy code
npm install
Create .env File: Create a .env file at the root of the project and configure the environment variables (see Environment Variables).

Backend Setup
To run this frontend, you'll need the Jobly backend up and running. Clone and follow the instructions in the Jobly Backend Repository.

Ensure the backend is running on http://localhost:3001 or modify the REACT_APP_BASE_URL variable to match your backend URL.

Create and seed the PostgreSQL database with:

bash
Copy code
psql < jobly.sql
Start the backend:

bash
Copy code
node server.js
Environment Variables
The app uses the following environment variables, defined in a .env file at the root of your project:

plaintext
Copy code
REACT_APP_BASE_URL=http://localhost:3001
REACT_APP_BASE_URL: The base URL for the backend API. By default, it's http://localhost:3001.
Running the App
Start the Development Server:

bash
Copy code
npm start
Visit http://localhost:3000 in your browser. Make sure your backend is running on http://localhost:3001.

File Structure
plaintext
Copy code
jobly-frontend/
├── public/               # Static assets like index.html
├── src/
│   ├── api/              # API helper functions
│   ├── components/       # Reusable React components (NavBar, Form, etc.)
│   ├── hooks/            # Custom React hooks
│   ├── pages/            # Page components (HomePage, JobList, etc.)
│   ├── App.js            # Main app entry point
│   ├── index.js          # Entry point for rendering the app
│   ├── styles/           # Styling (CSS/Bootstrap)
│   └── utils/            # Helper utility functions
├── .env                  # Environment variables
├── package.json          # Project metadata and scripts
└── README.md             # This file
API
All API requests are handled using Axios in the JoblyApi class. The API helper class centralizes all requests to the backend, including:

getCompanies(): Fetch all companies.
getCompany(handle): Fetch details of a specific company.
getJobs(): Fetch all jobs.
applyToJob(id): Apply to a job by job ID.
login(): Log in a user.
signup(): Register a new user.
Deployment
This app is deployed using Render.

Backend Deployment (Render)
Ensure the backend is working locally.
Deploy the backend using Render's web service.
Add the following environment variables on Render:
DATABASE_URL: Your PostgreSQL connection string.
SECRET_KEY: A secret key for JWT tokens.
NODE_ENV: Set to production.
Frontend Deployment (Render)
Ensure the frontend is working locally.
Deploy the frontend using Render's static site hosting.
Add the following environment variables on Render:
REACT_APP_BASE_URL: The URL of your deployed backend.
NODE_ENV: Set to production.
