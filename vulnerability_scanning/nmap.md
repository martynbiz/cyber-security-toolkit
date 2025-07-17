# Nmap

Check if a site is vulnerable to Heartbleed attacks

```
sudo nmap  -sS -sV -p 442 example.com --script=ssl-heartbleed -oN ???
```

