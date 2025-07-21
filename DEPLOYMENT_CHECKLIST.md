# 🚀 Deployment Checklist - Sofeia AI Agent

## ✅ Pre-Deployment Checklist

### 1. API Keys Setup
- [ ] **Groq API Key** - Get from https://console.groq.com/keys
  - Free tier: 14,000 requests/day
  - Used for: General questions (1 credit)
- [ ] **Perplexity API Key** - Get from https://www.perplexity.ai/settings/api
  - Paid service: ~$0.005 per request
  - Used for: Research with citations (2 credits)
- [ ] **Anthropic API Key** - Get from https://console.anthropic.com
  - Free tier: $5 credit, then $3-15 per million tokens
  - Used for: Content generation and grant writing (2-3 credits)
- [ ] **PayPal Credentials** - Get from https://developer.paypal.com
  - Business account required
  - Used for: Credit purchases

### 2. GitHub Repository
- [ ] Create new repository on GitHub
- [ ] Push code to repository
- [ ] Verify all files are included (check .gitignore)

### 3. Render Account Setup
- [ ] Create account at https://render.com
- [ ] Verify email address
- [ ] Add payment method (for paid plans)

## 🎯 Deployment Steps

### Step 1: GitHub Setup
```bash
# In your local project directory
git init
git add .
git commit -m "Initial commit - Sofeia AI Agent"
git branch -M main
git remote add origin https://github.com/yourusername/sofeia-ai.git
git push -u origin main
```

### Step 2: Create PostgreSQL Database on Render
1. Login to Render dashboard
2. Click "New +" → "PostgreSQL"
3. Configure:
   - **Name**: `sofeia-ai-database`
   - **Database**: `sofeia_ai`
   - **User**: `sofeia_user`
   - **Region**: Choose closest to your users
   - **Plan**: Free (or Standard for production)
4. Click "Create Database"
5. **Copy the External Database URL** - you'll need this

### Step 3: Create Web Service on Render
1. Click "New +" → "Web Service"
2. Select "Build and deploy from a Git repository"
3. Connect your GitHub repository
4. Configure:
   - **Name**: `sofeia-ai` (or your preferred name)
   - **Environment**: `Node`
   - **Region**: Same as your database
   - **Branch**: `main`
   - **Build Command**: `npm run build`
   - **Start Command**: `npm start`
   - **Auto-Deploy**: Yes

### Step 4: Environment Variables
Add these in Render dashboard under "Environment Variables":

```env
NODE_ENV=production
DATABASE_URL=<your-render-postgres-external-url>
SESSION_SECRET=<generate-64-character-random-string>
GROQ_API_KEY=<your-groq-api-key>
PERPLEXITY_API_KEY=<your-perplexity-api-key>
ANTHROPIC_API_KEY=<your-anthropic-api-key>
PAYPAL_CLIENT_ID=<your-paypal-client-id>
PAYPAL_CLIENT_SECRET=<your-paypal-client-secret>
ADMIN_KEY=0f5db72a966a8d5f7ebae96c6a1e2cc574c2bf926c62dc4526bd43df1c0f42eb
ADMIN_IP_ADDRESS=112.198.165.82
```

**Generate SESSION_SECRET:**
```bash
node -e "console.log(require('crypto').randomBytes(64).toString('hex'))"
```

### Step 5: Deploy
1. Click "Create Web Service"
2. Wait for build to complete (5-10 minutes)
3. Your app will be live at `https://your-app-name.onrender.com`

## 🧪 Testing Your Deployment

### 1. Basic Functionality Test
- [ ] Visit your app URL
- [ ] Test the landing page loads
- [ ] Try asking a free question (should work with IP-based credits)
- [ ] Check that responses are properly formatted

### 2. Admin Panel Test
- [ ] Visit `/admin` on your deployed app
- [ ] Enter admin key: `0f5db72a966a8d5f7ebae96c6a1e2cc574c2bf926c62dc4526bd43df1c0f42eb`
- [ ] Verify admin controls work

### 3. Payment System Test
- [ ] Try to purchase credits
- [ ] Verify PayPal integration works
- [ ] Test credit deduction after questions

## 💰 Cost Breakdown

### Monthly Operating Costs
- **Render Web Service**: $7/month (Starter) or $25/month (Standard)
- **Render PostgreSQL**: $20/month (includes backups)
- **API Usage**:
  - Groq: $0 (generous free tier)
  - Perplexity: $20-50 (depending on usage)
  - Anthropic: $15-30 (depending on usage)
- **Total**: ~$62-125/month

### Revenue Potential
- **Starter Plan**: €35/month per customer (150 questions)
- **Professional Plan**: €300/month per customer (1500 questions)
- **Break-even**: 2-4 customers/month

## 🔧 Troubleshooting

### Common Issues

**Build Fails:**
- Check that all dependencies are in package.json
- Verify Node.js version compatibility (18+)
- Check build logs for specific errors

**Database Connection Issues:**
- Verify DATABASE_URL is correct
- Ensure database is in same region as web service
- Check database is running and accessible

**API Key Issues:**
- Verify all API keys are valid and active
- Check API key permissions and quotas
- Test API keys individually

**Environment Variables:**
- Ensure all required variables are set
- Check for typos in variable names
- Verify SESSION_SECRET is properly generated

### Getting Help
- Check Render logs in dashboard
- Review error messages carefully
- Contact support if needed

## 🎉 Post-Deployment

### 1. Custom Domain (Optional)
- Purchase domain from registrar
- Add custom domain in Render dashboard
- Update DNS settings

### 2. Monitoring
- Set up Render monitoring alerts
- Monitor API usage and costs
- Track user engagement and revenue

### 3. Scaling
- Monitor performance metrics
- Upgrade to Standard plan when needed
- Consider database scaling for high traffic

## 📞 Support

**Founder**: Ottmar Francisca  
**WhatsApp**: +31 628 073 996  
**PayPal**: https://paypal.me/ojgmedia

**Admin Access**:
- **Key**: `0f5db72a966a8d5f7ebae96c6a1e2cc574c2bf926c62dc4526bd43df1c0f42eb`
- **IP**: `112.198.165.82` (Unlimited access)

---

**Ready to deploy?** Follow this checklist step by step and you'll have your AI agent live in under 30 minutes!

