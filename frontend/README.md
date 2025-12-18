# EnergyAI - Smart Energy Bill Predictor Frontend

A modern React-based frontend for the Smart City Energy Consumption Prediction System. This application provides an intuitive interface for users to predict their energy bills using AI/ML, manage their homes, and track consumption history.

## 🚀 Features

- **AI-Powered Predictions**: Get accurate energy bill predictions using machine learning
- **Home Management**: Add and manage multiple properties with detailed information
- **Interactive Dashboard**: Visualize your energy consumption with beautiful charts
- **History Tracking**: View past consumption, bills, and predictions
- **Responsive Design**: Works seamlessly on desktop, tablet, and mobile devices
- **Secure Authentication**: User registration and login with Supabase Auth
- **Real-time Updates**: Live data synchronization with PostgreSQL database

## 🛠️ Tech Stack

- **React 18** - Modern UI library
- **Vite** - Lightning-fast build tool
- **React Router** - Client-side routing
- **Tailwind CSS** - Utility-first CSS framework
- **Supabase** - Backend as a Service (PostgreSQL + Auth)
- **Recharts** - Data visualization
- **Lucide React** - Beautiful icons
- **Axios** - HTTP client for API calls

## 📋 Prerequisites

Before you begin, ensure you have the following installed:
- **Node.js** (v18 or higher)
- **npm** or **yarn**
- A **Supabase** account and project
- The **Flask backend** running (from BackEnd/app.py)

## 🔧 Installation

### 1. Clone the repository and navigate to the frontend directory

```bash
cd energy-frontend
```

### 2. Install dependencies

```bash
npm install
```

### 3. Set up environment variables

Create a `.env` file in the root directory:

```bash
cp .env.example .env
```

Edit `.env` and add your credentials:

```env
VITE_SUPABASE_URL=https://your-project.supabase.co
VITE_SUPABASE_ANON_KEY=your-anon-key-here
VITE_API_URL=http://localhost:5001
```

**To get your Supabase credentials:**
1. Go to [supabase.com](https://supabase.com)
2. Create a new project or select existing one
3. Go to Settings > API
4. Copy the Project URL and anon public key

### 4. Set up the database

Make sure you've executed the SQL schema from `Database` file in your Supabase SQL editor.

### 5. Start the Flask backend

In a separate terminal, start the Flask ML API:

```bash
cd BackEnd
python app.py
```

The backend should be running on `http://localhost:5001`

### 6. Start the development server

```bash
npm run dev
```

The application will open at `http://localhost:3000`

## 📁 Project Structure

```
energy-frontend/
├── src/
│   ├── components/
│   │   ├── Layout.jsx           # Main layout with navigation
│   │   └── ProtectedRoute.jsx   # Authentication guard
│   ├── pages/
│   │   ├── Landing.jsx          # Homepage
│   │   ├── Login.jsx            # Login page
│   │   ├── Register.jsx         # Registration page
│   │   ├── Dashboard.jsx        # Main dashboard
│   │   ├── Predictor.jsx        # ML prediction interface
│   │   ├── Homes.jsx            # Home management
│   │   └── History.jsx          # Consumption history
│   ├── services/
│   │   ├── supabase.js          # Supabase client & auth
│   │   └── api.js               # Flask API client
│   ├── styles/
│   │   └── index.css            # Global styles
│   ├── App.jsx                  # Root component
│   └── main.jsx                 # Entry point
├── index.html
├── package.json
├── vite.config.js
├── tailwind.config.js
└── .env.example
```

## 🎯 Usage Guide

### 1. User Registration & Login
- Navigate to the landing page
- Click "Get Started" or "Sign Up"
- Fill in your details and create an account
- You'll be automatically logged in and redirected to the dashboard

### 2. Adding a Home
- Go to "My Homes" from the sidebar
- Click "Add Home"
- Enter your property details:
  - Address
  - Home type (Apartment/House)
  - Size in square meters
  - Number of rooms
  - Check if you have AC/Heater
- Click "Add Home"

### 3. Making a Prediction
- Navigate to "Predictor"
- Select an existing home or enter details manually:
  - Home size (m²)
  - Number of appliances
  - Month for prediction
- Click "Predict Energy Bill"
- View your predicted bill and breakdown

### 4. Viewing History
- Go to "History" from the sidebar
- Switch between "Consumption History" and "Predictions" tabs
- Filter by year to see past records
- View detailed statistics and charts

## 🔌 API Integration

The frontend connects to two main services:

### Flask ML API (Port 5001)
```javascript
POST /predict
{
  "home_size": 100,
  "num_appliances": 8,
  "month": 12
}
```

### Supabase Database
- User authentication
- CRUD operations for Homes, Appliances, Consumption
- Real-time data queries with Row Level Security

## 🎨 Customization

### Changing Colors
Edit `tailwind.config.js`:

```javascript
colors: {
  primary: {
    50: '#f0f9ff',
    // ... your colors
  }
}
```

### Modifying Styles
Global styles are in `src/styles/index.css`

## 🚀 Deployment

### Build for production

```bash
npm run build
```

The production-ready files will be in the `dist/` directory.

### Deploy to Vercel

```bash
npm install -g vercel
vercel
```

### Deploy to Netlify

```bash
npm install -g netlify-cli
netlify deploy --prod
```

### Environment Variables in Production

Make sure to set all environment variables in your hosting platform:
- `VITE_SUPABASE_URL`
- `VITE_SUPABASE_ANON_KEY`
- `VITE_API_URL`

## 🔐 Security Notes

- Never commit `.env` files to version control
- Use Row Level Security (RLS) policies in Supabase
- Implement rate limiting on the Flask backend
- Use HTTPS in production
- Validate all user inputs on both frontend and backend

## 🐛 Troubleshooting

### "Cannot connect to backend"
- Ensure Flask backend is running on port 5001
- Check CORS settings in Flask app
- Verify `VITE_API_URL` in `.env`

### "Authentication failed"
- Check Supabase credentials in `.env`
- Verify RLS policies are set correctly
- Check browser console for detailed errors

### "Module not found" errors
- Run `npm install` again
- Clear node_modules: `rm -rf node_modules && npm install`
- Check Node.js version: `node --version` (should be 18+)

## 📝 Additional Resources

- [React Documentation](https://react.dev/)
- [Vite Guide](https://vitejs.dev/guide/)
- [Supabase Documentation](https://supabase.com/docs)
- [Tailwind CSS](https://tailwindcss.com/docs)
- [Recharts Examples](https://recharts.org/en-US/examples)

## 🤝 Contributing

Feel free to submit issues and enhancement requests!

## 📄 License

This project is part of the Smart City Energy Consumption Prediction System.

## 👨‍💻 Developer

Created by: Sharonne  
Date: December 2024

---

**Need help?** Check the troubleshooting section or open an issue in the repository.
