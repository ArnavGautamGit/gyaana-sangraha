---
{"dg-publish":true,"permalink":"/Risk Assessment & Management/","tags":["Academics"]}
---


---
# Risk Assessment & Management
> Process of identifying and mitigating (or at least reducing) risk of untoward events happening to us. In context of CyberSec, the "untoward events" may be [[Security Incidents\|Intrusion]].

Needless to say, 
this is a process performed in two halves: Assessing Risk then Managing said risk.
Risk is Assessed by using formulas & methods like [[The OWASP Method\|The OWASP Method]] and [[The CRAMM\|The CRAMM]].
Risk is managed by using [[Security Controls\|Security Controls]].

### Risk Assessment
The Process of Identifying Risk begins with the process to identify assets in the system. If we are protecting a computer network then we rank all the assets on the basis of a priority (either cost or criticality to functioning) and then identify top assets.

Once Assets are identified, we move on identifying vulnerability to the system and its software by the use of [[Penetration Testing\|Penetration Testing]] and [[Vulnerability Scanning\|Vulnerability Scanning]] among other techniques in [[Ethical Hacking\|Offensive Security]].

Now we create a chart or table of Attack Metrics of the Probability that the assets we are protecting end up getting attacked and the Impact of such an attack. These are also known as Impact & Probability Metrics.

Now we finally use methods like [[The OWASP Method\|The OWASP Method]] and [[The CRAMM\|The CRAMM]] to figure out the risks.
Once Risk is calculated, we move on to the next phase.

### Risk Management
Often performed according to the Risk Management Framework (RMF) is a structural approach to identify assets and who has access to them in order to manage risk in an organisation. 

It provides guidelines to integrate security & Risk Management into the deployment lifecycle of any asset's lifecycle. It has the following steps:
1. Prepare
2. Categorise
3. Select
4. Implement
5. Assess
6. Authorise
7. Monitor

In the previous phase (Risk Assessment) we have prepared and Categorised risk on the basis of a priority, now we select the risk and implement the [[Security Controls\|Security Controls]]. We then assess whether our controls are working as desired and if any changes are required then we authorise said changes else monitor our policies.

---
# Footnotes