# Online Voting System - Angular Project

## 📋 Project Overview

A secure and user-friendly online voting system built with Angular, Node.js, Express, and MongoDB. This system provides a complete electoral platform with voter registration, authentication, voting mechanisms, and real-time results.

## 🚀 Features

### Core Features
- **Secure User Authentication** - JWT-based login system
- **Voter Registration** - New voter registration with validation
- **Ballot Management** - Dynamic ballot creation and management
- **Real-time Voting** - Live vote casting with instant updates
- **Results Dashboard** - Real-time election results and analytics
- **Admin Panel** - Election management and monitoring tools

### Security Features
- Password encryption using bcrypt
- JWT token-based authentication
- Input validation and sanitization
- Rate limiting for API calls
- Secure session management
- One-vote-per-user validation

### Additional Features
- Responsive design for mobile and desktop
- Email notifications for registration/voting
- Vote audit trail
- Multi-language support
- Accessibility compliance (WCAG 2.1)

## 🛠️ Technology Stack

### Frontend
- **Angular 16+** - Main framework
- **Angular Material** - UI components
- **TypeScript** - Programming language
- **RxJS** - Reactive programming
- **Chart.js** - Data visualization
- **Bootstrap 5** - Additional styling

### Backend
- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **MongoDB** - Database
- **Mongoose** - ODM for MongoDB
- **JWT** - Authentication tokens
- **bcrypt** - Password hashing

### DevOps & Tools
- **Angular CLI** - Development tools
- **Nodemon** - Development server
- **Jest** - Testing framework
- **ESLint** - Code linting
- **Prettier** - Code formatting

## 📁 Project Structure

```
online-voting-system/
├── frontend/                    # Angular application
│   ├── src/
│   │   ├── app/
│   │   │   ├── components/
│   │   │   │   ├── auth/
│   │   │   │   │   ├── login/
│   │   │   │   │   ├── register/
│   │   │   │   │   └── forgot-password/
│   │   │   │   ├── voting/
│   │   │   │   │   ├── ballot/
│   │   │   │   │   ├── candidate-list/
│   │   │   │   │   └── voting-booth/
│   │   │   │   ├── results/
│   │   │   │   │   ├── live-results/
│   │   │   │   │   └── analytics/
│   │   │   │   ├── admin/
│   │   │   │   │   ├── dashboard/
│   │   │   │   │   ├── user-management/
│   │   │   │   │   └── election-management/
│   │   │   │   └── shared/
│   │   │   │       ├── header/
│   │   │   │       ├── footer/
│   │   │   │       └── sidebar/
│   │   │   ├── services/
│   │   │   │   ├── auth.service.ts
│   │   │   │   ├── voting.service.ts
│   │   │   │   ├── user.service.ts
│   │   │   │   └── admin.service.ts
│   │   │   ├── guards/
│   │   │   │   ├── auth.guard.ts
│   │   │   │   └── admin.guard.ts
│   │   │   ├── models/
│   │   │   │   ├── user.model.ts
│   │   │   │   ├── candidate.model.ts
│   │   │   │   └── vote.model.ts
│   │   │   └── interceptors/
│   │   │       ├── auth.interceptor.ts
│   │   │       └── error.interceptor.ts
│   │   ├── assets/
│   │   ├── environments/
│   │   └── styles/
│   ├── angular.json
│   ├── package.json
│   └── tsconfig.json
├── backend/                     # Node.js API
│   ├── src/
│   │   ├── controllers/
│   │   │   ├── authController.js
│   │   │   ├── userController.js
│   │   │   ├── voteController.js
│   │   │   └── adminController.js
│   │   ├── models/
│   │   │   ├── User.js
│   │   │   ├── Candidate.js
│   │   │   ├── Vote.js
│   │   │   └── Election.js
│   │   ├── routes/
│   │   │   ├── auth.js
│   │   │   ├── users.js
│   │   │   ├── votes.js
│   │   │   └── admin.js
│   │   ├── middleware/
│   │   │   ├── auth.js
│   │   │   ├── validation.js
│   │   │   └── rateLimit.js
│   │   ├── config/
│   │   │   ├── database.js
│   │   │   └── config.js
│   │   └── utils/
│   │       ├── helpers.js
│   │       └── email.js
│   ├── package.json
│   └── server.js
├── database/                    # Database scripts
│   ├── migrations/
│   └── seeders/
├── docs/                       # Documentation
│   ├── API.md
│   ├── DEPLOYMENT.md
│   └── USER_GUIDE.md
├── tests/                      # Test files
│   ├── frontend/
│   └── backend/
├── docker-compose.yml
├── README.md
└── LICENSE
```

## 🔧 Installation & Setup

### Prerequisites
- Node.js (v16 or higher)
- npm or yarn
- MongoDB (v4.4 or higher)
- Angular CLI (`npm install -g @angular/cli`)

### 1. Clone the Repository
```bash
git clone https://github.com/yourusername/online-voting-system.git
cd online-voting-system
```

### 2. Backend Setup
```bash
# Navigate to backend directory
cd backend

# Install dependencies
npm install

# Create environment file
cp .env.example .env

# Configure environment variables
# Edit .env file with your configurations
```

### 3. Environment Configuration (.env)
```env
# Server Configuration
PORT=3000
NODE_ENV=development

# Database Configuration
MONGODB_URI=mongodb://localhost:27017/voting_system
DB_NAME=voting_system

# JWT Configuration
JWT_SECRET=your_super_secret_jwt_key_here
JWT_EXPIRE=24h

# Email Configuration
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=587
EMAIL_USER=your_email@gmail.com
EMAIL_PASS=your_app_password

# Security
BCRYPT_ROUNDS=12
RATE_LIMIT_WINDOW=15
RATE_LIMIT_MAX=100

# Frontend URL
FRONTEND_URL=http://localhost:4200
```

### 4. Database Setup
```bash
# Start MongoDB service
sudo systemctl start mongod

# Import seed data
npm run seed
```

### 5. Start Backend Server
```bash
# Development mode
npm run dev

# Production mode
npm start
```

### 6. Frontend Setup
```bash
# Navigate to frontend directory
cd ../frontend

# Install dependencies
npm install

# Configure environment
cp src/environments/environment.example.ts src/environments/environment.ts
```

### 7. Frontend Environment Configuration
```typescript
// src/environments/environment.ts
export const environment = {
  production: false,
  apiUrl: 'http://localhost:3000/api',
  appName: 'Online Voting System',
  version: '1.0.0'
};
```

### 8. Start Frontend Application
```bash
# Development server
ng serve

# Build for production
ng build --prod
```

## 🗃️ Database Schema

### Users Collection
```javascript
{
  _id: ObjectId,
  voterId: String (unique),
  email: String (unique),
  fullName: String,
  password: String (hashed),
  dateOfBirth: Date,
  address: {
    street: String,
    city: String,
    state: String,
    zipCode: String
  },
  isVerified: Boolean,
  hasVoted: Boolean,
  role: String (enum: 'voter', 'admin'),
  createdAt: Date,
  updatedAt: Date
}
```

### Candidates Collection
```javascript
{
  _id: ObjectId,
  name: String,
  party: String,
  position: String,
  biography: String,
  image: String,
  electionId: ObjectId,
  voteCount: Number,
  isActive: Boolean,
  createdAt: Date,
  updatedAt: Date
}
```

### Votes Collection
```javascript
{
  _id: ObjectId,
  voterId: ObjectId,
  candidateId: ObjectId,
  electionId: ObjectId,
  timestamp: Date,
  ipAddress: String,
  isValid: Boolean
}
```

### Elections Collection
```javascript
{
  _id: ObjectId,
  title: String,
  description: String,
  startDate: Date,
  endDate: Date,
  isActive: Boolean,
  totalVotes: Number,
  positions: [String],
  createdAt: Date,
  updatedAt: Date
}
```

## 🔐 API Endpoints

### Authentication Routes
```
POST   /api/auth/register       - User registration
POST   /api/auth/login          - User login
POST   /api/auth/logout         - User logout
POST   /api/auth/refresh        - Refresh JWT token
POST   /api/auth/forgot         - Forgot password
POST   /api/auth/reset          - Reset password
GET    /api/auth/verify/:token  - Verify email
```

### User Routes
```
GET    /api/users/profile       - Get user profile
PUT    /api/users/profile       - Update user profile
GET    /api/users/voting-status - Check voting status
```

### Voting Routes
```
GET    /api/votes/candidates    - Get all candidates
POST   /api/votes/cast          - Cast a vote
GET    /api/votes/results       - Get election results
GET    /api/votes/my-vote       - Get user's vote history
```

### Admin Routes
```
GET    /api/admin/dashboard     - Admin dashboard data
GET    /api/admin/users         - Get all users
PUT    /api/admin/users/:id     - Update user
DELETE /api/admin/users/:id     - Delete user
POST   /api/admin/candidates    - Create candidate
PUT    /api/admin/candidates/:id - Update candidate
DELETE /api/admin/candidates/:id - Delete candidate
GET    /api/admin/analytics     - Get voting analytics
```

## 🧪 Testing

### Running Tests
```bash
# Frontend tests
cd frontend
ng test

# Backend tests
cd backend
npm test

# End-to-end tests
npm run e2e

# Test coverage
npm run test:coverage
```

### Test Categories
- **Unit Tests** - Individual component/service testing
- **Integration Tests** - API endpoint testing
- **E2E Tests** - Full user journey testing
- **Security Tests** - Authentication and authorization testing

## 🚀 Deployment

### Using Docker
```bash
# Build and run with Docker Compose
docker-compose up -d

# Build production images
docker-compose -f docker-compose.prod.yml up -d
```

### Manual Deployment

#### Backend (Node.js)
```bash
# Install PM2 for process management
npm install -g pm2

# Build and start application
npm run build
pm2 start ecosystem.config.js
```

#### Frontend (Angular)
```bash
# Build for production
ng build --prod

# Deploy to web server (nginx example)
sudo cp -r dist/* /var/www/html/
```

### Environment-Specific Configurations

#### Development
- Debug mode enabled
- Hot reload active
- Detailed error messages
- Mock data available

#### Staging
- Production-like environment
- Limited debug information
- Performance monitoring
- Security testing

#### Production
- Optimized builds
- Error logging
- Performance optimization
- Security hardening

## 📊 Features Breakdown

### 1. User Authentication System
- **Registration Process**
  - Form validation
  - Email verification
  - Duplicate checking
  - Age verification (18+)

- **Login System**
  - JWT token generation
  - Remember me functionality
  - Failed attempt tracking
  - Account lockout protection

### 2. Voting Mechanism
- **Ballot Display**
  - Candidate information
  - Position-based voting
  - Clear vote indicators
  - Accessibility features

- **Vote Casting**
  - One-vote validation
  - Confirmation dialogs
  - Vote encryption
  - Audit trail creation

### 3. Results System
- **Real-time Updates**
  - Live vote counting
  - Percentage calculations
  - Winner determination
  - Statistical analysis

- **Data Visualization**
  - Charts and graphs
  - Demographic breakdown
  - Historical comparisons
  - Export capabilities

### 4. Admin Dashboard
- **User Management**
  - User registration approval
  - Account status management
  - Voter verification
  - Role assignment

- **Election Management**
  - Candidate registration
  - Election scheduling
  - System configuration
  - Security monitoring

## 🔒 Security Measures

### Data Protection
- **Encryption**: All sensitive data encrypted at rest and in transit
- **Password Security**: bcrypt hashing with salt
- **Input Validation**: Server-side validation for all inputs
- **SQL Injection Prevention**: Parameterized queries
- **XSS Protection**: Content Security Policy headers

### Authentication & Authorization
- **JWT Tokens**: Secure token-based authentication
- **Role-Based Access**: Different access levels for users/admins
- **Session Management**: Secure session handling
- **Rate Limiting**: Prevent brute force attacks

### Voting Security
- **One Vote Per User**: Database-level constraints
- **Vote Anonymity**: Separation of voter identity and vote choice
- **Audit Trail**: Complete voting activity logging
- **Tamper Detection**: Vote integrity verification

## 📈 Performance Optimization

### Frontend Optimization
- **Lazy Loading**: Route-based code splitting
- **Caching**: HTTP caching and service worker
- **Minification**: CSS/JS minification
- **Image Optimization**: Compressed images and lazy loading

### Backend Optimization
- **Database Indexing**: Optimized queries
- **Connection Pooling**: Efficient database connections
- **Caching Layer**: Redis for session and data caching
- **Load Balancing**: Multiple server instances

## 🐛 Troubleshooting

### Common Issues

#### Frontend Issues
```bash
# Clear npm cache
npm cache clean --force

# Reinstall node_modules
rm -rf node_modules package-lock.json
npm install

# Angular CLI issues
npm uninstall -g @angular/cli
npm install -g @angular/cli@latest
```

#### Backend Issues
```bash
# MongoDB connection issues
sudo systemctl status mongod
sudo systemctl restart mongod

# Port already in use
lsof -ti:3000 | xargs kill -9

# Environment variables not loading
source .env
```

#### Database Issues
```bash
# Reset database
mongo voting_system --eval "db.dropDatabase()"
npm run seed

# Check MongoDB logs
sudo tail -f /var/log/mongodb/mongod.log
```

## 📞 Support & Contact

### Getting Help
- **Documentation**: Check the `/docs` folder for detailed guides
- **Issues**: Report bugs on GitHub Issues
- **Discussions**: Join community discussions
- **Email**: support@votingsystem.com

### Contributing
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests for new features
5. Submit a pull request

## 📜 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Angular team for the excellent framework
- MongoDB team for the robust database
- Contributors and beta testers
- Open source community

## 📋 Changelog

### Version 1.0.0 (Current)
- Initial release
- Basic voting functionality
- User authentication
- Admin dashboard
- Real-time results

### Planned Features (v1.1.0)
- Multi-language support
- Mobile app
- Blockchain integration
- Advanced analytics
- SMS notifications

---

**Note**: This is a demonstration project. For production use, ensure proper security audits, legal compliance, and infrastructure setup according to your local electoral laws and regulations.
