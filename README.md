# Blacklist

## Accessing the Blacklist

**Mikrotik is currently disabled**

- Plain text (Active): [blacklist.techmdw.com](https://blacklist.techmdw.com)
- Mikrotik (Disabled): [blacklist.techmdw.com](https://blacklist.techmdw.com)

### Protocol

- Plain text: `https` && `http`
- Mikrotik: `https`

## Response example:

### Plain text

`https://blacklist.techmdw.com`

```
192.168.2.10
192.168.2.11
192.168.2.12
192.168.2.13
192.168.2.14
192.168.2.15
192.168.2.16
192.168.2.17
192.168.2.18
192.168.2.19
192.168.2.20
```

### Mikrotik

`https://blacklist.techmdw.com/mikrotik`

```
/ip firewall address-list remove [find list=CrowdSec]
/ipv6 firewall address-list remove [find list=CrowdSec]
/ip firewall address-list add list=CrowdSec address=192.168.1.10 comment="crowdsecurity/ssh-bf for 107h49m41.423171736s"
/ip firewall address-list add list=CrowdSec address=192.168.1.11 comment="crowdsecurity/ssh-bf for 153h59m50.599772388s"
/ip firewall address-list add list=CrowdSec address=192.168.1.12 comment="crowdsecurity/http-crawl-non_statics for 161h22m55.412412856s"
/ip firewall address-list add list=CrowdSec address=192.168.1.13 comment="crowdsecurity/ssh-bf for 166h59m50.603371814s"
/ip firewall address-list add list=CrowdSec address=192.168.1.14 comment="crowdsecurity/ssh-bf for 143h59m50.599007691s"
/ip firewall address-list add list=CrowdSec address=192.168.1.15 comment="crowdsecurity/ssh-bf for 88h49m41.424205099s"
/ip firewall address-list add list=CrowdSec address=192.168.1.16 comment="crowdsecurity/ssh-bf for 141h59m50.598923614s"
/ip firewall address-list add list=CrowdSec address=192.168.1.17 comment="crowdsecurity/ssh-bf for 152h59m50.599511798s"
/ip firewall address-list add list=CrowdSec address=192.168.1.18 comment="crowdsecurity/ssh-bf for 108h49m41.42318363s"
/ip firewall address-list add list=CrowdSec address=192.168.1.19 comment="crowdsecurity/ssh-bf for 152h59m50.599637218s"
/ip firewall address-list add list=CrowdSec address=192.168.1.20 comment="crowdsecurity/ssh-bf for 152h59m50.599630926s"
```

## Query Parameters

**ipv4only** - Only return IPv4 addresses
`https://blacklist.techmdw.com?ipv4only`

**ipv6only** - Only return IPv6 addresses
`https://blacklist.techmdw.com?ìpv6only`

**nosort** - Do not sort IP's
`https://blacklist.techmdw.com?nosort`

**origin** - Only return IP's by origin (cscli|crowdsec|capi)
`https://blacklist.techmdw.com?origin=crowdsec`

### Combine

You can also combine multiple parameters like this `https://blacklist.techmdw.com?origin=capi&nosort`

### Origins

- `cscli` - Manual bans.
- `crowdsec` - Bans made by our local Crowdsec.
- `capi` - Crowdsec collection of bad actors (Not detected by us).

## Rate limit

Our website uses a rate limiting system to manage traffic. Each user can make up to 2 requests per second. However, there's a flexibility for short bursts of traffic, allowing up to 30 requests at once. If this limit is exceeded, additional requests will be temporarily blocked until the rate limit resets in the next second. This system helps to keep our website stable and responsive for everyone.

## Crowdsec

This system is powered by Crowdsec (Blocklist mirror) more information can be found [here](https://docs.crowdsec.net/u/bouncers/blocklist-mirror).
