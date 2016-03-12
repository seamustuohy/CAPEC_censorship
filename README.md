# CAPEC_censorship

This is a working space for me to build out, and get feedback on a possible addition of an "Obstruction" category for [CAPEC](http://capec.mitre.org/index.html)

## Current Draft Structure

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
    - XXX - [IP Address Blocking](https://github.com/elationfoundation/CAPEC_censorship/blob/master/manipulate_resources.md#ip-address-blocking)
    - XXX - [URL Blocking](https://github.com/elationfoundation/CAPEC_censorship/blob/master/manipulate_resources.md#url-blocking)
    - XXX - [Content Blocking](https://github.com/elationfoundation/CAPEC_censorship/blob/master/manipulate_resources.md#protocol-blocking)
    - XXX - [Protocol Blocking](https://github.com/elationfoundation/CAPEC_censorship/blob/master/manipulate_resources.md#protocol-blocking)
    - XXX - [Service/Application Blocking](https://github.com/elationfoundation/CAPEC_censorship/blob/master/manipulate_resources.md#serviceapplication-blocking)
    - XXX - [DNS Blocking](https://github.com/elationfoundation/CAPEC_censorship/blob/master/manipulate_resources.md#bgp-route-disabling)
  - XXX - [Route Disabling](https://github.com/elationfoundation/CAPEC_censorship/blob/master/manipulate_resources.md#route-disabling)
    - XXX - [Disabling Network Hardware](https://github.com/elationfoundation/CAPEC_censorship/blob/master/manipulate_resources.md#disabling-network-hardware)
    - XXX - [DNS Domain Removal](https://github.com/elationfoundation/CAPEC_censorship/blob/master/manipulate_resources.md#dns-domain-removal)
    - XXX - [BGP Route Disabling](https://github.com/elationfoundation/CAPEC_censorship/blob/master/manipulate_resources.md#bgp-route-disabling)

### CATEGORY: Deceptive Interactions (156)
- 154 - Resource Location Spoofing
  - 161 - Route Manipulation
    - XXX - [BGP Tampering](https://github.com/elationfoundation/CAPEC_censorship/blob/master/deceptive_interaction.md#bgp-tampering)
    - XXX - [BGP Route Leaks](https://github.com/elationfoundation/CAPEC_censorship/blob/master/deceptive_interaction.md#bgp-route-leaks)
- 148 - Content Spoofing
  - 141 - Cache Poisoning
    - 142 - [DNS Cache Poisoning](https://github.com/elationfoundation/CAPEC_censorship/blob/master/deceptive_interaction.md#dns-cache-poisoning-142)

### CATEGORY: [Injection](https://github.com/elationfoundation/CAPEC_censorship/blob/master/injection.md) (152)
- XXX - [Traffic Injection](https://github.com/elationfoundation/CAPEC_censorship/blob/master/injection.md#traffic-injection)
  - XXX - [Connection Reset](https://github.com/elationfoundation/CAPEC_censorship/blob/master/injection.md#connection-reset)
    - XXX - [TCP RST Injection](https://github.com/elationfoundation/CAPEC_censorship/blob/master/injection.md#tcp-rst-injection)
  - XXX - [Route Injection](https://github.com/elationfoundation/CAPEC_censorship/blob/master/injection.md#route-injection)
    - XXX - [DNS Injection](https://github.com/elationfoundation/CAPEC_censorship/blob/master/injection.md#dns-injection)

## Tasks

### Primary Content Creation Tasks

* **DONE:** [Category](http://capec.mitre.org/about/glossary.html#Category)
* **DONE:** [Meta Attack Patterns](http://capec.mitre.org/about/glossary.html#Meta_Attack_Pattern)
* **DONE:** [Standard Attack Patterns](http://capec.mitre.org/about/glossary.html#Standard_Attack_Pattern)
* **DONE:** [Detailed Attack Pattern](http://capec.mitre.org/about/glossary.html#Detailed_Attack_Pattern)
* **TODO:** Indicators/Warnings of Attack

This element represents a container of one or more indicator warning of attack. Indicator warning of attack describes activities, events, conditions or behaviors that may indicate that an attack of this type is imminent, in progress or has occurred.

* **TODO:** Relationships (with other attack patterns e.g. Interception)

The Relationships structure contains one or more Relationship elements, each of which identifies an association between this structure, whether it is an Attack Pattern, Category, or Compound_Element and another structure.

* **TODO:** Examples-Instances

This element represents a container of one or more example instances. An example instance details an explanatory example or demonstrative exploit instance of this attack, USAGE: This element is used to to help the reader understand the nature, context and variability of the attack in more practical and concrete terms.

### Primary Community Tasks

The censorship detection & measurement community, the CAPEC community, and censorship circumvention development community should be reached out to for feedback to ensure that anything developed can be included in CAPEC and is representative of the information sharing needs of the censorship circumvention and detection communities.

* **DONE:** Incorporate feedback on hierarchy and included items
* **TODO:** Get Examples/Instances for each item
* **TODO:** Collect indicators from censorship detection community
* **TODO:** Collect Design/security patterns from circumvention community
* **TODO:** Review existing content for possible text
  - https://tools.ietf.org/html/draft-hall-censorship-tech-01
  - https://www.ietf.org/id/draft-iab-filtering-considerations-09.txt
  - https://www.rfc-editor.org/rfc/rfc4949.txt

### Secondary Content Creation Tasks

* **TODO:** Observables (Probing Techniques)
* **TODO:** Solutions and Mitigation's
* **TODO:** Obfuscation Techniques
* **TODO:** Target Attack Surface
* **TODO:** Resources Required
* **TODO:** (Non)Recommended Design/Security Patterns
