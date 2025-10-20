🤖 Deploy Your First Robot on OpenMind Fabric Portal
A comprehensive guide for setting up and deploying an OM1 agent on macOS and Linux systems.

📋 Table of Contents

Requirements
macOS Installation
Linux Installation
Verification
Troubleshooting
Next Steps


🔧 Requirements
macOS

macOS (Apple Silicon or Intel)
Homebrew package manager
OpenMind API Keys (get from OpenMind Fabric Portal - $5 credit for new users)

Linux

Ubuntu/Debian-based distribution
Terminal access with sudo privileges
Internet connection


🍎 macOS Installation
Step 1: Homebrew Setup
If you don't have Homebrew installed, run this command in Terminal:
bashbash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
After installation, verify Homebrew is working:
bashbrew --version
Step 2: Install Required Dependencies
Install PortAudio, FFmpeg, and Rust:
bashbash# Install PortAudio, FFmpeg and Rust
brew install portaudio
brew install ffmpeg
brew install rust
Step 3: Install UV Package Manager
bashbrew install uv
Step 4: Clone OM1 Project
bash# Clone the project
git clone https://github.com/OpenMindAGI/OM1.git

# Navigate to project directory
cd OM1
Step 5: Update Git Submodules
bashgit submodule update --init
Step 6: Create Virtual Environment
bashuv venv
Step 7: Run the Setup
bashbash scripts/setup.sh

🐧 Linux Installation
Step 1: Install Required Packages
Update your system and install dependencies:
bash# Update package list
sudo apt-get update

# Install audio and Python development packages
sudo apt-get install portaudio19-dev python-all-dev -y

# Install FFmpeg
sudo apt-get install ffmpeg -y

# Install ALSA utilities
sudo apt-get install alsa-utils -y
sudo modprobe snd-dummy
Step 2: Install UV Package Manager
bashwget https://astral.sh/uv/install.sh
chmod +x install.sh
./install.sh
Step 3: Clone OM1 Repository
bashgit clone https://github.com/OpenMindAGI/OM1.git
cd OM1
Step 4: Update Git Submodules
bashgit submodule update --init
Step 5: Create Virtual Environment
bashuv venv
Step 6: Run the Setup
bashbash scripts/setup.sh

✅ Verification
After installation, verify everything is set up correctly:
Check Homebrew (macOS)
bashbrew --version
Check PortAudio
bashbrew list portaudio  # macOS
Check FFmpeg
bashffmpeg -version
Check Cargo (Rust)
bashcargo --version
Check UV
bashuv --version

🔍 Troubleshooting
macOS Issues
Problem: Homebrew command not found
bash# Add Homebrew to PATH
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"
Problem: Permission denied
bashsudo chmod +x install.sh
Linux Issues
Problem: Package installation fails
bashsudo apt-get update
sudo apt-get upgrade
Problem: Audio device issues
bash# Check available audio devices
aplay -l
Problem: Git submodule errors
bashgit submodule sync
git submodule update --init --recursive

🚀 Next Steps

Configure your API keys in the OM1 project
Set up your robot parameters according to the documentation
Run your first agent using the provided scripts
Connect to OpenMind Fabric Portal to monitor your deployment


📚 Additional Resources

OpenMind Fabric Portal
Homebrew Documentation
UV Documentation


🤝 Contributing
Contributions are welcome! Feel free to:

Report bugs
Suggest new features
Submit pull requests
Improve documentation


📝 License
This guide is provided as-is for educational purposes.

⚠️ Important Notes

When running commands with sudo, you'll be prompted for your password
Password characters won't be visible while typing (security feature)
Ensure stable internet connection during installation
Backup your system before making major changes


💡 Tips

Use Tab key for auto-completion in Terminal
Use ↑ arrow key to recall previous commands
Keep your system and packages updated regularly
