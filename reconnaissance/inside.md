From within the container, we enumerated environment variables and discovered SSH credentials for a real system user using ENV command .

```
env
```

```
find / -name "root.txt" 2>/dev/null
find / -name "user.txt" 2>/dev/null
find / -name "flag.txt" 2>/dev/null
```

## Docker containers

To determine if you are inside a Docker container rather than on a host system, you can check for specific characteristics and files that are unique to Docker environments. Here are some methods to confirm if you are in a Docker container:

Docker containers often have a specific hostname format. You can check the hostname with:

```
hostname
```

## Internal ports

```
ss -tuln
```

Remove the -n for a description e.g. mysql

### Port forwarding

Local?

```
ssh -L 8000:localhost:8000 enzo@planning.htb
```

Remote?

```
ssh -R 8000:localhost:8000 enzo@planning.htb
```