📲 Social Video Downloader

A fast and simple web app that allows users to download videos from multiple 
social media platforms including Instagram, TikTok, Twitter and more — built 
and deployed on Vercel.

🌐 **Live Demo:** https://social-video-downloader-nu.vercel.app

---

## 🚀 Features

- 📥 **Download videos** from multiple social platforms
- 🎬 **Supports Instagram, TikTok, Twitter** and more
- ⚡ **Fast processing** — quick download generation
- 🔗 **Simple UI** — just paste the URL and download
- 📱 **Fully responsive** — works on desktop and mobile
- 🎵 **Audio extraction** — download audio only if needed

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| Next.js / React | Frontend framework |
| yt-dlp | Video processing and extraction |
| Vercel | Deployment and hosting |
| Tailwind CSS | Styling and UI |

---

## 🔄 How It Works
User Pastes Social Media Video URL

↓

App Validates the URL & Platform

↓

yt-dlp Fetches Video Info

↓

User Selects Format & Quality

↓

Video Downloaded & Delivered

---

## ⚙️ Setup & Installation

1. Clone the repository
```bash
git clone https://github.com/greatman-786/social-video-downloader.git
cd social-video-downloader
```

2. Install dependencies
```bash
npm install
```

3. Run locally
```bash
npm run dev
```

4. Open `http://localhost:3000`

---

## 📁 Project Structure
social-video-downloader/

│

├── pages/          # Next.js pages

├── components/     # Reusable UI components

├── styles/         # Tailwind CSS styles

├── lib/            # yt-dlp integration logic

└── README.md       # Project documentation

---

## ⚡ Challenges & How I Solved Them

### 1. 🚀 Serverless Environment Limitations
**Problem:** yt-dlp is a command-line tool that doesn't run reliably inside 
Vercel's serverless functions — it requires a persistent runtime environment 
which serverless functions simply don't provide.  
**Solution:** Identified the architectural mismatch early and documented it 
clearly. For a production version, the solution would be to move yt-dlp 
processing to a **dedicated backend server** (VPS or containerised service) 
while keeping the frontend on Vercel.

### 2. 🔒 Platform Anti-Scraping Measures
**Problem:** Social media platforms like Instagram and TikTok frequently 
update their anti-scraping measures, causing download requests to fail 
without warning.  
**Solution:** Kept yt-dlp updated to the latest version which includes 
patches for platform changes, and added clear **error messaging** to inform 
users when a platform temporarily blocks requests.

### 3. ⏱️ Download Timeout Issues
**Problem:** Large video files took too long to process, hitting Vercel's 
serverless function timeout limits before downloads completed.  
**Solution:** Implemented a **streaming approach** where video data is piped 
directly to the user rather than being fully buffered server-side first — 
reducing timeout risk and improving download speed.

### 4. 📱 Mobile Download Compatibility
**Problem:** Download links behaved differently across browsers and mobile 
devices — some opened the video in a new tab instead of triggering a download.  
**Solution:** Used proper **Content-Disposition headers** and download 
attribute handling to ensure consistent download behaviour across all 
browsers and devices.

---

## 💡 Use Cases

- Saving social media videos for offline viewing
- Content creators downloading reference material
- Archiving important video content
- Downloading videos for personal use

---

## 📌 Note

This app is built for **educational and personal use only**. Always respect 
the Terms of Service of each social media platform and content creators' 
rights when downloading videos.

---

## 🙋‍♂️ Author

**Asad** — Software Engineer  
Building practical web applications for real-world use cases
