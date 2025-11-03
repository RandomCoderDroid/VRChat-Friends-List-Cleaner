# VRChat-Friends-List-Cleaner
VRChat Friend Cleaner (Full GUI) is a Python-based automation tool that lets you easily manage and declutter your VRChat friends list. It automatically scrapes your full friend list from the VRChat website, detects inactivity based on “Last Seen” timestamps, and allows you to safely unfriend inactive users through an intuitive graphical interface.

The tool supports Dry Run testing, automatic CSV backups, resume support (so you never lose progress), and full control over thresholds and speed. Designed for convenience, transparency, and safety — no credentials are stored or transmitted anywhere.


<p align="center">
  <img src="https://img.shields.io/badge/Python-3.11%2B-blue?logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/Firefox-Required-orange?logo=firefoxbrowser&logoColor=white" alt="Firefox Required">
  <img src="https://img.shields.io/badge/License-MIT-green.svg" alt="MIT License">
  <img src="https://img.shields.io/badge/Platform-Windows-lightgrey?logo=windows&logoColor=white" alt="Windows">
</p>

---

## ✨ Features

🧭 **Full Friends List Scraper**  
Automatically scrolls through all containers on VRChat’s web dashboard and collects your full friend list.

📜 **Saves Data to CSV**, including:
- Display Name  
- Profile URL  
- Last Seen Time  
- Removal Status  

🗓 **Automatic Inactivity Detection**  
Understands “a few seconds ago”, “3 months ago”, “1 year ago”, etc., and converts it to real-time day counts.

🧠 **Smart Resume**  
Remembers previously unfriended users to avoid accidental re-friending.

🖱 **One-Click GUI**  
No command line needed — everything runs from an intuitive window interface.

🧱 **Dry-Run Mode**  
Simulate unfriending without actually removing anyone. Perfect for testing.

---

## 🧰 Requirements

- 🐍 **Python 3.11+** (or any modern version)  
- 🌐 **Firefox Browser**  
- 📦 Python dependencies:
  ```bash
  pip install selenium pandas webdriver-manager

(Optional for building a standalone EXE)

pip install pyinstaller

⚙️ Quick Start

    Run the app:

    python vrc_friend_cleaner_fullgui.py

    Click “Scrape Friends List” → Log in to VRChat → Press OK when done.

        A CSV like vrchat_friends_full_YYYYMMDD_HHMMSS.csv will be created.

    Click “1) Open VRChat”, log in again, then press “2) I’m Logged In → Start” to begin cleaning.

    Friends inactive longer than your chosen threshold will be automatically unfriended (or simulated in Dry-Run mode).

🧾 CSV Columns
Column	Description
display_name	VRChat user’s display name
profile_url	Direct link to the user’s profile
status_title	(Reserved) user’s current status
removed	TRUE if unfriended
last_seen_text	Example: “2 months ago”
last_seen_days	Days converted from the text
last_checked	Timestamp of last verification
last_action	keep / unfriend / would_unfriend / skip / error
🚀 Building an Executable

To create a portable .exe:

pyinstaller --noconfirm --onefile --noconsole --icon=icon.ico --name "VRChat Friend Cleaner" vrc_friend_cleaner_fullgui.py

Output appears in the dist/ folder as:

VRChat Friend Cleaner.exe

🧩 Notes

    Designed for the VRChat Web Dashboard → https://vrchat.com/home

    Works via Firefox + Selenium WebDriver

    Reads “Last Seen” values from .tw-pl-1 text on profiles

    Auto-saves every 5 users

    Pressing Stop safely halts progress and ensures the next run resumes correctly

🛡 Safety

✅ Dry Run Mode = No real unfriending
🔒 No credentials stored – Authentication happens only through the live VRChat website
🧾 CSV Backups – All actions are logged and timestamped locally
❤️ Credits

Developed by: RandomCoderDroid

🧠 Built with Python, Selenium, and Tkinter
🎮 Designed to help keep your VRChat friend list clean, organized, and stress-free.
