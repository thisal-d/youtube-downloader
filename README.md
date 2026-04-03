<p align="center">
  <img src="src/icon/2.ico" alt="YouTube Downloader Logo" width="80"/>
</p>

<h1 align="center">YouTube Downloader</h1>

<p align="center">
  A feature-rich desktop application for downloading YouTube videos and audio, built with Python and CustomTkinter.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python"/>
  <img src="https://img.shields.io/badge/Platform-Windows-0078D6?style=for-the-badge&logo=windows&logoColor=white" alt="Windows"/>
  <img src="https://img.shields.io/badge/GUI-CustomTkinter-2B2B2B?style=for-the-badge" alt="CustomTkinter"/>
  <img src="https://img.shields.io/badge/Status-Outdated-red?style=for-the-badge" alt="Status"/>
</p>

> [!IMPORTANT]
> This version is **outdated** and no longer actively maintained.
> Check out the successor project: **[PyTube Downloader](https://github.com/Thisal-D/PyTube-Downloader)** for an improved and up-to-date experience.

---

## ✨ Features

| Feature | Description |
|---|---|
| 🎬 **Video Download** | Download YouTube videos in multiple resolutions (144p to 1080p+) |
| 🎵 **Audio-Only Download** | Extract audio tracks as MP3 (128kbps) |
| ⏸️ **Pause & Resume** | Pause active downloads and resume them at any time |
| 📊 **Live Progress Tracking** | Real-time progress bar, percentage, and file size indicators |
| 🖼️ **Thumbnail Previews** | Rounded-corner thumbnails with hover-to-brighten effects |
| 🎨 **Dual Themes** | Switch between **Dark** and **Ash** themes on the fly |
| 🔔 **Windows Notifications** | Native Windows 11 toast notifications on download complete/fail |
| 📂 **Custom Download Path** | Choose where your downloads are saved |
| 📋 **Right-Click Context Menu** | Built-in Select All, Cut, Copy, and Paste for the URL input |
| 🔄 **Auto Audio-Video Merge** | Automatically merges separate audio and video streams into a single MP4 |
| 📥 **Batch Downloads** | Add and manage multiple downloads simultaneously |

---

## 📸 Screenshots

<p align="center">
  <img src="https://github.com/Thisal-D/Youtube-Downloader/assets/93121062/a98c3a52-f9e4-4467-9087-749ce1f81055" width="45%"/>
  &nbsp;&nbsp;
  <img src="https://github.com/Thisal-D/Youtube-Downloader/assets/93121062/4de47abe-66d4-4131-ae8d-0671859836f6" width="45%"/>
</p>
<p align="center">
  <img src="https://github.com/Thisal-D/Youtube-Downloader/assets/93121062/c57e98c2-93cf-4d3b-a529-ce3f00a41aa3" width="45%"/>
  &nbsp;&nbsp;
  <img src="https://github.com/Thisal-D/Youtube-Downloader/assets/93121062/d27db295-1686-479b-bf08-fd77578233f6" width="45%"/>
</p>
<p align="center">
  <img src="https://github.com/Thisal-D/Youtube-Downloader/assets/93121062/19307c06-37a0-49ce-85cb-ee6d38922d23" width="45%"/>
  &nbsp;&nbsp;
  <img src="https://github.com/Thisal-D/Youtube-Downloader/assets/93121062/e08b3f3e-b7aa-42c5-9e71-769e37743621" width="45%"/>
</p>

---

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| [CustomTkinter 4.6.3](https://pypi.org/project/customtkinter/4.6.3/) | Modern themed GUI framework (built on Tkinter) |
| [pytube](https://pypi.org/project/pytube/) | YouTube video fetching, stream parsing, and downloading |
| [moviepy](https://pypi.org/project/moviepy/) | Audio-video merging for non-progressive streams |
| [Pillow](https://pypi.org/project/pillow/) | Thumbnail image processing (resize, crop, rounded corners) |
| [win11toast](https://pypi.org/project/win11toast/) | Windows 11 native toast notifications |
| [PyAutoGUI](https://pypi.org/project/PyAutoGUI/) | Keyboard shortcut simulation for copy/paste menu |

---

## 📁 Project Structure

```
youtube-downloader/
├── main.py                  # Application entry point & GUI layout
├── objects.py               # All custom widget classes & download logic
├── dependencies.txt         # Dependency listing
├── settings/
│   ├── download_path        # Persisted download directory path
│   └── theme                # Persisted theme preference (dark/ash)
└── src/                     # UI assets
    ├── icon/                # Application icons (.ico)
    ├── download button/     # Download button images
    ├── download path button/# Folder picker button images
    ├── loading/             # Loading spinner animation (GIF frames)
    ├── loading failed/      # Error state indicator images
    ├── pause/               # Pause button images (normal/hover)
    ├── resume/              # Resume button images (normal/hover)
    ├── reload button/       # Reload button images (normal/hover/clicked)
    └── remove button/       # Remove/delete button images
```

### Key Modules

- **`main.py`** — Sets up the root window, header with URL entry and Add button, tab navigation (Added / Downloading / Downloaded), theme switching, download path configuration, and the application lifecycle.
- **`objects.py`** — Contains all custom widget classes:
  - `AddedVideoObject` — Fetches video metadata (title, channel, thumbnail, available resolutions) in a background thread and displays a resolution picker.
  - `DownloadingVideoObject` — Handles the download process with pause/resume support, progress tracking, and automatic audio-video merging via moviepy.
  - `DownloadedVideoObject` — Displays completed downloads with options to play the file or open its folder.
  - `scrollableFrame` — A custom scrollable container built on `Canvas` + `CTkScrollbar`.
  - `customButton` / `customButton_2` — Image-based and text-based buttons with normal/hover/clicked states.
  - `copy_paste_menu` — Right-click context menu with Select All, Cut, Copy, and Paste actions.
  - `credits_menu` — Hover-triggered credits tooltip.

---

## 🚀 Getting Started

### Prerequisites

- **Python 3.x**
- **Windows OS** (required for `win11toast` notifications and `os.startfile`)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/Thisal-D/youtube-downloader.git
   cd youtube-downloader
   ```

2. **Install dependencies**
   ```bash
   pip install customtkinter==4.6.3 pytube moviepy pillow win11toast pyautogui
   ```

   > [!WARNING]
   > You **must** use `customtkinter==4.6.3`. Other versions may cause compatibility issues with the GUI layout.

3. **Run the application**
   ```bash
   python main.py
   ```

---

## 📖 How to Use

1. **Launch** the application by running `main.py`.
2. **Paste** a YouTube video URL into the input field at the top.
3. **Click "Add"** — the app fetches video info (title, channel, thumbnail, available qualities) in the background.
4. **Select a resolution** from the dropdown (video resolutions sorted highest-first, plus a 128kbps audio-only option).
5. **Click the download button** (▶) to start downloading. The video moves to the **Downloading** tab.
6. **Monitor progress** — see the progress bar, percentage, and downloaded/total size in real time.
7. **Pause/Resume** downloads using the pause button.
8. Once done, find your video in the **Downloaded** tab — click the thumbnail to play or the folder icon to reveal in Explorer.
9. **Switch themes** using the Dark / Ash buttons in the top-right corner.
10. **Change download path** with the folder icon next to the Add button (defaults to `~/Downloads/YT Downloader`).

---

## 👥 Contributors

| Contributor | Role |
|---|---|
| [<img src="https://github.com/Thisal-D.png?size=30" width="30" style="border-radius:50%"/>](https://github.com/Thisal-D) [**Thisal D**](https://github.com/Thisal-D) | Developer |
| [<img src="https://github.com/sooryasuraweera.png?size=30" width="30" style="border-radius:50%"/>](https://github.com/sooryasuraweera) [**Soorya Suraweera**](https://github.com/sooryasuraweera) | UI Designer |

---

## 📄 License

This project is open source. Feel free to fork, modify, and use it for personal or educational purposes.

---

<p align="center">
  <b>⭐ If you found this project helpful, consider starring the repo!</b>
</p>

<p align="center">
  <a href="https://github.com/Thisal-D/PyTube-Downloader">
    <img src="https://img.shields.io/badge/Try_the_new_version-PyTube_Downloader-FF0000?style=for-the-badge&logo=youtube&logoColor=white" alt="New Version"/>
  </a>
</p>
