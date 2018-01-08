
Glossaire SQL
=============


----------

| Notions SQL (ou BDD en g�n�ral) | D�finition |
|--------------|--------------------------------|
|**Banque de donn�es** |  Collection de bases de donn�es|
|**Base de donn�es** | Collection de tables de donn�es |
|**Table**| Collection de lignes d'enregistrement|
|**Ligne d'enregistrement**|Collection de donn�es associ�es (exemple dans une table "client", une ligne peut contenir nom, pr�nom et adresse du client, dans des "cases" correspondantes)|
|**SGBD**|Syst�me de Gestion de Base de Donn�es|
|**Moteur SQL**|Programme qui manipule les fichiers de la BDD, et retranscrit les informations stock�es de mani�re "lisible" |
|**Catalogue**|Description de la BDD ++ informations "subsidiaires" (typiquement les droits d'acc�s � la base de donn�es)|
|**Requ�te**|Demande envoy�e � la BDD, qui va renvoyer|
|**Langage de requ�te**|Langage informatique dans lequel sera cod� les requ�tes envoy�s au SGBD|
|**Processeur de requ�te**|Programme d'interpr�tation de la requ�te|
|**Plan d'�x�cution**|Liste des op�rations � r�aliser sur la BDD. pour une requ�te �crite dans le langage de requ�te, le processeur de requ�te d�termine un plan d'�x�cution. Apr�s avoir v�rifier que toutes les op�rations n�cessaires au plan d'�x�cution sont autoris�es � l'utilisateur (v�rification dans le catalogue), le plan est envoy� au moteur SQL, qui renvoie le r�sultat de la requ�te|
|**Primary Key**|Cl� primaire : ensemble de donn�es d'un enregistrement (un ou plusieurs champs) permettant d'identifier de mani�re unique un enregistrement donn�. La cl� primaire est d�finie � la cr�ation de la table|
|**Foreign Key**|Cl� �trang�re : cl� fasat r�f�rence dans une table � la cl� primaire d'une autre table. Ce sont ces r�f�rences entre tables qui permettent de cr�er des relations entre ces tables.|
|**Cardinalit�**|La cardinalit� d�finit, dans une relation entre 2 tables, le nombre d'�l�ment de la table 1 que l'on doit r�f�rencer dans un enregistrement de la table 2. Il y a 4 types de cardinalit� possibles : * 0..1 : Il y a 0 ou 1 enregistrement de la table 2 pouvant faire r�f�rence � un enregistrement de la table 1 <br> * 1 : Un seul enregistrement de la table 2 peut et doit faire r�f�rence � un enregistrement de la table 1. <br> * 0..N : Il peut y avoir 0, 1 ou plusieurs enregistrements dans la table 2 faisant r�f�rence � un seul enregistrement dans la table 1. <br> * 1..N : Il y a au moins un enregistrement dans la table 2 faisant r�f�rence � un enregistrement dans la table 1, il est possible d'en avoir plusieurs.|
|--|--|
|**Langage de d�finition de donn�es (LDD/DDL)**|Langage dans lequel s'�crit l'architecture de la BDD|
|**CREATE**|mot-cl� pour cr�er un �l�ment (**DATABASE**,**TABLE**,**VIEW**, **INDEX**)|
|**ALTER**|mot-cl� pour modifier (alt�rer) un �l�ment|
|**DROP**|mot-cl� pour supprimer un �l�ment|
|**Collation**|Table de conversion des caract�res sp�ciaux, par exemple pour les tris|
|**COLLATE**|mot-cl� d�finissant la collation � utiliser pour la table. ex. **COLLATE utf8_general_ci;**|
|--------------------|-------------------|
|**Langage de manipulation de donn�es (LMD/DML)**|Langage dans lequel les requ�tes INSERT SELECT UPDATE et DELETE sont �crites|
|--|--|
|**INSERT**|Insertion (cr�ation) de donn�es dans une table|
|**SELECT**|S�lection (lecture) de donn�es dans une table|
|**UPDATE**|Mise � jour (r��criture) de donn�es dans une table|
|**DELETE**|Suppression de donn�es dans une table|
|-------------------|--------------------------|
|**Langage de contr�le de donn�es (LCD)**|V�rification des droits|
|---------------|---------------------------|
|**Langage de contr�le des transactions(LCT/TCL)**||
|----------------------------|---------------------|

/!\ Les colonnes en SQL sont typ�es et d�pendent du SGBD/!\

| Notions SQL | D�finition |
|---------------|---------------------|
|**TINYINT**|Entier encod� sur 1 octet (0-255 non sign� ou -128-127 sign�)|
|**SMALLINT**|Entier encod� sur 2 octet (0-2^16 non sign� ou -2^15-2^15-1 sign�)|
|**MEDIUMINT**|Entier encod� sur 3 octet (0-2^24 non sign� ou 2^23-2^23-1 sign�)|
|**INT**|Entier encod� sur 4 octet (0-2^32 non sign� ou -2^31-2^31-1 sign�)|
|**BIGINT**|Entier encod� sur 8 octet (0-2^64 non sign� ou -2^63-2^63-1 sign�)|
|**DECIMAL**/**NUMERIC**(p,s)|d�finition d'une variable r�elle de pr�cision (nombre de chiffres) p et de scale (nombre de chiffres apr�s la virgule) s. max p = 65, max s = 30|
|**FLOAT**|Nombre � virgule flottante, de scale 23|
|**DOUBLE**| |

![Sch�ma de l'architecture d'un site](../pictures/architectureSite.png "Sch�ma d'architecture d'un site Web")
![Sch�ma de fonctionnement de mySQL](../pictures/schemeMySQL.png "Sch�ma de fonctionnement de mySQL") 