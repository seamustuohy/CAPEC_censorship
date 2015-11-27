### [CATEGORY: Injection](https://github.com/elationfoundation/CAPEC_censorship/blob/master/injection.md)A (152)
- XXX - [Traffic Injection](https://github.com/elationfoundation/CAPEC_censorship/blob/master/injection.md#traffic-injection)
  - XXX - [Connection Reset](https://github.com/elationfoundation/CAPEC_censorship/blob/master/injection.md#connection-reset)
    - XXX - [TCP RST Injection](https://github.com/elationfoundation/CAPEC_censorship/blob/master/injection.md#tcp-rst-injection)
  - XXX - [Route Injection](https://github.com/elationfoundation/CAPEC_censorship/blob/master/injection.md#route-injection)
    - XXX - [DNS Injection](https://github.com/elationfoundation/CAPEC_censorship/blob/master/injection.md#dns-injection)

# Traffic Injection

Meta Attack Pattern

* Method of Attack
  * Filter and return [1]

"A variant of filtering requests is where the censor decides to respond back to the user upon filtering the request.  The response may simply disrupt the connection at either or both end points or do so in addition to in- forming the user about the filtering." [1]

  * Allow but return first

"Another variation on “filter and return” is the case where a censor allows the TCP and HTTP connections to proceed as normal but responds back to ei- ther of the end points in a manner similar to “filter and re- turn”." [1]

  * Modify request or response
"As an alternative extreme measure, a censor may modify the request or the response.  A modified request could cause the destination web server to return a less objectionable page, such as the main page of a blogging site instead of a censored blog." [1]

* References
  * [Inferring Mechanics of Web Censorship Around the World](https://www.usenix.org/system/files/conference/foci12/foci12-final1.pdf)

## Connection Reset

Attack Pattern

* Resources Required
* Methods of attack
* Mitigations
* References


### TCP RST Injection

Detailed Attack Pattern

When a client makes a HTTP GET request they are sent one or more spoofed TCP RST packets. This causes the client to terminate the TCP connection.

* References
  * [1] [Inferring Mechanics of Web Censorship Around the World](https://www.usenix.org/system/files/conference/foci12/foci12-final1.pdf)

* Resources Required
  * On/In Path Device

* Methods of attack

* Mitigations

## Route Injection

Attack Pattern

* Resources Required
* Methods of attack
* Mitigations
* References

### DNS Injection

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
