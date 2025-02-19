# block

A collection of domains, wildcards and substrings designed for [`dnscrypt-proxy`](https://github.com/DNSCrypt/dnscrypt-proxy) filter method.

- __allowed-names.txt:__ it's the file used to bypass a specific domain blocked by a rule contained in the `blocked-names.txt` file.
- __domains-blocklist.conf:__ it's used to configure the sources to merge during the build process.
- __domains-blocklist-local-additions.txt:__ it's used during the generation process to add your own additions and remove duplicates from the sources.
- __domains-allowlist.txt:__ it's used during the generation process to remove legit domains.
- __generate-domains-blocklist.py:__ it's the script used to launch the build process.

## Sources

### blocked-names.txt

| Source | Maintainer(s) | Description | Home Page | RAW Source | License |
|--------|:-------------:|-------------|:---------:|:----------:|:-------:|
anudeepND: adservers | anudeepND (Anudeep) | Block advertising, trackers, malwares and other unsafe domains. | [LINK](https://github.com/anudeepND/blacklist) | [RAW](https://raw.githubusercontent.com/anudeepND/blacklist/master/adservers.txt) | [MIT](https://github.com/anudeepND/blacklist/blob/master/LICENSE) |
Developer Dan: Ads & Tracking | Daniel (lightswitch05) | Block advertising, trackers, malwares and other unsafe domains. | [LINK](https://github.com/lightswitch05/hosts) | [RAW](https://www.github.developerdan.com/hosts/lists/ads-and-tracking-extended.txt) | [Apache-2.0](https://github.com/lightswitch05/hosts/blob/master/LICENSE) |
Developer Dan: AMP Hosts | Daniel (lightswitch05) | Block Google's Accelerated Mobile Pages (AMP). | [LINK](https://github.com/lightswitch05/hosts) | [RAW](https://www.github.developerdan.com/hosts/lists/amp-hosts-extended.txt) | [Apache-2.0](https://github.com/lightswitch05/hosts/blob/master/LICENSE) |
Developer Dan: Tracking Aggressive | Daniel (lightswitch05) | A very aggressive block list for tracking, geo-targeting and ads. | [LINK](https://github.com/lightswitch05/hosts) | [RAW](https://www.github.developerdan.com/hosts/lists/tracking-aggressive-extended.txt) | [Apache-2.0](https://github.com/lightswitch05/hosts/blob/master/LICENSE) |
domains-blocklist-local-additions.txt | quindecim | Domains, wildcards and substrings collection. | [LINK](https://github.com/quindecim) | [RAW](https://raw.githubusercontent.com/quindecim/block/master/config/domains-blocklist-local-additions.txt) | [GPLv3](https://github.com/quindecim/block/blob/master/LICENSE.md) |
domains-allowlist.txt | quindecim | Legit domains collection. | [LINK](https://github.com/quindecim) | [RAW](https://raw.githubusercontent.com/quindecim/block/master/config/domains-allowlist.txt) | [GPLv3](https://github.com/quindecim/block/blob/master/LICENSE.md) |
Energized Protection: Core Hosts | Team Boltz | Core of the Energized Protection lists. | [LINK](https://energized.pro/) | [RAW](https://raw.githubusercontent.com/AdroitAdorKhan/EnergizedProtection/master/core/hosts) | [MIT](https://github.com/EnergizedProtection/block/blob/master/LICENSE) |
Energized Protection: Regional Extension | Team Boltz | Regional annoyance blocking. | [LINK](https://energized.pro/) | [RAW](https://block.energized.pro/extensions/regional/formats/domains.txt) | [MIT](https://github.com/EnergizedProtection/block/blob/master/LICENSE) |
Energized Protection: Xtreme Extension | Team Boltz | A very aggressive block list for tracking, geo-targeting and ads. | [LINK](https://energized.pro/) | [RAW](https://block.energized.pro/extensions/xtreme/formats/domains.txt) | [MIT](https://github.com/EnergizedProtection/block/blob/master/LICENSE) |
hBlock | Héctor Molinero Fernández (hectorm) | A merged list from a variety of other lists. | [LINK](https://github.com/hectorm/hblock) | [RAW](https://hblock.molinero.dev/hosts_domains.txt) | [MIT](https://github.com/hectorm/hblock/blob/master/LICENSE.md) |
NoTracking | notracking | A merged list from a variety of other lists. | [LINK](https://github.com/notracking/hosts-blocklists) | [RAW](https://raw.githubusercontent.com/notracking/hosts-blocklists/master/dnscrypt-proxy/dnscrypt-proxy.blacklist.txt) | All Rights Reserved |
OISD: full | Stephan (sjhgvr) | A merged list from a variety of other lists. | [LINK](https://oisd.nl/) | [RAW](https://dblw.oisd.nl/) | All Rights Reserved |
OISD: extra | Stephan (sjhgvr) | OISD's controversial domains list. | [LINK](https://oisd.nl/) | [RAW](https://dblw.oisd.nl/extra/) | All Rights Reserved |
Oneoffdallas: DoH Servers List | oneoffdallas | A list of publicly available DNS over HTTPS (DoH) servers. | [LINK](https://github.com/oneoffdallas/dohservers) | [RAW](https://raw.githubusercontent.com/oneoffdallas/dohservers/master/list.txt) | [MIT](https://github.com/oneoffdallas/dohservers/blob/master/LICENSE) |
WindowsSpyBlocker: spy | crazy-max (CrazyMax) | Block spying and tracking on Windows. | [LINK](https://github.com/crazy-max/WindowsSpyBlocker) | [RAW](https://raw.githubusercontent.com/crazy-max/WindowsSpyBlocker/master/data/dnscrypt/spy.txt) | [MIT](https://github.com/crazy-max/WindowsSpyBlocker/blob/master/LICENSE) |

### blocked-ips.txt

| Source | Maintainer(s) | Description | Home Page | RAW Source | License |
|--------|:-------------:|-------------|:---------:|:----------:|:-------:|
DNSCrypt: Rebind Protection | jedisct1 | DNS rebinding protection | [LINK](https://github.com/DNSCrypt/dnscrypt-proxy/wiki/Filters#dns-rebinding-protection) | - | [ISC](https://github.com/DNSCrypt/dnscrypt-proxy/blob/master/LICENSE) |

## Build

To generate your own list you can clone this repo, move into the `config` folder, edit files according to your needs and run this command:
```
python3 generate-domains-blocklist.py > list.txt.tmp && mv -f list.txt.tmp list
```
