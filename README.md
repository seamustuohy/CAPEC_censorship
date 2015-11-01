# CAPEC_censorship

This is a working space for me to build out, and get feedback on a possible addition of an "Obstruction" category for [CAPEC](http://capec.mitre.org/index.html)


[**Click here to explore the current draft structure of the Obstruction category.**](category.md)


## Tasks

### Primary Content Creation Tasks

* **TODO:** [Category](http://capec.mitre.org/about/glossary.html#Category)
* **TODO:** [Meta Attack Patterns](http://capec.mitre.org/about/glossary.html#Meta_Attack_Pattern)
* **TODO:** [Standard Attack Patterns](http://capec.mitre.org/about/glossary.html#Standard_Attack_Pattern)
* **TODO:** [Detailed Attack Pattern](http://capec.mitre.org/about/glossary.html#Detailed_Attack_Pattern)
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



## Notes on scoping from the CAPEC Discussion List

"Obstruction methods are well within scope for CAPEC. Their lack of inclusion is unfortunately due solely to a lack of submission / priority given to other areas. We would love to see obstruction methods added.

I could see a new category titled "Obstruct Interactions"   added to the [Mechanisms of Attack](http://capec.mitre.org/data/definitions/1000.html) view. Under this I could see a meta level pattern titled "Jamming".  What other meta level patterns would there be? Standard and detailed patterns would then want to be developed.

Note that "Flooding" already existing (CAPEC-125) and is used to describe a technique for depleting resources on a system by forcing it to engage in a large number of interactions. Is there a different pattern that might be related to obstruction about filling a communications channel with so much traffic that legitimate comms can't get through?

We would love help developing this area of CAPEC and can update the list with these new patterns if they are developed and submitted."
