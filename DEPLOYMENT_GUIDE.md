# 🚀 DEPLOYMENT GUIDE - Hockey Slang Translator

## The Problem You Hit

The app makes direct API calls to Anthropic from the browser, which doesn't work publicly because:
1. API keys can't be exposed in frontend code (security risk)
2. CORS restrictions prevent direct browser → Anthropic API calls

## The Solution

Use a **backend server** that:
- Keeps your API key secret
- Makes API calls on behalf of the frontend
- Serves the frontend HTML

---

## 📦 Files You Need

1. **server.js** - Backend Express server
2. **package.json** - Node.js dependencies
3. **index.html** - Frontend (put this in a `public` folder)
4. **.env** - Your API key (create this yourself)
5. **.env.example** - Template for .env file

---

## 🛠️ Setup Instructions (Local Testing)

### Step 1: Install Node.js
Download from https://nodejs.org/ (get the LTS version)

### Step 2: Organize Your Files
```
hockey-slang-translator/
├── server.js
├── package.json
├── .env
├── .env.example
└── public/
    └── index.html
```

### Step 3: Get Your API Key
1. Go to https://console.anthropic.com/
2. Sign up / log in
3. Go to "API Keys"
4. Create a new key
5. Copy it (starts with `sk-ant-`)

### Step 4: Create .env File
Create a file named `.env` in the root folder:
```
ANTHROPIC_API_KEY=sk-ant-your-actual-key-here
PORT=3000
```

⚠️ **NEVER commit .env to GitHub!**

### Step 5: Install Dependencies
Open terminal in your project folder and run:
```bash
npm install
```

### Step 6: Start the Server
```bash
npm start
```

### Step 7: Test It
Open your browser to: `http://localhost:3000`

---

## 🌐 Deploy to Production

### Option A: Vercel (Easiest!)

**1. Install Vercel CLI:**
```bash
npm install -g vercel
```

**2. Create vercel.json:**
```json
{
  "version": 2,
  "builds": [
    {
      "src": "server.js",
      "use": "@vercel/node"
    }
  ],
  "routes": [
    {
      "src": "/(.*)",
      "dest": "server.js"
    }
  ]
}
```

**3. Deploy:**
```bash
vercel
```

**4. Add API Key as Environment Variable:**
- Go to your Vercel dashboard
- Select your project
- Go to Settings → Environment Variables
- Add: `ANTHROPIC_API_KEY` = your key

---

### Option B: Render (Also Easy!)

**1. Push to GitHub:**
```bash
git init
git add .
git commit -m "Initial commit"
git remote add origin your-github-repo-url
git push -u origin main
```

**2. Create .gitignore:**
```
node_modules/
.env
```

**3. Go to Render.com:**
- Sign up / log in
- Click "New +" → "Web Service"
- Connect your GitHub repo
- Configure:
  - **Build Command:** `npm install`
  - **Start Command:** `npm start`
  - **Environment Variables:** Add `ANTHROPIC_API_KEY`

**4. Deploy!**
Render will give you a URL like: `your-app.onrender.com`

---

### Option C: Railway

**1. Install Railway CLI:**
```bash
npm install -g @railway/cli
```

**2. Deploy:**
```bash
railway login
railway init
railway up
```

**3. Add Environment Variable:**
```bash
railway variables set ANTHROPIC_API_KEY=your-key-here
```

---

### Option D: Heroku

**1. Install Heroku CLI:**
Download from https://devcenter.heroku.com/articles/heroku-cli

**2. Create Procfile:**
```
web: node server.js
```

**3. Deploy:**
```bash
heroku login
heroku create your-app-name
git push heroku main
heroku config:set ANTHROPIC_API_KEY=your-key-here
```

---

## 🔒 Security Checklist

- ✅ API key is in .env file
- ✅ .env is in .gitignore
- ✅ Never hardcode API keys in code
- ✅ Use environment variables in production
- ✅ CORS is configured properly

---

## 💰 Cost Considerations

**Anthropic API Pricing:**
- Claude Sonnet 4: ~$3 per million input tokens
- Each translation uses ~500-1000 tokens
- That's roughly $0.002-0.003 per translation
- 1000 translations ≈ $2-3

**Hosting:**
- Vercel: Free tier (enough for personal use)
- Render: Free tier with 750 hours/month
- Railway: $5/month for starter plan
- Heroku: $5-7/month for basic dyno

---

## 🐛 Troubleshooting

### "Failed to fetch" error
- Make sure server is running
- Check that API key is set correctly
- Look at browser console for detailed errors

### "API key not configured" error
- .env file is missing
- .env file has wrong key name
- Environment variable not set on hosting platform

### CORS errors
- Make sure `cors` is installed: `npm install cors`
- Check that server.js has `app.use(cors())`

### Port already in use
- Change PORT in .env to something else (e.g., 3001)
- Or kill the process using port 3000

---

## 📝 Quick Commands Reference

```bash
# Install dependencies
npm install

# Run locally
npm start

# Run with auto-restart (development)
npm run dev

# Check if API key is set
echo $ANTHROPIC_API_KEY   # Mac/Linux
echo %ANTHROPIC_API_KEY%  # Windows

# Test API endpoint
curl http://localhost:3000/api/health
```

---

## 🎉 You're Done!

Your hockey slang translator should now be live and working!

**Share your URL and let the boys wheel, snipe, and celly! 🏒**

---

## Need Help?

Common issues:
1. **Fetch failing**: Backend not running or wrong URL
2. **401 error**: Invalid API key
3. **500 error**: Check server logs for details
4. **CORS error**: Make sure cors middleware is enabled

Check server logs with `npm start` to see what's happening!
