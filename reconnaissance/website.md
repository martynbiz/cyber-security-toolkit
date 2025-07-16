# Website Analysis

## Web Application Fingerprinting

Use tools like Wappalyzer or BuiltWith to identify the technologies used on the website, including the WordPress version, plugins, and themes.

Wappalyzer

Can be accessed via a browser, or Chrome/Firefox plugin

https://www.wappalyzer.com/

There is also a command-line tool:

```
git clone https://github.com/gokulapap/wappalyzer-cli
cd wappalyzer-cli
python3 -m venv venv
source venv/bin/activate
pip3 install -r requirements.txt

python3 src/wappy.py -h
```

BuiltWith

Web Interface: BuiltWith is primarily a web-based tool. You can access it through your web browser on Kali Linux by visiting the BuiltWith website and entering the URL of the site you want to analyze.

API Access: BuiltWith also offers an API that you can use to programmatically access its data. You would need to sign up for an API key and then you can make requests using tools like curl or any programming language that can handle HTTP requests.

https://builtwith.com/

# Source Code Inspection

View the page source in your browser to identify comments, hidden fields, or other information that may reveal vulnerabilities.

## Vulnerability Scanning

## Automated Scanners

Tools like WPScan can be used specifically for WordPress to identify known vulnerabilities in plugins, themes, and the WordPress core.

WPScan

Obtain an API Token (Optional)

To access the latest vulnerability data, you can register for a free API token from the WPScan website. This is optional but recommended for comprehensive scanning.

1. Go to https://wpscan.com/
2. Sign up for an account and obtain your API token

Basic usage

```
wpscan --url http://example.com
```

Common Options

API Token: If you have an API token, include it in your scan:

```
wpscan --url http://example.com --api-token YOUR_API_TOKEN
```

Enumerate Plugins: To find installed plugins:

```
wpscan --url http://example.com --enumerate p
```

Enumerate Themes: To find installed themes:

```
wpscan --url http://example.com --enumerate t
```

Enumerate Users: To find usernames:

```
wpscan --url http://example.com --enumerate u
```

Scan for Vulnerabilities: To check for known vulnerabilities in the installed plugins and themes:

```
wpscan --url http://example.com --enumerate ap,at
```

Save Output: You can save the scan results to a file:

```
wpscan --url http://example.com --output results.txt
```

Rate Limiting: Be mindful of the target server's load. WPScan has built-in rate limiting to avoid overwhelming the server.

## General Vulnerability Scanners

Tools like Nessus or OpenVAS can also be used to scan for vulnerabilities in web applications.

# Brute Force and Credential Testing

## Password Cracking

Use tools like Hydra or Burp Suite to test for weak passwords on login pages. Ensure you have permission to perform such tests.

## User Enumeration

Check for user enumeration vulnerabilities by attempting to log in with common usernames and observing the error messages.

# Content Discovery

## Directory and File Enumeration

Use tools like DirBuster or Gobuster to discover hidden directories and files that may not be linked from the main site.

Search for Sensitive Files

Look for common sensitive files like wp-config.php, .htaccess, or backup files that may be exposed.
