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

### Rédaction du dictionnaire de données
Le dictionnaire de données permet de regrouper toute les données nécessaire pour le fonctionnement de notre application. 
Il a d'abord été conçu lors de notre diagramme de séquence puis modifié avec le diagramme de classe.
| Nom de la donnée  | Description                      | Format | Type        |          | Règles de calcul        |
|-------------------|----------------------------------|--------|-------------|----------|-------------------------|
|                   |                                  |        | Elementaire | Calculée |                         |
| Client            |                                  |        |             |          |                         |
| client_firstname  | First name of the client         | string | x           |          |                         |
| client_lastname   | Last name of the client          | string | x           |          |                         |
| client_mail       | mail of the client               | string | x           |          |                         |
| client_phone      | client phone number              | string | x           |          |                         |
| Réservation       |                                  |        |             |          |                         |
| desired_departure | desired departure city           | string | x           |          |                         |
| desired_arrival   | desired departure city           | string | x           |          |                         |
| date_of_departure | Desired departure date           | date   | x           |          |                         |
| date_of_arrival   | Desired arrival date             | date   | x           |          |                         |
| isConfirmed       | Booking reservation              | bool   | x           |          |                         |
| passenger         |                                  |        |             |          |                         |
| passenger_name    | name of the passenger            | string | x           |          |                         |
| passport_number   | number of the passport           | num    | x           |          |                         |
| ticket_number     | number of the ticket             | string | x           |          |                         |
| Agency            |                                  |        |             |          |                         |
| commission        | price of the agency commission   | string | x           |          |                         |
| agency_name       | name of the agency               | string | x           |          |                         |
| total_price             | price of the booking             | num    |             | x        | seat_price + commission |
| airplane          |                                  |        |             |          |                         |
| flight_number     | Number of the flight             | num    | x           |          |                         |
| company_name      | name of the company              | string | x           |          |                         |
| departure_hour    | hour of departure for the flight | date   | x           |          |                         |
| arrival_hour      | hour of arrival for the flight   | date   | x           |          |                         |
| departure_date    | date of the departure            | date   | x           |          |                         |
| arrival_date      | date of the departure            | date   | x           |          |                         |
| departure_airport | airport of departure             | string | x           |          |                         |
| arrival_airport   | airport of arrival               | string | x           |          |                         |
| seat              |                                  |        |             |          |                         |
| seat_number       | number of the seat               | num    |             |          |                         |
| isAvailable ?     | is the seat available ?          | bool   | x           |          |                         |
| seat_price        | price for the seat               | num    | x           |          |                         |