### CATEGORY: Deceptive Interactions (156)
- 154 - Resource Location Spoofing
  - 161 - Route Manipulation
    - XXX - [BGP Tampering](https://github.com/elationfoundation/CAPEC_censorship/blob/master/deceptive_interaction.md#bgp-tampering)
    - XXX - [BGP Route Leaks](https://github.com/elationfoundation/CAPEC_censorship/blob/master/deceptive_interaction.md#bgp-route-leaks)
- 148 - Content Spoofing
  - 141 - Cache Poisoning
    - 142 - [DNS Cache Poisoning](https://github.com/elationfoundation/CAPEC_censorship/blob/master/deceptive_interaction.md#dns-cache-poisoning-142)


### BGP Tampering

Detailed Attack Pattern

"BGP lacks mechanisms to authenticate the allocation of IP prefixes to autonomous systems; a prefix hijacker exploits this by originating a prefix that was not allocated to its AS." [1]

* References
  * [1] [Why Is It Taking So Long to Secure Internet Routing?](https://queue.acm.org/detail.cfm?id=2668966)
  * [Interconnection and Traffic Exchange on the Internet](http://www.bitag.org/documents/Interconnection-and-Traffic-Exchange-on-the-Internet.pdf)
  * [2] [Practical Defenses Against BGP Prefix Hijacking](http://docs.lib.purdue.edu/cgi/viewcontent.cgi?article=1365&context=ecetr)

* Resources Required
  * BGP Router

* Method of Attack
  * BGP Prefix Hijacking

Detailed Attack Pattern

"In a prefix hijack, the hijacking AS originates the exact same prefix as the AS(es) that is legitimately allocated the victim IP prefix. The bogus BGP announcement originated by the hijacking AS will be disseminated throughout the routing system, and the other ASes will use their local policies to choose between routes to the legitimate origin AS(es) and bogus routes originated by the hijacking AS." [1]

  * BGP Subprefix Hijacking

Detailed Attack Pattern

"In a subprefix hijack, the hijacking AS originates a subprefix of the victim’s IP prefix—that is, a prefix that is covered by the victim IP prefix."

### BGP Route Leaks

Detailed Attack Pattern

"... the perpetrator announces a legitimate route that it is actually using, but announces it to too many of its neighbors. The perpetrator is then overwhelmed by a flood of traffic from neighbors that select the leaked route." [1]

* Attack Motivation

" Understanding why this had an impact requires knowledge of [an AS' neighbors] local routing policies. Many routers likely including those in a neighboring [AS], are configured to prefer a route through a neighboring customer over one through a neighboring settlement-free peer. By forwarding traffic through its customers, an AS can generate more revenue. As such, [an AS' neighbors] routers [may prefer] the customer route through [the leaked route] over the usual settlement-free peering route directly to [the destination]." [1]


* References
  * [1] [Why Is It Taking So Long to Secure Internet Routing?](https://queue.acm.org/detail.cfm?id=2668966)

* Resources Required
  * BGP Router

### [DNS Cache Poisoning](http://capec.mitre.org/data/definitions/142.html) (142)

*Request to move and add minor additions to existing detailed attack pattern.*

* Mitigations

  * Hard Coded Alternate DNS server in applications
  * don't depend on DNS
  * include "hosts file"/IP address in your app
  * Use a .onion domain with Tor support

* Methods of Attack

  * Below-Recursive DNS Poisoning

When an otherwise legitimate recursive DNS server provides malicious ("NXDOMAIN" ("No such domain") code, or DNS A record) DNS responses to requests made of it.

When done through a legitimate recursive DNS server I would consider this redirection instead of injection. I would say this is "tampering" instead of "injection" in that they are utilizing their proper role as an in-path routing device to provide DNS responses. If they were an off-path device that was attempting to send a DNS response quicker than the normal DNS could be resolved I would say it is Injection.

"DNS blocking that’s done by an ISP or enterprise in order to censor content or protect end users or to insert ads into the web experience occurs between the end user’s laptop or desktop or mobile device and whatever recursive DNS server that end user is depending on. Your recursive DNS server as you read this article was most likely assigned to you by DHCP along with your IP address unless you’ve taken explicit steps to override this setting and it’s possible for the operator of your network to prevent you from successfully overriding it – which they will do if your override is costing them revenue or if their government insists." [1]

    * References
      * [1] [Blocking DNS](https://www.isc.org/blogs/blocking-dns/)

  * Above-Recursive DNS Poisoning

When an otherwise legitimate authority DNS server provides malicious ("NXDOMAIN" ("No such domain") code, or DNS A record) responses to requests made of it.

"DNS blocking that’s done by an authority server operator ... One could imagine a country that ... demands that all recursive name server operators in the country use a specific “alternate root” name server system whose design and configuration included various kinds of censorship and overrides." [1]

    * References
      * [1] [Blocking DNS](https://www.isc.org/blogs/blocking-dns/)
