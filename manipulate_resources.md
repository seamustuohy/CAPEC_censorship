### CATEGORY: [Manipulate Resources](https://github.com/elationfoundation/CAPEC_censorship/blob/master/manipulate_resources.md) (262)
- 607 - [Obstruction](https://github.com/elationfoundation/CAPEC_censorship/blob/master/manipulate_resources.md#obstruction-601)
  - 601 - [Jamming](https://github.com/elationfoundation/CAPEC_censorship/blob/master/manipulate_resources.md#jamming-601)
    - 604 - [WiFi Jamming](https://github.com/elationfoundation/CAPEC_censorship/blob/master/manipulate_resources.md#wi-fi-jamming-604)
    - 605 - [Cellular Jamming](https://github.com/elationfoundation/CAPEC_censorship/blob/master/manipulate_resources.md#cellular-jamming-605)
    - XXX - [Satellite Jamming](https://github.com/elationfoundation/CAPEC_censorship/blob/master/manipulate_resources.md#satellite-jamming)
  - XXX - [Limiting](https://github.com/elationfoundation/CAPEC_censorship/blob/master/manipulate_resources.md#throttling)
    - XXX - [Throttling](https://github.com/elationfoundation/CAPEC_censorship/blob/master/manipulate_resources.md#throttling)
    - XXX - [Time Delimited Access](https://github.com/elationfoundation/CAPEC_censorship/blob/master/manipulate_resources.md#data-filtering)
  - 603 - Blockage
    - 571 - Block Logging to Central Repository
    - XXX - [IP Address Filtering](https://github.com/elationfoundation/CAPEC_censorship/blob/master/manipulate_resources.md#ip-address-filtering)
    - XXX - [URL Based Filtering](https://github.com/elationfoundation/CAPEC_censorship/blob/master/manipulate_resources.md#url-based-filtering)
    - XXX - [Content Filtering](https://github.com/elationfoundation/CAPEC_censorship/blob/master/manipulate_resources.md#protocol-filtering)
    - XXX - [Protocol Filtering](https://github.com/elationfoundation/CAPEC_censorship/blob/master/manipulate_resources.md#protocol-filtering)
    - XXX - [Service/Application Blocking](https://github.com/elationfoundation/CAPEC_censorship/blob/master/manipulate_resources.md#serviceapplication-blocking)
  - XXX - [Route Disruption](https://github.com/elationfoundation/CAPEC_censorship/blob/master/manipulate_resources.md#route-disruption)
    - XXX - [Disabling Network Hardware](https://github.com/elationfoundation/CAPEC_censorship/blob/master/manipulate_resources.md#disabling-network-hardware)
    - XXX - [DNS Domain Removal](https://github.com/elationfoundation/CAPEC_censorship/blob/master/manipulate_resources.md#dns-domain-removal)
    - XXX - [DNS Filtering](https://github.com/elationfoundation/CAPEC_censorship/blob/master/manipulate_resources.md#bgp-route-disruption)
    - XXX - [BGP Route Disruption](https://github.com/elationfoundation/CAPEC_censorship/blob/master/manipulate_resources.md#bgp-route-disruption)

# [Obstruction](http://capec.mitre.org/data/definitions/607.html) (601)

Meta Attack Pattern

An adversary...
The goal of this attack is to... ||  The attacker is therefore able to...
This is usually the result of...
For example,...
This attack differs from ... in that ....
The techniques require...

## [Jamming](http://capec.mitre.org/data/definitions/601.html) (601)

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


An adversary...
The goal of this attack is to... ||  The attacker is therefore able to...
This is usually the result of...
For example,...
This attack differs from ... in that ....
The techniques require...


* References
* Resources Required
* Methods of attack
* Mitigations


## Limiting

Attack Pattern

An adversary...
The goal of this attack is to... ||  The attacker is therefore able to...
This is usually the result of...
For example,...
This attack differs from ... in that ....
The techniques require...


* References
* Resources Required
* Methods of attack
* Mitigations

### Throttling

Detailed Attack Pattern

An adversary...
The goal of this attack is to... ||  The attacker is therefore able to...
This is usually the result of...
For example,...
This attack differs from ... in that ....
The techniques require...


* Mitigations

  * modify application to ensure good handling of high latency
  * Add long timeouts
  * Add support for retry
  * Add resumeable up/downloads
  * Implement async http libraries like OkHTTP and Volley

### Time Delimited Access

Detailed Attack Pattern

An adversary...
The goal of this attack is to... ||  The attacker is therefore able to...
This is usually the result of...
For example,...
This attack differs from ... in that ....
The techniques require...


* References
* Resources Required
* Methods of attack
* Mitigations


## [Blockage](https://capec.mitre.org/data/definitions/603.html) (603)

Attack Pattern

An adversary blocks the delivery of an important system resource causing the system to fail or stop working.


### IP Address Blocking

Detailed Attack Pattern

Dropping packets because of they are destined for a given IP address.

An adversary...
The goal of this attack is to... ||  The attacker is therefore able to...
This is usually the result of...
For example,...
This attack differs from ... in that ....
The techniques require...

* Resources Required

* Mitigations

have a large pool of backup IPs built into the app support proxy capability in app

* Methods of Attack

The use of an access control list (ACL)

* References
  * [Censorship in the Wild: Analyzing Internet Filtering in Syria](http://conferences2.sigcomm.org/imc/2014/papers/p285.pdf)


### URL Blocking

Detailed Attack Pattern

Filtering based upon the requested domain, subdomain, or host.

An adversary...
The goal of this attack is to... ||  The attacker is therefore able to...
This is usually the result of...
For example,...
This attack differs from ... in that ....
The techniques require...


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

### Content Blocking

Detailed Attack Pattern

An adversary...
The goal of this attack is to... ||  The attacker is therefore able to...
This is usually the result of...
For example,...
This attack differs from ... in that ....
The techniques require...


* References
* Resources Required
* Methods of attack

* Mitigations

  * Protect content by using HTTPS
  * Encode content in non-obvious formats
  * Implement trickle-syncing
  * Implement self-throttling to avoid detection of larger downloads

### Protocol Blocking

Detailed Attack Pattern

An adversary...
The goal of this attack is to... ||  The attacker is therefore able to...
This is usually the result of...
For example,...
This attack differs from ... in that ....
The techniques require...

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

An adversary...
The goal of this attack is to... ||  The attacker is therefore able to...
This is usually the result of...
For example,...
This attack differs from ... in that ....
The techniques require...

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

#### DNS Blocking

Detailed Attack Pattern

When DNS requests for a specific domain are dropped by an in-path server.

An adversary...
The goal of this attack is to... ||  The attacker is therefore able to...
This is usually the result of...
For example,...
This attack differs from ... in that ....
The techniques require...

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


## Route Disabling

Attack Pattern

An adversary...
The goal of this attack is to... ||  The attacker is therefore able to...
This is usually the result of...
For example,...
This attack differs from ... in that ....
The techniques require...


### Disabling Network Hardware

Detailed Attack Pattern

"Disabling Internet access is an extreme form of Internet censor- ship in which a population’s Internet access is blocked completely, a coarse but technically more straightforward approach than the selective blocking used in most Internet censorship regimes. It can be implemented by simply powering down or physically disconnecting critical equipment, although this approach typically requires physical co-location with the communications equipment, which may be spread over a wide area"

An adversary...
The goal of this attack is to... ||  The attacker is therefore able to...
This is usually the result of...
For example,...
This attack differs from ... in that ....
The techniques require...


* References
  * [1] [Analysis of Country-wide Internet Outages Caused by
Censorship](http://www.caida.org/publications/papers/2011/outages_censorship/outages_censorship.pdf)

* Resources Required
* Methods of attack
* Mitigations

#### DNS Domain Removal

Detailed Attack Pattern

An adversary...
The goal of this attack is to... ||  The attacker is therefore able to...
This is usually the result of...
For example,...
This attack differs from ... in that ....
The techniques require...


*Is this worth including? It requires the adversary to actually have the root name server remove the domain against a services will.*

* References
* Resources Required
* Methods of attack
* Mitigations


### BGP Route Disabling

Detailed Attack Pattern

"Disabling the routing process on critical routers or suppressing BGP information transmission can effectively render large parts of a network unreachable." [2]

An adversary...
The goal of this attack is to... ||  The attacker is therefore able to...
This is usually the result of...
For example,...
This attack differs from ... in that ....
The techniques require...


* References
  * [1] [Why Is It Taking So Long to Secure Internet Routing?](https://queue.acm.org/detail.cfm?id=2668966)
  * [2] [Analysis of Country-wide Internet Outages Caused by Censorship](https://web.archive.org/web/20150912103705/http://www.caida.org/publications/papers/2011/outages_censorship/outages_censorship.pdf)

* Resources Required
  * BGP Router

Observables:  "Disabling a network’s connectivity to the Internet through BGP routing disruption is easily detectable, since it entails changes in the global routing state of the network, i.e., in the control plane. Previously advertised prefixes must be withdrawn or re-advertised with different properties in order to change global routing behavior." - [2]
