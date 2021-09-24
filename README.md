# block

A collection of domains, wildcards and substrings designed for [`dnscrypt-proxy`](https://github.com/DNSCrypt/dnscrypt-proxy) filter method.

- __allowed-names.txt:__ it's the file used to unblock a specific domain blocked by some substring/wildcard contained in the blocklists.
- __domains-blocklist.conf:__ it's used to configure the sources to merge during the process.
- __domains-blocklist-local-additions.txt:__ it's used during the generation process to add your own additions and remove duplicates from the sources.
- __domains-allowlist.txt:__ it's used during the generation process to remove legit domains.
- __example-blocklist.txt:__ it contains valid name patterns for this purpose.
- __generate-domains-blocklist.py:__ it's the script used to launch the generation process.

## Sources

Updated sources from the following locations are always merged and included.

#### blocked-names.txt

| Source | Maintainer(s) | Description | Home Page | RAW Source | License |
|--------|:-------------:|-------------|:---------:|:----------:|:-------:|
1Hosts: Domains (Xtra - Level 4) | badmojr | DNS filter-/blocklists for privacy, security and clean browsing. | [LINK](https://github.com/badmojr/1Hosts) | [RAW](https://raw.githubusercontent.com/badmojr/1Hosts/master/Xtra/domains.wildcards) | [MPL-2.0](https://github.com/badmojr/1Hosts/blob/master/LICENSE) |
Developer Dan: Hosts (Ads & Tracking) | Daniel (lightswitch05) | Block advertisements and tracking. | [LINK](https://github.com/lightswitch05/hosts) | [RAW](https://www.github.developerdan.com/hosts/lists/ads-and-tracking-extended.txt) | [Apache-2.0](https://github.com/lightswitch05/hosts/blob/master/LICENSE) |
Developer Dan: Hosts (AMP Hosts) | Daniel (lightswitch05) | Block Google's Accelerated Mobile Pages (AMP). | [LINK](https://github.com/lightswitch05/hosts) | [RAW](https://www.github.developerdan.com/hosts/lists/amp-hosts-extended.txt) | [Apache-2.0](https://github.com/lightswitch05/hosts/blob/master/LICENSE) |
Developer Dan: Hosts (Dating Services) | Daniel (lightswitch05) | Block all dating services. | [LINK](https://github.com/lightswitch05/hosts) | [RAW](https://www.github.developerdan.com/hosts/lists/dating-services-extended.txt) | [Apache-2.0](https://github.com/lightswitch05/hosts/blob/master/LICENSE) |
Developer Dan: Hosts (Tracking Aggressive) | Daniel (lightswitch05) | A very aggressive block list for tracking, geo-targeting and ads. | [LINK](https://github.com/lightswitch05/hosts) | [RAW](https://www.github.developerdan.com/hosts/lists/tracking-aggressive-extended.txt) | [Apache-2.0](https://github.com/lightswitch05/hosts/blob/master/LICENSE) |
domains-blocklist-local-additions.txt | quindecim | Domains, wildcards and substrings collection. | [LINK](https://codeberg.org/quindecim/block) | [RAW](https://codeberg.org/quindecim/block/raw/branch/master/config/domains-blocklist-local-additions.txt) | [GPLv3](https://codeberg.org/quindecim/block/src/branch/master/LICENSE.md) |
domains-allowlist.txt | quindecim | Legit domains collection. | [LINK](https://codeberg.org/quindecim/block) | [RAW](https://codeberg.org/quindecim/block/raw/branch/master/config/domains-allowlist.txt) | [GPLv3](https://codeberg.org/quindecim/block/src/branch/master/LICENSE.md) |
GoodbyeAds: Hosts | jerryn70 | Block ads, trackers, analytics, malware. (Included Xiaomi Adblock & Samsung Adblock list) | [LINK](https://github.com/jerryn70/GoodbyeAds) | [RAW](https://raw.githubusercontent.com/jerryn70/GoodbyeAds/master/Hosts/GoodbyeAds.txt) | [MIT](https://github.com/jerryn70/GoodbyeAds/blob/master/LICENSE) |
GoodbyeAds: Hosts (YouTube Adblock) | jerryn70 | Special List to block YouTube ads, trackers and analytics. | [LINK](https://github.com/jerryn70/GoodbyeAds) | [RAW](https://raw.githubusercontent.com/jerryn70/GoodbyeAds/master/Extension/GoodbyeAds-YouTube-AdBlock.txt) | [MIT](https://github.com/jerryn70/GoodbyeAds/blob/master/LICENSE) |
GoodbyeAds: Hosts (LeEco Adblock) | jerryn70 | Special List to block LeEco ads, trackers and analytics. | [LINK](https://github.com/jerryn70/GoodbyeAds) | [RAW](https://raw.githubusercontent.com/jerryn70/GoodbyeAds/master/Extension/GoodbyeAds-LeEco-Extension.txt) | [MIT](https://github.com/jerryn70/GoodbyeAds/blob/master/LICENSE) |
OISD: Domains (full) | Stephan (sjhgvr) | A merged domains list from a variety of other lists. | [LINK](https://oisd.nl/) | [RAW](https://dbl.oisd.nl/) | All Rights Reserved |
OISD: Domains (extra) | Stephan (sjhgvr) | OISD's controversial domains list. | [LINK](https://oisd.nl/) | [RAW](https://dbl.oisd.nl/extra/) | All Rights Reserved |

#### blocked-ips.txt

| Source | Maintainer(s) | Description | Home Page | RAW Source | License |
|--------|:-------------:|-------------|:---------:|:----------:|:-------:|
DNSCrypt: Rebind Protection | jedisct1 | DNS rebinding protection | [LINK](https://github.com/DNSCrypt/dnscrypt-proxy/wiki/Filters#dns-rebinding-protection) | - | [ISC](https://github.com/DNSCrypt/dnscrypt-proxy/blob/master/LICENSE) |

## Build

To generate your own list you can clone this repo, move into the `config` folder, edit files according to your needs and run this command:
```
python3 generate-domains-blocklist.py > list.txt.tmp && mv -f list.txt.tmp list
```