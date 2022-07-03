# adsblock

Ini adalah adblock untuk openclash, source list diambil dari berbagai sumber. Source list diupdate setiap hari secara otomatis oleh bot github.

PACK NAME	DESCRIPTION	SOURCES
Energized Blu	Mid range lightweight protection.	Energized Protection
Core List + Blu Go + AdGuard DNS & Tracking, Anudeep's Adservers, Better.fyi Trackers, Disconnect Advertising Filter List, EasyPrivacy, Hexxium Creations Threat List, hosts-blocklists, KADhosts, neoHosts, and YousList
ABPindo_annoyance	ABPindo merupakan filter tambahan untuk melengkapi filter internasional seperti EasyList atau AdGuard Base filter memblokir iklan mengganggu di situs berbahasa Indonesia dan Malaysia. ABPindo_annoyance memblokir situs iklan & situs judi di Indonesia dan Malaysia	ABPindo
Untuk menggunakan, edit config.yaml pada /etc/openclash/config/config.yaml seperti ini:

rule-providers:
  adblock_energized_blu:
    type: http
    behavior: classical
    path: "./rule_provider/energized_blu_adblock.yaml"
    url: https://raw.githubusercontent.com/hillz2/openclash_adblock/main/energized_blu_adblock.yaml
    interval: 14400 # Update rules every 4 hours
  adblock_abpindo_annoyance:
    type: http
    behavior: classical
    path: "./rule_provider/all_ads.yaml"
    url: https://github.com/aryobrokolly/adsblock/blob/main/all_ads.yaml
    interval: 14400 # Update rules every 4 hours
rules:
# Block ads
- RULE-SET,adblock_energized_blu,REJECT
- RULE-SET,adblock_abpindo_annoyance,REJECT
Setelah di test dengan situs Adblock Test hasilnya:

2022-06-08-213555-1920x986-scrot.png

Hasil di situs adblock test bisa berbeda beda karena source list diupdate setiap hari.
