---
{"dg-publish":true,"permalink":"/XML External Entity (XXE) Attack/","tags":["CyberSec","Academics"]}
---


---
# XML External Entity (XXE) Attack
The Shorthand (XXE) comes from the full title written above:  ==***X***==ML e==***X***==ternal ==***E***==ntity
It is a vulnerability which allows the attacker to interfere with the XML code.

In XML, you don't have predefined tags like `<head>` or `<img>`. It is democratic, one can assign their own tags in their code, but at the same time it is kept similar enough to HTML so to reduce the leaning curve

XML is used to stroe and transport data, it is platform independent (just like HTML).
Each XML file has a Document Type Declaration (also called DTD). It basicallyu defines the document & that the document is XML type, it is used to give the document a structure and define your own tags.

DTDs can be either internal or external where the DTD can be located either inside the XML itself or outside it respectively.
***Internal DTD*** is defined as the following:
```XML
<?xml version="1.0"?>
<!DOCTYPE note [
<!ELEMENT note (to,from,heading,body)>
<!ELEMENT to (#PCDATA)>
<!ELEMENT from (#PCDATA)>
<!ELEMENT heading (#PCDATA)>
<!ELEMENT body (#PCDATA)>
]>
<note>
<to>Tove</to>
<from>Jani</from>
<heading>Reminder</heading>
<body>Don't forget me this weekend</body>
</note>
```

Note: that here PC data refers to Parsed Character Data i.e., which will be parsed by a parser anc checked for markup etc.

For ***Extenal DTD***, note that we store all the DTD info in another file with a `.dtd` file extension.
The XML code is altered to:
```XML
<?xml version="1.0"?>
<!DOCTYPE note SYSTEM "external.dtd">
<note>
<to>Tove</to>
<from>Jani</from>
<heading>Reminder</heading>
<body>Don't forget me this weekend</body>
</note>
```
Note that we can take DTD info from the web as well and handle that as External DTD by simple changing "external.dtd" to the link of the webpage of the file

Just like what we saw in [[SQL Injection Attack\|SQL Injection Attack]] - XML (just like SQL) can lead to a generic page/data. Hence there is a variant of Blind XXE as well. 

---
# Types of XXE exploits
XXE can be exploited to get following data:
1. Retreive files
2. Perform SSRF attacks
3. Blind XXE can still be exploited for exfiltrating data out-of-band.
4. Blind XXE can be exploited to retrieve data using error messages

---
# Prevention of XXE Exploitation Attacks
1. Disable use of external entities in XML parsing libraries
2. Validate and Sanitize all XML input to remove any external entity references
3. Implement Filtering and validation to prevent injection attacks (including XXE injection)

