# 🎬 Reel Generator using Python

## 📘 Overview
The **Reel Generator** is a Python-based automation tool that creates short video reels by combining multiple video clips and background audio.  
It’s designed for creators, marketers, and developers who want to quickly produce social-media-ready reels (like Instagram Reels, YouTube Shorts, etc.) using simple scripts.

---

## ⚙️ Features
- 🖼️ Merge multiple video clips seamlessly  
- 🎵 Add background music or narration audio  
- 🪄 Auto-scale and crop videos for vertical format (1080x1920)  
- 💬 Optional text overlays and transitions  
- 📁 Outputs final MP4 file ready for social platforms  
- 🔄 Easily customizable parameters (duration, resolution, format)

---

## 🧰 Technologies Used
- **Python 3.10+**
- **FFmpeg** – video processing backend  
- **Flask** *(optional)* – if using as a web interface  
- **MoviePy / OpenCV** *(optional)* – for editing and transitions  
- **os, subprocess** – to handle file operations

---

## 🧑‍💻 Installation

### 1. Clone the repository
```bash
git clone https://github.com/abhay0727/vidsnapai_reelgenerator.git
cd vidsnapai_reelgenerator
```

### 2. Create a virtual environment
```bash
python -m venv venv
source venv/bin/activate      # On Mac/Linux
venv\Scripts\activate         # On Windows
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

### 4. Install FFmpeg
Make sure FFmpeg is installed and accessible from your system path.

- **Windows:** Download from [FFmpeg.org](https://ffmpeg.org/download.html)
- **Linux/macOS:**  
  ```bash
  sudo apt install ffmpeg
  ```

---

## ▶️ Usage

### 💡 Example: Generate a reel from clips and audio
```bash
python generate_reel.py --input_videos ./clips/ --audio ./music/bg.mp3 --output ./reels/final_reel.mp4
```

### ⚙️ Parameters
| Argument | Description | Example |
|-----------|--------------|----------|
| `--input_videos` | Folder path containing video clips | `./clips/` |
| `--audio` | Background music or voiceover | `./music/bg.mp3` |
| `--output` | Output file path | `./reels/output.mp4` |
| `--resolution` | Output video resolution | `1080x1920` |
| `--duration` | Max duration of reel | `30` |

---

## 🧩 Project Structure
```
reel-generator/
│
├── clips/                # Input video clips
├── music/                # Background music/audio
├── reels/                # Output reels
├── generate_reel.py      # Main script
├── requirements.txt      # Dependencies
└── README.md             # Documentation
```

---

## 🚀 Example FFmpeg Command (used internally)
```bash
ffmpeg -f concat -safe 0 -i input.txt -i audio.mp3 \
-vf "scale=1080:1920:force_original_aspect_ratio=decrease,pad=1080:1920:(ow-iw)/2:(oh-ih)/2:black" \
-c:v libx264 -c:a aac -shortest output.mp4
```

This command:
- Concatenates multiple videos  
- Adds background audio  
- Scales and pads to 1080×1920 (vertical)  
- Exports a ready-to-post reel  

---

## 💬 Example Output
A 30-second vertical video reel with:
- Merged video clips  
- Background music  
- Auto-adjusted aspect ratio  

---

## 🧠 Future Improvements
- Add transitions and filters  
- Support subtitles or text overlay  
- Add web UI using Flask or Streamlit  
- Integrate AI-based scene detection  



> 🎥 *“Create, automate, and post your reels in seconds — all with Python.”*
