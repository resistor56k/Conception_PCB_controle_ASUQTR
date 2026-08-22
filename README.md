# Conception du PCB de contrôle - Sous-marin autonome (ASUQTR)

**Projet de fin d'études en équipe - Génie électrique (UQTR)**

**Réalisé par Louis Lavallée**

## Contexte du projet
Ce projet fut réalisé dans le cadre du projet de fin d'étude en équipe du baccalauréat en génie électrique à l'UQTR. Le projet d'équipe était centralisé sur la poursuite du développement du sous-marin autonome du club étudiant [ASUQTR](https://oraprdnt.uqtr.uquebec.ca/portail/gscw031?owa_no_site=8035). L'objectif du club ASUQTR est de participer à la compétition internationale [Robosub](https://robosub.org/) où chaque équipe doit concevoir un sous-marin et lui faire accomplir des tâches et missions de manière entièrement autonome.

## Objectif du projet
Parmi les systèmes présents dans le sous-marin, se trouve le PCB de contrôle. C'est un circuit imprimé multicouche responsable du contrôle des moteurs et autres actionneurs ainsi que de la réception des données de certains capteurs. Il établit le lien matériel entre le Jetson Xavier AGX qui sert d'ordinateur principal et entre la plupart des sous-systèmes internes. L'ancienne version de ce circuit est devenue obsolète et doit être remplacée. Ce projet a donc pour but de créer une nouvelle version de ce circuit afin de le rendre plus adapté aux contexte actuel.

### Sous-objectifs:
  - ***Ajout d'un microcontrôleur :*** Intégration d'un microcontrôleur STM32G474VET6 afin de générer les signaux PWM et numériser les signaux analogiques (ADC) à l'aide d'un seul composant plutôt que plusieurs séparés. L'ajout d'un microcontrôleur offre une plus grande quantité de bus I2C et UART que le Jetson Xavier AGX. Ces bus de communication sont indispensables pour communiquer avec les capteurs et autres systèmes. Des bus CAN ou SPI peuvent aussi être ajoutés avec ce nouveau composant. L'ajout du STM32 octroie au PCB la capacité de prendre ses propres décisions et d'exécuter des protocoles de sécurité en cas de défaillance dans les autres systèmes.
  - ***Connectivité étendue :*** Une plus grande quantité de connecteurs I2C et UART permettra au PCB ainsi qu'au Jetson Xavier de communiquer avec de futurs capteurs ou sous-systèmes qui pourront être ajoutés au fil du développement du sous-marin. Des connecteurs 5V et 3.3V ont été installés afin de pallier d'éventuelles incompatibilités dans les niveaux de tensions.
  - ***Ajout de protections :*** Des protections ESD supplémentaires contre les décharges électrostatiques ont été placées près des connecteurs afin de protéger les composants et équipements importants et coûteux reliés au PCB.
  - ***Accéléromètre intégré :*** Un capteur accéléromètre à trois axes a été installé sur le PCB afin de donner au microcontrôleur des données d'orientation du sous-marin indépendantes des capteurs principaux en cas de défaillance et de prise de contrôle du sous-marin dans un protocole de sécurité.

## Documentation
- [Firmware de test du microcontrôleur](https://github.com/resistor56k/Firmware_test_PCB_controle_ASUQTR)
- [Extrait du rapport de PFE](Extrait_Rapport_PFE.pdf)
- [Schémas du PCB](Control_Board_ASUQTR_2026_PROTO.pdf)

**Schémas et layout du PCB réalisés sur** ***Altium Designer Professionnal***\
**Fabrication et assemblage partiel du PCB par** ***JLCPCB***

L'ancien PCB de contrôle a été réalisé par Bastien Côté, un ancien membre du club étudiant ASUQTR. Certain circuits présents sur l'ancien PCB ont été réutilisés pour la conception de la nouvelle version.

## Visuel 3D du nouveau PCB de contrôle
<img src="3D_New_PCB_Control_dessus.png" width="500" alt="Nouvelle version du PCB de contrôle (vue du dessus)" title="Nouvelle version du PCB de contrôle (vue du dessus)"> <img src="3D_New_PCB_Control_dessous.png" width="500" alt="Nouvelle version du PCB de contrôle (vue du dessous)" title="Nouvelle version du PCB de contrôle (vue du dessous)">

## Nouveau PCB de contrôle une fois imprimé et assemblé
<img src="Photo_PCB_Control_dessus.jpg" width="500" alt="Nouvelle version du PCB de contrôle (vue du dessus)" title="Nouvelle version du PCB de contrôle (vue du dessus)"> <img src="Photo_PCB_Control_dessous.jpg" width="500" alt="Nouvelle version du PCB de contrôle (vue du dessous)" title="Nouvelle version du PCB de contrôle (vue du dessous)">
