|Demande             |Requ�te SQL               |
|--------------------|--------------------------|
|Liste des boissons :|    SELECT name <br>FROM boissons;|
|Liste des ingr�dients en manque (dont la quantit� est nulle):| SELECT name <br>FROM ingredients <br>WHERE stock != 0;|
|Liste des boissons dont le libell� contient le mot � caf� �:|SELECT name <br>FROM boissons <br>WHERE name LIKE '%caf�%';|
|Liste des boissons dont le prix est entre 0.40 et 0.70 euros:|SELECT name <br>FROM boissons <br>WHERE prix >= 40 AND prix <= 70;|
|Liste des ventes d�aujourd�hui class�es par n� d�croissant:|SELECT *<br>FROM commande<br>WHERE DATE(date) = DATE(NOW())<br>ORDER BY id  DESC;|
|Liste des ingr�dients (nom et qte n�cesssaire) d�une boisson donn�e:|SELECT ingredients.name AS 'ingr�dient', recette.quantite <br>FROM ingredients<br> JOIN recette <br>ON ingredients.id = recette.ingredients_id <br>WHERE recette.boissons_id = 2|
|Liste des boissons disponibles (pour lesquelles les ingr�dients sont dispo):||
|Liste des boissons vendues aujourd�hui:|SELECT boissons.name <br> FROM commande <br> INNER JOIN boissons <br> WHERE commande.boissons_id = boissons.id <br> AND DATE(NOW()) = DATE(commande.date)|
|Prix de la derniere boisson vendue:|SELECT boissons.prix<br> FROM boissons, commande <br>WHERE commande.boissons_id = boissons.id <br>ORDER BY commande.date DESC LIMIT 1 |
|Nombre de ventes de la boisson � Caf� �:|SELECT COUNT(*)<br> FROM boissons, commande<br> WHERE commande.boissons_id = boissons.id <br>AND boissons.name = "caf�" |
|Rajouter la boisson � Caf� au lait �:|INSERT INTO boissons(name,code,prix)<br> VALUES ("Caf� au lait", "CAL", 50)|
|Rajouter 100 � la quantit� en stock de l�ingr�dient � sucre �:|UPDATE ingredients<br> SET ingredients.stock = ingredients.stock + 100 <br>WHERE ingredients.name = "sucre" |
|Augmenter de 0.10 euros le prix de toutes les boissons:|UPDATE boissons <br>SET boissons.prix = boissons.prix + 10 |
|Cr�er une nouvelle vente de caf� avec 2 sucres:|INSERT INTO commande(boissons_id, ingredients_id, nbSucres, date)<br>VALUES ((SELECT boissons.id FROM boissons WHERE boissons.name = "caf�"),<br>        (SELECT ingredients.id FROM ingredients WHERE ingredients.name = "sucre"),<br>        2, NOW()) |
|Supprimer cette vente:|DELETE FROM commande <br>ORDER BY commande.id DESC LIMIT 1 |