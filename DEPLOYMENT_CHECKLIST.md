# 🚀 Deployment Checklist - Sofeia AI Agent

## ✅ Pre-Deployment Checklist

### 1. API Keys Setup
- [ ] **Groq API Key** - Get from https://console.groq.com/keys
  - Free tier: 14,000 requests/day
  - Used for: General questions (1 credit )
- [ ] **Perplexity API Key** - Get from https://www.perplexity.ai/settings/api
  - Paid service: ~$0.005 per request
  - Used for: Research with citations (2 credits )
- [ ] **Anthropic API Key** - Get from https://console.anthropic.com
  - Free tier: $5 credit, then $3-15 per million tokens
  - Used for: Content generation and grant writing (2-3 credits )
- [ ] **PayPal Credentials** - Get from https://developer.paypal.com
  - Business account required
  - Used for: Credit purchases

### 2. GitHub Repository
- [ ] Create new repository on GitHub
- [ ] Push code to repository
- [ ] Verify all files are included (check .gitignore )

### 3. Render Account Setup
- [ ] Create account at https://render.com
- [ ] Verify email address
- [ ] Add payment method (for paid plans )

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
