# Installation Guide

*Detailed technical instructions for installing Courtroom Copilot*

## Installation Methods

Courtroom Copilot can be installed through multiple methods depending on your technical expertise and requirements.

### Standard Installation

Follow this method for the typical user experience with graphical installation:

#### Windows

1. Download the latest Windows installer `.exe` or `.zip` package from the [Releases page](https://github.com/courtroom-copilot-public/releases)
2. If using ZIP:
   - Extract to a location of your choice
   - Run `CourtCopilot-Setup.exe` from the extracted folder
3. If using installer:
   - Run the downloaded `.exe` file
   - Follow on-screen prompts
   - Choose installation directory (default recommended)
4. Allow the installer to create desktop and start menu shortcuts if desired
5. The application will launch automatically after installation

#### macOS

1. Download the `.dmg` file from the [Releases page](https://github.com/courtroom-copilot-public/releases)
2. Open the downloaded DMG file
3. Drag the Courtroom Copilot icon to your Applications folder
4. Close the DMG window and eject the disk image
5. In your Applications folder, right-click Courtroom Copilot and select "Open"
6. If prompted about an unidentified developer, click "Open" to override
7. The application will launch for setup

#### Linux

1. Download the `.AppImage` file from the [Releases page](https://github.com/courtroom-copilot-public/releases)
2. Open a terminal and navigate to your download location
3. Make the AppImage executable:
   ```bash
   chmod +x CourtCopilot-linux-x64.AppImage
   ```
4. Run the application:
   ```bash
   ./CourtCopilot-linux-x64.AppImage
   ```
5. For integration with your desktop environment, consider using AppImageLauncher

### Advanced Installation Methods

#### Command Line Installation (All Platforms)

For users comfortable with terminal/command line:

```bash
# Clone the repository
git clone https://github.com/courtroom-copilot/courtroom-copilot.git

# Navigate to repository
cd courtroom-copilot

# Install dependencies
npm install

# Build the application
npm run build

# Start the application
npm start
```

#### Docker Installation

For isolated environments or server deployment:

```bash
# Pull the Docker image
docker pull courtroom-copilot/app:latest

# Run the container
docker run -d \
  --name courtroom-copilot \
  -p 3000:3000 \
  -v copilot-data:/app/data \
  courtroom-copilot/app:latest
```

Access via browser at `http://localhost:3000`

## Post-Installation Setup

### Domain Module Installation

After initial installation, you'll need to install legal domain modules:

1. Launch Courtroom Copilot
2. Navigate to Settings > Modules
3. Select your jurisdiction (e.g., "Australia - Federal")
4. Choose domain modules relevant to your needs:
   - Family Law
   - Tenancy Disputes
   - Small Claims
   - Employment
   - Consumer Protection
   - Criminal Defense (Basic)
5. Click "Download Selected Modules"
6. Wait for download and installation to complete (500MB-2GB per module)

### Local Model Configuration

Courtroom Copilot uses on-device AI models that can be configured:

1. Go to Settings > AI Configuration
2. Choose performance level:
   - Balanced (default): Good performance on moderate hardware
   - Performance: Faster responses, less detail
   - Quality: More thorough answers, requires better hardware
3. Disk Space: Adjust how much storage to allocate for document indexing
4. Memory Usage: Configure RAM allocation for AI processing

### Verification

To verify correct installation:

1. Go to Help > Run Diagnostic
2. The system will check:
   - Model integrity
   - Module installation
   - Local storage access
   - Voice input (if enabled)
3. Review the diagnostic report and address any issues

## Troubleshooting

### Common Installation Issues

**Windows: "Missing DLL" Errors**
- Install the latest Visual C++ Redistributable Package from Microsoft
- Reboot your system and try again

**macOS: "App is Damaged" Warning**
- Open System Preferences > Security & Privacy
- Click "Open Anyway" for Courtroom Copilot
- If not visible, try right-clicking the app and selecting "Open"

**Linux: AppImage Won't Launch**
- Ensure FUSE is installed: `sudo apt install libfuse2`
- Check file permissions: `chmod +x CourtCopilot-linux-x64.AppImage`

### Module Download Failures

If legal modules fail to download:

1. Check your internet connection
2. Try the "Verify and Repair" option in Settings > Modules
3. Download individual modules rather than in bulk
4. Use the "Alternative Download" option for slower but more reliable transfer

### Performance Issues

If the application runs slowly:

1. Check that you meet minimum system requirements
2. Close other resource-intensive applications
3. In Settings > AI Configuration, adjust to "Performance" mode
4. Reduce the number of documents indexed in your case

## Uninstallation

### Windows
- Use "Add or Remove Programs" in Windows Settings
- Alternatively, run the uninstaller from the installation directory

### macOS
- Drag the application from Applications to Trash
- For complete removal, also delete:
  ```
  ~/Library/Application Support/CourtCopilot
  ~/Library/Caches/CourtCopilot
  ```

### Linux
- Delete the AppImage file
- Remove data directory: `rm -rf ~/.config/courtroom-copilot`

## Data Security Note

Courtroom Copilot stores all case data locally on your device by default. No information is transmitted to remote servers. For added security:

1. Consider encrypting your drive using your operating system's encryption features
2. Enable the application's built-in encryption in Settings > Security
3. Regularly back up your case data using File > Export Backup

---

For advanced installation scenarios or custom deployments, please consult the [Developer Documentation](./DEVELOPER_GUIDE.md) or open an issue on GitHub.