|Demande             |Requ�te SQL               |
|--------------------|--------------------------|
|Liste des boissons :|    SELECT name <br>FROM boissons;|
|Liste des ingr�dients en manque (dont la quantit� est nulle):| SELECT name <br>FROM ingredients <br>WHERE stock != 0;|
|Liste des boissons dont le libell� contient le mot � caf� �:|SELECT name <br>FROM boissons <br>WHERE name LIKE '%caf�%';|
|Liste des boissons dont le prix est entre 0.40 et 0.70 euros:|SELECT name <br>FROM boissons <br>WHERE prix >= 40 AND prix <= 70;|
|Liste des ventes d�aujourd�hui class�es par n� d�croissant:|SELECT *<br>FROM commande<br>WHERE DATE(date) = DATE(NOW())<br>ORDER BY id  DESC;|
|Liste des ingr�dients (nom et qte n�cesssaire) d�une boisson donn�e:|SELECT ingredients.name AS 'ingr�dient', recette.quantite <br>FROM ingredients<br> JOIN recette <br>ON ingredients.id = recette.ingredients_id <br>WHERE recette.boissons_id = 2|
|Liste des boissons disponibles (pour lesquelles les ingr�dients sont dispo):||
|Liste des boissons vendues aujourd�hui:||
|Prix de la derniere boisson vendue:||
|Nombre de ventes de la boisson � Caf�Long �:||
|Rajouter la boisson � Caf� au lait �:||
|Rajouter 100 � la quantit� en stock de l�ingr�dient � sucre �:||
|Augmenter de 0.10 euros le prix de toutes les boissons:||
|Cr�er une nouvelle vente d�expresso avec 2 sucres:||
|Supprimer cette vente:||