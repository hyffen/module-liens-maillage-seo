# Module de maillage SEO

## 1. Principe de l'outil SEO
Le module de maillage SEO Searchbios permet de gérer à distance les liens présents dans les modules de maillage SEO.
Les liens sont ajoutés dans une interface (dashboard SearchBios) et envoyés par JS ou API vers les sites web.
Les sites reçoivent des liens et les affichent sur le site dans les modules de maillage.

Intérêts d'un module de maillage SEO : 
- inclure dans la structure de votre site des pages orphelines qui ne sont pas dans votre arborescence
- faire découvrir de nouvelles pages aux moteurs de recherches
- faire remonter des pages qui sont trop profondes dans votre architecture de site
- diversifier les ancres des liens sur votre site
- regrouper les pages en SILO en fonction de leur thématique
- sculter votre maillage interne pour prioriser les bonnes pages

Intérêts du module de maillage piloté à distance : 
- diminuer le temps de développement sur votre site
- piloter efficacement vos modules de maillage SEO
- changer les liens des modules de maillage régulièrement et automatiquement
- faire varier les liens du module régulièrement sans intervention technique
- sélectionner et modifier sans intervention technique le nombre de liens à afficher et le temps de rotation des liens

Un lien de maillage se compose de :
- une URL liante : la page sur laquelle vous allez afficher le lien
- une URL liée : l'url de destination du lien
- une ancre : mot sur lequel l'internaute clique, comme "cliquez-ici"

## 2. Configuration du module de maillage
Pour créer un module de maillage commencez par le configurer en vous rendant sur le [tableau de bord Searchbios](http://dashboard.searchbios.com/links_modules)

Vous pouvez lui attribuer 
- un nom (de votre choix) 
- un nombre de liens à afficher
- activer ou non le javascript (le module sera accessible via une API accessible via HTTP le cas échant)
- choisir le nombre de jours entre chaque rotation de liens
- changer le code html englobant la liste de liens (pour la mise en forme par exemple)
- changer le code html par lien (idem, pratique pour la mise en forme)

Veillez à bien utiliser les trois champs : libelle, links et url (**en incluant les étoiles**)

## 3. Ajouter les liens dans l'interface SearchBios
Sur votre module de maillage cliquez sur le bouton "liens" :
![module de maillage](https://s3.amazonaws.com/awesomescreenshot/upload//181363/2a095b97-c8ee-4d07-5608-35fc0193b86a.png?AWSAccessKeyId=AKIAJSCJQ2NM3XLFPVKA&Expires=1482190088&Signature=KZi%2Bl6Sp7jLv%2BUalbiDJzPu%2FXCo%3D)

Vous pouvez ajouter un lien seul ou plusieurs liens d'un coup.

SearchBios peut s'occuper de setuper les modules de maillage pour vous. Nous récupérons toutes les URL de votre site web, et nous définissons toutes les règles de maillage afin de créer tous les formats de liens pour vous.

## 4. Intégrer le module de maillage SEO sur votre site

### A. En javascript
Nous proposons un format JavaScript afin d'afficher un module de maillage créé et géré dans le Dashboard de SearchBios.
Vous pouvez configurer en HTML le template du module, et le modifier à distance à tout moment.
Nous reprenons les éléments de design de votre site comme le CSS.
Cette méthode permet de créer et diffuser des modules rapidement, en limitant les développements sur le site web.

### B. Via l'API
L'API permet d'envoyer les instructions au site web, avec les liens à afficher pour chaque page, et les ancres à utiliser.
L'API est disponible via HTTP. De fait tous les languages supportant ce protocole permettent d'appeler l'API. 

- Le point d'API est le suivant : https://www.dynamolinks.com/
- La méthode à appeler est "/links/[ID]/generate.json" où ID est l'ID du module tel que présenté sur le dashboard. Par exemple (/links/5/generate.json)
- Il faut appeler l'API avec la méthode POST
- En paramètre il faut passer l'URL de la page liante : "url_page_liante". Veillez à bien intégrer le protocole dans l'URL (ex: http://google.com"). Veillez aussi à ce que l'URL soit l'URL exacte de la page est non une redirection (3xx). 

Exemple de requête : 
POST /links/5/generate.json HTTP/1.1
Host: www.dynamolinks.com
Content-Type: multipart/form-data
Cache-Control: no-cache

Nous proposons 2 versions du flux JSON : 
- version 1 : 1 requête par page liante, donc si votre site a 100 pages sur laquelle le module de maillage s'affiche, il faudra faire 100 requêtes.
- version 2 : 1 seule requête pour récupérer toutes les informations en tableau, et vous interroger le tableau pour récupérer les informations nécessaires.

### C. Via un plugin sur votre CMS
Nous proposons des plugins PrestaShop et Wordpress pour intégrer les modules de maillage sur votre CMS.
Sur Wordpress, le module est sous la forme d'un Widget que vous pouvez ajouter en colonne, dans le contenu d'une page, le header ou le footer. Vous devez simplement ajouter les informations nécessaires : 
- Titre du module de maillage qui va s'afficher sur votre site
- ID du module de maillage

Nous contacter pour en savoir plus : http://www.searchbios.com/contact.html
