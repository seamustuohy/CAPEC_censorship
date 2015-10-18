# Obstruction
Category

## Communications Blocking
Meta Attack Pattern

### Route Blocking
Attack Pattern

#### DNS Domain Removal
Detailed Attack Pattern

#### BGP Routing Disruption
Detailed Attack Pattern

"Disabling the routing process on critical routers or suppressing BGP information transmission can
  effectively render large parts of a network unreachable." - http://www.caida.org/publications/papers/2011/outages_censorship/outages_censorship.pdf

#### DNS Blocking
  Detailed Attack Pattern

### Data Blocking
Attack Pattern

#### IP address blocking
Detailed Attack Pattern

#### Port Blocking
Detailed Attack Pattern

#### URL Blocking
Detailed Attack Pattern

#### Keyword Blocking
Detailed Attack Pattern

#### Content Filtering
Detailed Attack Pattern

## Communications Limiting
Meta Attack Pattern

### Throttling
Attack Pattern

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

#### DNS redirection
Detailed Attack Pattern

### Protocol Tampering & Termination
Attack Pattern

#### Connection Reset
Detailed Attack Pattern

##### TCP RST Injection
Detailed Attack Pattern

#### DNS Injection
Detailed Attack Pattern

## Network Disruption
Meta Attack Pattern

### Jamming
Attack Pattern

### Disconnecting Hardware
Attack Pattern

### Disabling Network Hardware
Attack Pattern

"Disabling Internet access is an extreme form of Internet censor- ship in which a population’s Internet access is blocked completely, a coarse but technically more straightforward approach than the se- lective blocking used in most Internet censorship regimes. It can be implemented by simply powering down or physically disconnect- ing critical equipment, although this approach typically requires physical co-location with the communications equipment, which may be spread over a wide area" - http://www.caida.org/publications/papers/2011/outages_censorship/outages_censorship.pdf
