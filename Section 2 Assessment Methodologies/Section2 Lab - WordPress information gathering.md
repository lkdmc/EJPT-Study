
- 1. This tells search engines what to and what not to avoid.
	- This was about the preventing the crawling. 
	- curl {URL}/robots.txt
---
- 2. What website is running on the target, and what is its version?
	- First I need to see what kind of service/version the website is running on
	- curl -I {URL}
```
HTTP/1.1 200 OK
Date: Thu, 19 Feb 2026 16:33:56 GMT
Server: Apache/2.4.41 (Ubuntu)
Link: <http://target.ine.local/index.php/wp-json/>; rel="https://api.w.org/"
Content-Type: text/html; charset=UTF-8
```
	This response includes the wp-json, meaning it is made with word press
	- Since WordPress includes the generator automatically for showing its version,
	- curl {url} | grep "generator" gives me the flag.
---
- 3. Directory browsing might reveal where files are stored.
	- ```
	  gobuster dir -u {URL} -w /usr/share/wordlists/dirb/common.txt
	  ```
	[[gobuster]]
	- Result
	- ```
	  /.htaccess            (Status: 403) [Size: 281]
/.htpasswd            (Status: 403) [Size: 281]
/.hta                 (Status: 403) [Size: 281]
/index.php            (Status: 301) [Size: 0] [--> http://target.ine.local/]
/robots.txt           (Status: 200) [Size: 108]
/server-status        (Status: 403) [Size: 281]
/wp-admin             (Status: 301) [Size: 323] [--> http://target.ine.local/wp-admin/]
/wp-content           (Status: 301) [Size: 325] [--> http://target.ine.local/wp-content/]
/wp-includes          (Status: 301) [Size: 326] [--> http://target.ine.local/wp-includes/]
/xmlrpc.php           (Status: 405) [Size: 42]

	  ```
	- 301 means the certain URL is accessible, so go deeper
	- gobuster dir -u http://target.ine.local/wp-content -w /usr/share/wordlists/dirb/common.txt
---
- 4. An overlooked backup file in the webroot can be problematic if it reveals sensitive configuration details.
	- WordPress usually use the backup file like this 
		- curl http://target.ine.local/wp-config.bak
---
- 5. Certain files may reveal something interesting when mirrored.
	- This question is about mirror the website, and search for the flag.
	- 1. httrack http://target.ine.local -O ./mirror
	- 2. grep -r "FLAG" ./mirror/