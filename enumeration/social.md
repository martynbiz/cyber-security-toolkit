# Social Engineering and OSINT

## theHarvester

Passive recon. Used to gather OSINT on company or domain

```
theHarvester -d DigiNinja -b google,linkedin,bing
```

```
theHarvester -d zonetransfer.me -b google,linkedin,bing,twitter,yahoo,sublist3er
```

Limit to 500 and DNS lookup

```
theHarvester -d example.com -l 500 -b google,linkedin,bing,twitter,yahoo,sublist3er -n
```

Follow with manual searching

## Sublist3r

```
sublist3r -d example.com
```

## Social Media and Forums

Gather information from social media platforms and forums related to the website or its administrators.