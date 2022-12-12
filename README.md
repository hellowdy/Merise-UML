# KEKE voyage

### Contexte
Votre client, une agence de voyages, souhaite proposer la possibilité de réserver en ligne des billets d'avion à leurs clients.

Votre mission est de concevoir à l'aide du standard UML la modélisation de la plateforme.

### Conception
Nous proposons cette stratégie pour réaliser notre projet :
- Réalisation des règles de gestion
- Réalisation du diagramme des cas d'utilisation (use case diagram)
- Réalisation d'un diagramme d'activité
- Réalisation d'un Diagramme de séquence
- Réalisation d'un diagramme de classe
- Rédaction du dictionnaire de donnée
- Réalisation du MCD
- Transformation du MCD en MLD
- Transformation du MLD en MPD

### Réalisation des règles de gestion
**Client**
Le client consulte l'agence de voyage.
- Le client est constitué d'un nom, d'un prénom, d'un numéro de téléphone, d'une adresse mail. Celui-ce peut s'authentifier ou non.
- Le client renseigne ses souhaits : aéroport de départ souhaitée, aéroport d'arrivée souhaitée, date de départ, date d'arrivée souhaitée.
- Le client peut réserver plusieurs vols.
- Le client peut réserver pour des passagers.
- Le client choisit son numéro de siège.
- Le client paie sa réservation.
- Le client reçoit une facture/confirmation par mail.
- Le client peut annuler sa réservation.
  
**Agence de voyage**
L'agence de voyage consulte les différents compagnies afun de proposer des solutions au client.
- Récupère les infomations du client.
- Récupère les informations de vols auprès des différentes compagnies.
- L'agence calcule les potentielles escales.
- Propose au client les différents vols disponibles.
- Récupère le choix du client et confirme la réservation auprès de la compagnie.
- La compagnie définit un numéro de réservation.
- La réservation peut être composée d'un ou plusieurs vols (escales) et est composée des informations de vols pour chacun.
  
**Compagnie aérienne**
La compagnie est le festionnaire des différents vols.
- Définit en amont les informations de vol.
- La compagnie valide ou refuse la réservation.
- La compagnie peut annuler le vol.
- La compagnie aérienne fournit les informations nécessaire en cas d'escale : aéroport d'escale, heure d'arrivée, heure de départ.

**Vol**
Le vol est défini par la compagnie.
- Une place réservé devient occupée, sinon elle est libre.
- Un vol a un prix, un numéro de vol, un horaire de départ (date + heure) et un horaire d'arrivée.
- Un vol est composé de places, disponibles ou non.

**Ville**
- Une ville peut posséder un ou plusieurs aéroport.

### Réalisation du diagramme des cas d'utilisation (use case diagram)

Le use case diagram modèlise les actions entre chaque acteurs de l'application, permettant ainsi de faire fonctionner notre application.

![use case](https://cdn.discordapp.com/attachments/1027222476150816828/1051080906112245813/use_case_diagram.png)

### Réalisation d'un diagramme d'activité
Le diagramme d'activité représente le fonctionnement de l'application du côté du client.

![diagramme d'activité](https://cdn.discordapp.com/attachments/1027222476150816828/1051080906636525618/Activity_diagram.png)

### Réalisation d'un Diagramme de séquence

Le diagramme de séquence permet de suivre chaque étapes dans les détails.
Pour cette application, nous proposons 4 diagrammes :
- Le premier cas : un simple visiteur
![diagramme sequence_01](https://cdn.discordapp.com/attachments/1027222476150816828/1051080904581316668/sequence_01.png)

- le deuxième cas : un client achète un billet
![diagramme sequence_02](https://cdn.discordapp.com/attachments/1027222476150816828/1051080904921063514/sequence_02.png)

- Le troisième cas : la compagny qui va modifier les vols
![diagramme sequence_03](https://cdn.discordapp.com/attachments/1027222476150816828/1051080905692807250/sequence_04.png)

- le quatrième cas : le client annule son achat
![diagramme sequence_04](https://cdn.discordapp.com/attachments/1027222476150816828/1051080905353072720/sequence_03.png)

### Réalisation d'un diagramme de classe
le diagramme de classe est basé sur l'orientée objet permettant aux différents acteurs d'avoir des propriétés uniques. 

![class diagram](https://cdn.discordapp.com/attachments/1027222476150816828/1051080907139850330/class_diagram.png)