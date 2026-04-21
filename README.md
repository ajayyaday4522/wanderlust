# 🧭 WanderLust

> A full-stack Airbnb-inspired travel listing web application built with Node.js, Express.js, MongoDB & EJS.

![Node.js](https://img.shields.io/badge/Node.js-v22.18.0-green) ![Express](https://img.shields.io/badge/Express.js-4.x-blue) ![MongoDB](https://img.shields.io/badge/MongoDB-Atlas-brightgreen) ![Bootstrap](https://img.shields.io/badge/Bootstrap-5.3-purple) ![License](https://img.shields.io/badge/License-ISC-yellow)

---

## 🌐 Live Demo

🔗 [https://wanderlust-427v.onrender.com/listings](https://wanderlust-427v.onrender.com/listings)

> **Note:** Free Render tier may take ~50 seconds to spin up on first visit.

---

## 📌 Features

- 🔐 **User Authentication** — Signup, Login, Logout using Passport.js (Local Strategy)
- 🏠 **Listings CRUD** — Create, Read, Update, Delete travel listings with image upload
- 🗺️ **Interactive Map** — Mapbox GL JS with real-time geocoding on every listing page
- ⭐ **Review System** — Star ratings (1–5) + written comments with author-only delete
- 🔍 **Search & Filter** — Location-based search + 10 category filters
- 🖼️ **Cloud Image Upload** — Cloudinary + Multer for persistent image storage
- 📱 **Responsive Design** — Bootstrap 5 grid, mobile & desktop friendly
- 🔒 **Authorization** — Owner-only edit/delete for listings and reviews
- ✅ **Validation** — Joi server-side + Bootstrap client-side form validation
- 💾 **Session Persistence** — Sessions stored in MongoDB via connect-mongo

---

## 🗂️ Project Structure

```
MAJORPROJECT/
├── controllers/
│   ├── listings.js       # Listing CRUD logic
│   ├── reviews.js        # Review logic
│   └── users.js          # Auth logic
├── models/
│   ├── listing.js        # Listing Mongoose schema
│   ├── review.js         # Review Mongoose schema
│   └── user.js           # User schema (passport-local-mongoose)
├── routes/
│   ├── listing.js        # Listing routes
│   ├── review.js         # Review routes
│   └── user.js           # Auth routes
├── views/
│   ├── layouts/
│   │   └── boilerplate.ejs
│   ├── includes/
│   │   ├── navbar.ejs
│   │   ├── flash.ejs
│   │   └── footer.ejs
│   ├── listings/
│   │   ├── index.ejs
│   │   ├── show.ejs
│   │   ├── new.ejs
│   │   └── edit.ejs
│   └── users/
│       ├── login.ejs
│       └── signup.ejs
├── public/
│   ├── css/style.css
│   ├── js/script.js
│   ├── js/map.js
│   └── images/
├── utils/
│   ├── ExpressError.js   # Custom error class
│   └── wrapAsync.js      # Async error wrapper
├── init/
│   └── index.js          # DB seeder
├── app.js                # Main entry point
├── cloudConfig.js        # Cloudinary + Multer config
├── middleware.js         # Custom middleware
├── schema.js             # Joi validation schemas
├── .env                  # Environment variables (not committed)
├── .gitignore
└── package.json
```

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **Runtime** | Node.js v22.18.0 |
| **Backend** | Express.js 4.x |
| **Frontend** | EJS, Bootstrap 5.3, HTML5, CSS3 |
| **Database** | MongoDB Atlas + Mongoose 9 |
| **Authentication** | Passport.js + passport-local-mongoose |
| **Image Storage** | Cloudinary v1 + Multer v2 |
| **Maps** | Mapbox GL JS v3 + @mapbox/mapbox-sdk |
| **Validation** | Joi 18 |
| **Sessions** | express-session + connect-mongo v6 |
| **Deployment** | Render.com |

---

## ⚙️ Local Setup

### Prerequisites
- Node.js v18+
- MongoDB (local or Atlas)
- Cloudinary account
- Mapbox account

### 1. Clone the repository

```bash
git clone https://github.com/ajayyaday4522/wanderlust.git
cd wanderlust
```

### 2. Install dependencies

```bash
npm install
```

### 3. Create `.env` file

```env
ATLASDB_URL=mongodb://127.0.0.1:27017/wanderlust
CLOUD_NAME=your_cloudinary_cloud_name
CLOUD_API_KEY=your_cloudinary_api_key
CLOUD_API_SECRET=your_cloudinary_api_secret
MAP_TOKEN=your_mapbox_token
SECRET=your_session_secret
```

### 4. Seed the database (optional)

```bash
node init/index.js
```

### 5. Run the server

```bash
nodemon app.js
```

### 6. Open in browser

```
http://localhost:8080/listings
```

---

## 🔗 RESTful API Routes

### Listings

| Method | Route | Description | Access |
|---|---|---|---|
| GET | `/listings` | All listings (search + filter) | Public |
| GET | `/listings/new` | New listing form | Auth |
| POST | `/listings` | Create listing | Auth |
| GET | `/listings/:id` | Listing detail + map | Public |
| GET | `/listings/:id/edit` | Edit form | Auth + Owner |
| PUT | `/listings/:id` | Update listing | Auth + Owner |
| DELETE | `/listings/:id` | Delete listing | Auth + Owner |

### Reviews

| Method | Route | Description | Access |
|---|---|---|---|
| POST | `/listings/:id/reviews` | Add review | Auth |
| DELETE | `/listings/:id/reviews/:reviewId` | Delete review | Auth + Author |

### Users

| Method | Route | Description |
|---|---|---|
| GET/POST | `/signup` | Register |
| GET/POST | `/login` | Login |
| GET | `/logout` | Logout |

---

## 🌍 Environment Variables

| Variable | Description |
|---|---|
| `ATLASDB_URL` | MongoDB connection string |
| `CLOUD_NAME` | Cloudinary cloud name |
| `CLOUD_API_KEY` | Cloudinary API key |
| `CLOUD_API_SECRET` | Cloudinary API secret |
| `MAP_TOKEN` | Mapbox access token |
| `SECRET` | Session secret key |

---

## 🚀 Deployment (Render.com)

1. Push code to GitHub
2. Create new **Web Service** on [render.com](https://render.com)
3. Connect GitHub repo
4. Set **Build Command**: `npm install`
5. Set **Start Command**: `node app.js`
6. Add all environment variables in **Environment** tab
7. Add Render outbound IPs to MongoDB Atlas **Network Access**

---

## 📸 Categories

Listings can be filtered by:
`Trending` · `Rooms` · `Iconic Cities` · `Mountains` · `Castles` · `Amazing Pools` · `Camping` · `Farms` · `Domes` · `Boats`

---

## 👤 Author

**Ajay Yadav**
- GitHub: [@ajayyaday4522](https://github.com/ajayyaday4522)

---

## 📄 License

This project is licensed under the **ISC License**.

---

## 🙏 Acknowledgements

- [Airbnb](https://airbnb.com) — Inspiration
- [Unsplash](https://unsplash.com) — Sample images
- [Mapbox](https://mapbox.com) — Maps
- [Cloudinary](https://cloudinary.com) — Image hosting
- University of Engineering & Management, Jaipur
