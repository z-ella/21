# TP Spring Cloud : Eureka + WebClient (MySQL)

Java 17, Spring Boot 3.3.5, Spring Cloud 2023.0.3, Maven multi-module.

## Ouvrir dans IntelliJ
File > Open > dossier `tp-eureka-webclient` (pom.xml racine).

## Prérequis : MySQL (port 3306, user root, mot de passe vide)
Les bases `clientservicedb` et `carservicedb` sont créées automatiquement
(`createDatabaseIfNotExist=true`). Adapter `username/password` dans les `application.yml` si besoin.

Sans MySQL : lancer service-client et service-car avec le profil `h2`
(Run Configuration > Active profiles : `h2`).

## Ordre de lancement
1. EurekaServerApplication (8761)
2. ClientApplication (8081)
3. CarApplication (8082)

Puis exécuter `requests.http`. Résultat attendu : GET http://localhost:8082/api/cars
renvoie les voitures avec leur objet `client` imbriqué.
