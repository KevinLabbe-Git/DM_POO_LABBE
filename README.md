# DM_POO_LABBE

https://github.com/KevinLabbe-Git/DM_POO_LABBE
TP 2
Step 5) 
La dépendance Web de spring contient des termes web specifiques nécessaires pour le fonctionnement web. Il permet l’utilisation entre autres des environnement Servlet et Portlet. Dans notre cas il permet de lire et d’utiliser nos pages html et de rendre enable le modèle MVC pour notre environnement.
La dépendance JPA de spring permet d’effectuer des requètes SQL envers notre base de données. Ainsi nous pouvons donc depuis notre projet java écrire dans notre base de données des informations.
Hibernate est caché sous la dépendance JPA depuis les dernières mises à jour. Hibernate est un outil utilisé pour gérer la persistance des données dans une base de données. Hibernate mappe des classes java et des tables de données tout en fournissant des informations pour la récupération des données.
H2 est un système de gestion de base de données entièrement créée en Java. Il peut être intégré dans des applications en java, ou fonctionner en mode client/serveur.
Le module DevTools quand à lui, et comme l’indique son nom, est un package d’outils pour Developper Tool. Le but est d’optimiser le temps de développement via des outils disponibles sous Spring Boot. On y trouve des fonctionnalité comme Automatic Restart, LiveReload ou encore Property Defaults.
Enfin, Thymeleaf est un template engine en java pour procéder à la création de fichier html, xml, javascript, css et txt.Il est parfaitement adapter pour travailler sur la View des applications Web basées sur un modèle MVC. Il fournit également une intégration complète de spring framework.

Step 13)
La partie du code qui permet de paramétrer l’url d’appel de /greeting est le @GetMapping(‘’/greeting’’). Cela indique qu’on s’adresse à l’url site.com/greeting
La partie du code qui permet de choisir le fichier HTML à afficher est notre return greeting. Cela fait que notre fonction retourne le fichier greeting.html et en affiche donc le contenu à l’adresse prodigué par le @GetMapping.
Enfin, pour spécifier un nom précis pour dire bonjour avec un lien du type localhost:9090/greeting ?nameGET=NOM , cela se passe dans le code au niveau du @RequestParam. Via notre nameGET dans le @RequestParam on récupère le nom souhaité, puis la fonction model.addAttribute envoie cette donnée à Thymeleaf. Thymeleaf interprete ainsi la page HTML et renvoie le resultat. Par défaut la valeur étant dfaultValue=World, on voit donc le nom World afficher.

Step 17)
 La table Address est apparu. Avant l’ajout de la classe Address dans notre code java, lors de notre connexion a notre base de données nous ne pouvions voir que le nom de la base (jdbc :h2 :mem :testdb), un fichier INFORMATIOn_SCHEMA, un répertoire Users, et une information concernant H 1.4.200 (2019-10-14)
Une fois la classe Address rédigé et correctement placé dans le package model, on peut voir qu’elle est désormais visible depuis notre base de données, en plus d’un répertoire Sequences.
Step 18)
Lors de l’initialisation de notre application, Hibernate créer une base de données avec notre classe annotée par @Entity (ici Address). Dans cette classe, @Id et @GeneratedValue indique que le clef id est une clef primaire et que sa valeur peut être générée automatiquement. 
Step 20)
En effectuant une requete sql de type SELECT dans notre table Address, on voit bien tout le contenu de data.sql, à savoir les 2 adresses que nous avons rentrés au préalable.
Step 23)
Le @Autowired est une annotation qui permet de faire de l’injection de dépendances. D’après mes recherches, l’injection de dépendance en java se fait entre les beans de l’application, et il suffit d’annoter une méthode ou un constructeur de @Autowired pour que Spring fasse la création du bean, cherche la liaison et fasse l’injection automatiquement.
Dans notre cas, le @Autowired va s’occuper de faire l’injection de dépendance entre notre classe AddressController et notre AddressRepository.
Step 30) 
Pour inclure bootstrap on ajoute les 2 lignes de script suivantes dans nos fichiers de pages html (greeting et addresses) :
<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.12.0/jquery.min.js"></script>  
<script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/js/bootstrap.min.js"></script>

Il est aussi nécessaire de mettre un meta name= viewport en tête de fichier.



TP 4
Step 6)
1.	Il faut une clef API pour appeler OpenWeatherMap, auquel cas cela ne fonctionnera pas.
2.	On appelle l’URL suivante :
http://api.openweathermap.org/data/2.5/weather?lat=<>&lon=<>&units=metric&appid=<cléAPI>
Bien évidemment, on renseigne les champs nécessaires pour que l’URL fonctionne, ici la cléAPI

3.	Pour passer les paramètres d’appels, on utilise la méthode GET qui récupère les informations nécessaires pour utiliser l’API
4.	Pour afficher la température du lieu visé, l’information se situe dans le json, juste après le paramètre « temp ». Pour afficher les prévisions météo, l’URL a appeler n’est pas le même. On utilisera :
http://api.openweathermap.org/data/2.5/forecast/daily?lat=<>&lon=<&appid=<cléAPI> 

