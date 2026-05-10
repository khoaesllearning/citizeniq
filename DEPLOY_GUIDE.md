# 🇺🇸 CitizenIQ – Complete Launch Guide
### From Zero to Live iPhone Web App (No Coding Experience Required)

---

## What You're Building

A Duolingo-style US Citizenship Test quiz game that:
- Works on iPhone (and any phone/browser)
- Has 100 official USCIS civics questions
- Tracks XP, streaks, and progress
- Is completely FREE to host

Your live URL will be: **https://YOUR-USERNAME.github.io/citizeniq**

---

## PHASE 1: One-Time Setup (Do This Once)

### Step 1 – Create a GitHub Account
If you don't have one:
1. Go to **github.com**
2. Click **Sign up**
3. Choose a username (this becomes part of your game URL!)
4. Verify your email

### Step 2 – Install Claude Code

Claude Code is an AI coding assistant that runs in your terminal (Mac/PC command line). It will help you customize and improve your game without you needing to write code yourself.

**On Mac:**
```bash
# Open Terminal (search "Terminal" in Spotlight: Cmd+Space)
curl -fsSL https://claude.ai/install.sh | bash
```

**On Windows:**
```
# Open PowerShell as Administrator, then:
# First install WSL (Windows Subsystem for Linux):
wsl --install
# Restart your computer, then open Ubuntu from Start Menu:
curl -fsSL https://claude.ai/install.sh | bash
```

After installation:
```bash
claude --version
# Should show something like: Claude Code v2.x.x
```

**Claude Code requires a Claude Pro or Max subscription ($20/month).** Sign up at claude.ai if you haven't.

### Step 3 – Install Git

Git is how you send your game files to GitHub.

**Mac:** Git usually comes pre-installed. Test with:
```bash
git --version
```
If not found, install Xcode Command Line Tools:
```bash
xcode-select --install
```

**Windows (in WSL/Ubuntu):**
```bash
sudo apt-get update && sudo apt-get install git -y
```

### Step 4 – Configure Git with Your Identity
```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```
(Use the same email as your GitHub account)

---

## PHASE 2: Put Your Game on GitHub

### Step 5 – Create a New Repository on GitHub
1. Log into **github.com**
2. Click the **+** icon (top right) → **New repository**
3. Repository name: `citizeniq`
4. Set to **Public**
5. ✅ Check **Add a README file**
6. Click **Create repository**

### Step 6 – Download Your Game to Your Computer

You received the `index.html` file alongside this guide. Save it somewhere easy to find (like your Desktop).

Now open Terminal (Mac) or Ubuntu (Windows) and run:

```bash
# Go to your home folder
cd ~

# Clone (download) your GitHub repository
git clone https://github.com/YOUR-USERNAME/citizeniq.git

# Go into the folder
cd citizeniq
```

Replace `YOUR-USERNAME` with your actual GitHub username.

### Step 7 – Add Your Game File

Copy the `index.html` file into the `citizeniq` folder you just cloned, replacing the README if needed.

Or use the terminal to copy it:
```bash
# If index.html is on your Desktop (Mac):
cp ~/Desktop/index.html ~/citizeniq/index.html

# Windows (WSL):
cp /mnt/c/Users/YOUR-WINDOWS-USERNAME/Desktop/index.html ~/citizeniq/index.html
```

### Step 8 – Upload to GitHub
```bash
# Make sure you're in the right folder
cd ~/citizeniq

# Stage all files
git add .

# Save a snapshot with a message
git commit -m "Launch CitizenIQ game"

# Upload to GitHub
git push origin main
```

When prompted, enter your GitHub username and password.
> ⚠️ **Note:** GitHub no longer accepts your regular password here. You need a **Personal Access Token**:
> 1. Go to github.com → Settings → Developer settings → Personal access tokens → Tokens (classic)
> 2. Generate new token → check **repo** → Generate
> 3. Copy the token and use it as your "password" when git asks

---

## PHASE 3: Turn on Free Hosting

### Step 9 – Enable GitHub Pages
1. Go to your repository: **github.com/YOUR-USERNAME/citizeniq**
2. Click the **Settings** tab
3. In the left sidebar, click **Pages**
4. Under "Source", select **Deploy from a branch**
5. Branch: **main** / Folder: **/ (root)**
6. Click **Save**

Wait 1-2 minutes, then visit:
**https://YOUR-USERNAME.github.io/citizeniq**

🎉 **Your game is live!**

---

## PHASE 4: Use Claude Code to Customize Your Game

This is where the magic happens. Claude Code can modify your game for you — just describe what you want in plain English.

### Starting Claude Code
```bash
# Navigate to your game folder
cd ~/citizeniq

# Start Claude Code
claude
```

You'll see a prompt like `>`. Now just type what you want in English!

### Example Requests You Can Give Claude Code

**Add more questions:**
```
Add 20 more US citizenship test questions about the American flag and holidays to the QUESTIONS array in index.html
```

**Change the colors:**
```
Change the game's main color theme from blue to red, white, and blue — more patriotic
```

**Add a difficulty setting:**
```
Add an Easy/Medium/Hard difficulty toggle on the home screen. Easy shows 3 options, Medium 4 options, Hard has a timer
```

**Add sound effects:**
```
Add a satisfying "ding" sound on correct answers and a buzzer on wrong answers using the Web Audio API
```

**Add more categories:**
```
Add two new quiz categories: "Symbols & Holidays" and "Geography" with 10 questions each
```

**After Claude makes changes, deploy them:**
```bash
git add .
git commit -m "Added new features"
git push origin main
```

Your live game updates in about 1-2 minutes!

---

## PHASE 5: Share Your Game

### Your Game URL
```
https://YOUR-USERNAME.github.io/citizeniq
```

### Add to iPhone Home Screen (Feels Like a Real App!)
1. Open Safari on iPhone
2. Go to your game URL
3. Tap the **Share** button (box with arrow)
4. Scroll down → tap **Add to Home Screen**
5. Name it "CitizenIQ" → tap **Add**

Now it has its own icon and opens fullscreen like a native app!

### Share with Others
- Text/email the URL to friends
- Post on Reddit (r/immigration, r/citizenship)
- Share in Facebook groups for immigration/citizenship

---

## Troubleshooting

**"git: command not found"** → Install git (Step 3)

**"Permission denied" when pushing** → Use a Personal Access Token (Step 8 note)

**Game shows 404 error** → Wait 5 more minutes, or check that index.html is in the ROOT of the repository (not inside a subfolder)

**Game looks wrong on mobile** → Make sure you're opening with Safari, not Chrome, for best results

**Claude Code asks for API key** → Make sure you're logged in to claude.ai with a Pro/Max plan

---

## Cost Summary

| Thing | Cost |
|-------|------|
| GitHub account | FREE |
| GitHub Pages hosting | FREE |
| Custom domain (optional) | ~$12/year |
| Claude Pro (to use Claude Code) | $20/month |

Your game can handle unlimited visitors for free on GitHub Pages!

---

## Next Steps (Ask Claude Code!)

Once you're comfortable, here are ideas to grow your app:

- **Leaderboard** – Add Firebase (free tier) to store high scores
- **User accounts** – Let users create profiles and track progress
- **More languages** – Add Spanish translations for Spanish-speaking users studying for the test
- **Offline mode** – Make it work without internet using a Service Worker
- **Push notifications** – Remind users to practice daily

---

*Built with Claude Code + GitHub Pages. Questions? Use Claude Code and ask in plain English!*
