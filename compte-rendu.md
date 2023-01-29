# DICTIONNAIRE DES COMMANDES RESEAUX ET OS SUR LINUX ET WINDOWS



## Présentation :
Dans ce doccument vous allez pouvoir retrouver toutes les commande réseau et OS les plus utilisé sous linux et windows.
* ### <u>Arthur :</u> Création de toute la partie commandes Réseau. Ajout d'un bouton static en HTML/CSS pour pouvoir remonter tout en haut de la page.
* ### <u>Badr :</u> Création de toute la partie commandes OS.
## Sommaire :
* [Commandes Réseaux](#commandes-réseau)
* [Commandes OS](#commandes-os)

# Commandes Réseau
|LINUX | RACCOURCI | WINDOWS 
|-|-|-|
[ip addr show](#ip-addr-show)|ip a|[ipconfig](#ipconfig)
[ping '@ip'](#ping-ip)||[ping '@ip'](#ping-ip-1)
[ip addr add '@ip' dev "Nom De Votre Interface"](#ip-addr-add-ip-dev-nom-de-votre-interface)|ip a a ‘@ip’ dev "Nom De Votre Interface"|[netsh interface ip set address name="interface" static '@ip' masque '@DNS'](#netsh-interface-ip-set-address-nameinterface-static-ip-masque-dns)
[ip addr del ‘@ip’ dev "Nom De Votre Interface"](#ip-addr-del-ip-dev-nom-de-votre-interface)|ip a del ‘@ip’ dev "Nom De Votre Interface"|[ipconfig /release](#ipconfig-release)
[dhclient](#dhclient)||[ipconfig /renew](#ipconfig-renew)
[ip link set up dev "Nom De Votre Interface"](#ip-link-set-up-dev-nom-de-votre-interface)|ip l s up dev "Nom De Votre Interface"|[netsh int set int name="NomCarteReseau" admin=enable](#netsh-int-set-int-namenomcartereseau-adminenable)
[ip link set down dev "Nom De Votre Interface"](#ip-link-set-down-dev-nom-de-votre-interface)|ip l s down dev "Nom De Votre Interface"|[netsh int set int name="NomCarteReseau" admin=disable](#netsh-int-set-int-namenomcartereseau-admindisable)
[ip route add default via ‘@ip’ dev "Nom De Votre Interface"](#ip-route-add-default-via-ip-dev-nom-de-votre-interface)|ip r a default via ‘@ip’ dev "Nom De Votre Interface"|[route ADD 0.0.0.0 MASK](#route-add-0000-mask)
[ip route flush dev "Nom De Votre Interface"](#ip-route-flush-dev-nom-de-votre-interface)|ip r flush dev "Nom De Votre Interface"|[route delete 0.0.0.0](#route-delete-0000)
[mii-tool -w "Nom De Votre Interface"](#mii-tool--w-nom-de-votre-interface)||Pas de commande équivalente
[ip link show "Nom De Votre Interface"](#ip-link-show-nom-de-votre-interface)||[ifconfig /all](#ifconfig-all)
[ip addr flush dev "Nom De Votre Interface"](#ip-addr-flush-dev-nom-de-votre-interface)|ip a flush dev "Nom De Votre Interface"|[ipconfig /release](#ipconfig-release-1)
[ip neighbour](#ip-neighbour)|ip n|[arp](#arp)
[ip neighbour flush all](#ip-neighbour-flush-all)|ip n flush all|[arp -d](#arp--d)
[ifconfig](#ifconfig)||[encours1](#encours1)
[traceroute @'ip'](#traceroute-ip)||

# Commandes OS
| LINUX | UTILITE | WINDOWS 
|-|-|-|
cd "nom Fichier"|se déplacer | cd 
ls|donne la liste ds fichiers et répértoires|dir
tree| arborescence des fichiers|tree
alias nomV="contenu"|attribuer une donnée ou chaine de caracteres a une variable | set nomV="contenu"
mkdir "nomRepertoire"|créer un répértoire| mkdir "nom repertoire"
pwd|afficher le repertoire courant|..
touch "nomFichier"| creer fichier | md "nomFichier"
echo "valeur" > nomFichier.txt|ecrire dans un fichier texte | echo "valeur">nomFichier.txt
cat "nomFichier"| afficher le contenu d'un fichier texte| more nomFichier.txt
rm nomFichier|supprimer fichier| rm nomFichier
rmdir nomFichier| supprimer repertoire | rmdir nomFichier
find nomFichier | trouver un fichier ou repertoire et afficher son emplacement ou si il existe ..| where nomFichier
grep nomRepertoire "caractere recherché" | chercher une chaine de caracteres dans un fichier texte et afficher son emplacement | findstr "chaine de caracteres" nomReperotoire
cp nomFichierSource nomFichierDestination | copier un fichier a un autre endroit | copy 
mv fichierSource fichierDestination | deplacer un fichier | move fichierSource fichierDestination 
chmod [chiffre] nomFichier|changer les droits d'un fichier| attrib [options]

# Détail et utilisations des commandes Linux :

## ip addr show
#### Affiche toute la configuration réseau (Adresse IP, nom des interfaces, etc…)
![ipaddrshow](images/ipaddrshow.png)

## ping @ip
#### Envoie des paquets icmp à l’adresse donnée. On peut l’utiliser pour voir si une machine est bien connectée au réseau.
![ping](images/ping.png)

## ip addr add '@ip' dev "Nom De Votre Interface"
#### Permet d’ajouter une adresse IP à votre machine. Avec ip a on peut voir que l’adresse IP a bien été ajoutée à l’interface demandé.
![ipaddradd](images/ipaddradd.png)

## ip addr del ‘@ip’ dev "Nom De Votre Interface"
#### Permet de supprimer une adresse ip précise.
![ipaddrdel](images/ipaddrdel.png)

## dhclient
#### dhclient fonctionne sur le modèle client-serveur. Un serveur qui détient la politique d’attribution des configurations IP envoie une configuration au client pour une durée donnée.
![dhclient](images/dhcleint_.png)

## ip link set up dev "Nom De Votre Interface"
#### Cette commande permet d’activer la carte réseau demandée.
![ip link set up dev](images/setup.png)


## ip link set down dev "Nom De Votre Interface"
#### Cette commande permet d’éteindre la carte réseau demandée.
![ip link set down dev](images/setdown.png)



## ip route add default via ‘@ip’ dev "Nom De Votre Interface"
#### Cette commande permet d’ajouter une route par défaut.
![ip route add default via](images/routedefault.png)


## ip route flush dev "Nom De Votre Interface"
#### Suprimme toutes les routes, default et static.
![ip route flush dev](images/routeflush.png)


## mii-tool -w "Nom De Votre Interface"
#### Permet de voir l’état de la liaison link ok/link no. Si la carte réseau est bien branchée sur le réseau.
![mii-tool](images/mii-tool.png)



## ip link show "Nom De Votre Interface"
#### Pour regarder l’état de la carte réseau.
![ip link show](images/linkshow.png)


## ip addr flush dev "Nom De Votre Interface"
#### Supprime les adresses IP de cette interface.
![ip addr flush dev](images/addrflush.png)

## ip neighbour
#### Permet de voir le cache ARP.
![ip neight](images/ip-neighbour.png)

## ip neighbour flush all
#### Permet de supprimer le cache ARP.
![ip neighbour flush all](images/neighbour-flush-all.png)


## ifconfig
####
![ifconfig](images/ifconfig.png)



## traceroute @'ip'
####
![traceroute](images/traceroute.png)




# Détail et utilisations des commandes Windows :


## ipconfig
#### Cette commande affiche la configuration IP
![ipconfig](wimages/ipconfig.JPG)

## ping '@ip'
#### Envoie des paquets icmp à l’adresse donnée. On peut l’utiliser pour voir si une machine est bien connectée au réseau.
![ping](wimages/ping.JPG)

## netsh interface ip set address name="interface" static '@ip' masque 'Gateway'
#### Cette commande permet d'ajouter une addresse IP sur l'interface choisie (ici 'Ethernet') en Static ou Dynamique. La commande necessite l'addresse IP voulu, son masque et la passerelle.
![setaddress](wimages/setaddress.JPG)
![setaddressv2](wimages/setaddressv2.JPG)


## ipconfig /release
#### Cette commande permet de libérer' une adresse IP (dynamique) attribuée.
![release](wimages/ipconfigrelease.JPG)

## ipconfig /renew
#### Cette commande permet de réatribuer' une adresse IP (dynamique).
![renew](wimages/ipconfigrenew.JPG)

## netsh int set int name="NomCarteReseau" admin=enable
#### Cette commande permet d'activer la carte réseau (ici'Ethernet').
![enable](wimages/enable.JPG)

## netsh int set int name="NomCarteReseau" admin=disable
#### Cette commande permet de désactiver la carte réseau (ici'Ethernet').
![disable](wimages/disable.JPG)

## route ADD 0.0.0.0 MASK
#### Cette commande permet d'ajouter une route
![routeadd](wimages/routeadd.JPG)

## route delete 0.0.0.0
#### Cette commande permet de suprimer une route.
![routedelete](wimages/routedelete.JPG)

## ifconfig /all
#### Cette commande permet d'avoir les informations détaillées de toutes les cartes réseau.
![all](wimages/ipconfigall.JPG)

## ipconfig /release
#### Cette commande permet de libérer' une adresse IP (dynamique) attribuée.
![release](wimages/ipconfigrelease.JPG)

## arp
#### Cette commande permet de voir le cache ARP.
![arp](wimages/arp.JPG)

## arp -d
#### Cette commande permet de suprimmer le cache ARP.
![arpdelete](wimages/arpdelete.JPG)


# Détail et utilisations des commandes Linux :

## cd et pwd

![cd](images/pwd.png)

## ls 

![ls](images/ls.png)

## tree

![tree](images/treeL.png)

## alias 

![alias](images/alias.png)

## mkdir 

![mkdir](images/mkdirL.png)

## pwd 

![pwd](images/pwd.png)

## touch 
![touch](images/touch.png)

## echo "valeur">nomFichier.txt

![echo](images/ecrire.png)

## cat 
![cat](images/cat.png)

## rm 
![rm](images/rm.png)

## rmdir

![rmdir](images/rmdirL.png)

## find 
![find](images/findL.png)

## grep 

![grep](images/grep.png)

## cp

![cp](images/cp.png)

## mv 

![mv](images/mv.png)

## chmod 
![chmod](images/chmod.png)



# Commandes OS Windows 

# cd 
![cd](images/cd.png)

# dir 
![dir](images/dir.png)

# tree 

![tree](images/tree.png)

# alias 

![set](images/set.png)

# mkdir 

![mkdir](images/mkdir.png)

#  md 

![md](images/md.png)

# echo "Valeur" > nomFic.txt


# more 
![more](images/more.png)

# rmdir
![rmdir](images/rmdir.png)

# where

![where](images/where.png)

# findstr 

![findstr](images/findstr.png)

# copy 
![copy](images/.png)

# move 

![move](images/move.png)

# attrib

![attrib](images/attrib.png)


<div id="scroll_to_top">
    <a href="#top"><img src="hdp.png" alt="Retourner en haut"/></a>
    <h5>TOP</h5>
</div>