# Chat-Scribe Chatlog Analyzer


A powerful AI-driven tool for analyzing and improving customer service chat interactions. Transform your customer service quality through advanced analytics and insights.

## Features

### Core Functionality
- **Chatlog Evaluation**: Upload or paste chatlogs for AI-powered analysis
- **Comprehensive Dashboard**: Interactive visualizations and analytics
- **CPR Analysis**: Detailed metrics for Coherence, Politeness, and Relevance
- **Resolution Tracking**: Monitor customer issue resolution rates
- **Customer Satisfaction**: Track and visualize satisfaction metrics
- **Export Capabilities**: Export analysis results in various formats

### Technical Features
- **Secure Authentication**: JWT-based user authentication
- **Database Integration**: PostgreSQL with Prisma ORM
- **Real-time Processing**: Instant feedback and analysis
- **Responsive Design**: Works seamlessly on all devices
- **Dark/Light Mode**: User-friendly theme switching

## Tech Stack

### Frontend
- React 18.2
- TypeScript
- Tailwind CSS
- shadcn/ui components
- Recharts for data visualization
- React Router for navigation
- React Query for data fetching

### Backend
- Node.js
- Express
- TypeScript
- Prisma ORM
- PostgreSQL Database
- JWT Authentication

## Prerequisites

- Node.js (v18 or higher)
- PostgreSQL
- npm or yarn package manager

## Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd chat-scribe-clarity-analyzer
```

2. **Recommended: Run the setup script** to resolve common setup issues:
```bash
# First, install only the setup dependencies
npm install --no-package-lock --ignore-scripts

# Then run the setup script
npm run setup
```

If you're on Linux/Mac and the script isn't executable:
```bash
chmod +x setup-project.js
node setup-project.js
```

This script automatically:
- Fixes React version compatibility issues
- Ensures correct version of react-wordcloud
- Creates and applies patches for React 18 compatibility
- Cleans npm cache and reinstalls dependencies with the correct flags

3. Alternatively, you can install dependencies manually:
```bash
# Install frontend dependencies
npm install --legacy-peer-deps

# Install backend dependencies
cd server
npm install
```

4. Set up environment variables:
Create a `.env` file in the server directory with the following variables:
```env
DATABASE_URL="postgresql://your_username:your_password@localhost:5432/chatscribe"
JWT_SECRET="your_jwt_secret"
CLIENT_URL="http://localhost:5173"
PORT=3000
```

5. Set up the database:
```bash
cd server
npm run prisma:generate
npm run prisma:migrate
```

## Troubleshooting Setup Issues

If you encounter any issues during setup, try the following solutions:

### Node Version Mismatch
This project requires Node.js v18 or higher. Check your Node.js version with:
```bash
node -v
```
Update Node.js if necessary from [nodejs.org](https://nodejs.org/).

### Package Installation Issues
If you encounter React or other library compatibility issues, try using the setup script:
```bash
npm run setup
```

Or manually fix issues:
```bash
npm cache clean --force
rm -rf node_modules
npm install --legacy-peer-deps
npx patch-package
```

### react-wordcloud Dependency Issues
The word cloud visualization requires specific peer dependencies:
```bash
# Fix react-wordcloud issues
npm install d3-cloud@1.2.5 d3-scale@3.3.0 --save
```

### TypeScript Type Issues
If encountering TypeScript errors, make sure you're using a compatible TypeScript version (5.x):
```bash
npm install typescript@5.5.3 --save-dev
```

## Development

1. Start the frontend development server:
```bash
npm run dev
```

2. Start the backend development server:
```bash
cd server
npm run dev
```

The application will be available at:
- Frontend: http://localhost:5173
- Backend: http://localhost:3000

## Building for Production

1. Build the frontend:
```bash
npm run build
```

2. Build the backend:
```bash
cd server
npm run build
```

## Project Structure

```
chat-scribe-clarity-analyzer/
├── src/                    # Frontend source code
│   ├── components/        # React components
│   ├── contexts/         # React contexts
│   ├── pages/           # Page components
│   ├── services/        # API services
│   └── utils/           # Utility functions
├── server/               # Backend source code
│   ├── prisma/          # Database schema and migrations
│   ├── src/             # Server source code
│   │   ├── routes/      # API routes
│   │   ├── middleware/  # Express middleware
│   │   └── utils/       # Utility functions
│   └── dist/            # Compiled backend code
└── public/              # Static assets
```

## API Documentation

### Authentication Endpoints
- `POST /api/auth/login` - User login
- `POST /api/auth/signup` - User registration
- `GET /api/auth/profile` - Get user profile

### Evaluation Endpoints
- `POST /api/evaluations` - Create new evaluation
- `GET /api/evaluations` - Get user evaluations
- `GET /api/evaluations/:id` - Get specific evaluation

### Dashboard Endpoints
- `GET /api/dashboard/stats` - Get dashboard statistics
- `GET /api/dashboard/metrics` - Get evaluation metrics

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Support

For support, please open an issue in the GitHub repository or contact the development team.

## Acknowledgments

- Thanks to all contributors who have helped shape this project
- Special thanks to the open-source community for the amazing tools and libraries
