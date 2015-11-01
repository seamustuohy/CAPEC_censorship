## Tampering & Termination
Meta Attack Pattern

* References
* Resources Required
* Methods of attack
* Mitigations


### Route Tampering & Termination
Attack Pattern

* References
* Resources Required
* Methods of attack
* Mitigations


#### BGP Tampering
Detailed Attack Pattern
https://queue.acm.org/detail.cfm?id=2668966

"BGP lacks mechanisms to authenticate the allocation of IP prefixes to autonomous systems; a prefix hijacker exploits this by originating a prefix that was not allocated to its AS." [1]

* References
  * [1] [Why Is It Taking So Long to Secure Internet Routing?](https://queue.acm.org/detail.cfm?id=2668966)

* Resources Required
  * BGP Router


##### BGP Prefix hijacking
Detailed Attack Pattern

"In a prefix hijack, the hijacking AS originates the exact same prefix as the AS(es) that is legitimately allocated the victim IP prefix. The bogus BGP announcement originated by the hijacking AS will be disseminated throughout the routing system, and the other ASes will use their local policies to choose between routes to the legitimate origin AS(es) and bogus routes originated by the hijacking AS." [1]

* References
  * [1] [Why Is It Taking So Long to Secure Internet Routing?](https://queue.acm.org/detail.cfm?id=2668966)

* Resources Required
  * BGP Router

##### BGP Subprefix hijacking
Detailed Attack Pattern

"In a subprefix hijack, the hijacking AS originates a subprefix of the victim’s IP prefix—that is, a prefix that is covered by the victim IP prefix."

* References
  * [1] [Why Is It Taking So Long to Secure Internet Routing?](https://queue.acm.org/detail.cfm?id=2668966)
  * [2] [Practical Defenses Against BGP Prefix Hijacking](http://docs.lib.purdue.edu/cgi/viewcontent.cgi?article=1365&context=ecetr)

* Resources Required
  * BGP Router

##### BGP Route Leaks
Detailed Attack Pattern

"... the perpetrator announces a legitimate route that it is actually using, but announces it to too many of its neighbors. The perpetrator is then overwhelmed by a flood of traffic from neighbors that select the leaked route." [1]

* Attack Motivation

" Understanding why this had an impact requires knowledge of [an AS' neighbors] local routing policies. Many routers likely including those in a neighboring [AS], are configured to prefer a route through a neighboring customer over one through a neighboring settlement-free peer. By forwarding traffic through its customers, an AS can generate more revenue. As such, [an AS' neighbors] routers [may prefer] the customer route through [the leaked route] over the usual settlement-free peering route directly to [the destination]." [1]


* References
  * [1] [Why Is It Taking So Long to Secure Internet Routing?](https://queue.acm.org/detail.cfm?id=2668966)

* Resources Required
  * BGP Router


##### BGP Route Disruption
Detailed Attack Pattern

"Disabling the routing process on critical routers or suppressing BGP information transmission can effectively render large parts of a network unreachable." [2]

* References
  * [1] [Why Is It Taking So Long to Secure Internet Routing?](https://queue.acm.org/detail.cfm?id=2668966)
  * [2] [Analysis of Country-wide Internet Outages Caused by Censorship](https://web.archive.org/web/20150912103705/http://www.caida.org/publications/papers/2011/outages_censorship/outages_censorship.pdf)

* Resources Required
  * BGP Router

Observables:  "Disabling a network’s connectivity to the Internet through BGP routing disruption is easily detectable, since it entails changes in the global routing state of the network, i.e., in the control plane. Previously advertised prefixes must be withdrawn or re-advertised with different properties in order to change global routing behavior." - [2]


#### DNS Poisoning
Detailed Attack Pattern

When an otherwise legitimate DNS server provides malicious ("NXDOMAIN" ("No such domain") code, or ip address for a block-page) DNS responses to requests made of it.

* Resources Required
  * In-Path DNS resolver

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


### Protocol Tampering & Termination
Attack Pattern

* Method of Attack
  * Filter and return [1]

"A variant of filtering requests is where the censor decides to respond back to the user upon filtering the request.  The response may simply disrupt the connection at either or both end points or do so in addition to in- forming the user about the filtering." [1]

  * Allow but return first

"Another variation on “filter and return” is the case where a censor allows the TCP and HTTP connections to proceed as normal but responds back to ei- ther of the end points in a manner similar to “filter and re- turn”." [1]

  * Modify request or response
"As an alternative extreme measure, a censor may modify the request or the response.  A modified request could cause the destination web server to return a less objectionable page, such as the main page of a blogging site instead of a censored blog." [1]

* References
  * [Inferring Mechanics of Web Censorship Around the World](https://www.usenix.org/system/files/conference/foci12/foci12-final1.pdf)


#### Connection Reset
Detailed Attack Pattern

* References
* Resources Required
* Methods of attack
* Mitigations


##### TCP RST Injection
Detailed Attack Pattern

When a client makes a HTTP GET request they are sent one or more spoofed TCP RST packets. This causes the client to terminate the TCP connection.

* References
  * [1] [Inferring Mechanics of Web Censorship Around the World](https://www.usenix.org/system/files/conference/foci12/foci12-final1.pdf)

* Resources Required
  * On/In Path Device


* Methods of attack

* Mitigations
  *

#### DNS Injection
Detailed Attack Pattern

When an On/In-path device sends a malicious ("NXDOMAIN" ("No such domain") code, or DNS A record) responses before a legitimate resolver can, or in combination with DNS Filtering.

* References
  * [Towards a Comprehensive Picture of the Great Firewall’s DNS
Censorship](https://www.usenix.org/system/files/conference/foci14/foci14-anonymous.pdf)
  * [Inferring Mechanics of Web Censorship Around the World](https://www.usenix.org/system/files/conference/foci12/foci12-final1.pdf)


* Related
  * TCP RST Injection

* Resources Required
  * On/In Path Device

* Mitigations
  * DNSSEC
  * DNS-hold-open
  * don't depend on DNS
  * include "hosts file"/IP address in your app
  * Use a .onion domain with Tor support

* Methods of attack
  * Below-Recursive DNS Poisoning
Detailed Attack Pattern

When an On/In-path device between a recursive DNS server and a user sends a malicious ("NXDOMAIN" ("No such domain") code, or DNS A record ) response before a legitimate resolver can.

"DNS blocking that’s done by an ISP or enterprise in order to censor content or protect end users or to insert ads into the web experience occurs between the end user’s laptop or desktop or mobile device and whatever recursive DNS server that end user is depending on." [1]

    * References
      * [1] [Blocking DNS](https://www.isc.org/blogs/blocking-dns/)

  * Above-Recursive DNS Poisoning
Detailed Attack Pattern

When an On/In-path device between a recursive DNS server and a user sends a malicious ("NXDOMAIN" ("No such domain") code, or DNS A record) response before a legitimate resolver can.

"DNS blocking that’s done ... by a government using deliberate DNS poisoning will happen in between an authority server and a recursive server. One could imagine a country that rewrites DNS transactions at its international borders, or that injects false IP routes for well known authority name servers thus taking over their role, ..." [1]

    * References
      *  [1] [Blocking DNS](https://www.isc.org/blogs/blocking-dns/)
