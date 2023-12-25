## BIND9 DNS Server Log Decoder
BIND 9, very popular DNS Server, has evolved to be a very flexible, full-featured DNS system. Whatever your application is, BIND 9 probably has the required features.
### Log Format:
[X]19-Dec-2023 07:12:14.770 queries: info: client @0x7f6ae0796998 192.168.1.252#34124 (dragate-sg.dc.heytapmobi.com): query: dragate-sg.dc.heytapmobi.com IN A + (192.168.0.200)
[x]19-Dec-2023 07:12:04.014 queries: info: client @0x7f6ae00a34a8 192.168.1.252#65374 (secure.statcounter.com): query: secure.statcounter.com IN AAAA + (192.168.0.200)
[]19-Dec-2023 07:11:59.994 queries: info: client @0x7f6ae870fc68 192.168.0.69#45703 (api.segment.io): query: api.segment.io IN AAAA +E(0) (192.168.0.200)
[]19-Dec-2023 07:11:48.945 queries: info: client @0x7f6ae00a34a8 192.168.0.170#53801 (hooks.slack.com): query: hooks.slack.com IN A +E(0) (192.168.0.200)

### PCRE2 Regex:
client \S+ (\S+)#\d+ \(\S+\): query: (\S+) \S+ (\S+) \S+ \((\S+)\)
### Parsed data :
* ***srcip***
* ***address***
* ***type***
* ***server***
