# Tp3-network-security

# Introduction : 

Dans le domaine des réseaux informatiques, différentes configurations peuvent être utilisées pour connecter plusieurs machines entre elles. Trois cas courants sont souvent rencontrés dans la mise en œuvre de réseaux locaux *(LAN)* à l'aide du logiciel de simulation de réseau Packet Tracer. **Le premier cas** implique un switch unique connecté à trois machines dans le même réseau avec diffusion broadcast. **Le deuxième cas** implique trois PC, chacun connecté à un switch distinct dans trois LAN distincts. Enfin, **le troisième cas** implique trois PC connectés à un switch, mais avec trois réseaux locaux virtuels *(VLAN)* différents. Chaque configuration présente ses avantages et inconvénients en termes de simplicité, d'isolement du trafic, de complexité de configuration et de coûts. Dans cette discussion, nous examinerons en détail chaque cas et discuterons des avantages et des inconvénients de chaque configuration.

# Objectifs:

L'objectif globale de ce tp est de connaitre les avantages et les inconvénients de chaque cas.

## Schéma :

Voici un schéma de chacun des cas suivants :

 - **1er cas : Un switch connecté à trois machines dans le même réseau avec diffusion broadcast.**
 
 On a trois machines d'adresse respective 192.168.1.2, 192.168.1.3, 192.168.1.4.
 
 <p align="center">
  <img src="https://user-images.githubusercontent.com/73228919/232815044-bcfbb235-f134-47b2-8846-2257345ef44c.png">
</p>

Voilà une démo du pinging



https://user-images.githubusercontent.com/73228919/232833476-395fe88d-91e3-4cc0-b1ef-46c039ff1957.mp4



- *Avantages :*

La simplicité : Ce cas est simple à mettre en œuvre car il n'y a qu'un seul réseau et une diffusion broadcast simple à gérer.
La facilité de communication : Toutes les machines sont dans le même réseau, ce qui permet une communication facile entre elles sans nécessiter de routage.

- *Inconvénients :*

La diffusion broadcast : Dans un réseau avec une diffusion broadcast, chaque paquet envoyé par une machine est diffusé à toutes les autres machines du réseau, ce qui peut causer de la saturation du réseau en cas de trafic intense.
La sécurité : Toutes les machines sont dans le même réseau, ce qui peut poser des problèmes de sécurité si des mesures de sécurité appropriées ne sont pas mises en place pour isoler les différentes machines.


- **2ème cas : Trois PC, chaque PC est connecté à un switch différent dans 3 LAN distincts.**

 <p align="center">
  <img src="https://user-images.githubusercontent.com/73228919/232822562-378dffff-d765-45df-ac02-8220cf3fddac.png">
</p>

voila la table de routage

 <p align="center">
  <img src="https://user-images.githubusercontent.com/73228919/232832018-5fd93fd2-345d-4e45-961c-2afce32009c2.png">
</p>

Voilà une démo du pinging


https://user-images.githubusercontent.com/73228919/232832630-749c8a4d-82f3-44ae-b04d-86149c1d83e1.mp4



- *Avantages :*

L'isolement du trafic : Chaque PC est dans un réseau local distinct (LAN), ce qui permet d'isoler le trafic entre les différents réseaux. Cela peut être bénéfique en termes de sécurité et de performances du réseau.
La flexibilité : Chaque réseau local peut être configuré indépendamment en fonction des besoins spécifiques de chaque PC, offrant ainsi plus de flexibilité dans la gestion du réseau.

- *Inconvénients :*

La complexité : Ce cas peut être plus complexe à configurer et à gérer, car il nécessite la mise en place de routage entre les différents réseaux locaux pour permettre la communication entre les PC.
Les coûts : Avoir trois switches distincts peut entraîner des coûts supplémentaires en termes d'achat de matériel réseau.

- **3ème cas : Trois PC connectés à un switch avec 3 VLAN.**

 <p align="center">
  <img src="https://user-images.githubusercontent.com/73228919/232830182-017a58c8-ace6-45b4-8487-7c1603c5b450.png">
</p>
 
L'image ci-dessus montre le schéma et la configuration des vlans **v1 = vlan 10**  , **v2 = vlan 20 ** et **v3 = vlan 30**.

<p align="center">
  <img src="https://user-images.githubusercontent.com/73228919/232829568-d70c6388-ba05-4ece-8e3c-6e99dd61b967.png">
</p>

Si on teste maintenant les pings on va remarquer qu'il ne va pas fonctionner

<p align="center">
  <img src="https://user-images.githubusercontent.com/73228919/232829805-f0084e3f-94c2-4f82-8bc9-077de291810b.png">
</p>

Maintenant on va configurer le routeur avec encapsulation

<p align="center">
  <img src="https://user-images.githubusercontent.com/73228919/232830320-88f28cd8-2b22-467f-b3f4-47dc4b90d4d2.png">
  <img src="https://user-images.githubusercontent.com/73228919/232830335-6dffbe17-9496-4385-9419-e14c27a9c6fc.png">
 
</p>

Aprés ca on va configurer les adresses passerelles des machines

<p align="center">
  <img width="500" src="https://user-images.githubusercontent.com/73228919/232830686-2f781e33-6a43-4ddf-b97b-d1bd934f5a36.png">
  <img width="500" src="https://user-images.githubusercontent.com/73228919/232830693-3114c29c-e87a-4323-bec8-b255b4c41a3b.png">
  <img width="500" src="https://user-images.githubusercontent.com/73228919/232830706-ccd2fc69-21b1-4f4f-99d4-95b5fd23f7db.png">
  
</p>

Voila une vidéo démonstrative qui montre le pinging et le routing et meme les vlans.

https://user-images.githubusercontent.com/73228919/232831764-a54b588e-33dc-4445-957e-6c7e61683d14.mp4

# Comparaison:
 
- Comparaison des trois cas en termes de sécurité :

***Cas du switch unique avec diffusion broadcast :*** Dans cette configuration, toutes les machines sont connectées au même switch, ce qui signifie qu'elles sont dans le même réseau de diffusion broadcast. Cela peut présenter un risque en termes de sécurité, car toute machine peut potentiellement envoyer des diffusions broadcast qui seront reçues par toutes les autres machines du réseau. Cela peut augmenter la surface d'attaque et rendre plus difficile la gestion des niveaux de sécurité pour chaque machine individuelle.

***Cas de trois LAN distincts :*** Dans cette configuration, chaque PC est connecté à un switch distinct dans un LAN distinct. Cela peut offrir un niveau de sécurité plus élevé car les LAN sont isolés les uns des autres et les diffusions broadcast sont limitées à chaque LAN spécifique. Cependant, la sécurité dépendra également de la configuration spécifique du routeur utilisé pour interconnecter les LAN, ainsi que des politiques de sécurité mises en place au niveau des LAN individuels.

***Cas de trois VLAN distincts :*** Dans cette configuration, les PC sont connectés à un switch avec trois VLAN distincts. Cela permet de créer des réseaux locaux virtuels isolés, ce qui peut offrir un niveau de sécurité plus élevé par rapport à la diffusion broadcast. Les VLAN peuvent être configurés pour restreindre la communication entre eux, ce qui peut aider à limiter les risques potentiels d'attaques entre les différents réseaux.

# Recommandation et conclusion :
 
En termes de sécurité, le cas de trois VLAN distincts offre généralement un niveau de sécurité plus élevé par rapport aux autres deux cas, car il permet d'isoler les différents réseaux locaux virtuels et de limiter la diffusion broadcast. Cependant, la configuration spécifique du réseau et les besoins de sécurité de l'environnement doivent être pris en compte pour déterminer la meilleure solution. Il est recommandé de mettre en œuvre des politiques de sécurité appropriées, telles que la configuration de listes de contrôle d'accès (ACL) et de pare-feux pour protéger les réseaux et les machines individuelles, quelle que soit la configuration choisie.






