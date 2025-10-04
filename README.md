<img width="711" height="226" alt="image" src="https://github.com/user-attachments/assets/ed0e3289-58b0-48c9-8f6a-b37c01d20d6a" />

# 🐦 Twitter Data Collection Workflow (n8n + Bright Data + Google Sheets)

This workflow provides an **automated Twitter data collection solution** that extracts **profile information and tweet data** from specified Twitter accounts within custom date ranges.

Perfect for:
- ✅ Social media analytics
- ✅ Competitor research
- ✅ Brand monitoring
- ✅ Content strategy analysis

---

## ✨ Key Features

- 🔗 **Form-Based Input**: Simple form for entering Twitter URL and date range
- 🐦 **Twitter Integration**: Uses Bright Data’s Twitter dataset
- 📊 **Comprehensive Data**: Captures tweets, profile info, and engagement metrics
- 📈 **Google Sheets Output**: Automatically populates structured spreadsheets
- 🔄 **Progress Monitoring**: Real-time scraping job status & retries
- ⚡ **Fast & Reliable**: Built-in error handling
- 📅 **Custom Date Ranges**: Precise control for timeline selection
- 🎯 **Customizable Fields**: Choose which data points to extract

---

## 🚀 What This Workflow Does

### 📝 Input
- **Twitter Profile URL**: The public Twitter account to scrape
- **Date Range**: Start and end dates for tweet collection
- **Custom Fields**: Optional, user-defined fields for data extraction

### 🔧 Processing Flow
1. **Form Trigger**: Captures Twitter URL and date range
2. **API Request**: Sends request to Bright Data with specified filters
3. **Job Monitoring**: Polls for job status until completion
4. **Data Retrieval**: Fetches and processes the completed data
5. **Google Sheets Storage**: Inserts structured data into a spreadsheet

### 📤 Output Data Points

| Field | Description | Example |
|-------|-------------|---------|
| user_posted | Username of tweet poster | `@elonmusk` |
| name | Display name | `Elon Musk` |
| description | Tweet content | `Exciting updates coming soon...` |
| date_posted | Timestamp of tweet | `2025-01-15T10:30:00Z` |
| likes | Likes count | `1234` |
| reposts | Retweets count | `567` |
| replies | Replies count | `89` |
| views | View count | `12345` |
| followers | Follower count | `50M` |
| following | Following count | `123` |
| is_verified | Verified status | `true` |
| hashtags | Hashtags used | `#AI #Technology` |
| photos | Image URLs | `image1.jpg` |
| videos | Video URLs | `video1.mp4` |
| user_id | Twitter User ID | `12345678` |
| timestamp | Extraction time | `2025-01-15T11:00:00Z` |

---

## ⚙ Setup Instructions

### ✅ Prerequisites
- [ ] n8n instance (cloud or self-hosted)
- [ ] Bright Data account with Twitter dataset access
- [ ] Google account (for Sheets integration)
- [ ] Valid Twitter profile URLs
- [ ] ~15 minutes setup time

---

### Step 1: Import Workflow
1. Open n8n
2. Go to `Workflows` → `+ Add workflow` → `Import from JSON`
3. Paste workflow JSON
4. Click **Import**

---

### Step 2: Configure Bright Data
- Add credentials in n8n: `Credentials → + Add credential → HTTP Header Auth`
- Enter your Bright Data API token
- Dataset ID example: `gd_lwxkxvnf1cynvib9co`
- Confirm dataset access in Bright Data dashboard

---

### Step 3: Set Up Google Sheets
1. Create a new Google Sheet (e.g., **Twitter Data**)
2. Prepare columns based on the output data points table above
3. Copy the Sheet ID from the URL
4. Add Google Sheets credential in n8n (`Google Sheets OAuth2 API`)
5. Test the credential connection

---

### Step 4: Update Workflow
- In the **Trigger Twitter Scraping** node:
  - Replace `BRIGHT_DATA_API_KEY` with your API token
  - Confirm the correct dataset ID
- In the **Store Twitter Data in Google Sheet** node:
  - Replace `YOUR_GOOGLE_SHEET_ID` with your actual Sheet ID
  - Set the correct credential and tab name

---

### Step 5: Test & Activate
- Use a small test date range (e.g., last 7 days)
- Submit the form with a valid Twitter URL
- Watch the workflow logs in n8n
- Check Google Sheets for data population

---

## 🧭 Usage Guide

1. Access the form trigger URL
2. Enter:
   - A valid Twitter profile URL
   - Start and end dates
3. Submit the form
4. Wait for completion (~1-5 mins)
5. Check Google Sheets for results

---

## 🔧 Customization Options

📄 License

MIT License

MIT License

Copyright (c) 2025 
