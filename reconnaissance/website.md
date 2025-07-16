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
