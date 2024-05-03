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

```bash
sudo apt-get install apache2
sudo apt-get install php
sudo apt-get install nmap
```
### Step 2: Configure Permissions
Warning: The following configuration sets less secure permissions and is not recommended for production environments.

```bash
sudo chown ubuntu /var/www/html
sudo chmod 777 /var/www/html
```

### Step 3: Cron Job Setup
Open your crontab configuration:

```bash
sudo crontab -e
```

Add the following line to schedule an nmap scan every 10 minutes:
```bash
*/10 * * * * nmap 192.xxx.x.x/24 -oN /var/www/html/nmap.html
```

## Usage

### Viewing the Network Scans
Navigate to the following PHP script on your server to view the scan results:

```
URL: http://<server-ip>/network.php
```

Here is the PHP code used (network.php):

```php
Copy code
<?php
echo "Server Timestamp: ";
echo date("h:i:sa");

echo "<pre>";
include("nmap.html");
echo "</pre>";
```

## Conclusion
This network scanner project automates the process of scanning your network and viewing the results through a web interface. It demonstrates the power of integrating nmap, Cron jobs, and PHP to create a simple, yet effective network management tool.



