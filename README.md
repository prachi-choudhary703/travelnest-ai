# ✈️ TravelNest AI — Full-Stack MERN Travel Platform

TravelNest AI is a full-stack AI-powered travel platform built with the MERN stack. It allows users to explore and filter tour packages, view tour details, book tours, manage wishlists, submit reviews, and use AI-powered trip planning and travel chat.

The application also includes an admin dashboard for managing tours, users, bookings, and platform statistics.

---

## 🚀 Features

### 👤 User Features

- 🔐 User registration and login
- 🔑 JWT-based authentication
- 👤 User profile management
- 🗺️ Browse available tours
- 🔎 Search and filter tours
- 📄 View detailed tour information and itinerary
- ❤️ Add or remove tours from wishlist
- 🎫 Book tours
- 📋 View personal booking history
- ❌ Cancel bookings
- ⭐ Submit and view tour reviews and ratings
- 🤖 AI-powered trip planner
- 💬 AI travel chat assistant
- 🌙 Dark mode
- 📱 Responsive user interface

### 🛠️ Admin Features

- 📊 Dashboard statistics for users, tours, bookings, and confirmed revenue
- 🗺️ Add new tours
- ✏️ Edit existing tours
- 🗑️ Delete tours
- 👥 View all users
- 🗑️ Delete users
- 📋 View all bookings
- 🔄 Update booking status

### 🤖 AI Features

TravelNest AI integrates the Groq API using the `openai/gpt-oss-20b` model.

#### AI Trip Planner

Users can enter:

- Destination
- Budget
- Number of days
- Interests and preferences

The AI can generate:

- Day-by-day itinerary
- Accommodation suggestions
- Must-visit places
- Local food recommendations
- Travel tips
- Approximate cost breakdown

#### AI Travel Chat

Users can ask the AI assistant about:

- Destinations
- Travel planning
- Budget planning
- Travel tips
- Local culture
- Best time to visit
- Visa information
- General travel questions

#### Quick Prompts

The AI planner includes ready-to-use prompts for:

- Manali
- Goa
- Bali
- Rajasthan

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Frontend | React.js, Vite |
| Styling | Tailwind CSS |
| Backend | Node.js, Express.js |
| Database | MongoDB, Mongoose |
| Authentication | JWT, bcryptjs |
| AI Integration | Groq SDK |
| AI Model | `openai/gpt-oss-20b` |
| State Management | Zustand |
| API Communication | Axios |
| Routing | React Router |
| Icons | React Icons |
| Notifications | React Hot Toast |
| Markdown Rendering | React Markdown |

---

## 📁 Project Structure

```text
travelnest-ai/
│
├── backend/
│   ├── middleware/
│   │   └── auth.js
│   │
│   ├── models/
│   │   ├── User.js
│   │   ├── Tour.js
│   │   ├── Booking.js
│   │   ├── Wishlist.js
│   │   └── Review.js
│   │
│   ├── routes/
│   │   ├── auth.js
│   │   ├── tours.js
│   │   ├── bookings.js
│   │   ├── wishlist.js
│   │   ├── admin.js
│   │   ├── reviews.js
│   │   └── ai.js
│   │
│   ├── server.js
│   ├── seed.js
│   └── package.json
│
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   │   ├── Navbar.jsx
│   │   │   ├── Footer.jsx
│   │   │   ├── Loader.jsx
│   │   │   ├── ProtectedRoute.jsx
│   │   │   └── TourCard.jsx
│   │   │
│   │   ├── pages/
│   │   │   ├── Home.jsx
│   │   │   ├── Login.jsx
│   │   │   ├── Signup.jsx
│   │   │   ├── Tours.jsx
│   │   │   ├── TourDetail.jsx
│   │   │   ├── Dashboard.jsx
│   │   │   ├── AdminDashboard.jsx
│   │   │   ├── AIPlanner.jsx
│   │   │   └── Wishlist.jsx
│   │   │
│   │   ├── store/
│   │   │   ├── authStore.js
│   │   │   ├── wishlistStore.js
│   │   │   └── themeStore.js
│   │   │
│   │   ├── utils/
│   │   │   └── api.js
│   │   │
│   │   ├── App.jsx
│   │   ├── main.jsx
│   │   └── index.css
│   │
│   ├── index.html
│   ├── vite.config.js
│   ├── tailwind.config.js
│   └── package.json
│
├── .env.example
├── .gitignore
└── README.md
```

> The real `backend/.env` file is intentionally excluded from GitHub because it contains sensitive credentials.

---

## ⚙️ Setup & Installation

### 1. Prerequisites

Install the following:

- Node.js v18+
- MongoDB (local installation or MongoDB Atlas)
- Git
- Groq API key

### 2. Clone the Repository

```bash
git clone https://github.com/prachi-choudhary703/travelnest-ai.git
cd travelnest-ai
```

### 3. Backend Setup

```bash
cd backend
npm install
```

Create a `.env` file inside the `backend` folder:

```env
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
GROQ_API_KEY=your_groq_api_key
```

### 4. Seed the Database

From the `backend` directory:

```bash
npm run seed
```

The seed script creates:

- 1 Admin user
- 5 Normal users
- 10 Tour packages
- 5 Sample bookings

> Running the seed script clears the existing User, Tour, and Booking collections before inserting the sample data.

### 5. Start the Backend

```bash
npm run dev
```

Backend:

```text
http://localhost:5000
```

Health check:

```text
http://localhost:5000/api/health
```

### 6. Frontend Setup

Open a new terminal:

```bash
cd frontend
npm install
npm run dev
```

Frontend:

```text
http://localhost:5173
```

---

## 🔑 Demo Credentials

These credentials are created by `seed.js`.

### Admin

```text
Email: admin@travelnest.com
Password: admin123
```

### User

```text
Email: priya@example.com
Password: password123
```

> These are development/demo credentials only. Do not use them in a production deployment.

---

## 📡 API Routes

### Authentication

| Method | Endpoint | Description |
|---|---|---|
| POST | `/api/auth/signup` | Register a new user |
| POST | `/api/auth/login` | Login |
| GET | `/api/auth/me` | Get current authenticated user |
| PUT | `/api/auth/profile` | Update user profile |

### Tours

| Method | Endpoint | Description |
|---|---|---|
| GET | `/api/tours` | List tours with filters |
| GET | `/api/tours/featured` | Get featured tours |
| GET | `/api/tours/:id` | Get tour details |
| POST | `/api/tours` | Create tour (Admin) |
| PUT | `/api/tours/:id` | Update tour (Admin) |
| DELETE | `/api/tours/:id` | Delete tour (Admin) |

### Bookings

| Method | Endpoint | Description |
|---|---|---|
| POST | `/api/bookings` | Create a booking |
| GET | `/api/bookings/my` | Get user's bookings |
| DELETE | `/api/bookings/:id` | Cancel a booking |

### Wishlist

| Method | Endpoint | Description |
|---|---|---|
| GET | `/api/wishlist` | Get user's wishlist |
| POST | `/api/wishlist/toggle` | Add/remove a tour from wishlist |

### Reviews

| Method | Endpoint | Description |
|---|---|---|
| GET | `/api/reviews/:tourId` | Get reviews for a tour |
| POST | `/api/reviews` | Add a review |

### Admin

| Method | Endpoint | Description |
|---|---|---|
| GET | `/api/admin/stats` | Get dashboard statistics |
| GET | `/api/admin/users` | Get all users |
| DELETE | `/api/admin/users/:id` | Delete a user |
| GET | `/api/admin/bookings` | Get all bookings |
| PUT | `/api/admin/bookings/:id` | Update booking status |

### AI

| Method | Endpoint | Description |
|---|---|---|
| POST | `/api/ai/travel` | Generate an AI travel itinerary |
| POST | `/api/ai/chat` | Chat with the AI travel assistant |

### Health

| Method | Endpoint | Description |
|---|---|---|
| GET | `/api/health` | Check backend server status |

---

## 🌱 Seed Data

The seed script creates development data including:

### Users

- 1 Admin user
- 5 Normal users

### Tours

10 sample tour packages covering Indian and international destinations, including:

- Delhi, Agra & Jaipur
- Kerala
- Manali
- Rajasthan
- Goa
- Bali
- Dubai
- Thailand
- Ladakh
- Switzerland

### Bookings

5 sample bookings are created with different users, tours, traveler counts, prices, and booking statuses.

---

## 🔐 Authentication & Security

The application uses:

- JWT-based authentication
- bcryptjs password hashing
- Protected API routes
- Admin-only route protection
- Environment variables for sensitive configuration
- CORS configuration for local frontend development

Sensitive values such as the following should never be committed to GitHub:

```text
MONGO_URI
JWT_SECRET
GROQ_API_KEY
```

The repository includes `.env.example` as a template without real credentials.

---

## 🎨 UI & User Experience

TravelNest AI includes:

- Modern travel-focused interface
- Glassmorphism-inspired UI
- Responsive layouts
- Dark mode
- Interactive tour cards
- Loading states
- Toast notifications
- Markdown-rendered AI responses
- Mobile-friendly navigation

---

## 💳 Payments

TravelNest AI currently supports the complete tour booking workflow but **does not include an integrated online payment gateway**.

Payment integration can be added as a future enhancement.

---

## 🔮 Future Improvements

Possible future improvements include:

- 💳 Online payment gateway integration
- 🗺️ Maps and location services
- 📧 Email booking confirmations
- 🧾 Downloadable booking invoices
- 🔔 Push notifications
- 🌐 Multi-language support
- 📱 Mobile application
- 📈 Advanced analytics
- ☁️ Production deployment
- 🖼️ Cloud image storage

---

## 👩‍💻 Author

**Prachi Choudhary**

Computer Science Engineering Student  
Interested in Full-Stack Development, AI Integration and Software Engineering.

GitHub:  
https://github.com/prachi-choudhary703

---

## 📄 License

This project is developed for educational and portfolio purposes.
