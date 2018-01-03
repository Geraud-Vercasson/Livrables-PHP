> Written with [StackEdit](https://stackedit.io/).

Glossaire PHP
=============


----------

| Fonction PHP | Rôle                           |
|--------------|--------------------------------|
|**date**(string \$format, [int \$timestamp])  |  Renvoie une string de la date \$timestamp (par défaut la date actuelle) reformatée selon les règles dans \$format|
|**getdate**([int \$timestamp])| Renvoie un tableau associatif (clés => valeurs) contenant les informations de \$timestamp (par défaut la date actuelle)|
|**time**(void)|Renvoie le timestamp actuel|
| **trim**(\$string [, \$character_mask]) | supprime de \$string les caractères de la chaine \$character_mask, par défaut les espaces |
| **ltrim**(\$string [, \$character_mask]) | même comportement que trim() appliqué uniquement au début de la \$string (left trim)|
|**rtrim**(\$string [, \$character_mask]) | même comportement que trim() appliqué uniquement à la fin de la \$string (right trim)|
|**strlen**($string)| renvoie la longueur de la \$string|
|**strtoupper**($string) | renvoie la conversion en majuscules de la \$string|
|**ucfirst**(\$string)| met en majuscule le premier caractère de la $string et renvoie la chaîne créée|
|**substr**(\$string, int \$start [, int \$length])| renvoie le segment de \$string à partir \$start de longueur \$length (par défaut jusqu'à la fin de \$string). Si \$start est négatif, le segment commencera à compter à partir de la fin|
|**strpos**(\$string, \$toFind [, \$offset])| Renvoie la position de l'élément \$toFind dans \$string. \$offset permet de définir à partir d'où \$string sera parcouru|
|**explode**(\$separateur, \$string [, $limit])| revoie le tableau des sous-chaînes de \$string, séparée par \$separateur. Si \$limit est défini, renvoie \$limit éléments, le dernier étant le reste de la chaîne|
|**hmlspecialchars**(\$string)|convertit les caractères spéciaux dde \$string en entités HTML|
|**urlencode**(\$string)| renvoie une version encodée de \$string insérable dans une URL (plus d'espace, etc)|
|**isset**(\$var[,\$var2 ...])|renvoie TRUE si toutes les variables passées en paramètres sont définies et différentes de NULL|
|**empty**(\$var)| renvoie FALSE si \$var est définie et non vide|
|**\$_GET**|Tableau associatif (clé => valeur) passé par l'URL (méthode GET). exemple:|
|`echo htmlspecialchars($_GET["name"]);`|renvoie `Geraud` si l'URL était `http://example.com/?name=Geraud`|
|**\$_POST**|Tableau associatif passé au script par la méthode POST (voir **\$_GET**)|
|**\$_REQUEST**|Un tableau associatif qui contient par défaut le contenu des variables \$_GET, \$_POST et \$_COOKIE. |
|**\$_SERVER**|Tableau associatif des informations du serveur **(à préciser)**|
|**\$_SESSION**|Tableau associatif des valeurs stockées dans la session. La session s'ouvre dès l'entrée sur le site du visiteur, et se ferme dès sa sortie, au bout d'un temps d'inactivité (timeout) ou la déconnexion via session_destroy(). \$_SESSION nécessite l'appel de la fonction **start_session**() **AVANT TOUT CODE HTML ET SUR CHAQUE PAGE L'UTILISANT** pour pouvoir être utilisé|
|**\$_COOKIE**|Un tableau associatif de variables, passé au script courant, via des cookies HTTP. |
|**include**(\$string)|Inclut au script actuel le fichier spécifié par le chemin \$string. (exemple un autre script php)|
|**require**(\$string)|Comportement analogue à include() mais renvoie une erreur fatale (et donc arrête le script) si l'inclusion renvoie une erreur (include n'émet qu'une alerte **E_WARNING** le cas échéant|
|**include_once**(\$string)|idem include(), mais si le fichier a déjà été inclus, ne le réinclut pas et renvoie TRUE|
|**require_once**(\$string)|idem include_once(), pour require()|
|**key_exists**(\$key, \$array)|alias de **array_key_exists**(), vérifie si la clé \$key existe dnas \$array. renvoie le booléen TRUE si vrai, FALSE sinon|
|**in_array**(\$toFind, \$array)| renvoie TRUE si \$toFind est dans \$array, FALSE sinon|
|**array_search**(\$toFind, \$array)|renvoie la clé associé à \$toFind s'il se trouve dans \$array, FALSE sinon|
|**array_keys**(\$array [,\$search_value])|renvoie un tableau des clés de \$array. Si \$search_value est spécifié, ne renvoie que les clés contenant la valeur de \$search_value|
|**array_values**(\$array)|renvoie toutes les valeurs d'un tableau associatif indexé de façon numérique|
|**is_array**(\$var)|renvoie TRUE si \$var est un tableau, FALSE sinon|
|**sort**(\$array)|trie le tableau \$array dans l'ordre croissant **(à préciser)**|
|**ksort**(\$array)|trie le tableau \$array suivant ses clés|
|**asort**(\$array)|trie le tableau \$array en conservant l'association clé => valeur|
|**each**(\$array)|renvoie chaque paire clé/valeur d'un tableau|
|**print_r**(\$var)|Affiche des informations lisibles pour une variable|

Glossaire SQL
=============


----------

| Notions SQL (ou BDD en général) | Définition |
|--------------|--------------------------------|
|**Banque de données** |  Collection de bases de données|
|**Base de données** | Collection de tables de données |
|**Table**| Collection de lignes d'enregistrement|
|**Ligne d'enregistrement**|Collection de données associées (exemple dans une table "client", une ligne peut contenir nom, prénom et adresse du client, dans des "cases" correspondantes)|
|**SGBD**|Système de Gestion de Base de Données|
|**Moteur SQL**|Programme qui manipule les fichiers de la BDD, et retranscrit les informations stockées de manière "lisible" |
|**Catalogue**|Description de la BDD ++ informations "subsidiaires" (typiquement les droits d'accès à la base de données)|
|**Langage de requête**|Langage informatique dans lequel sera codé les requêtes envoyés au SGBD|
|**Processeur de requête**|Programme d'interprétation de la requête|
|**Plan d'éxécution**|Liste des opérations à réaliser sur la BDD. pour une requête écrite dans le langage de requête, le processeur de requête détermine un plan d'éxécution. Après avoir vérifier que toutes les opérations nécessaires au plan d'éxécution sont autorisées à l'utilisateur (vérification dans le catalogue), le plan est envoyé au moteur SQL, qui renvoie le résultat de la requête|
|--|--|
|**Langage de définition de données (LDD/DDL)**|Architecture de la BDD|
|**CREATE**|mot-clé pour créer un élément (**DATABASE**,**TABLE**,**VIEW**, **INDEX**)|
|**ALTER**|mot-clé pour modifier (altérer) un élément|
|**DROP**|mot-clé pour supprimer un élément|
|**Collation**|Table de conversion des caractères spéciaux, par exemple pour les tris|
|**COLLATE**|mot-clé définissant la collation à utiliser pour la table. ex. **COLLATE utf8_general_ci;**|
|--|--|
|**Langage de manipulation de données (LMD/DML)**|Requête, tri, filtre etc|
|--|--|
|**Langage de contrôle de données (LCD)**|Vérification des droits|
|--|--|
|**Langage de contrôle des transactions(LCT/TCL)**||
|--|--|

/!\ Les colonnes en SQL sont typées et dépendent du SGBD/!\

| Notions SQL | Définition |
|--|--|
|**TINYINT**|Entier encodé sur 1 octet (0-255 non signé ou -128-127 signé)|
|**SMALLINT**|Entier encodé sur 2 octet (0-2^16 non signé ou -2^15-2^15-1 signé)|
|**MEDIUMINT**|Entier encodé sur 3 octet (0-2^24 non signé ou 2^23-2^23-1 signé)|
|**INT**|Entier encodé sur 4 octet (0-2^32 non signé ou -2^31-2^31-1 signé)|
|**BIGINT**|Entier encodé sur 8 octet (0-2^64 non signé ou -2^63-2^63-1 signé)|
|--|--|
|**DECIMAL**/**NUMERIC**(p,s)|définition d'une variable réelle de précision (nombre de chiffres) p et de scale (nombre de chiffres après la virgule) s. max p = 65, max s = 30|


