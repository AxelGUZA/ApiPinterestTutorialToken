# Tutorial [ENGLISH VERSION](https://developers.pinterest.com/docs/api/overview/?)

# FR Version| Bonjour & bienvenue sur le tutorial pour API Pinterest pour avoir unToken


Documentation et tutorial pour avoir l'acces à un token pinterest 

Nous allons voir ici comment faire marcher [l'API de Pinterest ](https://developers.pinterest.com/docs/getting-started/introduction/)

Vous avez 2 possibiliter :
-Sois faire avec du XML et donc un fichier .rss qui vous donne une Architecture.
    Avec ce type de lien : 
      - https://www.pinterest.com/<username>/feed.rss
      - https://www.pinterest.com/<username>/<board>.rss
 - Sois vous pouvez faire un token de connexion qui vous permet de récupérer ce ficier en JSON 
  
Nous allons travailler ici avec le Json et comment avoir un Acces au token qui est une clé d'access dans un URL qui permet de s'identifier a l'API en question.

***
## Parti I Connexion

Il va vous falloir vous connectez au compte pinterest dont vous voulez avoir les "Pins".
Après vous avoir connectez vous devez vous rendre sur [Getting Started](https://developers.pinterest.com/docs/api/overview/).
***
## Parti II Création de notre app

1. Allez dans [Apps](https://developers.pinterest.com/apps/).
![Insta-création app](https://user-images.githubusercontent.com/38752522/56871902-46e2fc00-6a66-11e9-8a6b-62980a5d4609.PNG)
2. Accepter les [termes](https://developers.pinterest.com/terms/) et la [politique](https://developers.pinterest.com/policy/) de pinterest et enfin Créer l'application.
![Insta-création Police](https://user-images.githubusercontent.com/38752522/56871901-46e2fc00-6a66-11e9-80b3-f58afd1049f0.PNG)
3. Donnez un nom(il ne pourra pas être changer après) a votre application avec une légère description, cela est plus pour vous et les suivant qui réutiliseron votre application. Puis créer

Voila vous avez créer une application Pinterest. Mais cela n'est pas encore fini il faut maintenant récupérer le token Access pour pouvoir avoir le Json.
***
## Parti III Utilisation de PostMan
C'est une application qui est facile utilisation et gratuit. Elle vous permettra de faire des token sur plusieur APi comme Instagram ou encore facebook.

Vous pouvez le trouver [ici](https://www.getpostman.com/)

Arpès avoir téléchargé l'applciation : il vous faut vous enregistrez
![Postman-register](https://user-images.githubusercontent.com/38752522/56871529-94f60080-6a62-11e9-912c-300b13b65f61.PNG)

Après il faut définir vos préférence :
![PostMan-Configuration](https://user-images.githubusercontent.com/38752522/56871542-c4a50880-6a62-11e9-9014-68aabe588e97.PNG)

Ensuite vous avez la possibiliter de crée et de travailler en équipe :
![Postman-create team](https://user-images.githubusercontent.com/38752522/56871551-f1f1b680-6a62-11e9-8540-7621555c907c.PNG)
ou seul en appuyant sur "skip for now"

Maintenant que vous avez passé tous les paramètre de configuration, nous allons vraiment commencer.

Vous pouvez rajouter tous de suite le get : https://api.pinterest.com/v1/me/boards
qui vous permettra d'avoir votre boards pinterest.
Les Pins (https://api.pinterest.com/v1/me/pins).
Après je vous laisse chercher pour autres cela n'est pas très compliquer.

Dans un premier temps allez dans l'autorisation :
![Postman-autorisation](https://user-images.githubusercontent.com/38752522/56871558-26fe0900-6a63-11e9-8309-aa96ed0e441c.PNG)
C'est ici que l'on configure les autorisations en fonction de L'API.
Pour L'API pinterest il nous faut la OAuth 2.0 :
![Postman-OAuth 2 0](https://user-images.githubusercontent.com/38752522/56871588-85c38280-6a63-11e9-9060-b461aecb2b0f.PNG)
Clicker sur "GET access Token"

Puis dans un seconde temps nous allons voir les information à remplir :
vous-vous retrouvez devant cette pop-up qui vous affiche les information suivant :

Token Name : Token  exemple
***
Grant Type : Authorization Code
***
Callback URL : https://exemple.com/ (Atention c'est l'url de callback que vous avez mit dans Pinterest)
***
Auth URL : https://api.pinterest.com/oauth/
***
Access Token URL :https://api.pinterest.com/v1/oauth/token
***
Client ID : Votre ID  d'application  Pinterest
***
Client Secret : Votre ID privée  d'application  Pinterest
***
Scope : read_public,write_public,read_relationship,write_relationships (Ce que nous allons récurpérer comme information en JSON [plus informations](https://developers.pinterest.com/docs/api/overview/?) 
***
State : State
***
Client Authentication : (laisser par défaut)
***
![Postman-getToken](https://user-images.githubusercontent.com/38752522/56871606-ba373e80-6a63-11e9-9a01-c88136706da5.PNG)

Maintenant il va vous demandez de accepter les conditions
![Postman-apiAcess](https://user-images.githubusercontent.com/38752522/56871747-1d75a080-6a65-11e9-9228-3002325310af.PNG)


Et voila votre token est créer et prêt à être utilisé :
![Postman-token](https://user-images.githubusercontent.com/38752522/56871765-4138e680-6a65-11e9-9330-16b9303ac04f.PNG)



## Comment ça marche :

Maintenant que vous avez le token Access rien de plus simple, il ne vous reste plus qu'a remplir.
URL suivant : https://api.pinterest.com/v1/me/pins/?access_token=<TOKEN ACCESS>&limit=<Votre limite de poste>&fields=<CE que vous voulez avoir>
    
     
 [exemple](https://developers.pinterest.com/docs/api/pins/?) 



Maintenant à vous de jouer !

## Erreur fréquente :
L'erreur :
![Postman-erreur](https://user-images.githubusercontent.com/38752522/56871871-f4094480-6a65-11e9-92a8-ccb3a3ef53c8.PNG)
La solution :
![Postman-erreur solution](https://user-images.githubusercontent.com/38752522/56871873-f4094480-6a65-11e9-822a-4d633cdec20f.PNG)

Forum sur le sujet  :https://socialchamps.com/topic/why-i-cannot-sign-in-to-pinterest/

Vous pouvez Allez voir aussi pour AUTRE API :
# API FACEBOOK : https://github.com/AxelGUZA/tutorialAPIFacebook/
# API INSTAGRAM :https://github.com/AxelGUZA/ApiInstagramTutorial
