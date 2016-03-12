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

An adversary originates a BGP prefix that was not allocated to its ISP's AS (autonomous system). The goal of this attack is to have the traffic destined for a legitimate service be forwarded to the adversaries AS instead of to the legitimate AS. For example, Pakistan Telecom's AS 17557 originated the subprefix 208.65.153.0/24 of YouTube's prefix 208.65.153.0/22 to its customer ASes in Pakistan in response to Authoritiees demanding that YouTube be censored within Pakistan. The techniques require the adversary to have control of an ISP's AS with neighbors that it can make malicious BGP announcements to.


* References
  * [1] [Why Is It Taking So Long to Secure Internet Routing?](https://queue.acm.org/detail.cfm?id=2668966)
  * [Interconnection and Traffic Exchange on the Internet](http://www.bitag.org/documents/Interconnection-and-Traffic-Exchange-on-the-Internet.pdf)
  * [2] [Practical Defenses Against BGP Prefix Hijacking](http://docs.lib.purdue.edu/cgi/viewcontent.cgi?article=1365&context=ecetr)

* Resources Required
  * AS (autonomous system)

* Method of Attack
  * BGP Prefix Hijacking

"In a prefix hijack, the hijacking AS originates the exact same prefix as the AS(es) that is legitimately allocated the victim IP prefix. The bogus BGP announcement originated by the hijacking AS will be disseminated throughout the routing system, and the other ASes will use their local policies to choose between routes to the legitimate origin AS(es) and bogus routes originated by the hijacking AS." [1]

  * BGP Subprefix Hijacking

"In a subprefix hijack, the hijacking AS originates a subprefix of the victim’s IP prefix—that is, a prefix that is covered by the victim IP prefix."

### BGP Route Leaks

Detailed Attack Pattern

"... the perpetrator announces a legitimate route that it is actually using, but announces it to too many of its neighbors. The perpetrator is then overwhelmed by a flood of traffic from neighbors that select the leaked route." [1]

An adversary announces a legitimate route, but announces it to too many neighboring ASes. The adversary is then overwhelmed by a traffic from neighbors that select the leaked route. The goal of this attack is to capture legitimate traffic that would otherwise be routed through other ASes routed through the "leaking AS". This attack can be used to intentionally censor through targeted dropping/rejection of traffic or unintentionally blackholeing all traffic by overwhelming the network. The techniques require the adversary to have control of an ISP's AS with neighbors that it can make BGP announcements to.

* Attack Motivation

" Understanding why this had an impact requires knowledge of [an AS' neighbors] local routing policies. Many routers likely including those in a neighboring [AS], are configured to prefer a route through a neighboring customer over one through a neighboring settlement-free peer. By forwarding traffic through its customers, an AS can generate more revenue. As such, [an AS' neighbors] routers [may prefer] the customer route through [the leaked route] over the usual settlement-free peering route directly to [the destination]." [1]

* References
  * [1] [Why Is It Taking So Long to Secure Internet Routing?](https://queue.acm.org/detail.cfm?id=2668966)

* Resources Required
  * ISP's AS

### [DNS Cache Poisoning](http://capec.mitre.org/data/definitions/142.html) (142)


* Mitigations

  * Hard Coded Alternate DNS server in applications
  * don't depend on DNS
  * include "hosts file"/IP address in your app
  * Use a .onion domain with Tor support

* Methods of Attack

  * Below-Recursive DNS Poisoning

An adversary provides malicious ("NXDOMAIN" ("No such domain") code, or DNS A record) DNS responses to requests made of it. This technique requires the adversary to be an otherwise legitimate recursive DNS server.

  * Above-Recursive DNS Poisoning

An adversary provides malicious ("NXDOMAIN" ("No such domain") code, or DNS A record) DNS responses to requests made of it. This technique requires the adversary to be an otherwise legitimate authority DNS server.
