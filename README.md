# PharmaCare - Online Pharmacy Management System

A full-stack web application for managing online pharmacy operations, including medicine inventory, orders, prescriptions, deliveries, and AI-powered chatbot support.

## 🌟 Features

- **User Management**: Registration, login, authentication with JWT
- **Medicine Catalog**: Browse medicines, view details, and check availability
- **Shopping Cart**: Add medicines to cart and proceed to checkout
- **Order Management**: Place orders, track status, and view history
- **Prescription Upload**: Upload and manage medical prescriptions
- **Payment Integration**: Razorpay payment gateway (test mode)
- **Delivery Management**: Assign and track deliveries
- **AI Chatbot**: Powered by Google Gemini and Groq for customer support
- **Rewards System**: Earn and redeem rewards
- **Admin Dashboard**: Manage medicines, users, and orders
- **SMS Notifications**: Twilio integration for order updates
- **Email Notifications**: SMTP configuration for alerts

## 🛠️ Tech Stack

### Backend
- **Framework**: Spring Boot 3.x
- **Language**: Java 17+
- **Database**: MySQL
- **Authentication**: JWT (JSON Web Tokens)
- **APIs**: RESTful APIs
- **Build Tool**: Maven

### Frontend
- **Framework**: React with Vite
- **Styling**: Tailwind CSS
- **State Management**: Context API
- **Build Tool**: Vite
- **Package Manager**: npm

### External Services
- **Database**: MySQL
- **Payment Gateway**: Razorpay
- **AI Integration**: Google Gemini, Groq
- **SMS Service**: Twilio
- **Email Service**: Gmail SMTP

## 📁 Project Structure

```
pharma/
├── backend/                          # Spring Boot application
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/com/pharma/backend/
│   │   │   │   ├── controllers/      # REST API endpoints
│   │   │   │   ├── services/         # Business logic
│   │   │   │   ├── repository/       # Data access layer
│   │   │   │   ├── entity/           # JPA entities
│   │   │   │   ├── security/         # JWT & Security config
│   │   │   │   ├── config/           # Spring configuration
│   │   │   │   └── payload/          # DTOs
│   │   │   └── resources/
│   │   │       ├── application.properties
│   │   │       ├── data/medicines.csv
│   │   │       └── static/uploads/
│   │   └── test/
│   └── pom.xml                       # Maven dependencies
│
├── frontend/                         # React application
│   ├── src/
│   │   ├── components/              # Reusable components
│   │   ├── pages/                   # Page components
│   │   ├── services/                # API calls
│   │   ├── context/                 # State management
│   │   └── App.jsx
│   ├── public/                      # Static assets
│   ├── package.json
│   ├── vite.config.js
│   └── tailwind.config.js
│
├── API_Endpoints_Postman.md         # API documentation
├── Project_Documentation.md         # Project details
├── SQL_Documentation.md             # Database schema
└── # PharmaCare - Setup & Run Guide.txt
```

## 🚀 Getting Started

### Prerequisites
- **Java 17 or higher**
- **Node.js 16+ and npm**
- **MySQL 8.0+**
- **Git**

### Backend Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/ram-tech2026/cyberton.git
   cd cyberton/backend
   ```

2. **Set environment variables**
   Create a `.env` file in the `backend/` directory:
   ```env
   DB_URL=jdbc:mysql://localhost:3306/pharma_db?createDatabaseIfNotExist=true&useSSL=false&allowPublicKeyRetrieval=true
   DB_USERNAME=root
   DB_PASSWORD=your_db_password
   
   TWILIO_ACCOUNT_SID=your_twilio_sid
   TWILIO_AUTH_TOKEN=your_twilio_token
   TWILIO_PHONE_NUMBER=+91_your_number
   
   MAIL_USERNAME=your_email@gmail.com
   MAIL_PASSWORD=your_app_password
   
   GOOGLE_GENAI_API_KEY=your_google_genai_key
   GROQ_API_KEY=your_groq_api_key
   ```

3. **Build and run**
   ```bash
   mvn clean install
   mvn spring-boot:run
   ```
   The backend will run on `http://localhost:8081`

### Frontend Setup

1. **Navigate to frontend directory**
   ```bash
   cd frontend
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Run development server**
   ```bash
   npm run dev
   ```
   The frontend will run on `http://localhost:5173`

### Database Setup

1. **Create database**
   ```sql
   CREATE DATABASE pharma_db;
   ```

2. **Import schema** (if available)
   - See `SQL_Documentation.md` for schema details
   - Spring Boot will auto-create tables with `spring.jpa.hibernate.ddl-auto=update`

## 📋 API Endpoints

All API endpoints are documented in `API_Endpoints_Postman.md`. Key endpoints include:

- **Authentication**: `/api/auth/login`, `/api/auth/register`
- **Medicines**: `/api/medicines` (GET, POST)
- **Orders**: `/api/orders` (GET, POST, PUT)
- **Prescriptions**: `/api/prescriptions` (GET, POST)
- **Payments**: `/api/payments` (POST, GET)
- **Chatbot**: `/api/chatbot/chat` (POST)
- **Delivery**: `/api/delivery` (GET, POST)
- **Admin**: `/api/admin/*` (Admin operations)

## 🔐 Environment Variables

### Required Variables

| Variable | Description | Example |
|----------|-------------|---------|
| `DB_URL` | MySQL connection string | `jdbc:mysql://localhost:3306/pharma_db` |
| `DB_USERNAME` | Database user | `root` |
| `DB_PASSWORD` | Database password | `password123` |
| `TWILIO_ACCOUNT_SID` | Twilio account ID | `AC...` |
| `TWILIO_AUTH_TOKEN` | Twilio auth token | `token...` |
| `TWILIO_PHONE_NUMBER` | Twilio phone number | `+919876543210` |
| `MAIL_USERNAME` | Gmail address | `your_email@gmail.com` |
| `MAIL_PASSWORD` | Gmail app password | `xxxx xxxx xxxx xxxx` |
| `GOOGLE_GENAI_API_KEY` | Google Gemini API key | `AIza...` |
| `GROQ_API_KEY` | Groq API key | `gsk_...` |

## 🧪 Testing

### Backend Tests
```bash
cd backend
mvn test
```

### Frontend Tests
```bash
cd frontend
npm run test
```

## 📦 Build & Deployment

### Backend Build
```bash
cd backend
mvn clean package
# JAR file: backend/target/backend-*.jar
```

### Frontend Build
```bash
cd frontend
npm run build
# Output: frontend/dist/
```

## 🔑 Key Features Explained

### JWT Authentication
- Token-based authentication for secure API access
- Tokens are issued on login and validated on protected routes

### Payment Integration
- Razorpay payment gateway integration
- Test mode enabled - use test card: 4111 1111 1111 1111

### AI Chatbot
- Powered by Google Gemini and Groq
- Provides 24/7 customer support
- Integrated into the frontend UI

### SMS & Email
- Order notifications via SMS (Twilio)
- Account alerts via Email (SMTP)
- OTP verification support

## 📚 Documentation

- **API_Endpoints_Postman.md** - Complete API reference
- **Project_Documentation.md** - Detailed project information
- **SQL_Documentation.md** - Database schema and relations
- **# PharmaCare - Setup & Run Guide.txt** - Quick start guide

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is private and maintained by the development team.

## 👥 Contributors

- **Rami Reddy Byredy** (ram-tech2026)

## 📞 Support

For issues and questions, please refer to the documentation files or contact the development team.

## 🎯 Future Enhancements

- [ ] Mobile app (React Native)
- [ ] Advanced analytics dashboard
- [ ] Prescription verification system
- [ ] Insurance integration
- [ ] Multi-language support
- [ ] Real-time inventory sync
- [ ] Advanced reporting

---

**Last Updated**: April 27, 2026
