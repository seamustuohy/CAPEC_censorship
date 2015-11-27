# CAPEC_censorship

This is a working space for me to build out, and get feedback on a possible addition of an "Obstruction" category for [CAPEC](http://capec.mitre.org/index.html)

## Current Draft Structure

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

### CATEGORY: Injection (152)
XXX - Traffic Injection
      XXX - Connection Reset
            XXX - TCP RST Injection
      XXX - Route Injection
            XXX - DNS Injection

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

* **TODO:** Incorporate feedback on hierarchy and included items
* **TODO:** Get Examples/Instances for each item
* **TODO:** Collect indicators from censorship detection community
* **TODO:** Collect Design/security patterns from circumvention community

### Secondary Content Creation Tasks

* **TODO:** Observables (Probing Techniques)
* **TODO:** Solutions and Mitigation's
* **TODO:** Obfuscation Techniques
* **TODO:** Target Attack Surface
* **TODO:** Resources Required
* **TODO:** (Non)Recommended Design/Security Patterns
