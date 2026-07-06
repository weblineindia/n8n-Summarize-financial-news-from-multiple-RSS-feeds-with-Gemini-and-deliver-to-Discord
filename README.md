# Multi-Source RSS + Gemini AI → Daily Wealth Brief to Discord

This workflow automatically collects financial news from multiple trusted sources, filters and cleans the data and uses AI (Google Gemini) to generate a concise daily wealth briefing. The final summary is formatted and delivered directly to a Discord channel, ensuring you get actionable financial insights without manual effort.

---

# Quick Implementation Steps

1. Import the workflow into n8n.
2. Replace the Manual Trigger with a Schedule Trigger (daily recommended).
3. Add your Google Gemini API credentials.
4. Connect your Discord Bot credentials.
5. Configure RSS feeds (optional).
6. Activate the workflow.

---

# What It Does

This workflow acts as your automated financial intelligence assistant. It gathers news from multiple high-quality sources including Yahoo Finance, CoinDesk and the Federal Reserve. Instead of overwhelming you with raw headlines, it intelligently filters and prioritizes only high-impact macroeconomic updates.

After collecting the data, the workflow removes duplicate articles and filters out low-value noise using keyword-based logic. It then selects the top 15 most relevant news items and feeds them into Google Gemini AI.

The AI processes this information and generates a clear, actionable wealth briefing focused on major financial themes like inflation, crypto markets, interest rates and global economic trends. The final output is formatted and delivered to your Discord channel for easy consumption.

---

# Who's It For

- Wealth managers and financial advisors
- Crypto traders and investors
- Stock market enthusiasts
- Startup founders tracking macro trends
- Anyone who wants a daily financial summary without information overload

---

# Requirements

To use this workflow, you'll need:

- **[n8n account (Cloud or Self-Hosted)](https://n8n.partnerlinks.io/om1efg2qgvwi)**
- **Google Gemini API credentials (Google AI Studio)**
- **Discord Bot credentials**
- Internet access to RSS feeds

---

# How It Works & Set Up

## 1. Import Workflow

Upload the workflow JSON into your n8n instance.

---

## 2. Replace Trigger

Replace the **Manual Trigger** with a **Schedule Trigger**.

**Recommended schedule:**

- Daily
- Between **7:00 AM and 9:00 AM**

---

## 3. Configure RSS Nodes

The workflow includes the following RSS sources:

- Yahoo Finance RSS
- CoinDesk RSS
- Federal Reserve RSS

You can modify or add more RSS feeds as needed.

## 4. Set Up Gemini AI

- Add your **Google Gemini** credentials.
- Ensure the model is set to:

```text
gemini-flash-latest
```

---

## 5. Configure Discord

- Connect your **Discord Bot** credentials.
- Select the Discord server (guild).
- Choose the destination channel.
- Ensure the bot has permission to send messages in that channel.

---

## 6. Activate Workflow

- Turn the workflow **ON**.
- Monitor the first execution to verify everything is working correctly.

---

# Workflow Logic Breakdown

## Data Collection

- Fetch news from three RSS sources.
- Merge all articles into a single stream.

---

## Data Cleaning

- Remove duplicate article titles.
- Filter news using keywords such as:
  - bitcoin
  - inflation
  - fed
  - market
  - oil

---

## Prioritization

- Select the top **15** most relevant news items.

---

## Transformation

- Convert the selected news into structured text suitable for AI processing.

---

## AI Processing

Google Gemini analyzes the news and generates:

- Top 5 insights
- Simple explanations
- Actionable financial advice

---

## Delivery

- Format the AI-generated summary for Discord.
- Send the message to the configured Discord channel.
- If AI processing fails, send a fallback error message instead.

---

# How To Customize Nodes

## AI Node (Gemini)

Modify the prompt to:

- Add region-specific insights.
- Include stock recommendations.
- Change the writing style (technical, beginner, professional, etc.).

---

## Filter Node

Customize the keyword list.

Example:

```javascript
const keywords = [
  "bitcoin",
  "fed",
  "inflation",
  "stock",
  "market",
  "oil"
];
```

You can also add keywords like:

- gold
- real estate
- rupee
- bonds
- recession
- interest rates

---

## RSS Nodes

Add additional RSS sources such as:

- Bloomberg
- Reuters
- Economic Times

---

## Limit Node

Adjust the number of news articles processed.

Default:

- **15 articles**

You can increase or decrease this value depending on your requirements.

---

## Discord Node

Customize:

- Discord server
- Channel
- Mentions (`@everyone`, specific roles, etc.)

# Add-ons

Extend this workflow with additional automation and integrations:

- Save daily wealth briefs to **Google Sheets** or **Notion**.
- Send summaries via **Email** or **Telegram**.
- Add an **AI sentiment analysis** layer.
- Store historical daily briefs for long-term trend analysis.
- Add **portfolio-specific filtering** to receive personalized investment insights.

---

# Use Case Examples

## 1. Daily Investor Briefing

Receive a concise overview of market conditions every morning before the trading day begins.

---

## 2. Crypto Market Monitoring

Track Bitcoin, macroeconomic indicators and cryptocurrency market trends automatically.

---

## 3. Wealth Advisory Automation

Generate daily financial insights and automatically distribute them to clients through Discord or other communication channels.

---

## 4. Startup Founder Intelligence

Stay informed about macroeconomic events, interest rates and financial developments that could impact your business.

---

## 5. Discord Community Engagement

Share AI-curated financial news summaries with your Discord community to keep members informed with high-quality market updates.

---

There are many more ways to customize and extend this workflow depending on your preferred news sources, AI prompts and delivery channels.

---

# Troubleshooting Guide

| Issue | Possible Cause | Solution |
|--------|----------------|----------|
| **No RSS articles retrieved** | RSS feed unavailable or incorrect URL | Verify that each RSS feed URL is accessible and correctly configured. |
| **Duplicate news still appears** | Duplicate filtering logic not matching article titles | Review the duplicate removal node and adjust the matching logic if necessary. |
| **Gemini AI node fails** | Missing or invalid Google Gemini API credentials | Verify your Gemini credentials and ensure the selected model is available. |
| **Discord message not sent** | Bot permissions or incorrect channel configuration | Confirm the bot has permission to send messages and that the correct server and channel are selected. |
| **Workflow stops after AI node** | AI response format changed or unexpected output | Review the AI prompt and ensure downstream nodes expect the correct response format. |

---

# Need Help?

If you need help setting up, customizing or extending this workflow, our **n8n workflow automation experts at WeblineIndia** are here to help.

We can assist you with:

- n8n workflow setup and deployment
- RSS feed aggregation and filtering
- Google Gemini AI integration and prompt engineering
- Discord, Telegram and email integrations
- AI-powered financial news automation
- Dashboard and reporting solutions
- Historical data storage and analytics
- Production-ready workflow optimization and scaling

Whether you're building a personal market intelligence assistant or an enterprise-grade financial news platform, we can help customize this workflow to fit your exact requirements.

**Need expert assistance?**

- **Hire n8n Developers:** https://www.weblineindia.com/hire-n8n-developers/
- **Contact WeblineIndia:** https://www.weblineindia.com/contact-us.html
