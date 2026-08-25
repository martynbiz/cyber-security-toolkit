# Domain

## WHOIS Lookup

Use WHOIS services to gather information about the domain registration, including the owner's contact details, registration date, and hosting provider.

```
whois example.com > example_com__whois.txt
```

## DNS Enumeration

Tools like dig or nslookup can help you gather DNS records, including A, MX, and TXT records, which can provide insights into the infrastructure.

## Nmap

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

## DNSEnum

DNSEnum is a powerful Perl script that performs DNS enumerations on domain names.

```
dnsenum --noreverse -o example.xml example.com
```

## DNSRecon

Enumerate DNS records

```
dnsrecon -d example.com
```

TXT records will show any protective services such as SPF mail.

## Host

The host command is widely used to determine the IP address of a domain name. 

```
host example.com
```

## NSLookup

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

## Trace route

```
traceroute example.com
```

## Wafw00f

```
wafw00f example.com
```

Get registrar, domain expiry date, DNSSec enabled, 

## Dig

DNS lookup utility

```
dig example.com
```

Limit to nameservers only

```
dig example.com NS
```

## Fierce

Performs zone transfer?

```
fierce --domain example.com
```

## Knockpy

Perform subdomain brute force

```
knockpy example.com
```

```
knockpy example.com -w custom_wordlist.txt
```

IP Info

```
https://ipinfo.io/2.2.2.2/json
```


TODO
- netcraft website - ssl info, ca, heartbleed vuln, dmark? dkim? 
- dnsdumpster.com - mapping of domain, graphs, openssh version
- SecurityTrails
- https://zonetransfer.me - for training purposes
- historical DNS
- bypass Cloudflare IP protection?

## Cloudflare

Finding the real IP address of a website implies getting to the actual web server’s IP address, even if the origin server is being hidden by a CDN like Cloudflare. Finding the real IP address of a website is difficult when the user is using Cloudlfare as the requests by visitors are routed through the CDN’s global network, hiding the real IP address.

### Cloudsnare

Note: seems you need to pay for API

Step 1: Create the Account on Censys.io

Go to censys.io and sign up for a free account.

Step 2: Generating API and Secret Key.

Go to your Censys account profile by clicking on "My Account"

https://www.geeksforgeeks.org/linux-unix/find-real-ip-behind-cloudflare-with-cloudsnare/

### CloudPeter

Not working :(

```
git clone https://github.com/zidansec/CloudPeler
cd CloudPeter
./crimeflare example.com
```

### OsintSec

Not working :(

Simple tools for further penetration, this tool is able to visualize network from Domain, IP, Email and more.

https://osinthreat.herokuapp.com/



https://github.com/christophetd/CloudFlair?tab=readme-ov-file


A variety of free and premium tools such as SecurityTrails, DNS Spy, and other tools offer detailed DNS record history and analytical capabilities useful for domain owners, IT professionals, and security experts.

SecurityTrails DNS Check – Check Historial DNS Data

DNS Trails (now SecurityTrails)

DNS Spy
https://dnsspy.io/scan

WhoISrequest
Whoxy