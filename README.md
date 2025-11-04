# Conception-et-Mise-en-uvre-d-un-Syst-me-R-seau-Avanc-pour-un-Campus
<img width="677" height="872" alt="image" src="https://github.com/user-attachments/assets/6586c134-823a-4f7c-8aa7-03146f95d9cc" /> 
<img width="655" height="594" alt="image" src="https://github.com/user-attachments/assets/cef201fb-990c-47fe-9389-baddd7812c13" />
<img width="674" height="282" alt="image" src="https://github.com/user-attachments/assets/ed2c82a6-23e9-4889-bba2-9ed3ea235e15" />

Ces serveurs hébergent des services critiques du réseau et sont situés dans une DMZ
pour une sécurité renforcée :
•Server-PT DHCP 1 & DHCP 2 : Attribution dynamique des adresses IP aux
dispositifs du réseau (redondance pour éviter les pannes). En cas de panne de DHCP1, le
trafic est redirigé vers DHCP-2 via des protocoles comme HSRP (le HSRP permet à plusieurs
routeurs d’agir ensemble formant un groupe virtuel où un seul routeur agit pour éviter les
pannes de connéctivité en cas de défaillance d’un routeur).
•Server-PT DNS : Résolution des noms de domaine pour les requêtes internes et
externes. Il traduit les noms de domaine en adresses IP.
•Server-PT WEB : Hébergement des sites web de l’université (intranet, portail
étudiant…).
•Server-PT EMAIL : Gestion des services de messagerie électronique pour étudiants
et personnels.
•Server-PT FTP : Stockage et partage sécurisé de fichiers volumineux (documents
académiques, support de cours).
Cette DMZ est connectée à un Switch central (2960-24TT) et protégée par un pare-feu
(5506-X HQ-FWL) pour éviter que les utilisateurs externes n’aient un accès direct
au cœur du réseau interne.

<img width="356" height="257" alt="image" src="https://github.com/user-attachments/assets/7688fd70-e88d-45bd-9fde-14ab7c8ee2f3" />

Cette partie joue un rôle dans la gestion des services en ligne, l’accès à l’internet,
l’interconnexion des éléments du réseau.
• Server-PT GOOGLE & 2960-24TT (GOOGLE VSW) : Intégration avec Google
Cloud pour l’accès aux ressources technologiques (stockage, etc.).
• PC-PT Google VM : Machines virtuelles hébergées sur Google Cloud.
• 2911 Internet : Simulation du backbone Internet pour les tests de connectivité.
• 2901 HQ-ISP & 2911 BRANCH-ISP : Routeurs ISP fournissant la connectivité
aux deux campus.

<img width="540" height="301" alt="image" src="https://github.com/user-attachments/assets/0705b93a-b69d-403a-a027-56e3e1ec3270" />

Gère le trafic entre les différents segments des deux campus et assure la connectivité
externe.
• 5506-X HQ-FWL & 5505 BRANCH-FWL : Pare-feux Cisco pour la sécurité
périmétrique (filtrage du trafic, prévention des intrusions…).
• 3650-24PS HQ-MLSW1 & 3650-24PS HQ-MLSW2 & 3650-24PB-MLSW1 &
3650-24PB-MLSW2 : Multilayer switches assurant le routage inter-VLAN et la connectivité
haute performance entre les bâtiments.

<img width="615" height="347" alt="image" src="https://github.com/user-attachments/assets/6d9f8fe0-0f56-4a7b-a762-86933cb45907" />

•WLC-2504 HQ-WLC : Contrôleur LAN sans fil centralisé pour gérer tous les points
d’accès (LAP-PT) et assurer une couverture homogène.
Même si les points d’accès sont répartis dans tous les bâtiments, ils sont toujours gérés
de manière centralisée par le WLC (configuration, sécurité, authentification, supervision,
maintenance…).
•LAP-PT (HS-LAP, BUS-LAP, ENG-LAP, ART-LAP, IT-LAP, BHS-LAP, BBUSLAP, BENG-LAP, BART-LAP) : Points d’accès Wi-Fi pour connecter les terminaux
mobiles (ordinateurs portables, smartphones, tablettes…).
•PC-PT NET-SEC-PC : Ce PC sert de poste d’administration et de supervision du
réseau sans fil. L’administrateur réseau s’en sert pour configurer le contrôleur WLC
(création/modification de SSID, attribution des VLANs, etc…), superviser les points d’accès,
surveiller la sécurité Wi-Fi et maintenir les WLCs.

<img width="328" height="154" alt="image" src="https://github.com/user-attachments/assets/2bcc4d62-3226-4d51-af62-1ac11af2ab0b" />

Chaque faculté dispose de son propre segment VLAN pour isoler le trafic et appliquer
des politiques de sécurité spécifiques.
➢ Faculté des sciences de la santé :
• 2960-24TT HS-SW : Assure la connectivité réseau entre les différents appareils et
services, et permet la connexion des équipements locaux, la gestion du trafic réseau,
l’interconnexion avec l’infrastructure centrale et l’isolation et sécurité pour prévenir les accès
non autorisés.
• PC-PT (HS-PC1 & PC2), Printer-PT HS-PRINT : Postes de travail, imprimantes
et smartphones connectés pour les utilisateurs.
• Laptop-PT HS-LPT, Tablet PC-PT HS-TBL, Smartphone-PT (HS-SM) :
Dispositifs terminaux pour accéder aux ressources réseau pour les utilisateurs finaux.
 Mêmes dispositifs pour les autres facultés sur les deux campus
➢ Faculté de Business
➢ Faculté d’Engineering & Computing
➢ Faculté d’Art et Design
➢ Département IT (Information Technology)

<img width="695" height="255" alt="image" src="https://github.com/user-attachments/assets/9123b41e-51f9-49f6-aaad-2118274c5e44" />

 Voici les deux tableaux d’adressage bien présentés :
• Advanced Campus Network : il décrit les plages d’adresses, passerelles et
adresses de broadcast pour les zones WLAN, LAN, Management et DMZ.
<img width="645" height="244" alt="image" src="https://github.com/user-attachments/assets/e53b2a81-5757-434b-b7c0-4ecfe33c71d9" />

• Entre le Cloud, les ISP, les pare-feu et les switches couche 3 : il liste les adresses
de réseau utilisées entre les équipements principaux (Cloud, ISP, firewalls, MLSW).

<img width="502" height="393" alt="image" src="https://github.com/user-attachments/assets/57eb679d-c394-4e76-8e76-d0e79ae4b096" />
Le plan de routage repose sur une combinaison de routage statique pour les liaisons
critiques (Cloud, ISP, DMZ) et de routage dynamique OSPF à l’intérieur du réseau,
notamment entre les switches multicouches et les routeurs.
 L’OSPF a été choisi pour sa capacité à :
 converger rapidement en cas de panne,
 s’adapter automatiquement aux changements topologiques,
 hiérarchiser les routes selon leur coût.
Les liaisons point-à-point entre les pare-feux, les routeurs et les MLSW utilisent des
adresses /30 (ex. : 10.20.20.32/30) tandis que les VLANs sont intégrés dans l’espace OSPF
Area 0.
 Des ACL sont appliquées au niveau des routeurs pour restreindre le trafic inter-VLAN,
en complément des règles de filtrage définies sur les ASA.





