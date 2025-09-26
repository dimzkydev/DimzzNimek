# 🚀 DimzzNimek Deployment Guide

## Quick Deployment Steps

### 1. Export Code to GitHub
1. In Emergent chat, look for **"Save to GitHub"** button
2. Click it to push your complete DimzzNimek codebase to GitHub
3. Choose repository name (e.g., "dimzznimek-app")

### 2. Deploy Frontend to Vercel
1. **Go to [vercel.com](https://vercel.com)**
2. **Sign up/Login** with GitHub account
3. **Click "New Project"**
4. **Import** your DimzzNimek GitHub repository
5. **Configure Build Settings**:

. **Add Environment Variable**:
- Name: `REACT_APP_BACKEND_URL`
- Value: `https://your-backend-url.com` (add after backend deployment)
7. **Click Deploy**

### 3. Deploy Backend (Choose One Option)

#### Option A: Railway.app (Easiest)
1. **Go to [railway.app](https://railway.app)**
2. **Sign up** with GitHub
3. **New Project** → **Deploy from GitHub repo**
4. **Select** your DimzzNimek repository
5. **Configure**:
- Root Directory: `backend`
- Start Command: `uvicorn server:app --host 0.0.0.0 --port $PORT`
6. **Add Environment Variables**:

MONGO_URL=mongodb+srv://username:password@cluster.mongodb.net/dimzznimek CORS_ORIGINS=https://your-vercel-app.vercel.app DB_NAME=dimzznimek

. **Deploy** and copy the Railway URL

#### Option B: Render.com (Free Tier)
1. **Go to [render.com](https://render.com)**
2. **Create Account** → **New Web Service**
3. **Connect GitHub** repository
4. **Configure**:
- Root Directory: `backend`
- Build Command: `pip install -r requirements.txt`
- Start Command: `uvicorn server:app --host 0.0.0.0 --port $PORT`
5. **Add Environment Variables** (same as Railway)
6. **Deploy** and copy the Render URL

### 4. Update Frontend Environment
1. **Go back to Vercel dashboard**
2. **Settings** → **Environment Variables**
3. **Update** `REACT_APP_BACKEND_URL` with your backend URL
4. **Redeploy** the frontend

### 5. Setup MongoDB (If Needed)
1. **Go to [mongodb.com/atlas](https://mongodb.com/atlas)**
2. **Create free cluster**
3. **Get connection string**
4. **Update** backend `MONGO_URL` environment variable

## 🔗 Your Live URLs
After deployment, you'll have:
- **Frontend**: `https://your-app-name.vercel.app`
- **Backend**: `https://your-backend.railway.app` or `https://your-backend.onrender.com`

## 🛠️ Troubleshooting

### Common Issues:
1. **Build fails**: Check Node.js version (should be 18+)
2. **Backend not connecting**: Verify CORS_ORIGINS matches frontend URL
3. **Database errors**: Check MongoDB connection string format
4. **API calls failing**: Ensure REACT_APP_BACKEND_URL is correct

### Quick Fixes:
- **Clear Vercel cache**: Settings → Functions → Clear cache
- **Redeploy backend**: Push new commit to trigger rebuild
- **Check logs**: Both Vercel and Railway/Render provide deployment logs

## ✅ Success Checklist
- [ ] Code exported to GitHub
- [ ] Frontend deployed to Vercel
- [ ] Backend deployed to Railway/Render
- [ ] MongoDB connected
- [ ] Environment variables configured
- [ ] Frontend connects to backend API
- [ ] Anime/manga data loads correctly

## 🎯 Final Result
Your DimzzNimek app will be live with:
- Real anime/manga data from Jikan API
- Search functionality
- Responsive mobile design
- Professional UI with favorites system