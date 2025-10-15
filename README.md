# 📊 Prediction Market Tracker

A beautiful, self-hosted web application for tracking your prediction market trades (Kalshi, Polymarket, etc.) and documenting your market insights. All data is stored directly in your GitHub repository with automatic version control.

![Prediction Market Tracker](https://img.shields.io/badge/prediction-markets-blue) ![GitHub Pages](https://img.shields.io/badge/GitHub-Pages-green)

## ✨ Features

- 📈 **Trade Tracking** - Log all your prediction market trades with detailed information
- 💡 **Market Insights** - Document your understanding of market dynamics and patterns
- 📊 **Portfolio Analytics** - Track total invested, win rate, P&L, and average entry odds
- ⚡ **Market Impact Analysis** - See how your trades move the market (great for low-volume markets)
- 🔄 **GitHub Integration** - All data commits directly to your repo with full version history
- 📱 **Responsive Design** - Works beautifully on desktop, tablet, and mobile
- 🎨 **Beautiful UI** - Clean, modern interface with smooth animations

## 🚀 Quick Start Guide

### Step 1: Fork/Clone This Repository

```bash
# Option 1: Fork on GitHub (recommended)
Click the "Fork" button at the top right of this repository

# Option 2: Clone directly
git clone https://github.com/yourusername/prediction-tracker.git
cd prediction-tracker
```

### Step 2: Enable GitHub Pages

1. Go to your repository **Settings**
2. Navigate to **Pages** (in the left sidebar)
3. Under **Source**, select your `main` branch
4. Click **Save**
5. Your site will be live at `https://yourusername.github.io/prediction-tracker`

### Step 3: Create a GitHub Personal Access Token

1. Go to GitHub **Settings** → **Developer settings** → **Personal access tokens** → **Tokens (classic)**
2. Click **Generate new token (classic)**
3. Give it a descriptive name (e.g., "Prediction Tracker")
4. Set expiration (recommend: 1 year)
5. Check the `repo` scope (full control of repositories)
6. Click **Generate token**
7. **Important:** Copy the token immediately - you won't see it again!

### Step 4: Configure Your Tracker

1. Visit your GitHub Pages URL
2. Scroll to the **GitHub Configuration** section
3. Enter:
   - **GitHub Username**: Your GitHub username
   - **Repository Name**: The name of this repository (e.g., `prediction-tracker`)
   - **Personal Access Token**: Paste the token you just created
4. Click **Save Configuration**
5. Click **Test Connection** to verify everything works

### Step 5: Start Tracking!

You're all set! Start adding trades and insights.

## 📝 How to Use

### Adding a Trade

1. **Market/Event Name**: What you're betting on (e.g., "Hurricane Category 2+ in October")
2. **Position**: Yes or No
3. **Amount Invested**: How much you put in
4. **Entry Odds**: The odds when you entered
5. **Post-Trade Odds** (optional): Odds after your trade executed
6. **Post-Trade Value** (optional): Your position value after execution
7. **Reasoning & Analysis**: Why you made this trade (e.g., "Referenced Google WeatherLab chart showing low probability...")
8. **Result** (optional): Update later when the market resolves (Win/Loss/Partial)
9. **Profit/Loss** (optional): Your actual P&L when the trade closes

Click **Add Trade** and it will commit to your repository!

### Adding Market Insights

Use this section to document your learning about prediction markets:

- Market dynamics you've discovered
- Patterns you've noticed
- Strategies that work or don't work
- Understanding of how liquidity affects pricing

**Example Insight:**
```
Title: Market Impact from Low Volume
Description: In low-volume markets, individual trades can significantly 
move odds. My $24.49 trade moved odds from 74% to 63%, a 11% shift. 
This suggests the market had thin liquidity and my trade became a 
significant portion of the order book.
```

### Viewing Your Data

- **Portfolio Statistics**: See your total trades, capital deployed, win rate, and P&L at a glance
- **Trade History**: All your trades with full details, market impact analysis, and results
- **Market Insights**: Your accumulated knowledge about prediction markets

## 🎯 Use Cases

### 1. Personal Trading Journal
Keep detailed records of all your prediction market trades with reasoning for future analysis.

### 2. Portfolio Showcase
Share your GitHub Pages link to showcase your prediction market track record to others.

### 3. Market Research
Document patterns you notice in prediction markets and build a knowledge base.

### 4. Learning Tool
Analyze which types of trades work best by reviewing your historical performance.

### 5. Transparency
Create a public record of your predictions and reasoning (useful for building credibility).

## 🔒 Data Privacy

### Public vs Private

- **Public Repository**: Anyone can see your trades and insights (great for transparency)
- **Private Repository**: Only you can see the data (requires paid GitHub account)

**To make private:**
1. Go to repository **Settings**
2. Scroll to **Danger Zone**
3. Click **Change visibility** → **Make private**

### Token Security

- Your Personal Access Token is stored in **browser localStorage only**
- It's never committed to the repository
- It's only used for API calls to your own repository
- Keep it secure - don't share your token with anyone
- You can revoke it anytime from GitHub settings

## 🎨 Customization

### Change Colors

Edit the CSS in `index.html`:

```css
/* Main gradient */
background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);

/* Change to your preferred colors */
background: linear-gradient(135deg, #your-color-1 0%, #your-color-2 100%);
```

### Add Custom Fields

Want to track additional data? Add new form fields in the HTML:

```html
<div class="form-group">
    <label>Your Custom Field</label>
    <input type="text" id="customField" placeholder="...">
</div>
```

Then capture it in the JavaScript trade object:

```javascript
const trade = {
    // ... existing fields
    customField: document.getElementById('customField').value,
};
```

### Modify Statistics

Edit the `updateStats()` function to calculate different metrics.

## 📱 Mobile Usage

The tracker is fully responsive and works great on mobile:

- Add trades from your phone while at a coffee shop
- Review your portfolio on the go
- Share your tracker URL with friends

## 🔄 Data Format

All data is stored in `data.json` in your repository:

```json
{
  "trades": [
    {
      "marketName": "Hurricane Category 2+ in October",
      "position": "No",
      "amount": "24.49",
      "entryOdds": "74",
      "postOdds": "63",
      "postValue": "20.79",
      "reasoning": "Referenced Google WeatherLab chart...",
      "result": "Win",
      "profitLoss": "25.51",
      "date": "2025-10-09T10:30:00.000Z"
    }
  ],
  "insights": [
    {
      "title": "Market Impact from Low Volume",
      "text": "In low-volume markets...",
      "date": "2025-10-09T10:35:00.000Z"
    }
  ],
  "lastUpdated": "2025-10-09T10:35:00.000Z"
}
```

## 🐛 Troubleshooting

### "Connection failed" error
- Verify your GitHub username and repo name are correct
- Check that your Personal Access Token has `repo` scope
- Ensure the token hasn't expired

### Trades not appearing
- Click "Test Connection" to reload data from GitHub
- Check your browser console for errors (F12)
- Verify `data.json` exists in your repository

### GitHub Pages not working
- Wait 5-10 minutes after enabling Pages (it takes time to build)
- Make sure `index.html` is in the root of your repository
- Check Settings → Pages to see build status

### Token security concerns
- Tokens are stored locally in your browser only
- Never commit your token to the repository
- Revoke and regenerate if you suspect it's compromised

## 🌟 Example Use Case: The Hurricane Trade

Let's walk through the example mentioned in the app:

**Scenario:** You want to bet that a hurricane will NOT reach Category 2+

**Trade Entry:**
- Market: "Hurricane Category 2+ in October"
- Position: No
- Amount: $24.49
- Entry Odds: 74%
- Reasoning: "Referenced Google WeatherLab chart showing current conditions indicate low probability of intensification. Water temperatures are marginal and wind shear is expected to increase."

**Market Impact:**
- Post-Trade Odds: 63%
- Post-Trade Value: $20.79
- Your trade moved the market 11%!

**Insight Documented:**
- Title: "Market Impact in Low-Volume Markets"
- Text: "My $24.49 trade significantly moved odds from 74% to 63%. This highlights that in prediction markets with limited liquidity, even small trades can have outsized impact on pricing. This suggests that the total market depth was likely under $250, making this a thin market."

**Result (when market resolves):**
- Result: Win ✅
- Profit/Loss: +$25.51

This creates a complete record of your trade, reasoning, market analysis, and outcome!

## 🤝 Contributing

Want to improve the tracker? Contributions are welcome!

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is open source and available under the MIT License.

## 🙏 Acknowledgments

- Built for prediction market traders who want to track and improve their performance
- Inspired by the need for better trade journaling tools
- Uses GitHub's amazing free hosting via GitHub Pages

## 📧 Support

Having issues? Found a bug? Have a feature request?

- Open an issue in this repository
- The community is here to help!

---

**Happy Trading! May your predictions be accurate and your profits plentiful! 📈**

---

## 🔗 Quick Links

- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [GitHub Personal Access Tokens Guide](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)
- [Kalshi](https://kalshi.com) - Prediction market platform
- [Polymarket](https://polymarket.com) - Prediction market platform

---

**Pro Tip:** Bookmark your GitHub Pages URL on your phone for quick trade entry on the go!
