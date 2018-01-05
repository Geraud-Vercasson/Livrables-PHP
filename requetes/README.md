|Demande             |Requête SQL               |
|--------------------|--------------------------|
|Liste des boissons :|    SELECT name <br>FROM boissons;|
|Liste des ingrédients en manque (dont la quantité est nulle):| SELECT name <br>FROM ingredients <br>WHERE stock != 0;|
|Liste des boissons dont le libellé contient le mot « café »:|SELECT name <br>FROM boissons <br>WHERE name LIKE '%café%';|
|Liste des boissons dont le prix est entre 0.40 et 0.70 euros:|SELECT name <br>FROM boissons <br>WHERE prix >= 40 AND prix <= 70;|
|Liste des ventes d’aujourd’hui classées par n° décroissant:|SELECT *<br>FROM commande<br>WHERE DATE(date) = DATE(NOW())<br>ORDER BY id  DESC;|
|Liste des ingrédients (nom et qte nécesssaire) d’une boisson donnée:|SELECT ingredients.name AS 'ingrédient', recette.quantite <br>FROM ingredients<br> JOIN recette <br>ON ingredients.id = recette.ingredients_id <br>WHERE recette.boissons_id = 2|
|Liste des boissons disponibles (pour lesquelles les ingrédients sont dispo):||
|Liste des boissons vendues aujourd’hui:||
|Prix de la derniere boisson vendue:||
|Nombre de ventes de la boisson « CaféLong »:||
|Rajouter la boisson « Café au lait »:||
|Rajouter 100 à la quantité en stock de l’ingrédient « sucre »:||
|Augmenter de 0.10 euros le prix de toutes les boissons:||
|Créer une nouvelle vente d’expresso avec 2 sucres:||
|Supprimer cette vente:||