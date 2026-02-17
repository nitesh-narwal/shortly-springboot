<p align="center">
  <img src="url-shortner-frontend/public/images/img2.png" alt="SnapLink Logo" width="200"/>
</p>

<h1 align="center">🔗 SnapLink - Smart URL Shortener</h1>

<p align="center">
  <strong>A powerful, feature-rich URL shortening service built with Spring Boot & React</strong>
</p>

<p align="center">
  <a href="#features">Features</a> •
  <a href="#tech-stack">Tech Stack</a> •
  <a href="#installation">Installation</a> •
  <a href="#api-documentation">API Docs</a> •
  <a href="#screenshots">Screenshots</a> •
  <a href="#contributing">Contributing</a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Spring%20Boot-4.0.0-brightgreen?style=for-the-badge&logo=spring" alt="Spring Boot"/>
  <img src="https://img.shields.io/badge/React-19.2.0-blue?style=for-the-badge&logo=react" alt="React"/>
  <img src="https://img.shields.io/badge/PostgreSQL-Latest-blue?style=for-the-badge&logo=postgresql" alt="PostgreSQL"/>
  <img src="https://img.shields.io/badge/JWT-Secured-orange?style=for-the-badge&logo=jsonwebtokens" alt="JWT"/>
  <img src="https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge" alt="License"/>
</p>

---

## ✨ Overview

**SnapLink** is a modern, full-stack URL shortening application that transforms long URLs into compact, shareable links. Built with enterprise-grade technologies, it offers advanced features like one-time URLs, expiring links, device tracking, and comprehensive analytics.

Perfect for marketers, developers, and businesses who need reliable link management with detailed insights.

---

## 🚀 Features

### Core Features
| Feature | Description |
|---------|-------------|
| 🔗 **URL Shortening** | Convert long URLs into short, memorable links |
| 📊 **Advanced Analytics** | Track clicks, dates, and access patterns with interactive graphs |
| ⏰ **Time-Based URLs** | Create links that expire after a custom duration |
| 🔐 **One-Time URLs** | Generate single-use links for sensitive content |
| 📱 **Device Fingerprinting** | Track unique device access per URL |
| 🗑️ **Auto Cleanup** | URLs older than 3 months are automatically deleted |

### User Management
| Feature | Description |
|---------|-------------|
| 👤 **User Authentication** | Secure JWT-based login & registration |
| ⚙️ **Account Settings** | Manage profile and preferences |
| 🛡️ **5-Day Grace Period** | Safe account deletion with recovery option |
| 🚪 **Instant Logout** | Secure session management |

### Dashboard Features
| Feature | Description |
|---------|-------------|
| 📋 **URL Management** | View, copy, and delete your shortened URLs |
| 📈 **Click Graphs** | Visual representation of link performance |
| 🏷️ **Status Badges** | Visual indicators for one-time, expired, and active URLs |
| ⌨️ **Keyboard Shortcuts** | Power user features (Ctrl+K for quick actions) |

---

## 🛠️ Tech Stack

### Backend
```
├── Java 22
├── Spring Boot 4.0.0
├── Spring Security + JWT Authentication
├── Spring Data JPA
├── PostgreSQL (Neon.tech compatible)
├── Lombok
├── Maven
└── JJWT 0.13.0
```

### Frontend
```
├── React 19.2.0
├── Vite 7.x (Build Tool)
├── Tailwind CSS 3.x
├── Material-UI 7.x
├── React Router 7.x
├── Axios
├── Chart.js + react-chartjs-2
├── React Hook Form
├── Framer Motion (Animations)
├── React Hot Toast (Notifications)
└── Day.js (Date handling)
```

---

## 📁 Project Structure

```
url-shortner-sb/
├── 📂 src/main/java/com/url/shortner/
│   ├── 📂 controller/
│   │   ├── AuthController.java          # Authentication endpoints
│   │   ├── UrlMappingController.java    # URL management endpoints
│   │   └── RedirectController.java      # Short URL redirect handler
│   ├── 📂 dtos/
│   │   ├── CreateUrlRequest.java        # URL creation with options
│   │   ├── UrlMappingDTO.java          # URL response object
│   │   ├── UserDTO.java                # User profile data
│   │   └── ClickEventDTO.java          # Analytics data
│   ├── 📂 models/
│   │   ├── User.java                   # User entity with soft delete
│   │   ├── UrlMapping.java             # URL entity with advanced features
│   │   ├── ClickEvent.java             # Click tracking entity
│   │   └── DeviceAccess.java           # Device fingerprint tracking
│   ├── 📂 repository/
│   │   ├── UserRepository.java
│   │   ├── UrlMappingRepository.java
│   │   ├── ClickEventRepository.java
│   │   └── DeviceAccessRepository.java
│   ├── 📂 security/
│   │   ├── WebSecurityConfig.java      # Security configuration
│   │   └── jwt/
│   │       ├── JwtAuthenticationFilter.java
│   │       ├── JwtUtils.java
│   │       └── JwtAuthenticationResponse.java
│   └── 📂 service/
│       ├── UserService.java            # User business logic
│       ├── UrlMappingService.java      # URL business logic
│       ├── UrlCleanupScheduler.java    # Scheduled cleanup tasks
│       ├── UserDetailsImpl.java
│       └── UserDetailsServiceImpl.java
│
├── 📂 url-shortner-frontend/src/
│   ├── 📂 api/
│   │   └── api.js                      # Axios configuration
│   ├── 📂 components/
│   │   ├── NavBar.jsx                  # Navigation with user menu
│   │   ├── LandingPage.jsx             # Animated landing page
│   │   ├── LoginPage.jsx               # User login
│   │   ├── RegisterPage.jsx            # User registration
│   │   ├── SettingsPage.jsx            # Account management
│   │   └── 📂 Dashboard/
│   │       ├── DashboardLayout.jsx     # Dashboard container
│   │       ├── CreateNewShorten.jsx    # URL creation form
│   │       ├── ShortenUrlList.jsx      # URL listing
│   │       ├── ShortenItem.jsx         # Individual URL card
│   │       └── Graph.jsx               # Analytics charts
│   ├── 📂 contextApi/
│   │   └── ContextApi.jsx              # Global state management
│   └── 📂 utils/
│       ├── constant.js
│       └── helper.js
│
└── 📂 src/main/resources/
    ├── application.properties          # App configuration
    └── db_migration.sql                # Database migrations
```

---

## ⚙️ Installation

### Prerequisites
- **Java 22+** (JDK)
- **Node.js 18+** & npm
- **PostgreSQL** database (local or cloud like [Neon.tech](https://neon.tech))
- **Maven** (or use the included wrapper)

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/yourusername/url-shortner-sb.git
cd url-shortner-sb
```

### 2️⃣ Database Setup

#### Option A: Local PostgreSQL
```bash
# Create database
createdb urlshortner

# Run migrations
psql -d urlshortner -f src/main/resources/db_migration.sql
```

#### Option B: Neon.tech (Cloud)
1. Create a project at [neon.tech](https://neon.tech)
2. Run the SQL from `db_migration.sql` in the SQL editor
3. Copy your connection string

### 3️⃣ Backend Configuration

Create environment variables or update `application.properties`:

```properties
# Database Configuration
DATABASE_URL=jdbc:postgresql://your-host/your-database
DATABASE_USERNAME=your-username
DATABASE_PASSWORD=your-password
DATABASE_DIALECT=org.hibernate.dialect.PostgreSQLDialect

# JWT Configuration
JWT_TOKEN=your-super-secret-jwt-key-at-least-256-bits

# Frontend URL (for CORS)
FRONTEND_URL=http://localhost:5173
```

### 4️⃣ Start Backend
```bash
# Using Maven Wrapper
./mvnw spring-boot:run

# Or using Maven
mvn spring-boot:run
```
Backend runs on: `http://localhost:8089`

### 5️⃣ Frontend Configuration

Create `url-shortner-frontend/.env`:
```env
VITE_BACKEND_URL=http://localhost:8089
VITE_REACT_FRONT_END_URL=http://localhost:5173
VITE_REACT_SUBDOMAIN=http://localhost:8089
```

### 6️⃣ Start Frontend
```bash
cd url-shortner-frontend
npm install
npm run dev
```
Frontend runs on: `http://localhost:5173`

---

## 📖 API Documentation

### Authentication Endpoints

#### Register User
```http
POST /api/auth/public/register
Content-Type: application/json

{
  "username": "johndoe",
  "email": "john@example.com",
  "password": "securepassword123"
}
```

#### Login
```http
POST /api/auth/public/login
Content-Type: application/json

{
  "username": "johndoe",
  "password": "securepassword123"
}

Response:
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
  "username": "johndoe",
  "email": "john@example.com"
}
```

### URL Management Endpoints

#### Create Short URL
```http
POST /api/urls/shorten
Authorization: Bearer <token>
Content-Type: application/json

{
  "originalUrl": "https://example.com/very/long/url",
  "isOneTimeUrl": false,
  "expiresInHours": 24
}

Response:
{
  "id": 1,
  "originalUrl": "https://example.com/very/long/url",
  "shortUrl": "abc123XY",
  "clickCount": 0,
  "createdDate": "2026-01-10T10:30:00",
  "isOneTimeUrl": false,
  "isUsed": false,
  "expiresAt": "2026-01-11T10:30:00",
  "isActive": true
}
```

#### Get User's URLs
```http
GET /api/urls/myurls
Authorization: Bearer <token>
```

#### Delete URL
```http
DELETE /api/urls/{id}
Authorization: Bearer <token>
```

#### Get URL Analytics
```http
GET /api/urls/analytics/{shortUrl}?startDate=2026-01-01T00:00:00&endDate=2026-12-31T23:59:59
Authorization: Bearer <token>
```

### Account Management

#### Schedule Account Deletion (5-day grace period)
```http
POST /api/auth/account/schedule-deletion
Authorization: Bearer <token>
```

#### Cancel Deletion
```http
POST /api/auth/account/cancel-deletion
Authorization: Bearer <token>
```

#### Immediate Delete
```http
DELETE /api/auth/account
Authorization: Bearer <token>
```

### Redirect
```http
GET /{shortUrl}

# Example: GET /abc123XY
# Redirects to original URL (302)
```

---

## 🗄️ Database Schema

### Users Table
```sql
CREATE TABLE users (
    id BIGSERIAL PRIMARY KEY,
    username VARCHAR(255) UNIQUE NOT NULL,
    email VARCHAR(255) UNIQUE NOT NULL,
    password VARCHAR(255) NOT NULL,
    role VARCHAR(50) DEFAULT 'ROLE_USER',
    is_deleted BOOLEAN DEFAULT false,
    deletion_scheduled_at TIMESTAMP,
    deletion_date TIMESTAMP
);
```

### URL Mapping Table
```sql
CREATE TABLE url_mapping (
    id BIGSERIAL PRIMARY KEY,
    original_url TEXT NOT NULL,
    short_url VARCHAR(20) UNIQUE NOT NULL,
    click_count INTEGER DEFAULT 0,
    created_date TIMESTAMP,
    is_one_time_url BOOLEAN DEFAULT false,
    is_used BOOLEAN DEFAULT false,
    expires_at TIMESTAMP,
    is_active BOOLEAN DEFAULT true,
    user_id BIGINT REFERENCES users(id)
);
```

### Click Events Table
```sql
CREATE TABLE click_event (
    id BIGSERIAL PRIMARY KEY,
    click_date TIMESTAMP,
    url_mapping_id BIGINT REFERENCES url_mapping(id) ON DELETE CASCADE
);
```

### Device Access Table
```sql
CREATE TABLE device_access (
    id BIGSERIAL PRIMARY KEY,
    device_fingerprint VARCHAR(255),
    accessed_at TIMESTAMP,
    url_mapping_id BIGINT REFERENCES url_mapping(id) ON DELETE CASCADE
);
```

---

## 🔧 Scheduled Tasks

The application includes automated cleanup tasks:

| Task | Schedule | Description |
|------|----------|-------------|
| **Expired URL Cleanup** | Hourly | Deactivates URLs past their expiration time |
| **Old URL Cleanup** | Daily (midnight) | Deletes URLs older than 3 months |
| **User Deletion Cleanup** | Hourly | Permanently removes users after 5-day grace period |

---

## 🎨 UI Features

### Landing Page
- Modern animated design with Framer Motion
- Interactive stats display
- Feature showcase with icons
- Responsive layout

### Dashboard
- Clean URL management interface
- Status badges for URL types
- Copy-to-clipboard functionality
- Interactive analytics graphs
- Delete confirmation modals

### Navigation
- Smart user menu dropdown
- Keyboard shortcuts (Ctrl+K)
- Scroll-aware navbar styling
- Mobile responsive hamburger menu

### Settings
- Profile overview
- Account deletion with 5-day recovery
- Immediate delete option with confirmation

---

## 🔒 Security Features

- **JWT Authentication** - Secure token-based auth
- **BCrypt Password Hashing** - Industry-standard password encryption
- **CORS Configuration** - Secure cross-origin requests
- **Device Fingerprinting** - SHA-256 hashed IP + User-Agent
- **Soft Delete** - Recoverable account deletion
- **Protected Routes** - Role-based access control

---

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📝 Environment Variables

### Backend
| Variable | Description | Example |
|----------|-------------|---------|
| `DATABASE_URL` | PostgreSQL connection URL | `jdbc:postgresql://localhost:5432/urlshortner` |
| `DATABASE_USERNAME` | Database username | `postgres` |
| `DATABASE_PASSWORD` | Database password | `password` |
| `DATABASE_DIALECT` | Hibernate dialect | `org.hibernate.dialect.PostgreSQLDialect` |
| `JWT_TOKEN` | Secret key for JWT | `your-256-bit-secret` |
| `FRONTEND_URL` | Frontend URL for CORS | `http://localhost:5173` |

### Frontend
| Variable | Description | Example |
|----------|-------------|---------|
| `VITE_BACKEND_URL` | Backend API URL | `http://localhost:8089` |
| `VITE_REACT_FRONT_END_URL` | Frontend base URL | `http://localhost:5173` |
| `VITE_REACT_SUBDOMAIN` | Short URL redirect base | `http://localhost:8089` |

---

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 👨‍💻 Author

**Nitesh Narwal**

- GitHub: [@nitesh-narwal](https://github.com/nitesh-narwal)

---

## 🙏 Acknowledgments

- [Spring Boot](https://spring.io/projects/spring-boot) - Backend framework
- [React](https://reactjs.org/) - Frontend library
- [Tailwind CSS](https://tailwindcss.com/) - Styling
- [Neon.tech](https://neon.tech/) - Serverless PostgreSQL

---

<p align="center">
  <strong>⭐ Star this repo if you find it helpful! ⭐</strong>
</p>

<p align="center">
  Made with ❤️ and ☕
</p>
