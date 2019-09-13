## Peering Policy ##

FastEthernet (AS206479) has a nearly open peering policy, but we do have some policies to follow:

 * If your IXP connection is NOT in PeeringDB, changes need to be handled manually
 * All peers' prefixes are filtered based on IRR. Exceptions are made on an individual basis.
 * All peers' prefixes are filtered based on RPKI.
 * Prefix filters facing peers are updated every 6 hours from `whois.radb.net`.

We provision our peering configuration automatically from PeeringDB, please ensure that your entry is kept up-to-date including IP addresses and number of prefixes announced.
