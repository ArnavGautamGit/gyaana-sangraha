---
{"dg-publish":true,"permalink":"/Cross Site Scripting (XSS) Attack/","tags":["Academics","CyberSec"]}
---


---
# Cross Site Scripting (XSS) Attack
It is a manuipulation of a website such that it returns malicious [[JavaScript\|JavaScript]] to the user.
It is not any ordinary code - but the code can execute on the client's browser and then take the entire PC under control.
At the very least, it compromises the interaction between the victim's browser and the website.

It is of the following types:
1. ***DOM-based XSS***: The vulnerability exists in the client's browser and not the server side. First the legitimate server script executes, followed by malicious JavaScript on client browser.
2. ***[[Cross Site Scripting (XSS) Attack#^1\|Reflected XSS]]***: Malicious JavaScript originates from the current HTTP request.
3. ***[[Cross Site Scripting (XSS) Attack#^2\|Stored XSS]]***: The XSS script was stored on the website's server and that's where the attack came from.

The cross-site script itself is not an attack, but only a vulnerability. Websites like Facebook have been using this for a long time but they have the necessary safety measures to prevent the use of the vulnerability in any attack. In effect, the vulnerability can be considered as patched.
### Prevention of XSS Attacks:
1. ***Proper Input Validation***: Just like [[SQL Injection Attack\|SQL Injection Attack]], here as well, we must filter the input accroding to what we expect. Reject everything else as "unexpected input". 
2. ***Proper encoding of data on output***: If the website is sending code as output, encode all to prevent the browser thinking it is some active file.
3. ***Use appropriate response headers***: To prevent XSS in HTTP responses that aren't intended to contain any HTML or JavaScript, you can use the Content-Type to ensure that browsers interpret the responses in the way you intend.
4. ***Content Security Policy (CSP)***: Last line of defence to reduce the severity of any XSS vulnerability that may occur.

---
# Footnotes
1. ***Reflected XSS Attack*** is a type of XSS attack where the malicious JavaScript code is executed on the sender's side. No part of the code is stored on the servers.
{ #1}

2. ***Stored XSS Attack*** is a type of XSS attack where the script is stored on the servers of the website. It is also executed on the server end everytime the website is requested.
{ #2}
