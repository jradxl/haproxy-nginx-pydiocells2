# Haproxy Nginx PydioCells
Example of Haproxy and Nginx reverse proxies in front of Pydio Cells v2

Simplified examples inculded here.
I run Bind9 on my local LAN, thus I can use the public domain both outside
my local LAN and within it. Hence the two reverse proxies


Haproxy
Is the end-point for the LetsEncrypt certificate
and the default routing to my CMS


Nginx
Is on the same server as Pydio Cells
A Rsync task copies the certificate from Haproxy to Nginx servers


Pydio Cells
Internal: https://192.168.14.251:8085
External: https://pca.XXXXX.dyndns.org
Pydio docs says full https paths are necessary for sync to work


Bind9
Runs on the Haproxy server.
e.g:
  pca IN     A      192.168.14.251
Note that the DNS resolve.conf on the Nginx server must point to the Haproxy server




