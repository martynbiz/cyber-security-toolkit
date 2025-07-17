# Website Analysis

Use tools like Wappalyzer or BuiltWith to identify the technologies used on the website, including the WordPress version, plugins, and themes.

## BuiltWith

Can be accessed via a browser, or Chrome/Firefox plugin.

API Access: BuiltWith also offers an API that you can use to programmatically access its data. You would need to sign up for an API key and then you can make requests using tools like curl or any programming language that can handle HTTP requests.

https://builtwith.com/

## WhatWeb

Included in Kali Linux

```
whatweb example.com
```

Tech stack e.g. PHP version, LAMP stack, Wordpress, 
Emails

## Wappalyzer

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

## Google Dorking

Use advanced Google search queries to find specific information about the site, such as exposed files or vulnerabilities.

Limit search to one domain

```
site:bbc.com
```

Limit search to subdomains only

```
site:*.bbc.com -site:www.bbc.com
```

Filter by keywork in url

```
site:example.com inurl:wp-admin
```

Filter by keywork in title

```
site:example.com intitle:wp-admin
```

Search by file types

```
site:example.com filetype:pdf
```

https://www.wikihow.com/Google-Dorking-Commands

## User Enumeration

Check for user enumeration vulnerabilities by attempting to log in with common usernames and observing the error messages.

## Directory and File Enumeration

Use tools like DirBuster or Gobuster to discover hidden directories and files that may not be linked from the main site.

Search for Sensitive Files

Look for common sensitive files like wp-config.php, .htaccess, or backup files that may be exposed.