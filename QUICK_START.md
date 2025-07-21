# Quick Start Guide - Sofeia AI Agent

## 🚀 Deploy to Render in 5 Minutes

### 1. Fork/Clone this Repository
```bash
git clone https://github.com/yourusername/sofeia-ai.git
cd sofeia-ai
```

### 2. Get Your API Keys
- **Groq**: https://console.groq.com/keys (Free tier: 14,000 requests/day)
- **Perplexity**: https://www.perplexity.ai/settings/api (Paid: ~$0.005/request)
- **Anthropic**: https://console.anthropic.com (Free: $5 credit)
- **PayPal**: https://developer.paypal.com (Business account)

### 3. Deploy to Render
1. Go to https://render.com
2. Click "New +" → "Web Service"
3. Connect your GitHub repository
4. Use these settings:
   - **Build Command**: `npm run build`
   - **Start Command**: `npm start`
   - **Node Version**: 18+

### 4. Add Environment Variables
In Render dashboard, add these environment variables:
```
NODE_ENV=production
DATABASE_URL=<your-render-postgres-url>
SESSION_SECRET=<64-char-random-string>
GROQ_API_KEY=<your-groq-key>
PERPLEXITY_API_KEY=<your-perplexity-key>
ANTHROPIC_API_KEY=<your-anthropic-key>
PAYPAL_CLIENT_ID=<your-paypal-id>
PAYPAL_CLIENT_SECRET=<your-paypal-secret>
ADMIN_KEY=0f5db72a966a8d5f7ebae96c6a1e2cc574c2bf926c62dc4526bd43df1c0f42eb
ADMIN_IP_ADDRESS=112.198.165.82
```

### 5. Create PostgreSQL Database
1. In Render, click "New +" → "PostgreSQL"
2. Name: `sofeia-ai-db`
3. Copy the connection URL to `DATABASE_URL` above

### 6. Deploy!
Your app will be live at `https://your-app-name.onrender.com`

## 💰 Revenue Model
- **Starter Plan**: €35/month (150 questions)
- **Professional Plan**: €300/month (1500 questions)
- **Free Tier**: 5 questions per IP address

## 🔧 Local Development
```bash
npm install
cp .env.example .env
# Fill in your API keys in .env
npm run dev
```

## 📞 Support
**Founder**: Ottmar Francisca  
**WhatsApp**: +31 628 073 996  
**PayPal**: https://paypal.me/ojgmedia

## 🎯 Features
- **Smart Country Detection** - Prioritizes government sources by country
- **Professional SEO Content** - RankMath 100/100 optimization
- **Grant Writing** - C.R.A.F.T framework with official citations
- **Real-time Chat** - WebSocket with HTML formatting
- **Credit System** - IP-based tracking with PayPal integration

