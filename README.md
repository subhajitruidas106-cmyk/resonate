# Resonate

A music streaming web app, built from scratch. Work in progress.

**Status:** Backend (basic version) done. Frontend and music recommendation system coming soon.

## Tech Stack

- Node.js, Express
- MongoDB with Mongoose
- JWT authentication (cookies) with bcryptjs
- Multer for file uploads
- ImageKit for storing music files

## Project Structure

```
resonate/
└── backend/
    ├── server.js
    └── src/
        ├── app.js
        ├── controllers/
        ├── db/
        ├── middlewares/
        ├── models/
        ├── routes/
        └── services/
```

## API Endpoints

**Auth** (`/api/auth`)

- `POST /register` - create an account
- `POST /login` - log in
- `POST /logout` - log out

**Music** (`/api/music`)

- `POST /upload` - upload a track (artist only)
- `POST /album` - create an album (artist only)
- `GET /` - get all tracks (logged-in user)
- `GET /albums` - get all albums (logged-in user)
- `GET /albums/:albumId` - get a single album (logged-in user)

## Planned: Music Recommendation System

I am building a music recommendation system that will be integrated into Resonate, so users get song suggestions based on what they listen to and like.

- Recommends tracks to a user from their listening and liking activity
- Will connect to the existing backend through its own API endpoints
- Approach and model details will be added here once development starts

**Status:** Planned, not started yet.

## Run Locally

1. Clone the repo and go to the backend folder:

   ```
   git clone https://github.com/<your-username>/resonate.git
   cd resonate/backend
   ```

2. Install dependencies:

   ```
   npm install
   ```

3. Create a `.env` file from the example and fill in your values:

   ```
   copy .env.example .env
   ```

   (On Mac/Linux use `cp .env.example .env`.)

   | Variable | Description |
   | --- | --- |
   | `MONGO_URI` | MongoDB connection string |
   | `JWT_SECRET` | Any long random string used to sign tokens |
   | `IMAGEKIT_PRIVATE_KEY` | Private key from your ImageKit dashboard |

4. Start the server:

   ```
   npm run dev
   ```

   The server runs on `http://localhost:3000`.

## Roadmap

- [x] User auth (register, login, logout)
- [x] Music upload and albums
- [ ] Frontend
- [ ] Music recommendation system
- [ ] Playlists
- [ ] Search
