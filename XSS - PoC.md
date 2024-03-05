# Soosyze CMS / Stored Cross Site Scripting


## Affected Component
> /user/X

## Impact


## Proof of Concept
**HTTP Request Example**
``` http request
GET /user/1 HTTP/1.1
Host: [REDACTED]
Sec-Fetch-Site: same-origin
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Referer:[REDACTED]
Accept-Encoding: gzip, deflate, br
Accept-Language: en-US,en;q=0.9
Cookie: PHPSESSID=[REDACTED]
Connection: close
```

## Proof of Concept (POC):


## Screenshot
![2024-03-05 17_05_18-VirtualBoxVM](https://github.com/dumiAron/CVE/assets/110510895/e49acdb1-1980-4a25-8eea-a8bd336c3564)


## **Credits**
> [Aaron Wy](https://github.com/WyAaron)
