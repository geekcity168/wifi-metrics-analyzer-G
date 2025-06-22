# WiFi Metrics Analyzer v2.0

A comprehensive WiFi monitoring and analysis tool with modern UI, desktop notifications, and advanced features.

![WiFi Analyzer](https://img.shields.io/badge/Python-3.7+-blue)
![Platform](https://img.shields.io/badge/Platform-Linux%20%7C%20Windows%20%7C%20macOS-green)
![License](https://img.shields.io/badge/License-MIT-yellow)

## 🚀 Features

### Core Monitoring
- **Real-time Signal Strength**: Visual gauge with dBm readings and quality percentage
- **Internet Speed Testing**: Download, upload speeds and ping latency measurement
- **Network Usage Tracking**: Live graphs showing real-time bandwidth utilization
- **Connected Device Discovery**: Scan and identify devices on your network
- **Interface Management**: Support for multiple WiFi interfaces with easy switching

### Modern UI & UX
- **Dark Theme**: Modern glassmorphism design with cyan accents
- **Responsive Layout**: Optimized for different screen sizes
- **Real-time Graphs**: Animated charts for signal strength and network usage
- **Interactive Controls**: Hover effects and smooth transitions
- **Status Indicators**: Color-coded quality indicators (green/yellow/red)

### Smart Notifications
- **Desktop Alerts**: Cross-platform notifications for connection issues
- **Signal Threshold Monitoring**: Configurable low/critical signal warnings
- **Connection Stability Tracking**: Alerts for frequent disconnections
- **Customizable Settings**: Adjust notification thresholds and cooldown periods

### Advanced Features
- **Network Diagnostics**: Comprehensive connectivity testing and analysis
- **Data Export**: Export reports (JSON) and raw data (CSV) for analysis
- **Historical Data**: Track signal quality and network performance over time
- **Keyboard Shortcuts**: Quick access to common functions (F5, F11, Ctrl+R, etc.)
- **Always-on-Top Mode**: Keep the window visible while working
- **Fullscreen Support**: Distraction-free monitoring mode

## 📋 Requirements

- **Python**: 3.7 or higher
- **Operating System**: Linux (primary), Windows, macOS
- **Privileges**: Root/sudo access for full functionality (device scanning, interface monitoring)
- **Dependencies**: Listed in requirements.txt

## 🛠️ Installation

### 1. Clone the Repository
```bash
git clone https://github.com/geekcity168/wifi-metrics-G.git
cd wifi-metricsg
```

### 2. Create Virtual Environment
```bash
python3 -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. System Packages (Linux)
For full functionality on Linux, install additional system packages:
```bash
# Ubuntu/Debian
sudo apt-get install wireless-tools net-tools

# Kali Linux
sudo apt install wireless-tools net-tools python3-tk

# For notifications
sudo apt install libnotify-bin  # Optional, for fallback notifications
```

## 🚀 Usage

### Basic Usage
```bash
# Activate virtual environment
source venv/bin/activate

# Run the application
python src/main.py

# Or with specific interface
python src/main.py -i wlan0

# With debug logging
python src/main.py --debug
```

### Running with Elevated Privileges
For full functionality (device scanning, accurate signal monitoring):
```bash
sudo venv/bin/python src/main.py
```

### Command Line Options
```bash
python src/main.py [OPTIONS]

Options:
  -i, --interface TEXT    Specify WiFi interface to use
  --no-gui               Run in command-line mode (basic info only)
  --debug                Enable debug logging
  --force-root           Force application to run with sudo
  --version              Show version information
  -h, --help             Show help message
```

## 🎮 User Interface Guide

### Main Dashboard

#### 1. Signal Strength Panel
- **Gauge Visualization**: Semi-circular gauge showing signal quality (0-100%)
- **Signal Metrics**: dBm strength, quality percentage, bit rate, frequency
- **Color Coding**:
  - 🟢 Green (70-100%): Excellent signal
  - 🟡 Yellow (30-69%): Good signal
  - 🔴 Red (0-29%): Poor signal

#### 2. Speed Test Panel
- **On-Demand Testing**: Click "Run Speed Test" for internet speed analysis
- **Progress Indication**: Real-time progress bar during testing
- **Results Display**: Download/upload speeds (Mbps/Gbps) and ping (ms)
- **History Tracking**: Maintains record of recent speed tests

#### 3. Network Usage Panel
- **Live Graphs**: Real-time download/upload bandwidth visualization
- **Rate Display**: Current transfer rates in KB/s or MB/s
- **Historical Data**: 60-point rolling history for trend analysis
- **Time Labels**: X-axis shows timestamps for data points

#### 4. Connected Devices Panel
- **Device Discovery**: Scan for devices on your network
- **Device List**: IP addresses and MAC addresses of found devices
- **Device Count**: Total number of connected devices
- **Refresh Capability**: Re-scan network for updated device list

#### 5. Settings Panel
- **Notification Toggle**: Enable/disable desktop notifications
- **Threshold Configuration**: Set low and critical signal strength warnings
- **Refresh Interval**: Adjust how often metrics are updated
- **Real-time Adjustment**: Changes apply immediately

### Menu System

#### File Menu
- **Export Report**: Save comprehensive analysis as JSON
- **Export Data**: Export raw metrics as CSV for external analysis
- **Settings**: Open advanced configuration dialog
- **Exit**: Close application

#### View Menu
- **Full Screen (F11)**: Toggle fullscreen mode
- **Always on Top**: Keep window above other applications
- **Refresh All (F5)**: Manually refresh all data

#### Tools Menu
- **Network Diagnostics**: Run comprehensive network tests
- **Connection Test**: Quick internet connectivity verification
- **WiFi Signal History**: Detailed historical signal analysis
- **Reset All Data**: Clear all collected metrics and history

#### Help Menu
- **User Guide**: Comprehensive application documentation
- **Keyboard Shortcuts**: List of hotkeys and shortcuts
- **About**: Application information and version details

## ⚙️ Configuration

### Notification Settings
- **Low Signal Threshold**: Default 30% (configurable 10-80%)
- **Critical Signal Threshold**: Default 15% (configurable 5-50%)
- **Notification Cooldown**: 30 seconds between similar alerts
- **Cross-platform Support**: Works on Linux, Windows, and macOS

### Monitoring Configuration
- **Update Interval**: 1 second (configurable 1-60 seconds)
- **History Length**: 60 data points for graphs
- **Connection Tracking**: 100 connection stability measurements
- **Auto-refresh**: Continuous monitoring when application is active

### Advanced Options
- **Debug Logging**: Detailed application logs for troubleshooting
- **Auto-save**: Automatic configuration preservation
- **Interface Detection**: Automatic WiFi adapter discovery
- **Privilege Checking**: Smart detection of required permissions

## 🔧 Troubleshooting

### Common Issues

#### No WiFi Interfaces Detected
```bash
# Check wireless interfaces
iwconfig

# Verify wireless tools installation
sudo apt install wireless-tools

# Run with elevated privileges
sudo python src/main.py
```

#### Notifications Not Working
```bash
# Install notification dependencies
pip install plyer

# For Linux fallback notifications
sudo apt install libnotify-bin

# Check notification permissions in system settings
```

#### Device Scanning Issues
```bash
# Run with root privileges for network scanning
sudo python src/main.py

# Check firewall settings
sudo ufw status

# Verify network interface is up
ip link show
```

#### Speed Test Failures
```bash
# Check internet connectivity
ping google.com

# Install speedtest-cli
pip install speedtest-cli

# Test from command line
speedtest-cli
```

### Debug Mode
Enable detailed logging for troubleshooting:
```bash
python src/main.py --debug

# Check log file
tail -f ~/.wifi-metrics-analyzer.log
```

### Performance Optimization
- Increase update interval for slower systems
- Reduce history length to save memory
- Disable notifications if not needed
- Close unused features to reduce CPU usage

## 📊 Data Export

### JSON Reports
Comprehensive reports include:
- Current signal metrics
- Network usage statistics
- Interface information
- Speed test results
- Connected devices
- Historical data
- Configuration settings

### CSV Data Export
Raw data files contain:
- Timestamp
- Signal quality (%)
- Signal level (dBm)
- Connection status
- Network usage (KB/s)

## 🔒 Security & Privacy

- **Local Processing**: All analysis performed locally
- **No Data Collection**: No personal information sent to external servers
- **Network Scanning**: Only scans local network segment
- **Privilege Requirements**: Clearly documented why root access is needed
- **Log Management**: Logs stored locally with rotation

## 🛡️ System Requirements

### Minimum Requirements
- **RAM**: 512 MB
- **CPU**: Any modern processor
- **Display**: 800x600 resolution
- **Python**: 3.7+
- **Network**: WiFi adapter with driver support

### Recommended Requirements
- **RAM**: 1 GB or more
- **CPU**: Dual-core processor
- **Display**: 1024x768 or higher
- **Python**: 3.9+
- **Network**: Modern WiFi adapter (802.11n or newer)

## 🤝 Contributing

We welcome contributions! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

### Development Setup
```bash
# Clone repository
git clone https://github.com/yourusername/wifi-metricsg.git
cd wifi-metricsg

# Create development environment
python3 -m venv dev-venv
source dev-venv/bin/activate
pip install -r requirements.txt
pip install -r requirements-dev.txt  # If exists

# Run tests
python -m pytest tests/

# Code formatting
black src/
flake8 src/
```

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **Python Libraries**: psutil, scapy, matplotlib, tkinter, plyer
- **System Tools**: iwconfig, ip, ping
- **UI Inspiration**: Modern dashboard designs and glassmorphism trends
- **Community**: Thanks to all contributors and users providing feedback

## 📞 Support

- **Issues**: [GitHub Issues](https://github.com/geekcity168/wifi-metrics-G/issues)
- **Documentation**: Built-in help system (Help → User Guide)
- **Logs**: Check `~/.wifi-metrics-analyzer.log` for detailed information
- **Community**: Discussions and support in GitHub Discussions

---

**Made with ❤️ for network administrators and WiFi enthusiasts**
