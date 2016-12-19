# maillage
Module de maillage automatique Searchbios

## 1. Configuration du module de maillage
Pour créer un module de maillage commencez par le configurer en vous rendant sur le [tableau de bord Searchbios](http://dashboard.searchbios.com/links_modules)

Vous pouvez lui attribuer 
- un nom (de votre choix) 
- un nombre de liens à afficher
- activer ou non le javascript (le module sera accessible via une API accessible via HTTP le cas échant)
- choisir le nombre de jours entre chaque rotation de liens
- changer le code html englobant la liste de liens (pour la mise en forme par exemple)
- changer le code html par lien (idem, pratique pour la mise en forme)

Veillez à bien utiliser les trois champs : libelle, links et url (**en incluant les étoiles**)

## 2. Ajoutez les liens que vous souhaitez voir apparaître 

Sur votre module de maillage cliquez sur le bouton "liens" :
![module de maillage](https://s3.amazonaws.com/awesomescreenshot/upload//181363/2a095b97-c8ee-4d07-5608-35fc0193b86a.png?AWSAccessKeyId=AKIAJSCJQ2NM3XLFPVKA&Expires=1482190088&Signature=KZi%2Bl6Sp7jLv%2BUalbiDJzPu%2FXCo%3D)

Vous pouvez ajouter un lien seul ou plusieurs liens d'un coup

## 3. Intégrez l'API sur votre site

### A. En javascript (coming soon)

### B. Via HTTP

L'API est disponible via HTTP. De fait tous les languages supportant ce protocole permettent d'appeler l'API. 

- Le point d'API est le suivant : http://dashboard.searchbios.com
- La méthode à appeler est "/links/[ID]/generate.json" où ID est l'ID du module tel que présenté sur le dashboard. Par exemple (/links/5/generate.json)
- Il faut appeler l'API avec la méthode POST
- En paramètre il faut passer l'URL de la page liante : "url_page_liante". Veillez à bien intégrer le protocole dans l'URL (ex: http://google.com"). Veillez aussi à ce que l'URL soit l'URL exacte de la page est non une redirection (3xx). 

Exemple de requête : 

POST /links/5/generate.json HTTP/1.1

Host: dashboard.searchbios.com

Content-Type: multipart/form-data

Cache-Control: no-cache



