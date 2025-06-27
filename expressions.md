## Part 1 - Allow Legitimate Services<div id="part1"></div>
> **Action:** Skip
```
(cf.client.bot)
```

## Part 2 - Block Malicious Traffic & Exploit Probes<div id="part2"></div>
> **Action:** Block
```
(http.user_agent contains "HeadlessChrome") or 
(http.user_agent contains "OPD") or 
(http.user_agent contains "fasthttp") or 
(http.user_agent contains "ALittle Client") or 
(http.user_agent contains "ct‑git‑scanner") or 
(http.user_agent contains "python-requests") or 
(http.user_agent contains "curl") or 
(http.user_agent contains "wget") or 
(http.user_agent contains "libwww-perl") or 
(http.user_agent contains "masscan") or 
(http.user_agent contains "nmap") or 
(http.user_agent contains "sqlmap") or 
(http.user_agent contains "nikto") or 
(http.user_agent contains "ZmEu") or 
(http.user_agent contains "w3af") or 
(http.user_agent contains "dirbuster") or 
(http.user_agent contains "gobuster") or 
(http.user_agent contains "ffuf") or 
(http.user_agent contains "wfuzz") or 
(http.user_agent contains "nuclei") or 
(http.user_agent contains "httpx") or 
(http.user_agent contains "subfinder") or 
(http.user_agent contains "amass") or 
(http.user_agent contains "zgrab") or 
(http.user_agent contains "zmap") or 
(http.user_agent contains "Go-http-client") or 
(http.user_agent contains "Apache-HttpClient") or 
(http.user_agent eq "") or 
(http.request.uri.path contains "/.git") or 
(http.request.uri.path contains "/.env") or 
(http.request.uri.path contains "/wp-login") or 
(http.request.uri.path contains "/wp-admin") or 
(http.request.uri.path contains "/config.") or 
(http.request.uri.path contains "/phpinfo") or 
(http.request.uri.path contains "/shell") or 
(http.request.uri.path eq "/admin") or 
(http.request.uri.path eq "/admin/") or 
(http.request.uri.path contains "/admin.php") or 
(http.request.uri.path contains "/administrator") or 
(http.request.uri.path contains "cgi-bin") or 
(http.request.uri.path contains "/.aws") or 
(http.request.uri.path contains "/.ssh") or 
(http.request.uri.path contains "/backup") or 
(http.request.uri.path contains "/database") or 
(http.request.uri.path contains "/db_") or 
(http.request.uri.path contains "/sql") or 
(http.request.uri.path contains "/phpmyadmin") or 
(http.request.uri.path contains "/adminer") or 
(http.request.uri.path contains "/.htaccess") or 
(http.request.uri.path contains "/.htpasswd") or 
(http.request.uri.path contains "/web.config") or 
(http.request.uri.path contains "/composer.json") or 
(http.request.uri.path contains "/package.json") or 
(http.request.uri.path contains "/Dockerfile") or 
(http.request.uri.path contains "/docker-compose") or 
(http.request.uri.path contains "/.terraform") or 
(http.request.uri.path contains "/server-status") or 
(http.request.uri.path contains "/server-info") or 
(http.request.uri.path contains "/.svn") or 
(http.request.uri.path contains "/.hg") or 
(http.request.uri.path contains "/CVS") or 
(http.request.uri.path contains "/.bzr")
```

## Part 3 - Block Known Bad ASNs<div id="part3"></div>
> **Action:** Block
```
(ip.geoip.asnum in {
    197695 49505 201776 202425 49392 44812 
    202422 25513 31133 42610 49981 60068 
    44901 51167 200000 197540 61317 48314 
    60781 16265 60404 206264 208091 202448 
    63949 16276 24940 45090 37963 55990 
    132203 38365 20473 14061 19531 46562 
    62904 26496 9009 35913 31034 8100 
    46844 40676 53667 209605 212238 29802 
    48693
})
```

## Part 4 - Strict Rule<div id="part4"></div>
> **Action:** Managed Challenge
```
(not ip.geoip.country in {"CN" "HK" "JP" "SG" "US" "KR"}) or 
(http.x_forwarded_for eq ".") or 
(not http.request.version in {"HTTP/2" "HTTP/3"}) or 
(not http.user_agent contains "Mozilla/")
```
