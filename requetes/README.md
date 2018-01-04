|Demande             |Requête SQL               |
|--------------------|--------------------------|
|Liste des boissons :|    SELECT name FROM boissons;|
|Liste des ingrédients en manque (dont la quantité est nulle):| SELECT name FROM ingredients WHERE stock != 0;|
|Liste des boissons dont le libellé contient le mot « café »:|SELECT name FROM boissons WHERE name LIKE '%café%';|
|Liste des boissons dont le prix est entre 0.40 et 0.70 euros:|SELECT name FROM boissons WHERE prix >= 40 AND prix <= 70;|
|Liste des ventes d’aujourd’hui classées par n° décroissant:||
|Liste des ingrédients (nom et qte nécesssaire) d’une boisson donnée:|SELECT ingredients.name AS 'ingrédient', recette.quantite
FROM ingredients
JOIN recette
ON ingredients.id = recette.ingredients_id
WHERE recette.boissons_id = 2|

|Liste des boissons disponibles (pour lesquelles les ingrédients sont dispo):|
SELECT DISTINCT boissons.name AS 'Boissons disponibles'
FROM boissons
JOIN recette
ON boissons.id = recette.boissons_id
JOIN ingredients
ON recette.ingredients_id = ingredients.id
WHERE ingredients.stock > recette.quantite|

|Liste des boissons vendues aujourd’hui:||


|Prix de la derniere boisson vendue:||


|Nombre de ventes de la boisson « CaféLong »:||


|Rajouter la boisson « Café au lait »:||


|Rajouter 100 à la quantité en stock de l’ingrédient « sucre »:||


|Augmenter de 0.10 euros le prix de toutes les boissons:||


|Créer une nouvelle vente d’expresso avec 2 sucres:||


|Supprimer cette vente:||
