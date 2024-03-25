# QRCodeGenerator
[@jere344](https://www.github.com/jere344) & [@olivierbh2](https://www.github.com/olivierbh2)

Une application de génération avancée de codes QR, avec interface graphique ou console.

# Références
  
- [QRCodeGenerator](#qrcodegenerator)
  * [2024-03-22 - VERSION FINALE](#2024-03-22---version-finale)
    + [Description](#description)
      - [NOTES](#notes)
    + [Installation](#installation)
    + [Utilisation](#utilisation)
      - [Fenêtre de génération](#fenêtre-de-génération)
      - [Fenêtre de personnalisation](#fenêtre-de-personnalisation---personnalise-le-dernier-code-qr-généré)
  * [Application console](#application-console)
    + [Arguments](#arguments)
    + [Example d'utilisation](#example-dutilisation)
      - [Utilisation de base](#utilisation-de-base)
      - [Avec couleur de fond et de module](#avec-couleur-de-fond-et-de-module)
      - [Avec logo](#avec-logo)
      - [Avec tout les paramètres](#avec-tout-les-paramètres)
  * [DOCUMENTATION](#documentation)


## 2024-03-22 - VERSION FINALE
  
### Description
  
Cette version de QrCodeGenerator propose maintenant une interface graphique à l'utilisateur.
L'utilisateur peut choisir tous les paramètres de génération, ou laisser l'application choisir les meilleurs paramètres.
Un message d'erreur sera retourné en cas de paramètres incompatibles.
De plus, il est maintenant possible de personnaliser le code QR en y ajoutant un logo central et en changeant les couleurs d'arrière plan et de modules.
  
#### NOTES
```
- Certaines combinaisons de couleurs peuvent rendre le code QR illisible.
- L'ajout d'un logo central force le niveau de correction d'erreur H.
```
  
### Installation
  
- Télécharger le Windows-Build du dernier release
- Extraire le contenu
- Lancer QRGenerator_Interface.exe pour utilisation avec l'interface graphique
- OU ouvrir un invite de commande et appeler QRGenerator.exe pour utilisation console avec lignes de commandes
  
### Utilisation
  
#### Fenêtre de génération
-  L'utilisateur entre son texte à convertir en code QR.
-  Il choisit ses paramètres (ou coche la case "Auto" pour que l'application sélectionne les meilleurs paramètres à sa place).
-  Si l'utilisateur choisit lui même et qu'un des paramètres cause des problèmes de génération, une erreur est retournée pour demander à l'utilisateur de changer ce paramètre.
-  L'utilisateur choisit un chemin ou enregistrer son fichier (png).
-  L'utilisateur choisit un path ou enregistrer son fichier.
-  NOTE : Si un fichier de même nom existe à cet endroit, il sera remplacé par le nouveau code QR.
-  Une fois le code QR généré et exporté, le bouton pour ouvrir la fenêtre "personnalisation" est maintenant clickable.  

![b8ea0c93-423f-46e3-b1b4-d6c51db89869](https://github.com/jere344/QRCodeGenerator/assets/86294972/4bbd9d42-8c3d-43d4-bd6a-54464d826b4d)

  
#### Fenêtre de personnalisation - PERSONNALISE LE DERNIER CODE QR GÉNÉRÉ
-  L'utilisateur clique sur le bouton "personnaliser" pour ouvrir la fenêtre de personnalisation
-  L'utilisateur importe un logo à mettre au centre de son code qr
-  L'utilisateur choisit les couleurs des modules et de fond
-  Le bouton "OK" génère un nouveau fichier.png qui sera nommé : [NomDuCodeQr]-custom-[dateheure].png, l'utilisateur peut donc faire plusieurs personnalisations du même code QR sans que la nouvelle image écrase la précédente.
-  Le bouton "Fermer" ferme la fenêtre de personnalisation (peut être fermée sans avoir effectué de personnalisation).
  
![a83a95f8-9054-48d2-9a9e-7439d1aedb54](https://github.com/jere344/QRCodeGenerator/assets/86294972/bdae2e80-72c0-463a-95e7-511cb970a5f5)

  
## Application console
  
### Arguments
  
```
Usage: QRGenerator [-t text] [-s scale] [-p path] [-pc patternColor] [-l logoPath] [-ls logoShadowType] [-bc backgroundColor] [-e errorCorrectionLevel] [-v version] [-em encodingMode] [-m mask] [-h]
Options:
  -t text: Text to encode
  -s scale: Scale of the QRCode output image
  -p path: Path to save the QRCode
  -pc patternColor: HTML color code of the pattern
  -l logoPath: Path to the logo
  -ls logoShadowType: Type of shadow for the logo (circle, shadow, cicle+shadow)
  -bc backgroundColor: HTML color code for the Background
  -e errorCorrectionLevel: Error correction level (L, M, Q, H)
  -v version: Version of the QRCode
  -em encodingMode: Encoding mode (Numeric, Alphanumeric, Byte)
  -m mask: Mask to apply
  -h: Display this help message
  --version: Display the version
```
  
### Example d'utilisation
  
#### Utilisation de base
```
QRGenerator -t "Hello World" -p qrcode.png
```
![7fc67a2e-74a2-49b4-936e-7eaf9025fca9](https://github.com/jere344/QRCodeGenerator/assets/86294972/443f9f33-2e15-4154-b42f-a25a813ab688)

  
#### Avec couleur de fond et de module
```
QRGenerator -t "Hello World" -s 10 -p qrcode.png -pc #FF0000 -bc #ffffcf 
```
![9fac489f-13eb-4d46-818b-e3735563bb95](https://github.com/jere344/QRCodeGenerator/assets/86294972/c96f7b5b-5085-4b3e-b864-d644fed7cd6e)

  
#### Avec logo
```
QRGenerator -t "Hello World" -s 20 -p qrcode.png -pc #FF0000 -bc #ffffcf -e H -l logo.png -ls circle+shadow
```
  
#### Avec tout les paramètres
```
QRGenerator -t "Hello World" -s 10 -p qrcode.png -pc #FF0000 -bc #ffffcf -e H -v 5 -em Byte -m 1 -l logo.png -ls circle+shadow
```
![7cfae556-f7f6-4921-85f2-ae164ea37a46](https://github.com/jere344/QRCodeGenerator/assets/86294972/cacab301-46e4-480c-ae33-32fc97531c5a)

  
## DOCUMENTATION
  
https://www.thonky.com/qr-code-tutorial/
