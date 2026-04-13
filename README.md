High Level Approach:

I generally followed the instructions on the project doc for how to implement my dns resolver, starting with basic in-zone lookups and finishing with bailiwick-checking and caching. At each new step I would consider what the current behavior of my server was, and what new behavior/funcionality it would then need to support. It was helpful to first think of all the different kinds of communnication that would happen (i.e. intra-domain queries, external domain queries, responses from upstream servers, etc...) and how that behavior would interact in each case.

Challenges:

The most frustrating thing about this project was figuring out/remembering the syntax and features offered by dnslib. It took me a while to get comfortable with accessing the different attributes, building questions/queries, auto-generating replies to queries and understanding what that actually entailed. A close second was dealing with some of the more esoteric edge cases, for example, when a queries result would be a CNAME to a new, unrelated server, and my DNS server was supposed to keep track of the "partial answer" up to that point and then copy that over and begin the querying process anew starting from the CNAME record result.
