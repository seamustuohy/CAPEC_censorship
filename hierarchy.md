# Obstruction
Category

Disruption of system operations by blocking, limiting, disrupting, or tampering with user data, control information, or the communications channel itself.

## Interference
Meta Attack Pattern

"Disruption of system operations by blocking communication of user data or control information." [1]

* Reference
  * [1] [Obstruction; Sub-Def: Interference - Internet Security Glossary, Version 2](https://tools.ietf.org/html/rfc4949#page-204)

### Jamming
Attack Pattern

"An attack that attempts to interfere with the reception of broadcast communications." [1]

* References
  * [1] [jamming - Internet Security Glossary, Version 2](https://tools.ietf.org/html/rfc4949#page-170)

* Mitigations
  * [Frequency Hopping](https://tools.ietf.org/html/rfc4949#page-134)

##### Satellite Jamming
Detailed Attack Pattern

##### Cellular Jamming
Detailed Attack Pattern

##### Wi-Fi Jamming
Detailed Attack Pattern

### Disabling Network Hardware
Attack Pattern

"Disabling Internet access is an extreme form of Internet censor- ship in which a population’s Internet access is blocked completely, a coarse but technically more straightforward approach than the selective blocking used in most Internet censorship regimes. It can be implemented by simply powering down or physically disconnecting critical equipment, although this approach typically requires physical co-location with the communications equipment, which may be spread over a wide area"

* References
  * [1] [Analysis of Country-wide Internet Outages Caused by
Censorship](http://www.caida.org/publications/papers/2011/outages_censorship/outages_censorship.pdf)

### Routing Information Filtering
Attack Pattern
#### DNS Domain Removal
Detailed Attack Pattern

*Is this worth including? It requires the adversary to actually have the root name server remove the domain against a services will.*

#### BGP Routing Disruption
Detailed Attack Pattern

"Disabling the routing process on critical routers or suppressing BGP information transmission can
effectively render large parts of a network unreachable."

* References
  * [1] [Analysis of Country-wide Internet Outages Caused by
Censorship](http://www.caida.org/publications/papers/2011/outages_censorship/outages_censorship.pdf)

#### DNS Filtering
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

### Data Filtering
Attack Pattern

When a specific type of data is dropped by an in-path server. When requests are filtered, corresponding connections time out.

* References
  * [https://www.usenix.org/system/files/conference/foci12/foci12-final1.pdf]

#### IP Address Filtering
Detailed Attack Pattern

Dropping packets because of they are destined for a given IP address.

* Mitigations

have a large pool of backup IPs built into the app
support proxy capability in app

* Methods of Attack

The use of an access control list (ACL)

* References
  * [Censorship in the Wild: Analyzing Internet Filtering in Syria](http://conferences2.sigcomm.org/imc/2014/papers/p285.pdf)


#### Port Based Filtering
Detailed Attack Pattern

* Mitigations

  * Use well-known ports for high-use protocols like 80/tcp, 443/tcp, 993/tcp

#### URL Based Filtering
Detailed Attack Pattern

Filtering based upon the requested URL.

##### Full URL Based Filtering
Detailed Attack Pattern

Filtering based upon the requested URL.

##### URL String-based Filtering
Detailed Attack Pattern

Filtering based upon the use of particular strings included in the requested URL.

* References
  * [Censorship in the Wild: Analyzing Internet Filtering in Syria](http://conferences2.sigcomm.org/imc/2014/papers/p285.pdf)

* Mitigations
  * don't encode meaningful data in URLs


#### Content Filtering
Detailed Attack Pattern

* Mitigations

  * Protect content by using HTTPS
  * Encode content in non-obvious formats
  * Implement trickle-syncing
  * Implement self-throttling to avoid detection of larger downloads

#### Protocol Filtering
Detailed Attack Pattern

Filtering specific protocols.

* Related
  * [Fingerprinting](http://capec.mitre.org/data/definitions/224.html)
  * TODO: Add proposal for network protocol/service fingerprinting along with this

* Mitigations
  * Implement Domain Fronting
  * Implement Pluggable Transport support

#### Service/Application Blocking
Detailed Attack Pattern

Filtering specific protocols.

* Related
  * [Fingerprinting](http://capec.mitre.org/data/definitions/224.html)
  * TODO: Add proposal for network protocol/service fingerprinting along with this

* Mitigations
  * Implement Domain Fronting
  * Implement Pluggable Transport support

## Communications Limiting
Meta Attack Pattern

### Throttling
Attack Pattern

* Mitigations

  * modify application to ensure good handling of high latency
  * Add long timeouts
  * Add support for retry
  * Add resumeable up/downloads
  * Implement async http libraries like OkHTTP and Volley

### Time Delimited Access
Attack Pattern

## Communications Tampering & Termination
Meta Attack Pattern

### Route Tampering & Termination
Attack Pattern

#### BGP Tampering
Detailed Attack Pattern
https://queue.acm.org/detail.cfm?id=2668966

##### BGP Prefix hijacking
Detailed Attack Pattern

##### BGP Subprefix hijacking
Detailed Attack Pattern

##### Route Leaks
Detailed Attack Pattern

Previously advertised prefixes are withdrawn or re-advertised with different properties in order to change global routing behavior.
 -- Detection:  "Disabling a network’s connectivity to the Internet through BGP routing disruption is easily detectable, since it entails changes in the global routing state of the network, i.e., in the control plane .  Previously advertised prefixes must be withdrawn or re-advertised with different properties in order to change global routing behavior." - outages censorship

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

##### Below-Recursive DNS Poisoning
Detailed Attack Pattern

When an otherwise legitimate recursive DNS server provides malicious ("NXDOMAIN" ("No such domain") code, or DNS A record) DNS responses to requests made of it.

When done through a legitimate recursive DNS server I would consider this redirection instead of injection. I would say this is "tampering" instead of "injection" in that they are utilizing their proper role as an in-path routing device to provide DNS responses. If they were an off-path device that was attempting to send a DNS response quicker than the normal DNS could be resolved I would say it is Injection.

"DNS blocking that’s done by an ISP or enterprise in order to censor content or protect end users or to insert ads into the web experience occurs between the end user’s laptop or desktop or mobile device and whatever recursive DNS server that end user is depending on. Your recursive DNS server as you read this article was most likely assigned to you by DHCP along with your IP address unless you’ve taken explicit steps to override this setting and it’s possible for the operator of your network to prevent you from successfully overriding it – which they will do if your override is costing them revenue or if their government insists." [1]

* References

- [1] [Blocking DNS](https://www.isc.org/blogs/blocking-dns/)

##### Above-Recursive DNS Poisoning
Detailed Attack Pattern

When an otherwise legitimate authority DNS server provides malicious ("NXDOMAIN" ("No such domain") code, or DNS A record) responses to requests made of it.

"DNS blocking that’s done by an authority server operator ... One could imagine a country that ... demands that all recursive name server operators in the country use a specific “alternate root” name server system whose design and configuration included various kinds of censorship and overrides." [1]

* References

- [1] [Blocking DNS](https://www.isc.org/blogs/blocking-dns/)


### Protocol Tampering & Termination
Attack Pattern

* Method of Attack
  * Filter and return [1]
  * Allow but return first [1]
  * Modify request or response [1]

* References
  * [](https://www.usenix.org/system/files/conference/foci12/foci12-final1.pdf)

#### Connection Reset
Detailed Attack Pattern

##### TCP RST Injection
Detailed Attack Pattern

#### DNS Injection
Detailed Attack Pattern

When an On/In-path device sends a malicious ("NXDOMAIN" ("No such domain") code, or DNS A record) responses before a legitimate resolver can, or in combination with DNS Filtering.

* References
  * [Towards a Comprehensive Picture of the Great Firewall’s DNS
Censorship](https://www.usenix.org/system/files/conference/foci14/foci14-anonymous.pdf)
  * [](https://www.usenix.org/system/files/conference/foci12/foci12-final1.pdf)
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

##### Below-Recursive DNS Poisoning
Detailed Attack Pattern

When an On/In-path device between a recursive DNS server and a user sends a malicious ("NXDOMAIN" ("No such domain") code, or DNS A record ) response before a legitimate resolver can.

"DNS blocking that’s done by an ISP or enterprise in order to censor content or protect end users or to insert ads into the web experience occurs between the end user’s laptop or desktop or mobile device and whatever recursive DNS server that end user is depending on." [1]

* References

- [1] [Blocking DNS](https://www.isc.org/blogs/blocking-dns/)

##### Above-Recursive DNS Poisoning
Detailed Attack Pattern

When an On/In-path device between a recursive DNS server and a user sends a malicious ("NXDOMAIN" ("No such domain") code, or DNS A record) response before a legitimate resolver can.

"DNS blocking that’s done ... by a government using deliberate DNS poisoning will happen in between an authority server and a recursive server. One could imagine a country that rewrites DNS transactions at its international borders, or that injects false IP routes for well known authority name servers thus taking over their role, ..." [1]

* References

- [1] [Blocking DNS](https://www.isc.org/blogs/blocking-dns/)
