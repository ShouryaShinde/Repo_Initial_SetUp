# MERN Project Template

A reusable starter template for building MERN stack applications quickly.

## Project Structure

```text
My-MERN-Template/
├── client/          # React + Vite frontend
│
└── server/          # Node.js + Express backend
    ├── config/
    ├── controllers/
    ├── middleware/
    ├── models/
    ├── routes/
    ├── services/
    ├── utils/
    ├── app.js
    ├── server.js
    ├── .env
    └── .env.example
```

---

## Client Setup

From the project root, create the Vite React application:

```bash
npx create-vite@latest client
```

When prompted, select:

```text
Framework: React
Variant: JavaScript
```

Then install the dependencies:

```bash
cd client
npm install
```

Start the development server:

```bash
npm run dev
```

By default, Vite runs the client at:

```text
http://localhost:5173
```

---

## Server Setup

Navigate to the server directory:

```bash
cd server
```

Install the dependencies:

```bash
npm install
```

Create your environment file:

### Git Bash

```bash
touch .env
```

### Windows PowerShell

```powershell
New-Item .env
```

---

## Environment Variables

Add the following variables to your `.env` file:

```env
PORT=5000
CLIENT_URL=http://localhost:5173
```

### Variables

| Variable | Description | Example |
|---|---|---|
| `PORT` | Port on which the Express server runs | `5000` |
| `CLIENT_URL` | URL of the frontend application | `http://localhost:5173` |

> Replace the values with your actual configuration.

---

## Running the Server

From the `server` directory:

```bash
npm run dev
```

or, if your project uses Node directly:

```bash
npm start
```

The backend will run on:

```text
http://localhost:5000
```

---

## CORS Configuration

The server uses the `CLIENT_URL` environment variable to configure CORS.

Example:

```javascript
app.use(
    cors({
        origin: process.env.CLIENT_URL,
        credentials: true,
    })
);
```

This allows the Vite frontend to communicate with the Express backend.

---

## Quick Start

### 1. Clone the template

```bash
git clone <repository-url>
cd My-MERN-Template
```

### 2. Create the client

```bash
npx create-vite@latest client
```

Select:

```text
React
JavaScript
```

Then:

```bash
cd client
npm install
```

### 3. Configure the server

```bash
cd ../server
npm install
touch .env
```

Add:

```env
PORT=5000
CLIENT_URL=http://localhost:5173
```

### 4. Start the project

Run the frontend:

```bash
cd client
npm run dev
```

Run the backend in another terminal:

```bash
cd server
npm run dev
```

---

## Environment Security

Never commit your `.env` file to GitHub.

Make sure `.gitignore` contains:

```gitignore
node_modules/
.env
```

Use `.env.example` to document the required environment variables:

```env
PORT=5000
CLIENT_URL=http://localhost:5173
```

The `.env.example` file **can be committed** to the repository.

---

## Tech Stack

- **Frontend:** React + Vite
- **Backend:** Node.js + Express
- **Database:** MongoDB
- **Environment Variables:** dotenv
- **CORS:** cors
- **Package Manager:** npm

---

## Author

**Shourya Shinde**

This template is intended to speed up the initial setup of MERN stack projects and hackathon applications.
