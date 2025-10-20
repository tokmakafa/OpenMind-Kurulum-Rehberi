# 🤖 Deploy Your First Robot on OpenMind Fabric Portal

A comprehensive guide for setting up and deploying an OM1 agent on macOS and Linux systems.

---

## 📋 Table of Contents
- [Requirements](#-requirements)
- [macOS Installation](#-macos-installation)
- [Linux Installation](#-linux-installation)
- [Verification](#-verification)
- [Troubleshooting](#-troubleshooting)
- [Next Steps](#-next-steps)

---

## 🔧 Requirements

### macOS
- macOS (Apple Silicon or Intel)
- Homebrew package manager
- OpenMind API Keys (get from OpenMind Fabric Portal - $5 credit for new users)

### Linux
- Ubuntu/Debian-based distribution
- Terminal access with sudo privileges
- Internet connection

---

## 🍎 macOS Installation

### Step 1: Homebrew Setup

If you don't have Homebrew installed, run this command in Terminal:
```bash
bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

### Verify Homebrew Installation
```bash
brew --version
```

### Step 2: Install PortAudio
```bash
brew install portaudio
```

### Step 3: Install FFmpeg
```bash
brew install ffmpeg
```

### Step 4: Install Rust
```bash
brew install rust
```

### Step 5: Install UV Package Manager
```bash
brew install uv
```

### Step 6: Clone OM1 Project
```bash
git clone https://github.com/OpenMindAGI/OM1.git
```

### Navigate to Project Directory
```bash
cd OM1
```

### Step 7: Update Git Submodules
```bash
git submodule update --init
```

### Step 8: Create Virtual Environment
```bash
uv venv
```

### Step 9: Run the Setup
```bash
bash scripts/setup.sh
```

---

## 🐧 Linux Installation

### Step 1: Update System
```bash
sudo apt-get update
```

### Step 2: Install PortAudio and Python Dev Packages
```bash
sudo apt-get install portaudio19-dev python-all-dev -y
```

### Step 3: Install FFmpeg
```bash
sudo apt-get install ffmpeg -y
```

### Step 4: Install ALSA Utils
```bash
sudo apt-get install alsa-utils -y
```

### Load Sound Module
```bash
sudo modprobe snd-dummy
```

### Step 5: Download UV Installer
```bash
wget https://astral.sh/uv/install.sh
```

### Make Installer Executable
```bash
chmod +x install.sh
```

### Run UV Installer
```bash
./install.sh
```

### Step 6: Clone OM1 Repository
```bash
git clone https://github.com/OpenMindAGI/OM1.git
```

### Navigate to Project Directory
```bash
cd OM1
```

### Step 7: Update Git Submodules
```bash
git submodule update --init
```

### Step 8: Create Virtual Environment
```bash
uv venv
```

### Step 9: Run the Setup
```bash
bash scripts/setup.sh
```

---

## ✅ Verification

### Check Homebrew (macOS)
```bash
brew --version
```

### Check PortAudio (macOS)
```bash
brew list portaudio
```

### Check FFmpeg
```bash
ffmpeg -version
```

### Check Cargo (Rust)
```bash
cargo --version
```

### Check UV
```bash
uv --version
```

---

## 🔍 Troubleshooting

### macOS: Homebrew Command Not Found
```bash
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile
```
```bash
eval "$(/opt/homebrew/bin/brew shellenv)"
```

### Permission Denied Error
```bash
sudo chmod +x install.sh
```

### Linux: Update System Packages
```bash
sudo apt-get update
```
```bash
sudo apt-get upgrade
```

### Check Audio Devices
```bash
aplay -l
```

### Git Submodule Sync
```bash
git submodule sync
```
```bash
git submodule update --init --recursive
```

---

## 🚀 Next Steps

1. **Configure your API keys** in the OM1 project
2. **Set up your robot parameters** according to the documentation
3. **Run your first agent** using the provided scripts
4. **Connect to OpenMind Fabric Portal** to monitor your deployment

---

## 📚 Additional Resources

- [OpenMind Fabric Portal](https://openmind.com)
- [Homebrew Documentation](https://docs.brew.sh)
- [UV Documentation](https://github.com/astral-sh/uv)

---

## 🤝 Contributing

Contributions are welcome! Feel free to:
- Report bugs
- Suggest new features
- Submit pull requests
- Improve documentation

---

## 📝 License

This guide is provided as-is for educational purposes.

---

## ⚠️ Important Notes

- When running commands with `sudo`, you'll be prompted for your password
- Password characters won't be visible while typing (security feature)
- Ensure stable internet connection during installation
- Backup your system before making major changes

---

## 💡 Tips

- Use `Tab` key for auto-completion in Terminal
- Use `↑` arrow key to recall previous commands
- Keep your system and packages updated regularly

---

**Made with ❤️ for the OpenMind Community**

*For support and questions, please refer to the official OpenMind documentation or community forums.*
