# docker-pi4-ekfm
Docker -> i386 -> ElasticSearch + Kibana + Filebeat + Metricbeat

Wanted to get a small ElasticSearch going for home LAB with basic monitoring and testing.

I have my boundary router sending 1Gbps ISP NETFLOW directly into Filebeat. Packet sniffing also works... For a little while... Be warned...


Open http://server:5601 and login using elastic and 12345678.

Please note:

- Licenses where due
- Home LAB only, many default password
- No SSL encryption
- Use at own risk
- NETFLOW data can contain private information, so respect the users on the network
