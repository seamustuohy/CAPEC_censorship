# Interference#

Meta Attack Pattern

"Disruption of system operations by blocking communication of user data or control information." [1]

* Reference
  * [1] [Obstruction; Sub-Def: Interference - Internet Security Glossary, Version 2](https://tools.ietf.org/html/rfc4949#page-204)

* Resources Required
* Methods of attack
* Mitigations


## Jamming##

Attack Pattern

"An attack that attempts to interfere with the reception of broadcast communications." [1]

* References
  * [1] [jamming - Internet Security Glossary, Version 2](https://tools.ietf.org/html/rfc4949#page-170)

* Mitigations
  * [Frequency Hopping](https://tools.ietf.org/html/rfc4949#page-134)

* Resources Required
* Methods of attack


#### Satellite Jamming####

Detailed Attack Pattern

* References
* Resources Required
* Methods of attack
* Mitigations

#### Cellular Jamming####

Detailed Attack Pattern

* References
* Resources Required
* Methods of attack
* Mitigations


#### Wi-Fi Jamming####

Detailed Attack Pattern

* References
* Resources Required
* Methods of attack
* Mitigations

## Disabling Network Hardware##

Attack Pattern

"Disabling Internet access is an extreme form of Internet censor- ship in which a population’s Internet access is blocked completely, a coarse but technically more straightforward approach than the selective blocking used in most Internet censorship regimes. It can be implemented by simply powering down or physically disconnecting critical equipment, although this approach typically requires physical co-location with the communications equipment, which may be spread over a wide area"

* References
  * [1] [Analysis of Country-wide Internet Outages Caused by
Censorship](http://www.caida.org/publications/papers/2011/outages_censorship/outages_censorship.pdf)

* Resources Required
* Methods of attack
* Mitigations


## Routing Information Filtering##

Attack Pattern

* References
* Resources Required
* Methods of attack
* Mitigations

### DNS Domain Removal###

Detailed Attack Pattern

*Is this worth including? It requires the adversary to actually have the root name server remove the domain against a services will.*

* References
* Resources Required
* Methods of attack
* Mitigations


### BGP Routing Disruption###

Detailed Attack Pattern

"Disabling the routing process on critical routers or suppressing BGP information transmission can
effectively render large parts of a network unreachable."

* References
  * [1] [Analysis of Country-wide Internet Outages Caused by
Censorship](http://www.caida.org/publications/papers/2011/outages_censorship/outages_censorship.pdf)

* Resources Required
* Methods of attack
* Mitigations

### DNS Filtering###

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

## Data Filtering##

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

### IP Address Filtering###

Detailed Attack Pattern

Dropping packets because of they are destined for a given IP address.

* Resources Required

* Mitigations

have a large pool of backup IPs built into the app
support proxy capability in app

* Methods of Attack

The use of an access control list (ACL)

* References
  * [Censorship in the Wild: Analyzing Internet Filtering in Syria](http://conferences2.sigcomm.org/imc/2014/papers/p285.pdf)


### Port/Protocol Based Filtering###

Detailed Attack Pattern

Dropping packets because they are destined for a specific port and protocol combination.

* References
* Resources Required
* Methods of attack

* Mitigations

  * Use well-known ports for high-use protocols like 80/tcp, 443/tcp, 993/tcp
  * Implement Pluggable Transport support

### URL Based Filtering###

Detailed Attack Pattern

Filtering based upon the requested domain, subdomain, or host.

* References
* Resources Required
* Methods of attack
* Mitigations

#### Full URL Based Filtering####

Detailed Attack Pattern

Filtering based upon the requested URL.

* References
* Resources Required
* Methods of attack
* Mitigations


#### URL String-based Filtering####

Detailed Attack Pattern

Filtering based upon the use of particular strings included in the requested URL.

* Resources Required
* Methods of attack


* References
  * [Censorship in the Wild: Analyzing Internet Filtering in Syria](http://conferences2.sigcomm.org/imc/2014/papers/p285.pdf)

* Mitigations
  * don't encode meaningful data in URLs


### Content Filtering###

Detailed Attack Pattern

* References
* Resources Required
* Methods of attack

* Mitigations

  * Protect content by using HTTPS
  * Encode content in non-obvious formats
  * Implement trickle-syncing
  * Implement self-throttling to avoid detection of larger downloads

### Protocol Filtering###

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

### Service/Application Blocking###

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
