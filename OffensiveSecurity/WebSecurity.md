

# Programme  

* Introduction 
  * HTTP Basics
  * Tools
  * Discovery
  * Identification de la faille
  * Exploitation
* Server-side

<img width="1190" alt="image" src="https://user-images.githubusercontent.com/11661521/195179777-a08fa52f-3980-4b86-9b99-c173fe22680e.png">

* Client-side

<img width="1200" alt="image" src="https://user-images.githubusercontent.com/11661521/195180289-14a06e53-02b2-4ab0-98bc-a70b8dd36ddf.png">


# Pour aller plus loin 

Tous les cours en detail sont accessibles à l'adresse https://portswigger.net/web-security/all-materials/detailed.

<img width="1185" alt="image" src="https://user-images.githubusercontent.com/11661521/195180452-c8b06b90-a105-42b4-894a-c08689e0a0c0.png">


# Instructions / Setup

* Installer VM Kali ou distro. Linux (https://www.kali.org/get-kali/) avec a minima Burp Suite Free (https://portswigger.net/burp) 
* S'enregistrer sur https://portswigger.net/users (Nécessaire pour les TPs)
* Configurer son browser ou OS avec certificat Burp (https://portswigger.net/burp/documentation/desktop/external-browser-config/certificate) 


# Course Plan
## Introduction (30 min.-1h) 

Support presente pendant les cours. 

## Server-side 

### SQL Injection
* Warm- up : https://portswigger.net/web-security/sql-injection/lab-retrieve-hidden-data
* TD : https://portswigger.net/web-security/sql-injection/examining-the-database/lab-querying-database-version-oracle
* TP : Any from Practicioner level 

### File Upload
* WU:
https://portswigger.net/web-security/file-upload/lab-file-upload-remote-code-execution-via-web-shell-upload
* TD: 
https://portswigger.net/web-security/file-upload/lab-file-upload-web-shell-upload-via-content-type-restriction-bypass
* TP: 
https://portswigger.net/web-security/file-upload/lab-file-upload-web-shell-upload-via-path-traversal

### OS Command Injection 
* WU:
https://portswigger.net/web-security/os-command-injection/lab-simple
* TD:
https://portswigger.net/web-security/os-command-injection/lab-blind-time-delays
* TP:
https://portswigger.net/web-security/os-command-injection/lab-blind-output-redirection

### XXE
* WU: 
https://portswigger.net/web-security/xxe/lab-exploiting-xxe-to-retrieve-files
* TD: 
https://portswigger.net/web-security/xxe/blind/lab-xxe-with-out-of-band-interaction
* TP: 
https://portswigger.net/web-security/xxe/lab-xinclude-attack

### SSRF
* WU : 
https://portswigger.net/web-security/ssrf/lab-basic-ssrf-against-localhost
* TD: 
https://portswigger.net/web-security/ssrf/blind/lab-shellshock-exploitation
* TP: 
https://portswigger.net/web-security/ssrf/blind/lab-out-of-band-detection

### Insecure Deserialization 
* WU : 
https://portswigger.net/web-security/deserialization/exploiting/lab-deserialization-modifying-serialized-objects
* TD : 
https://portswigger.net/web-security/deserialization/exploiting/lab-deserialization-arbitrary-object-injection-in-php
* TP : 
https://portswigger.net/web-security/deserialization/exploiting/lab-deserialization-exploiting-java-deserialization-with-apache-commons
OR 
https://portswigger.net/web-security/deserialization/exploiting/lab-deserialization-modifying-serialized-data-types

## Client-side 

### Cross-Site Scripting 
* WU : 
https://portswigger.net/web-security/cross-site-scripting/stored/lab-html-context-nothing-encoded
https://portswigger.net/web-security/cross-site-scripting/reflected/lab-html-context-nothing-encoded
* TD: 
https://portswigger.net/web-security/cross-site-scripting/exploiting/lab-stealing-cookies
* TP : 
Any Practitioner level 
https://portswigger.net/web-security/cross-site-scripting/contexts/lab-onclick-event-angle-brackets-double-quotes-html-encoded-single-quotes-backslash-escaped

### CSRF 
* WU : https://portswigger.net/web-security/csrf/lab-no-defenses
* TP : https://portswigger.net/web-security/csrf/lab-token-duplicated-in-cookie (hard)

### CORS Abuse
* WU : https://portswigger.net/web-security/cors/lab-basic-origin-reflection-attack
* TP : https://portswigger.net/web-security/cors/lab-breaking-https-attack (a little hard)

## Authentication, session and IDOR 

### User Enumeration 
* WU : https://portswigger.net/web-security/authentication/password-based/lab-username-enumeration-via-different-responses
* TP : https://portswigger.net/web-security/authentication/password-based/lab-username-enumeration-via-subtly-different-responses

### 2FA Brute force 
* WU : https://portswigger.net/web-security/authentication/multi-factor/lab-2fa-simple-bypass
* TD : https://portswigger.net/web-security/authentication/multi-factor/lab-2fa-bypass-using-a-brute-force-attack 


### Business logic vulnerabilities
* Warm-up : https://portswigger.net/web-security/logic-flaws/examples/lab-logic-flaws-excessive-trust-in-client-side-controls
* TP : https://portswigger.net/web-security/logic-flaws/examples/lab-logic-flaws-low-level

## Exam (Later)

Mystery challenge 
