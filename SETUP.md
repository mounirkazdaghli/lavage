# Getting Started Guide

## Prerequisites
- Node.js 16+ 
- MongoDB 4.4+
- npm or yarn

## Backend Setup

1. Navigate to backend directory:
```bash
cd backend
```

2. Install dependencies:
```bash
npm install
```

3. Create `.env` file (copy from `.env.example`):
```bash
cp .env.example .env
```

4. Start MongoDB (if not running as a service):
```bash
mongod
```

5. Start the backend server:
```bash
npm run dev
```

Server will run on `http://localhost:5000`

---

## Frontend Setup

1. Navigate to frontend directory:
```bash
cd frontend
```

2. Install dependencies:
```bash
npm install
```

3. Start the development server:
```bash
npm run dev
```

App will open at `http://localhost:3000`

---

## Testing the Application

### Admin Login
- Email: `admin@example.com`
- Password: `admin123`
- Role: `Admin`

### User Login
- Email: `user@example.com`
- Password: `user123`
- Role: `User`

**Note:** For demo purposes, any email/password combination will work.

---

## Features Available

### Admin Dashboard
- ✅ View all customer reservations
- ✅ Manage staff schedules and availability
- ✅ Track daily capacity
- ✅ Manage personal operations and maintenance tasks

### User Dashboard
- ✅ Book car wash services
- ✅ View personal reservations
- ✅ Cancel reservations
- ✅ View booking history and statistics

---

## Project Structure

```
lavage/
├── backend/
│   ├── src/
│   │   ├── models/
│   │   │   ├── User.ts
│   │   │   └── Reservation.ts
│   │   ├── routes/
│   │   │   ├── auth.ts
│   │   │   ├── reservations.ts
│   │   │   └── planning.ts
│   │   └── server.ts
│   ├── package.json
│   └── .env.example
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   │   └── Navbar.tsx
│   │   ├── pages/
│   │   │   ├── LoginPage.tsx
│   │   │   ├── AdminDashboard.tsx
│   │   │   └── UserDashboard.tsx
│   │   ├── App.tsx
│   │   ├── main.tsx
│   │   └── index.css
│   ├── index.html
│   ├── package.json
│   ├── vite.config.ts
│   └── tailwind.config.ts
└── docs/
    └── API.md
```

---

## API Endpoints Summary

- **Auth:** POST `/api/auth/login`
- **Reservations:** GET, POST, PATCH, DELETE `/api/reservations`
- **Planning:** GET `/api/planning/staff`, `/api/planning/slots/:date`, `/api/planning/capacity/:date`

See `docs/API.md` for detailed documentation.

---

## Troubleshooting

### MongoDB Connection Error
- Ensure MongoDB is running: `mongod`
- Check connection string in `.env` file

### Port Already in Use
- Backend: Change PORT in `.env`
- Frontend: Run `npm run dev -- --port 3001`

### CORS Errors
- Frontend and backend URLs should match proxy configuration
- Check `vite.config.ts` for correct backend URL

---

## Next Steps

1. Set up MongoDB Atlas for production
2. Add email notifications for reservations
3. Implement payment processing
4. Add review/rating system
5. Create mobile app version
6. Deploy to Vercel/Heroku
