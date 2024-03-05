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

## Screenshot


## **Credits**
> [Russel James Avenido](https://github.com/lucishtml)
