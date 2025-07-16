## Information Gathering

### WHOIS Lookup

Use WHOIS services to gather information about the domain registration, including the owner's contact details, registration date, and hosting provider.

```
whois example.com > example_com__whois.txt
```

### DNS Enumeration

Tools like dig or nslookup can help you gather DNS records, including A, MX, and TXT records, which can provide insights into the infrastructure.

#### Nmap

Broadcast-dns-service-discovery Script

This script reveals the services using the DNS Discovery Protocol on the web server. The script sends multiple multicast DNS-SD queries and collects all the responses given by the server. However, all that is done procedurally. The scripts first sends the for _services._dns-sd._udp.local query that lists all the running services. Once done, it sends another query to each listed service and collects this information.

```
nmap --script=broadcast-dns-service-discovery example.com
```

Dns-brute Nmap Script

This script performs a brute-force on the server to try and get all the hostnames.

```
nmap -T4 -p 53 --script dns-brute example.com
```

#### DNSEnum

DNSEnum is a powerful Perl script that performs DNS enumerations on domain names.

```
dnsenum --noreverse -o example.xml example.com
```

#### DNSRecon

```
dnsrecon -d example.com
```

#### Host

The host command is widely used to determine the IP address of a domain name. 

```
host example.com
```

#### NSLookup

NsLookup is another tool you can use for DNS enumeration and comes pre-installed on Kali Linux. This will open an interactive shell where you can execute commands.

```
nslookup
> set type=ns
> example.com
```

```
nslookup
> set type=mx
> example.com
```

## Website Analysis

### Web Application Fingerprinting

Use tools like Wappalyzer or BuiltWith to identify the technologies used on the website, including the WordPress version, plugins, and themes.

## Source Code Inspection

View the page source in your browser to identify comments, hidden fields, or other information that may reveal vulnerabilities.

### Vulnerability Scanning

### Automated Scanners

Tools like WPScan can be used specifically for WordPress to identify known vulnerabilities in plugins, themes, and the WordPress core.

### General Vulnerability Scanners

Tools like Nessus or OpenVAS can also be used to scan for vulnerabilities in web applications.

## Brute Force and Credential Testing

### Password Cracking

Use tools like Hydra or Burp Suite to test for weak passwords on login pages. Ensure you have permission to perform such tests.

### User Enumeration: Check for user enumeration vulnerabilities by attempting to log in with common usernames and observing the error messages.

## Content Discovery

### Directory and File Enumeration

Use tools like DirBuster or Gobuster to discover hidden directories and files that may not be linked from the main site.

Search for Sensitive Files

Look for common sensitive files like wp-config.php, .htaccess, or backup files that may be exposed.

## Social Engineering and OSINT

### Social Media and Forums

Gather information from social media platforms and forums related to the website or its administrators.

### Google Dorking

Use advanced Google search queries to find specific information about the site, such as exposed files or vulnerabilities.

## Monitoring and Reporting

### Log Monitoring

If you have access, monitor server logs for unusual activity or access patterns.

### Reporting

Document your findings in a structured report, highlighting vulnerabilities and providing recommendations for remediation.
