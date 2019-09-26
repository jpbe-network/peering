### Peering Policy ###

FastEthernet (AS206479) has a nearly open peering policy, but we do have some policies to follow:

 * If your IXP connection is ***NOT*** in PeeringDB, changes need to be handled manually
 * We will ***NOT*** setup any IPv4/IPv6-only sessions. Peer with the RS for that.
 * All peers' prefixes are filtered based on IRR. Exceptions are made on an individual basis.
 * All peers' prefixes are filtered based on RPKI.
 * Prefix filters facing peers are updated every 6 hours from `whois.radb.net`.

We provision our peering configuration automatically from PeeringDB, please ensure that your entry is kept up-to-date including IP addresses and number of prefixes announced. We always add 10% of your PeeringDB number of prefixes announced on top. You will get at 80% of your configured limit a warning. If you exceeded the limit the session is going to shut down. The session will recover 5 minutes after you stop exceeding the limit.

For all concerns just drop us a mail at ```peerops@fastether.net```.

### How can i peer with you ? ###

Peering with FastEthernet (AS206479) is as simple as writing a configuration file.

Just fork this repository, add yourself to ```peers.yaml``` and create a pull request. Thats it!

Now, when your pull request is accepted and merged, our system (lovely called PeerBot) is going to configure your session within an hour or so. PeerBot sets up a session for every exchange we have in common. So when you remove a exchange from PeeringDB the session will be removed on the next run.
In the meantime you could setup your side, so the session come up when the system is finished.

### Can i peer only/except at ... ?

Sure, you can. Just use ```only:``` or ```except:```. For eg.:

```
123456:
  description: test
  only:
    - kleyrex
```

Following ixps are available to be used there:

- kleyrex
- locix
- speedix
- nlocix
- decix_dus
- decix_ham
- decix_muc

### Can we use MD5 ? ###

Sure, we can. Just drop us a mail at ```peerops@fastether.net``` with your ASN and your password. We will add this to our configuration. For the rest proceed as described above.

### Peering details ###

Up-to-date peering details you find on PeeringDB: https://as206479.peeringdb.net

```
Name:  FastEthernet (by JPBE-Network)
ASN:   AS206479
Macro: AS-FASTETHERNET
NOC:   noc@as206479.net

IXP:   DE-CIX Dusseldorf
IPv4:  185.1.58.146
IPv6:  2001:7f8:9e:0:3:268f:0:1

IXP:   DE-CIX Hamburg
IPv4:  80.81.203.150
IPv6:  2001:7f8:3d:0:3:268f:0:1

IXP:   DE-CIX Munich
IPv4:  80.81.202.147
IPv6:  2001:7f8:44:0:3:268f:0:1

IXP:   KleyReX
IPv4:  193.189.82.203
IPv6:  2001:7f8:33::a120:6479:1

IXP:   LocIX
IPv4:  185.1.119.25
IPv6:  2a07:1c44:61f0::a105:6479:1

IXP:   NLocIX
IPv4:  185.1.138.14
IPv6:  2a0c:b641:700::206:479

IXP:   Speed-IX
IPv4:  185.1.95.22
IPv6:  2001:7f8:b7::a520:6479:1

```
