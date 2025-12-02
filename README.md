<div align="center">

<img src="https://user-images.githubusercontent.com/74038190/229223156-0cbdaba9-3128-4d8e-8719-b6b4cf741b67.gif" width="100%" alt="Hacker Header">

<br>

# SUBDOMAIN SCANNER

<img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&weight=600&size=24&duration=3000&pause=1000&color=00FF00&center=true&vCenter=true&width=600&lines=Passive+Reconnaissance+Tool;Stealth+Mode+Enabled;Multi-Threaded+Enumeration;Zero+Detection+Risk;Built+for+Bug+Hunters" alt="Typing SVG" />

<br>

[![Made by](https://img.shields.io/badge/Developed%20by-Mishra%20Chandan-00ff00?style=for-the-badge)](https://github.com/mishrachandan5512)
[![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)](LICENSE)
[![Platform](https://img.shields.io/badge/Platform-Termux%20%7C%20Android-red?style=for-the-badge)](https://github.com/mishrachandan5512)
[![Status](https://img.shields.io/badge/Status-Active-success?style=for-the-badge)](https://github.com/mishrachandan5512)

</div>

---

## OVERVIEW

**Subdomain Scanner** is a lightweight yet powerful reconnaissance tool engineered for **passive subdomain enumeration** using public datasets and APIs. Designed by security researcher **Mishra Chandan**, this tool ensures **zero direct interaction** with the target server during discovery, making it ideal for stealthy reconnaissance operations where avoiding detection is mission-critical.

The scanner leverages **multi-threading** to simultaneously query multiple intelligence sources including Certificate Transparency logs (crt.sh), HackerTarget, and AlienVault OTX. Optimized specifically for **Android (Termux)** environment, it provides security researchers with a fast and efficient method to map an organization's complete attack surface directly from their mobile device.

<div align="center">

```ascii
╔══════════════════════════════════════════════════════════════╗
║  TARGET: example.com                                                    ║
║  MODE: Passive Enumeration                                              ║
║  THREADS: Active                                                        ║
║  DETECTION: Zero Risk                                                   ║
╚══════════════════════════════════════════════════════════════╝
```

</div>

---

## KEY FEATURES

<table>
<tr>
<td width="50%">

### Stealth Operations
- **Passive Reconnaissance** - No direct packets to target
- **IP Protection** - Your identity stays hidden
- **Firewall Bypass** - Evades detection systems
- **Log-Free Operations** - Zero footprint

</td>
<td width="50%">

### Performance
- **Multi-Threaded Engine** - Concurrent execution
- **Lightning Fast** - Results in seconds
- **Resource Efficient** - Low memory footprint
- **Scalable** - Handles large domains

</td>
</tr>
<tr>
<td width="50%">

### Intelligence Sources
- **Certificate Transparency** (crt.sh)
- **HackerTarget API**
- **AlienVault OTX**
- **Custom Aggregation**

</td>
<td width="50%">

### Advanced Capabilities
- **Live DNS Verification**
- **Active Subdomain Detection**
- **Clean Output Format**
- **Duplicate Removal**

</td>
</tr>
</table>

---

## INSTALLATION ON TERMUX

### Step 1: Update and Upgrade Termux

```bash
pkg update && pkg upgrade -y
```

### Step 2: Install Required Packages

```bash
pkg install python -y
pkg install git -y
```

### Step 3: Clone the Repository

```bash
git clone https://github.com/mishrachandan5512/Subdomain-Scanner.git
```

### Step 4: Navigate to Directory

```bash
cd Subdomain-Scanner
```

### Step 5: Check Files

```bash
ls
```

**Expected Output:**
```text
README.md  subdomain_scanner.py
```

### Step 6: Install Python Dependencies (if requirements.txt exists)

```bash
pip install -r requirements.txt
```

**Note:** If no requirements.txt file exists, the tool uses only Python standard libraries.

### Step 7: Make Script Executable

```bash
chmod +x subdomain_scanner.py
```

### Step 8: Verify Installation

```bash
python subdomain_scanner.py -h
```

**Expected Output:**
```text
usage: subdomain_scanner.py [-h] -d DOMAIN [-o OUTPUT] [-v] [--check]

Core Scanner by Mishra Chandan

options:
  -h, --help            show this help message and exit
  -d DOMAIN, --domain DOMAIN
                        Target Domain (e.g., example.com)
  -o OUTPUT, --output OUTPUT
                        Save output to file
  -v, --verbose         Show verbose output
  --check               Check for live domains (DNS resolution)
```

---

## USAGE GUIDE

### Display Help Menu

```bash
python subdomain_scanner.py -h
```

### Basic Subdomain Scan

```bash
python subdomain_scanner.py -d example.com
```

### Save Results to File

```bash
python subdomain_scanner.py -d example.com -o results.txt
```

### Verbose Mode (Detailed Output)

```bash
python subdomain_scanner.py -d example.com -v
```

### Check Live Subdomains (DNS Resolution)

```bash
python subdomain_scanner.py -d example.com --check
```

### Full Scan with All Options

```bash
python subdomain_scanner.py -d example.com -o subdomains.txt -v --check
```

### Quick Recon for Bug Bounty

```bash
python subdomain_scanner.py -d target.com --check -o live_subdomains.txt
```

---

## COMMAND REFERENCE

<div align="center">

| Option | Short | Description | Required |
|:---|:---:|:---|:---:|
| `--domain` | `-d` | Target domain to scan | Yes |
| `--output` | `-o` | Save results to specified file | No |
| `--verbose` | `-v` | Enable detailed output | No |
| `--check` | - | Verify live domains via DNS | No |
| `--help` | `-h` | Show help message | No |

</div>

---

## USAGE EXAMPLES

### Example 1: Basic Enumeration

```bash
~/Subdomain-Scanner $ python subdomain_scanner.py -d hackerone.com
```

**Expected Output:**
```text
[+] Core Scanner by Mishra Chandan
[+] Target Domain: hackerone.com
[+] Starting passive enumeration...

[*] Querying Certificate Transparency...
[*] Querying HackerTarget API...
[*] Querying AlienVault OTX...

[+] Total unique subdomains found: 342

api.hackerone.com
www.hackerone.com
docs.hackerone.com
support.hackerone.com
gslink.hackerone.com
mta-sts.hackerone.com
...

[+] Scan completed
```

### Example 2: Save to File

```bash
~/Subdomain-Scanner $ python subdomain_scanner.py -d target.com -o results.txt
```

**Expected Output:**
```text
[+] Core Scanner by Mishra Chandan
[+] Target Domain: target.com
[+] Starting passive enumeration...

[*] Querying sources...

[+] Total unique subdomains found: 156
[+] Results saved to: results.txt
[+] Scan completed
```

### Example 3: Verbose Mode

```bash
~/Subdomain-Scanner $ python subdomain_scanner.py -d example.com -v
```

**Expected Output:**
```text
[+] Core Scanner by Mishra Chandan
[+] Target Domain: example.com
[+] Verbose mode enabled
[+] Starting passive enumeration...

[*] Querying Certificate Transparency (crt.sh)...
[DEBUG] Connecting to crt.sh...
[DEBUG] Response received: 200 OK
[✓] Found 89 subdomains from crt.sh

[*] Querying HackerTarget API...
[DEBUG] Connecting to HackerTarget...
[DEBUG] Response received: 200 OK
[✓] Found 67 subdomains from HackerTarget

[*] Querying AlienVault OTX...
[DEBUG] Connecting to AlienVault...
[DEBUG] Response received: 200 OK
[✓] Found 112 subdomains from AlienVault

[+] Aggregating results...
[+] Removing duplicates...
[+] Total unique subdomains found: 234

api.example.com
www.example.com
mail.example.com
...

[+] Scan completed in 15.3 seconds
```

### Example 4: Live Domain Check

```bash
~/Subdomain-Scanner $ python subdomain_scanner.py -d company.com --check
```

**Expected Output:**
```text
[+] Core Scanner by Mishra Chandan
[+] Target Domain: company.com
[+] Starting passive enumeration...

[*] Querying sources...
[+] Total unique subdomains found: 178

[*] Checking live domains (DNS resolution)...
[✓] api.company.com - LIVE
[✓] www.company.com - LIVE
[✗] old.company.com - NOT LIVE
[✓] mail.company.com - LIVE
[✗] dev.company.com - NOT LIVE
[✓] admin.company.com - LIVE
...

[+] Live subdomains: 134/178
[+] Scan completed
```

### Example 5: Complete Scan

```bash
~/Subdomain-Scanner $ python subdomain_scanner.py -d bugcrowd.com -o bugcrowd_subs.txt -v --check
```

**Expected Output:**
```text
[+] Core Scanner by Mishra Chandan
[+] Target Domain: bugcrowd.com
[+] Verbose mode enabled
[+] Live check enabled
[+] Starting passive enumeration...

[*] Querying Certificate Transparency (crt.sh)...
[✓] Found 156 subdomains from crt.sh

[*] Querying HackerTarget API...
[✓] Found 98 subdomains from HackerTarget

[*] Querying AlienVault OTX...
[✓] Found 201 subdomains from AlienVault

[+] Total unique subdomains found: 389

[*] Checking live domains (DNS resolution)...
[✓] api.bugcrowd.com - LIVE (104.18.34.112)
[✓] www.bugcrowd.com - LIVE (104.18.35.112)
[✓] tracker.bugcrowd.com - LIVE (52.84.167.89)
...

[+] Live subdomains: 312/389
[+] Results saved to: bugcrowd_subs.txt
[+] Scan completed in 24.8 seconds
```

---

## GIT COMMANDS REFERENCE

### Clone Repository

```bash
git clone https://github.com/mishrachandan5512/Subdomain-Scanner.git
```

### Update to Latest Version

```bash
cd Subdomain-Scanner
git pull origin main
```

### Check Repository Status

```bash
git status
```

### View Commit History

```bash
git log --oneline
```

### Create New Branch (For Contributors)

```bash
git checkout -b feature/new-feature
```

### Add and Commit Changes (For Contributors)

```bash
git add .
git commit -m "Added new feature"
```

### Push Changes (For Contributors)

```bash
git push origin feature/new-feature
```

### Fork and Clone Your Fork

```bash
# After forking on GitHub
git clone https://github.com/YOUR-USERNAME/Subdomain-Scanner.git
cd Subdomain-Scanner
git remote add upstream https://github.com/mishrachandan5512/Subdomain-Scanner.git
```

### Sync Your Fork

```bash
git fetch upstream
git checkout main
git merge upstream/main
git push origin main
```

---

## ADVANCED USAGE

### Scan Multiple Domains

```bash
for domain in hackerone.com bugcrowd.com intigriti.com; do
    python subdomain_scanner.py -d $domain -o ${domain}_subs.txt --check
done
```

### Filter Specific Subdomains

```bash
python subdomain_scanner.py -d target.com | grep -E "admin|dev|staging|test"
```

### Count Total Subdomains

```bash
python subdomain_scanner.py -d target.com -o subs.txt && wc -l subs.txt
```

### Sort and Remove Duplicates

```bash
python subdomain_scanner.py -d target.com -o subs.txt && sort -u subs.txt -o sorted_subs.txt
```

### Monitor New Subdomains

```bash
# Run every hour
while true; do
    python subdomain_scanner.py -d target.com -o scan_$(date +%Y%m%d_%H%M%S).txt
    sleep 3600
done
```


---

## USE CASES

<div align="center">

| Scenario | Command | Purpose |
|:---|:---|:---|
| **Bug Bounty Recon** | `python subdomain_scanner.py -d target.com --check` | Find live subdomains for testing |
| **Asset Discovery** | `python subdomain_scanner.py -d company.com -o assets.txt` | Map complete attack surface |
| **Quick Enumeration** | `python subdomain_scanner.py -d domain.com` | Fast subdomain discovery |
| **Deep Scan** | `python subdomain_scanner.py -d site.com -v --check -o full.txt` | Comprehensive analysis |
| **Passive OSINT** | `python subdomain_scanner.py -d target.com -v` | Intelligence gathering |

</div>

---

## SECURITY FEATURES

<div align="center">

```text
╔═══════════════════════════════════════════════════════╗
║           SECURITY FEATURES                                     ║
╠═══════════════════════════════════════════════════════╣
║  [+] Zero Direct Target Interaction                             ║
║  [+] No Logs on Target Systems                                  ║
║  [+] IP Address Protection                                      ║
║  [+] Public Data Sources Only                                   ║
║  [+] Compliant with Responsible Disclosure                      ║
╚═══════════════════════════════════════════════════════╝
```

</div>

**Important:** This tool is designed for authorized security testing only. Always obtain proper permission before scanning any domain you don't own.

---

## PERFORMANCE METRICS

<div align="center">

| Metric | Performance |
|:---:|:---:|
| **Average Scan Time** | 10-20 seconds |
| **Subdomains per Second** | 20-30 |
| **Memory Usage** | Less than 50 MB |
| **CPU Utilization** | Low-Medium |
| **Success Rate** | 95 percent plus |
| **Accuracy** | High (Public Data) |

</div>

---

## TROUBLESHOOTING

### Issue: No subdomains found

**Solution:**
```bash
# Check internet connection
ping google.com

# Try with verbose flag
python subdomain_scanner.py -d target.com -v
```

### Issue: DNS resolution errors

**Solution:**
```bash
# Run without --check flag
python subdomain_scanner.py -d target.com

# Or use different DNS
```

### Issue: Module not found

**Solution:**
```bash
# Reinstall Python
pkg install python -y

# Check Python version
python --version
```

### Issue: Permission denied

**Solution:**
```bash
# Make script executable
chmod +x subdomain_scanner.py

# Run with python explicitly
python subdomain_scanner.py -d target.com
```

---

## ROADMAP

- [x] Basic passive enumeration
- [x] Multi-threaded scanning
- [x] DNS verification
- [x] Verbose output mode
- [x] File output support
- [ ] Integration with more sources (SecurityTrails, VirusTotal)
- [ ] Export to JSON/CSV/XML
- [ ] Subdomain takeover detection
- [ ] Port scanning integration
- [ ] Screenshot capture module
- [ ] Wayback Machine integration

---

## CONTRIBUTING

Contributions are welcome. Here is how you can help:

### Fork the Repository

```bash
# On GitHub, click Fork button
# Then clone your fork
git clone https://github.com/YOUR-USERNAME/Subdomain-Scanner.git
```

### Create Feature Branch

```bash
cd Subdomain-Scanner
git checkout -b feature/AmazingFeature
```

### Make Changes and Commit

```bash
# Make your changes
git add .
git commit -m 'Add some AmazingFeature'
```

### Push to Your Fork

```bash
git push origin feature/AmazingFeature
```

### Open Pull Request

Go to GitHub and open a Pull Request from your fork to the main repository.

---

## LICENSE

This project is licensed under the **MIT License** - see the LICENSE file for details.

```text
MIT License - Free for commercial and private use
```

---

## DEVELOPER

<div align="center">

### Mishra Chandan
**Security Researcher | Bug Bounty Hunter | Tool Developer**

[![GitHub](https://img.shields.io/badge/GitHub-mishrachandan5512-181717?style=for-the-badge&logo=github)](https://github.com/mishrachandan5512)
[![HackerOne](https://img.shields.io/badge/HackerOne-Ranked-black?style=for-the-badge&logo=hackerone)](https://hackerone.com/mishrachandan5512)
[![Email](https://img.shields.io/badge/Email-Contact-red?style=for-the-badge&logo=gmail)](mailto:mishrachandan5512@gmail.com)

</div>

---

## DISCLAIMER

```text
This tool is intended for legal security research and authorized 
penetration testing only. Unauthorized access to computer systems 
is illegal. Users are responsible for complying with all applicable 
local, state, and federal laws. The developer assumes no liability 
and is not responsible for any misuse or damage caused by this tool.

USE AT YOUR OWN RISK.
```

---

<div align="center">

### If you find this tool useful, please star the repository

<img src="https://user-images.githubusercontent.com/74038190/212284100-561aa473-3905-4a80-b561-0d28506553ee.gif" width="700">

**Built with dedication by Mishra Chandan**

</div>

---

<div align="center">

![Visitors](https://komarev.com/ghpvc/?username=mishrachandan5512&label=Repository%20Views&color=00ff00&style=flat-square)

**Star this repo | Fork it | Share it**

</div>
