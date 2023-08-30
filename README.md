# Average-rating-book-prediction

L'objectif de ce projet est de prédire la note moyenne pouvant être obtenue par un livre à base d'informations sur celui-ci. Cette note peut être comprise entre 1 et 5 et peut dépendre de plusieurs facteurs tels que : 
 - son titre, 
 - son/ses auteur(s) ;
 - son/ses éditeur(s) ;
 - sa langue d'édition ;
 - son nombre de pages ;
 - le nombre de critiques obtenu ;
 - le nombre de personnes lui ayant affecté une note.
 Ces différents facteurs pourraient intervenir dans notre prédiction en tant que variables explicatives.
 
ANALYSE EXPLORATOIRE

Analyse structurelle

- Notre jeu de données contient 11123 lignes et 12 colonnes ;
- Notre jeu de données ne contient pas de valeurs nulles ;
- Notre jeu de données ne contient aucune ligne dupliquée ;
- Notre jeu de données comporte des variables catégorielles (authors, title, language_code, publication_date, publisher, isbn, isbn13) et numériques (bookID, average_rating, num_pages, ratings_count, text_review_count).

Analyse statistique

Après avoir observé les courbes de distribution et les boites à moustaches de nos variables quantitatives, nous avons décidé d’imposer des critères de cohérence à notre jeu de données, à savoir :
- num_pages : ne dépasse pas 1.500 pages ;
- text_reviews_count : ne dépasse 20.000 commentaires ;
- ratings_count : ne dépasse pas 800.000 votes ;
- average_rating : est compris entre 2.5 et 4.7.

CHOIX DE L’ALGORITHME ET ENTRAINEMENT DU MODELE

Nous avons décidé de sélectionner comme variables explicatives les variables suivantes :
- title : le titre du livre ;
- authors : le/les auteurs du livre ;
- language_code : la langue d'édition du livre ;
- publisher : le/les éditeurs du livre.
- num_pages : le nombre de pages.

En effet ces variables nous semblent pertinentes et cohérentes pour la prédiction de la variable cible average_rating.

Pour effectuer notre sélection de modèle, nous avons divisé notre jeu de données en 2 parties : une pour l’entrainement (80%) et une autre pour le test (20%). Etant donné que nous souhaitons prédire une valeur numérique et continue, il s’agit d’un problème de régression. Nous avons donc appliqué plusieurs modèles de ce type et comparé les résultats, en considérant les métriques suivantes : le score R2 et la MSE (l’erreur quadratique moyenne). De ces résultats, il en ressort que le modèle ayant obtenu les meilleurs résultats est le  Gradient Boosting Regressor.

