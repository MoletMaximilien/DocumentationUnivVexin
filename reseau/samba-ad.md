# Samba AD

`nano /etc/network/interfaces`

Après ce commentaire (# The primary network interface), remplacez :

`allow-hotplug enp0s3`\
`iface enp0s3 inet dhcp`

Par :

`allow-hotplug enp0s3`\
`iface enp0s3 inet static`\
`address 192.168.1.29`\
`netmask 255.255.255.0`\
`gateway 192.168.1.1`\
`dns-nameservers 208.67.222.222`

\--

`cat /etc/hostname`

Cette commande doit vous renvoyer le hostname du serveur.

Dans notre cas, la commande nous renvoie :

`scribe`

\--

`nano /etc/hosts`

À la ligne qui correspond à la résolution du nom du serveur (le FQDN), remplacez :&#x20;

`127.0.1.1 scribe.iut.univ-vexin.fr scribe`

Par :&#x20;

`192.168.1.29 scribe.iut.univ-vexin.fr scribe` (l'adresse IP qui correspond à celle du serveur)

\--

`nano /etc/resolv.conf`

Remplacez :

`nameserver 192.168.1.1`

Par :

`domain iut.univ-vexin.fr`\
`search iut.univ-vexin.fr`\
`nameserver 208.67.222.222`

\--
