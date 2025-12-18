# 🚀 Quick Start Guide - EnergyAI Frontend

Get your frontend up and running in 5 minutes!

## Step 1: Prerequisites Check ✅

Make sure you have:
- [ ] Node.js 18+ installed (`node --version`)
- [ ] npm or yarn installed
- [ ] Supabase account created
- [ ] Flask backend code ready

## Step 2: Install Dependencies 📦

```bash
cd energy-frontend
npm install
```

## Step 3: Set Up Supabase 🗄️

### Create Supabase Project
1. Go to https://supabase.com
2. Click "New Project"
3. Fill in project details and wait for setup

### Execute Database Schema
1. In Supabase Dashboard, go to SQL Editor
2. Copy the entire content from `Database` file
3. Paste and run it in the SQL Editor
4. Verify tables are created in the Table Editor

### Get API Credentials
1. Go to Settings > API
2. Copy:
   - Project URL
   - anon public key

## Step 4: Configure Environment 🔧

Create `.env` file:

```bash
cp .env.example .env
```

Edit `.env` and paste your Supabase credentials:

```env
VITE_SUPABASE_URL=https://xxxxx.supabase.co
VITE_SUPABASE_ANON_KEY=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...
VITE_API_URL=http://localhost:5001
```

## Step 5: Start Backend API 🔌

In a **separate terminal**:

```bash
cd BackEnd
python app.py
```

Should see: `Running on http://127.0.0.1:5001`

## Step 6: Start Frontend 🎨

```bash
npm run dev
```

Open browser to: **http://localhost:3000**

## Step 7: Test the Application 🧪

1. **Register a new account**
   - Click "Get Started"
   - Fill in registration form
   - Submit

2. **Add a home**
   - Navigate to "My Homes"
   - Click "Add Home"
   - Enter property details

3. **Make a prediction**
   - Go to "Predictor"
   - Select your home or enter details
   - Click "Predict Energy Bill"

## 🎉 Success!

You should now see your predicted energy bill!

## Common Issues & Fixes 🔧

### Issue: "Cannot connect to Supabase"
**Fix:** Check your `.env` file has correct credentials

### Issue: "Prediction API failed"
**Fix:** Ensure Flask backend is running on port 5001

### Issue: "Module not found"
**Fix:** Run `npm install` again

### Issue: Port 3000 already in use
**Fix:** 
```bash
# Kill the process
lsof -ti:3000 | xargs kill -9
# Or use a different port
npm run dev -- --port 3001
```

## Next Steps 📚

- Read the full [README.md](./README.md) for detailed documentation
- Explore the [Dashboard](http://localhost:3000/dashboard)
- Customize colors in `tailwind.config.js`
- Deploy to production (Vercel, Netlify, etc.)

## Need Help? 💬

- Check browser console for errors (F12)
- Check Flask terminal for backend errors
- Review Supabase logs in dashboard
- Ensure all tables and RLS policies are set up

---

**Happy Coding! ⚡**
