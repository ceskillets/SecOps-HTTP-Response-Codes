# HTTP Response Codes

This HTTP Status code Skillet will create custom threat prevention signatures that will log all HTTP status codes in PAN-OS logs. 
It is designed to help customers determine misconfigurations and help with more focused Application ID (App-ID) signatures.

As you interact with a website you make the request and the server responds. 
Status codes let us know whether the request was a success, a failure, or something in-between. 
Upon creating the custom threat prevention signatures you can immediately start to utilize them for a few use cases:

* Build more granular security rules based on the response codes

* Mine HTTP 200 to better understand how the application works to build better App-IDs and/or rules.

* HTTP 4XX client errors can indicate an application issue like a broken link or potential scanning activity.

* HTTP 5XX client made a valid request but the server didn’t complete it – server problem.

Consider resetting these responses so an attacker does not get positive feedback that the application was impacted. 
Also, match the URL for the session and provide that to the app team to harden the code. 
If you have not fully adopted App-ID, then there is most likely a “catch-all” rule that exists that will be similar to this one.

In PAN-OS 8.1 rule count and first/last seen features were introduced. Correlating this data with the HTTP status codes, 
you can create more granular rules for your applications and not only see if those rules are being hit, 
but you can also filter on that rule in the traffic logs as well. 
As you keep building more App-ID centric rule in your security policy, see a decline in hit count for your “catch-all” rule 
and eventually be able to disable it with confidence. 
Disabling the catch-all rule prevents scanning tools such as Shodan and port scanners from footprinting your web application. 
This means that an attacker must actually know the proper URL for your hosted application to access it – 
a bar that any valid user will automatically pass.

