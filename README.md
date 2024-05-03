# Network Scanner Web App

## Introduction
This project provides a simple network scanner that can be accessed from any web browser on your network. Utilizing a Cron Job that triggers every 10 minutes, the scanner uses `nmap` to scan the network and outputs the results to a text file. A PHP script then formats these results and displays them in a web browser.

## Features
- **Automated Network Scanning:** Scans your network every 10 minutes.
- **Web Interface:** View network scan results through a browser interface.

## Prerequisites
Before you begin, ensure you have the following installed on a Linux system:
- Cron jobs for scheduling tasks (`crontab`)
- Proper permissions setup (`chmod`, `chown`)
- Apache2, PHP, and `nmap`

## Installation

### Step 1: Install Necessary Packages
Run the following commands to install Apache2, PHP, and nmap:
'''bash
sudo apt-get install apache2
sudo apt-get install php
sudo apt-get install nmap

### Step 2: Configure Permissions

**Warning:** The following configuration sets less secure permissions and is not recommended for production environments.

```bash
sudo chown ubuntu /var/www/html
sudo chmod 777 /var/www/html
