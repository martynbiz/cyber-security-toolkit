# Wordpress

## WPScan

https://pentesting.site/cheat-sheets/wpscan-cheat-sheet/

API token is required to perform full scan. Can be obtained by creating an account with WPScan.

https://github.com/daffainfo/AllAboutBugBounty/blob/master/Technologies/WordPress.md

Find older versions of Wordpress themes:

"It's time to build the website you want. THEMELOCK is 100% legal.
All themes are released under the GPL (General Public License). Trusted and verified. You are free to use them as often as you like and on as many sites as you want."

https://themelock.com/

## Enumerating users

Users can be enumerated by hovering over post author links to see the URL path:

```
blog.inlanefreight.com/index.php/author/*admin*
```

The admin user is usually assigned the user ID 1. We can confirm this by specifying the user ID for the author parameter in the URL, which in the browser might trigger a redirect:

```
http://blog.inlanefreight.com/?author=1
```

### JSON Endpoint

```
curl http://blog.inlanefreight.com/wp-json/wp/v2/users | jq

[
  {
    "id": 1,
    "name": "admin",
    "url": "",
    "description": "",
    "link": "http://blog.inlanefreight.com/index.php/author/admin/",
    <SNIP>
  },
  {
    "id": 2,
    "name": "ch4p",
    "url": "",
    "description": "",
    "link": "http://blog.inlanefreight.com/index.php/author/ch4p/",
    <SNIP>
  },
<SNIP>
```

Once armed with a list of valid users, a password brute-forcing attack can be attempted to gain access to the WordPress backend.