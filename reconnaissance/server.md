# Server 

## Nmap

Port scanning

```
sudo nmap -sS -sV example.com
```

Port scanning with scripts(?) for more info

```
sudo nmap -sC -sV example.com
```

Scan open UDP ports

```
sudo nmap -sU example.com
```

-sC : Equivalent to --script=default
-A : Enable OS detection, version detection, script scanning, and traceroute
-Pn : Treat all hosts as online -- skip host discovery

```
sudo nmap -sC -Pn -A 10.129.95.192
```