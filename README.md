# GPS-Logger

## Objectif : 

Concevoir un module permettant de récupérer la position GPS à intervalles réguliers et de les stocker sur une carte SD dans un fichier CSV.

## Contexte : 

Récupérer les traces GPS des voiliers embarquant les sondes de température/salinité de surface dans le cadre de la future campagne de mesure MorBraz dans le Golfe du Morbihan (Eté 2026)

## Matériel utilisé (non exhaustif) :

- Cartes électronique PCB des sondes CTD LittObs : 
https://github.com/astrolabe-expeditions/LittObs_CTD/tree/ed4291ef54c2eff3621bca63024c3ba20032e0d1/hardware/pcbs

- Microcontrôleur de type ESP32 FireBeetle DFR0478

- Module GPS Neo-6M + antenne

- Support de carte micro SD

- Horloge RTC DS3231 (pas forcément nécessaire en fonction de l'acquisition du GPS)

- Batteries 18650

## Cahier des charges (non exhaustif) :

- Programme Arduino pas trop complexe

- Produire un fichier CSV avec com nommage : "OWNER_GPS_XXX_datecreation"
    OWNER en majuscules (ex : "AE")
    XXX correspond au numéro de l'instrument (ex : "001")
    datecreation correspond à la date de création du fichier en UTC au format ISO 8601 (ex : "2025-01-25T02:03:10Z)

- Remplir le fichier CSV avec les colonnes suivantes :
    - datetime au format ISO8601
    - lat pour la lattitude
    - long pour la longitude
    - éventuellement une colonne debug avec des codes retours correspond à différentess anomalies ou modes de fonctionnement à imaginer

- Réutiliser la base électronique des sondes CTD LittObs (ESP32 + lecteur carte micro SD + GPS neo6M + RTC DS3231)    

- Gérer l'autonomie d'au moins 2 mois sur batterie et imaginer un système de recharge des batteries par USB

- Intégration de l'électronique dans un boitier à minima résistant aux éclaboussures et au mieux étanche 
