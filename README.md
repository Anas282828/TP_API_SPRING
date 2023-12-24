# TP API
## TP3
## Description du projet TP3
Ce projet TP3, réalisé dans le cadre d'un cours de programmation orientée objet, illustre une application de développement web moderne utilisant le cadre Spring Boot. Le projet s'appuie sur des concepts clés de la programmation Java et des technologies web pour construire une application web dynamique et interactive.

À travers ce projet, nous avons exploré diverses dépendances et outils de Spring Boot, chacun jouant un rôle spécifique dans le développement de l'application. De la gestion des requêtes web avec Spring Web à la manipulation de données avec Spring Data JPA, en passant par l'utilisation de la base de données H2 pour le stockage en mémoire et l'intégration de Thymeleaf pour les templates HTML, chaque composant a été méticuleusement sélectionné et implémenté pour répondre aux besoins spécifiques du projet.

L'application est conçue pour être à la fois fonctionnelle et esthétiquement agréable, grâce à l'intégration de Bootstrap pour le design front-end. Cette bibliothèque a été soigneusement intégrée via Maven pour offrir une interface utilisateur réactive et attrayante.

### Réponses aux Questions Techniques
### Etape 5
Description des Dépendances
Spring Web
Description : Fournit des fonctionnalités essentielles pour le développement d'applications web, y compris le modèle MVC de Spring, la gestion des requêtes REST, la sérialisation JSON, et plus.
Spring Data JPA
Description : Simplifie l'implémentation des couches d'accès aux données, en fournissant une abstraction pour les opérations CRUD et une intégration étroite avec JPA.
H2 Database
Description : Base de données en mémoire, utilisée pour le développement et les tests. Elle offre une configuration rapide sans nécessité d'installation externe.
Thymeleaf
Description : Moteur de template pour créer des vues HTML dynamiques. Il permet de construire des interfaces utilisateur riches en intégrant des données du côté serveur.
Spring Boot DevTools
Description : Ensemble d'outils pour améliorer le développement d'applications Spring Boot, notamment le rechargement automatique des classes et des ressources à la volée.

### Etape 13
Analyse du Contrôleur HelloWorldController
Paramétrage de l'URL d'Appel /greeting :
L'annotation @GetMapping("/greeting") dans la classe HelloWorldController définit l'URL /greeting. Cette annotation indique que la méthode greeting sera invoquée lorsque cette URL est demandée.

Choix du Fichier HTML à Afficher :
La méthode greeting retourne la chaîne "greeting", qui est le nom du fichier template Thymeleaf (sans l'extension .html). Thymeleaf recherche donc un fichier nommé greeting.html dans le répertoire des templates.

Envoi du Nom pour le Message de Bienvenue :
L'annotation @RequestParam(name = "nameGET", required = true, defaultValue = "World") permet de récupérer un paramètre de requête HTTP nommé nameGET. Ce paramètre est ensuite ajouté au modèle avec model.addAttribute("nomTemplate", nameGET), et utilisé dans le fichier greeting.html pour afficher le message de bienvenue personnalisé.

### Etape 17
Observation de la Console H2
Après le redémarrage de l'application et l'accès à la console H2, vous auriez dû observer l'apparition de la table ADDRESS. Cela est dû à l'annotation @Entity dans la classe Address, qui indique à Hibernate de créer une table correspondante dans la base de données.

### Etape 18
Explication de la Création de la Table
Hibernate, configuré par la dépendance Spring, utilise les annotations JPA dans la classe Address pour déterminer la structure de la table dans la base de données. La table ADDRESS est créée automatiquement pour stocker les objets Address.

### Etape 20
Vérification des Données dans la Base de Données H2
Après le redémarrage de l'application et l'accès à la console H2, une requête SELECT a été exécutée sur la table Address. Cette requête avait pour but de vérifier si toutes les données prévues dans data.sql ont été correctement insérées dans la base de données. Les observations sont les suivantes :

Résultat : La requête a retourné toutes les lignes insérées dans data.sql, confirmant ainsi que les données ont été correctement chargées et stockées dans la table Address.
Importance : Cette vérification est cruciale pour s'assurer que le mécanisme d'initialisation de la base de données fonctionne comme prévu, et que les données sont disponibles pour être utilisées par l'application.

### Etape 22
Usage de @Autowired
L'annotation @Autowired dans AddressController permet l'injection automatique de l'instance de AddressRepository par Spring. Cela signifie que Spring s'occupe de la création et de la gestion de cette instance, et la fournit au contrôleur sans nécessité de l'instancier manuellement.

### Etape 27
 Ajout d'une Navbar
Pour la navigation, une navbar a été ajoutée dans le fichier HTML. Elle utilise Bootstrap pour le style et Thymeleaf pour l'intégration dynamique avec le backend.

### Etape 30
 Intégration de Bootstrap dans le Projet
Pour améliorer l'interface utilisateur et le design de l'application, Bootstrap a été intégré. Cette intégration a été réalisée en ajoutant la dépendance Bootstrap au fichier pom.xml du projet. Voici les détails de la dépendance ajoutée :
<dependency>
    <groupId>org.webjars</groupId>
    <artifactId>bootstrap</artifactId>
    <version>5.3.0</version> <!-- La version peut être ajustée selon la dernière disponible -->
</dependency>

Rôle de Bootstrap : Bootstrap est une bibliothèque front-end populaire qui fournit des composants de style et de mise en page pour développer des interfaces utilisateur réactives et attrayantes.
Choix de la Version : La version 5.3.0 a été choisie, mais elle peut être mise à jour en fonction des dernières versions disponibles pour bénéficier des dernières fonctionnalités et améliorations

## Conclusion du TP3
En somme, ce projet TP3 représente un effort collaboratif et approfondi pour créer une application web complète et bien structurée. Il démontre non seulement une compréhension approfondie des principes de programmation Java et de développement web mais illustre également l'importance de l'architecture d'application et de la conception d'interfaces utilisateur dans le développement de logiciels modernes.

Le projet sert de preuve concrète de notre capacité à appliquer des compétences théoriques dans un contexte pratique, tout en mettant en lumière l'efficacité des technologies Spring Boot et Bootstrap dans le développement d'applications web contemporaines.

## TP4
## Description du projet TP4 

Ce projet TP4 est une application web qui utilise l'API MeteoConcept pour fournir des prévisions météorologiques en fonction des coordonnées GPS fournies. Le projet implique l'intégration d'APIs externes et la gestion de données géographiques et météorologiques.

### Réponses aux Questions Techniques

Utilisation de l'API MeteoConcept
Clé API Nécessaire : Oui, une clé API est requise pour accéder aux services de MeteoConcept. Dans ce projet, j’ai utilisé la clé "f79059a4ee26190824e70fef6b08d295136d9467f7cdaaaf00eb06fcabf78c8c".

URL à Appeler : L'URL utilisée pour récupérer les données météorologiques est "https://api.meteo-concept.com/api/forecast/daily/0?token="+token+"&insee="+insee+"&latlng="+longt+"2C"+lat"

Méthode HTTP Utilisée : Nous utilisons la méthode GET pour récupérer les données de l'API.

Passage des Paramètres d'Appels : Les paramètres sont passés via l'URL de requête. Par exemple, les coordonnées GPS et l'identifiant INSEE sont ajoutés à l'URL de l'API MeteoConcept comme paramètres de requête.

Information dans la Réponse pour la Température et la Prévision Météo :

La température (minimale et maximale) et la prévision météorologique pour le lieu visé par les coordonnées GPS sont extraites de la réponse de l'API MeteoConcept.
Les champs pertinents de la réponse sont tmin, tmax, et weather dans l'objet Forecast de la réponse
.
Intégration dans l'Application
Le contrôleur MeteoController gère la logique de traitement des données météorologiques. Lorsqu'une adresse est soumise, le contrôleur effectue les actions suivantes :

Convertit l'adresse en coordonnées GPS en utilisant l'API api-adresse.data.gouv.fr.
Utilise ces coordonnées pour faire une requête à l'API MeteoConcept et récupérer les prévisions météorologiques.
Les données météorologiques sont ensuite affichées sur la page meteo.


1– On a besoin de la latitude et de la longitude et du code postal 
2– La même chose en remplacant le 0 dans notre lien en ajoutant les parametres du premier et du dernier jour (0: aujourd'hui, 1: demain, etc.)

## Conclusion du TP4

Ce TP4 illustre la capacité à intégrer et à manipuler des données provenant d'APIs externes, en l'occurrence des données météorologiques, dans une application web. La réussite de ce projet témoigne de compétences avancées en matière de développement web, de traitement de données JSON, et d'intégration d'APIs.

