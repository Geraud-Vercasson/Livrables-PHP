|Demande             |Requête SQL               |
|--------------------|--------------------------|
|Liste des boissons :|    SELECT name <br>FROM boissons;|
|Liste des ingrédients en manque (dont la quantité est nulle):| SELECT name <br>FROM ingredients <br>WHERE stock != 0;|
|Liste des boissons dont le libellé contient le mot « café »:|SELECT name <br>FROM boissons <br>WHERE name LIKE '%café%';|
|Liste des boissons dont le prix est entre 0.40 et 0.70 euros:|SELECT name <br>FROM boissons <br>WHERE prix >= 40 AND prix <= 70;|
|Liste des ventes d’aujourd’hui classées par n° décroissant:|SELECT *<br>FROM commande<br>WHERE DATE(date) = DATE(NOW())<br>ORDER BY id  DESC;|
|Liste des ingrédients (nom et qte nécesssaire) d’une boisson donnée:|SELECT ingredients.name AS 'ingrédient', recette.quantite <br>FROM ingredients<br> JOIN recette <br>ON ingredients.id = recette.ingredients_id <br>WHERE recette.boissons_id = 2|
|Liste des boissons disponibles (pour lesquelles les ingrédients sont dispo):||
|Liste des boissons vendues aujourd’hui:|SELECT boissons.name <br> FROM commande <br> INNER JOIN boissons <br> WHERE commande.boissons_id = boissons.id <br> AND DATE(NOW()) = DATE(commande.date)|
|Prix de la derniere boisson vendue:|SELECT boissons.prix<br> FROM boissons, commande <br>WHERE commande.boissons_id = boissons.id <br>ORDER BY commande.date DESC LIMIT 1 |
|Nombre de ventes de la boisson « Café »:|SELECT COUNT(*)<br> FROM boissons, commande<br> WHERE commande.boissons_id = boissons.id <br>AND boissons.name = "café" |
|Rajouter la boisson « Café au lait »:|INSERT INTO boissons(name,code,prix)<br> VALUES ("Café au lait", "CAL", 50)|
|Rajouter 100 à la quantité en stock de l’ingrédient « sucre »:|UPDATE ingredients<br> SET ingredients.stock = ingredients.stock + 100 <br>WHERE ingredients.name = "sucre" |
|Augmenter de 0.10 euros le prix de toutes les boissons:|UPDATE boissons <br>SET boissons.prix = boissons.prix + 10 |
|Créer une nouvelle vente de café avec 2 sucres:|INSERT INTO commande(boissons_id, ingredients_id, nbSucres, date)<br>VALUES ((SELECT boissons.id FROM boissons WHERE boissons.name = "café"),<br>        (SELECT ingredients.id FROM ingredients WHERE ingredients.name = "sucre"),<br>        2, NOW()) |
|Supprimer cette vente:|DELETE FROM commande <br>ORDER BY commande.id DESC LIMIT 1 |