### CATEGORY: Manipulate Resources (262)
607 - Obstruction
      601 - Jamming
              604 - WiFi Jamming
              605 - Cellular Jamming
              XXX - Satellite Jamming
      XXX - Limiting
              XXX - Throttling
              XXX - Time Delimited Access
      XXX - Data Filtering
              XXX - IP Address Filtering
              XXX - URL Based Filtering
              XXX - Content Filtering
              XXX - Protocol Filtering
              XXX - Service/Application Blocking

161 - Infrastructure Manipulation
      XXX - Route Manipulation
              XXX - BGP Tampering
              XXX - BGP Route Leaks
              142 - DNS Cache Poisoning
      XXX - Route Disruption
              XXX - Disabling Network Hardware
              XXX - DNS Domain Removal
              XXX - DNS Filtering
              XXX - BGP Route Disruption

# [Obstruction](http://capec.mitre.org/data/definitions/607.html) (601)

Meta Attack Pattern

## [Jamming[(http://capec.mitre.org/data/definitions/601.html) (601)

Attack Pattern

An adversary uses radio noise or signals in an attempt to disrupt communications.

* References
  * [1] [jamming - Internet Security Glossary, Version 2](https://tools.ietf.org/html/rfc4949#page-170)

* Mitigations
  * [Frequency Hopping](https://tools.ietf.org/html/rfc4949#page-134)

* Resources Required
* Methods of attack

### [Wi-Fi Jamming](http://capec.mitre.org/data/definitions/604.html) (604)

Detailed Attack Pattern

In this attack scenario, the attacker actively transmits on the Wi-Fi channel to prevent users from transmitting or receiving data from the targeted Wi-Fi network. There are several known techniques to perform this attack – for example: the attacker may flood the Wi-Fi access point (e.g. the retransmission device) with deauthentication frames. Another method is to transmit high levels of noise on the RF band used by the Wi-Fi network.

* References
* Resources Required
* Methods of attack
* Mitigations

### [Cellular Jamming](http://capec.mitre.org/data/definitions/605.html) (605)

Detailed Attack Pattern

In this attack scenario, the attacker actively transmits signals to overpower and disrupt the communication between a cellular user device and a cell tower. Several existing techniques are known in the open literature for this attack for 2G, 3G, and 4G LTE cellular technology. For example, some attacks target cell towers by overwhelming them with false status messages, while others introduce high levels of noise on signaling channels.

* References
* Resources Required
* Methods of attack
* Mitigations

### Satellite Jamming

Detailed Attack Pattern

* References
* Resources Required
* Methods of attack
* Mitigations


## Limiting

Attack Pattern

* References
* Resources Required
* Methods of attack
* Mitigations

### Throttling

Detailed Attack Pattern

* Mitigations

  * modify application to ensure good handling of high latency
  * Add long timeouts
  * Add support for retry
  * Add resumeable up/downloads
  * Implement async http libraries like OkHTTP and Volley

### Time Delimited Access

Detailed Attack Pattern

* References
* Resources Required
* Methods of attack
* Mitigations


## Data Filtering

Attack Pattern

When a specific type of data is dropped by an in-path server. When requests are filtered the corresponding connections time out.

* Resources Required
  * in-path router

* Methods of attack
  * Filter Request

"The first opportunity for this arises during the TCP connection establishment phase.  However, since hostnames are not available in TCP SYN packets, the black- list for such filtering would consist of IP addresses, port and protocol combinations. The next opportunity for filtering requests arises when HTTP requests are made. The blacklist for such filtering can consist of a combination of domain, sub-domain, or hostnames and even regular expressions focusing on URLs and keywords. When requests are filtered, corresponding connections time out and the browser dis- plays an error stating this to the end user.  Likewise, since the request never reaches the destination web server, it can- not even infer that censorship is occurring." [1]

  * Filter Response

"As the dual to filtering the request, a censor may filter on response, either instead of filtering requests or in addition.  Response-based filtering can only be keyword based, however, as the host- name and page requested are not included in an HTTP response" [1]

* Mitigations

* References
  * [1] [Inferring Mechanics of Web Censorship Around the World](https://www.usenix.org/system/files/conference/foci12/foci12-final1.pdf)

### IP Address Filtering

Detailed Attack Pattern

Dropping packets because of they are destined for a given IP address.

* Resources Required

* Mitigations

have a large pool of backup IPs built into the app support proxy capability in app

* Methods of Attack

The use of an access control list (ACL)

* References
  * [Censorship in the Wild: Analyzing Internet Filtering in Syria](http://conferences2.sigcomm.org/imc/2014/papers/p285.pdf)


### URL Based Filtering

Detailed Attack Pattern

Filtering based upon the requested domain, subdomain, or host.

* References
* Resources Required
* Mitigations
  * don't encode meaningful data in URLs

* Methods of Attack
  * Full URL Based Filtering

Filtering based upon the requested URL.

  * URL String-based Filtering

Filtering based upon the use of particular strings included in the requested URL.

    * References
      * [Censorship in the Wild: Analyzing Internet Filtering in Syria](http://conferences2.sigcomm.org/imc/2014/papers/p285.pdf)

    * Mitigations

### Content Filtering

Detailed Attack Pattern

* References
* Resources Required
* Methods of attack

* Mitigations

  * Protect content by using HTTPS
  * Encode content in non-obvious formats
  * Implement trickle-syncing
  * Implement self-throttling to avoid detection of larger downloads

### Protocol Filtering

Detailed Attack Pattern


Filtering specific traffic because they are destined for a specific port and protocol combination.

* References
* Resources Required
* Methods of attack

* Related
  * [Fingerprinting](http://capec.mitre.org/data/definitions/224.html)
  * TODO: Add proposal for network protocol/service fingerprinting along with this

* Mitigations
  * Implement Domain Fronting
  * Implement Pluggable Transport support
  * Use well-known ports for high-use protocols like 80/tcp, 443/tcp, 993/tcp
  * Implement Pluggable Transport support

### Service/Application Blocking

Detailed Attack Pattern

Filtering specific protocols.

* References
* Resources Required
* Methods of attack

* Related
  * [Fingerprinting](http://capec.mitre.org/data/definitions/224.html)
  * TODO: Add proposal for network protocol/service fingerprinting along with this

* Mitigations
  * Implement Domain Fronting
  * Implement Pluggable Transport support


# [Infrastructure Manipulation](http://capec.mitre.org/data/definitions/161.html) (161)

Meta Attack Pattern

An attacker exploits characteristics of the infrastructure of a network entity in order to perpetrate attacks or information gathering on network objects or effect a change in the ordinary information flow between network objects. Most often, this involves manipulation of the routing of network messages so, instead of arriving at their proper destination, they are directed towards an entity of the attackers' choosing, usually a server controlled by the attacker. The victim is often unaware that their messages are not being processed correctly. For example, a targeted client may believe they are connecting to their own bank but, in fact, be connecting to a Pharming site controlled by the attacker which then collects the user's login information in order to hijack the actual bank account.

## Route Manipulation

Attack Pattern

* References
* Resources Required
* Methods of attack
* Mitigations


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

## Route Disruption

Attack Pattern

### Disabling Network Hardware

Detailed Attack Pattern

"Disabling Internet access is an extreme form of Internet censor- ship in which a population’s Internet access is blocked completely, a coarse but technically more straightforward approach than the selective blocking used in most Internet censorship regimes. It can be implemented by simply powering down or physically disconnecting critical equipment, although this approach typically requires physical co-location with the communications equipment, which may be spread over a wide area"

* References
  * [1] [Analysis of Country-wide Internet Outages Caused by
Censorship](http://www.caida.org/publications/papers/2011/outages_censorship/outages_censorship.pdf)

* Resources Required
* Methods of attack
* Mitigations

#### DNS Domain Removal####

Detailed Attack Pattern

*Is this worth including? It requires the adversary to actually have the root name server remove the domain against a services will.*

* References
* Resources Required
* Methods of attack
* Mitigations

#### DNS Filtering####

Detailed Attack Pattern

When DNS requests for a specific domain are dropped by an in-path server.

*Is this common enough to include? I have only really heard of DNS blocking that uses redirection being used in the wild.*

* Mitigations
  * Hard Coded Alternate DNS server in applications
  * don't depend on DNS
  * include "hosts file"/IP address in your app
  * Use a .onion domain with Tor support

* Notes
  * See: delisting & DNS-based Blackhole Lists

* References
* Resources Required
* Methods of attack

### BGP Route Disruption

Detailed Attack Pattern

"Disabling the routing process on critical routers or suppressing BGP information transmission can effectively render large parts of a network unreachable." [2]

* References
  * [1] [Why Is It Taking So Long to Secure Internet Routing?](https://queue.acm.org/detail.cfm?id=2668966)
  * [2] [Analysis of Country-wide Internet Outages Caused by Censorship](https://web.archive.org/web/20150912103705/http://www.caida.org/publications/papers/2011/outages_censorship/outages_censorship.pdf)

* Resources Required
  * BGP Router

Observables:  "Disabling a network’s connectivity to the Internet through BGP routing disruption is easily detectable, since it entails changes in the global routing state of the network, i.e., in the control plane. Previously advertised prefixes must be withdrawn or re-advertised with different properties in order to change global routing behavior." - [2]
