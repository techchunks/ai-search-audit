# AI Search Audit Tool

A high-end, production-ready SaaS platform that analyzes websites for SEO and AI search readiness using Google Gemini AI and Stripe payments.

## Features

✨ **Website Analysis**
- Comprehensive SEO audit with scoring
- AI search readiness analysis
- Crawlability assessment
- On-page optimization suggestions
- Structured actionable recommendations

💰 **Freemium Pricing**
- **Free**: Unlimited scans, 6 suggestions per report
- **Pro** ($49/mo): 15 suggestions, advanced tools, internal linking graph
- **Managed** ($499/mo): Unlimited suggestions, dedicated support, API access

🤖 **AI-Powered**
- Google Gemini 2.0 Flash API integration
- Structured JSON responses
- Real-time website analysis
- Smart categorization of issues

💳 **Payment Processing**
- Stripe integration for subscriptions
- Secure checkout flow
- Email lead capture
- Success confirmation

🎨 **Modern Design**
- React 19 + TypeScript
- Tailwind CSS 4
- Framer Motion animations
- Responsive mobile-first design
- Professional UI components

🚀 **Production Ready**
- Deployed on Vercel
- Automatic GitHub integration
- Environment variable management
- Error handling and logging

---

## Quick Start

### 1. Clone Repository

```bash
git clone https://github.com/techchunks/ai-search-audit.git
cd ai-search-audit
```

### 2. Initialize New Project

Use the setup script to create a new project with all dependencies:

```bash
bash scripts/setup_project.sh my-audit-tool
cd my-audit-tool
```

This will:
- ✅ Create Vite + React + TypeScript project
- ✅ Install Stripe, Framer Motion, and other dependencies
- ✅ Setup Tailwind CSS
- ✅ Create `.env.example` template
- ✅ Initialize Git repository

### 3. Configure Environment

```bash
cp .env.example .env.local
```

Edit `.env.local` and add your API keys:

```env
VITE_GEMINI_API_KEY=your_gemini_api_key
VITE_STRIPE_PUBLIC_KEY=pk_test_your_stripe_key
VITE_STRIPE_PRICE_ID_PRO=price_your_pro_id
VITE_STRIPE_PRICE_ID_MANAGED=price_your_managed_id
```

### 4. Start Development Server

```bash
npm run dev
```

Open http://localhost:5173 in your browser.

### 5. Build for Production

```bash
npm run build
npm run preview
```

---

## API Setup

### Google Gemini API

1. Visit https://aistudio.google.com
2. Click "Get API Key"
3. Copy key to `.env.local`

**See `references/gemini-setup.md` for detailed instructions.**

### Stripe API

1. Create account at https://stripe.com
2. Create products and prices
3. Copy keys to `.env.local`

**See `references/stripe-setup.md` for detailed instructions.**

---

## Deployment

### Deploy to Vercel

1. Push to GitHub:
```bash
git push origin main
```

2. Go to https://vercel.com/new
3. Import your GitHub repository
4. Add environment variables
5. Click "Deploy"

**See `references/deployment.md` for detailed instructions.**

---

## Project Structure

```
ai-search-audit/
├── scripts/                # Setup and generation scripts
│   ├── setup_project.sh   # Initialize new project
│   └── generate_components.py  # Generate components
├── templates/             # Reusable service templates
│   ├── gemini.service.ts  # Gemini AI integration
│   ├── stripe.service.ts  # Stripe payment processing
│   ├── types.ts           # TypeScript definitions
│   └── tailwind.config.js # Tailwind configuration
├── references/            # API setup guides
│   ├── gemini-setup.md    # Gemini API guide
│   ├── stripe-setup.md    # Stripe integration guide
│   └── deployment.md      # Vercel deployment guide
├── SKILL.md               # Skill documentation
└── README.md              # This file
```

---

## Using Templates

### Copy Service Templates

After creating a new project, copy the templates:

```bash
cp templates/gemini.service.ts src/services/
cp templates/stripe.service.ts src/services/
cp templates/types.ts src/
cp templates/tailwind.config.js .
```

### Generate Components

```bash
python scripts/generate_components.py component Dashboard
python scripts/generate_components.py page Analytics
```

---

## Services

### Gemini Service (`templates/gemini.service.ts`)
Analyzes websites using Google Gemini AI. Returns structured audit reports with scores and suggestions.

```typescript
const report = await analyzeWebsite('example.com', 'FREE');
```

### Stripe Service (`templates/stripe.service.ts`)
Handles subscription payments and checkout flow.

```typescript
await createCheckoutSession(priceId, email);
```

---

## Customization

### Branding
Edit `src/components/Navbar.tsx` to change logo and brand name.

### Colors
Modify `tailwind.config.js` to customize the color palette:

```javascript
colors: {
  indigo: { 600: '#YOUR_COLOR' },
  slate: { 50: '#YOUR_COLOR' },
}
```

### Pricing Tiers
Edit `src/services/stripe.ts` to modify pricing plans and features.

### Analysis Criteria
Customize the Gemini prompt in `src/services/gemini.ts` to change what gets analyzed.

---

## Troubleshooting

### Build Errors

```bash
rm -rf node_modules .vite
npm install
npm run build
```

### API Key Issues

- Verify key format (pk_test_ or pk_live_)
- Check `.env.local` file exists
- Ensure no extra spaces in keys
- Restart dev server after changing .env

### Stripe Checkout Not Loading

- Check public key is correct
- Verify price IDs exist in Stripe
- Check browser console for errors
- Test with Stripe test cards

### Gemini Analysis Fails

- Verify API key is valid
- Check rate limits in Google Cloud Console
- Ensure domain is accessible
- Check network requests in DevTools

---

## Security

- ✅ Never commit `.env.local` to Git
- ✅ Use environment variables for all secrets
- ✅ Validate email addresses before checkout
- ✅ Implement CSRF protection
- ✅ Use HTTPS only in production
- ✅ Keep dependencies updated

---

## Performance Tips

- Use Vercel Edge Functions for API routes
- Cache Gemini responses in database
- Implement request debouncing
- Use React.memo for heavy components
- Lazy load pages with React.lazy()
- Monitor bundle size with `npm run build`

---

## Testing

### Local Testing

```bash
npm run dev
```

### Test Stripe Payments

Use test card: `4242 4242 4242 4242`
- Expiry: Any future date
- CVC: Any 3 digits

### Test Gemini Analysis

Enter any domain to test analysis:
- example.com
- google.com
- github.com

---

## Next Steps

1. ✅ Initialize project with setup script
2. ✅ Configure API keys
3. ✅ Deploy to Vercel
4. Set up custom domain
5. Add database for storing reports
6. Implement user authentication
7. Create admin dashboard
8. Add email notifications
9. Set up analytics tracking

---

## Resources

- **React**: https://react.dev
- **Tailwind CSS**: https://tailwindcss.com
- **Stripe Docs**: https://stripe.com/docs
- **Gemini API**: https://ai.google.dev
- **Vercel**: https://vercel.com/docs

---

## Support

For detailed setup instructions:
- See `references/gemini-setup.md` for Gemini API
- See `references/stripe-setup.md` for Stripe integration
- See `references/deployment.md` for Vercel deployment
- See `SKILL.md` for complete skill documentation

---

## License

MIT - Feel free to use this project for your own purposes.

---

**Built with ❤️ using React, TypeScript, Tailwind CSS, Gemini AI, and Stripe**
