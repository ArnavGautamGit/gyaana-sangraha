---
{"dg-publish":true,"permalink":"/NASDAQ Price Rendering Error/","tags":["Academics","CyberSec","Software-Development","Investing"]}
---


---
# NASDAQ Price Rendering Error
The American Stock Exchange - [[NASDAQ\|NASDAQ]] was unable to showcase the share price of [[Berkshire Hathaway Group\|Berkshire Hathaway Group]] owned by [[Warren Buffet\|Warren Buffet]] due to the share price being so high that the platform ran into [[Integer Overflow and Underflow\|Integer Overflow]]. 

### Initial Detection
The problem was first noticed when many APIs and clients of the exchange were not able to display the info safely and the page always read "Data is not available" or something similar.

### Cause
The problem occured since instead of rounding off the values of share prices and storing them as floats, the developer team decided to multiply the price by 10,000 and store it, then divide it by 10,000 to get the share price (accurate to multiple decimal digits). Berkshire's share price got upto $435,000 USD - which meant that multiplying by 10,000 would exceed the limit of unsigned integers by a sizable margin.

### Effect
The exchange was taken down by the developers until the problem was fixed and it ended up staying down for 9 days. Many retail investors have said to have lost money during this time.

---
# Footnotes