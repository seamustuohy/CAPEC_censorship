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

# [Obstruction](http://capec.mitre.org/data/definitions/607.html) (607)

Meta Attack Pattern


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

In this attack scenario, the attacker actively transmits signals to overpower and disrupt the communication between a target and a satellite. There are two techniques of satellite jamming, orbital and terrestrial.

* References
    * [1] https://smallmedia.org.uk/sites/default/files/Satellite%20Jamming.pdf

* Resources Required
    * Orbital: A Satellite uplink station
    * Terrestrial: A terrestrial satellite jammer
* Methods of attack
    * Orbital Jamming

    An adversary beams contradictory signals at a target satellite using a rogue uplink station. The frequencies sent mix with those of the satellite and the channel group of the targeted feed overridden. The attacker therefore disrupts the ability for anyone within a satellites footprint to use the satellites targeted or neighboring channels. The footprint of a satellite depends upon its position in the sky with higher orbital satellites covering multiple continents.

    * Terrestrial Jamming

    An adversary actively transmits disruptive signals in the direction of the targets consumer-level satellite dishes. The attacker is therefore able to cause disruption in a more targeted range. Portable terrestrial jammers have a range of 3-5 kilometers in urban areas and 20 kilometers in rural areas. This technique requires a terrestrial jammer that is more powerful than the frequencies sent from the satellite.


* Mitigations


## Limiting

Attack Pattern

An adversary intentionally hampers the internet service of the target.

* References
* Resources Required
* Methods of attack
* Mitigations

### Throttling

Detailed Attack Pattern

An adversary intentionally slows the internet service of the target by limiting the total transfer capacity of the target. The attacker is therefore able to limit communication, frustrate the target, or reduce the quality of a specific protocol or service in order to discourage its use.

* Mitigations

  * modify application to ensure good handling of high latency
  * Add long timeouts
  * Add support for retry
  * Add resumeable up/downloads
  * Implement async http libraries like OkHTTP and Volley

### Time Delimited Access

Detailed Attack Pattern

An adversary drops a targets traffic streams after a specified period of time. The attacker is therefore able to frustrate the target and reduce their ability to use the targeted protocol or service in order to discourage its use. For example, in May of 2013 all unknown traffic streams in Iran were dropped after a period of 60 seconds. [1] This technique requires an in-path device.


* References
- [1] https://mailman.stanford.edu/pipermail/liberationtech/2013-May/008334.html
* Resources Required
* Methods of attack
* Mitigations


## [Blockage](https://capec.mitre.org/data/definitions/603.html) (603)

Attack Pattern

An adversary blocks the delivery of an important system resource causing the system to fail or stop working.


### IP Address Blocking

Detailed Attack Pattern

An adversary drops packets because they are destined for a target IP address. The goal of this attack is to prevent connections to the service hosted at the target IP address.

* Resources Required

* Mitigations

have a large pool of backup IPs built into the app support proxy capability in app

* Methods of Attack

The use of an access control list (ACL)

* References
  * [Censorship in the Wild: Analyzing Internet Filtering in Syria](http://conferences2.sigcomm.org/imc/2014/papers/p285.pdf)


### URL Blocking

Detailed Attack Pattern

An adversary drops packets based upon character strings in the requested domain, subdomain, or host. The attacker is therefore able to continue to censor a targeted service if the service changes its IP address and broadly censor a range of websites based upon shared keywords.


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

An adversary drops packets based upon character strings found within the traffic. This technique requires the ability to conduct deep packet inspection with an In-Path device that can drop the targeted traffic and/or connection. The attacker is therefore able to censor targeted content regardless of its source.

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

An adversary drops packets because they are destined for a specific port and protocol combination or matches a protocol specific pattern. The goal of this attack is to prevent the use of specific protocols. This is often used to block protocols that prevent the adversaries from conducting IP, URL, or content blocking and/or monitoring the targets internet usage.

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

An adversary drops packets because they matches a service/application specific pattern. The goal of this attack is to prevent the use of a specific service or application. This is often used to block services that prevent the adversaries from conducting IP, URL, or content blocking and/or monitoring the targets internet usage.

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

An adversary drops DNS requests for a specific domain The attacker is therefore able to censor targeted content by making clients unable to obtain the location of a service.


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

An adversary disables the network route between two targets. The goal of this attack is to fully sever the communications channel ensuing that the targets are unable to communicate. This is usually the result of major error or the use of an "Internet kill switch" in times of social unrest. This pattern differs from most other obstruction patterns because by targeting the route itself, instead of the data passed over the route, there are very few technical mitigation's that the targets can leverage to circumvent this obstruction.

### Disabling Network Hardware

Detailed Attack Pattern

An adversary disables networking hardware by powering down or physically disconnecting critical equipment. The attacker is therefore able to cause widespread censorship that is course, but technically more straightforward than the selective blocking used in most obstruction attacks. This approach typically requires physical co-location with the communications equipment (networking devices, cables, etc.), which may be spread over a wide area Examples of this include a 2008 severing of underseas cables in the Persian Gulf by weather conditions or a ships anchor, and in 2011 when an elderly Georgian woman cut off all internet services to Armenia when she sliced through an underground cable when digging for copper wiring to sell as scrap.

* References
  * [1] [Analysis of Country-wide Internet Outages Caused by
Censorship](http://www.caida.org/publications/papers/2011/outages_censorship/outages_censorship.pdf)

* Resources Required
* Methods of attack
* Mitigations


#### DNS Domain Seizure

Detailed Attack Pattern

An adversary gains control of and disables the domain names for a target service. The goal of this attack is to remove the ability for others to find the targeted service using its domain name. This attack is usually the result of civil or criminal legal interventions. Examples of this attack include the US FBI's seizure of gambling websites, the US DOJ's seizure of child pornography websites, and Microsoft's seizure of all domains owned by the company No-IP in order to disrupt a cyberattack originating from a subset of those domains. This technique requires cooperation from the registrar of the domain being targeted.

* References
* Resources Required
* Methods of attack
* Mitigations


### BGP Route Disabling

Detailed Attack Pattern

An adversary suppresses BGP information from an AS to render the underlying network inaccessible, and/or force less effective routes for traffic to AS's that would otherwise pass through the attackers network. The techniques require the adversary to have control of an ISP's AS.

* References
  * [1] [Why Is It Taking So Long to Secure Internet Routing?](https://queue.acm.org/detail.cfm?id=2668966)
  * [2] [Analysis of Country-wide Internet Outages Caused by Censorship](https://web.archive.org/web/20150912103705/http://www.caida.org/publications/papers/2011/outages_censorship/outages_censorship.pdf)

* Resources Required
  * BGP Router

Observables:  "Disabling a network’s connectivity to the Internet through BGP routing disruption is easily detectable, since it entails changes in the global routing state of the network, i.e., in the control plane. Previously advertised prefixes must be withdrawn or re-advertised with different properties in order to change global routing behavior." - [2]
