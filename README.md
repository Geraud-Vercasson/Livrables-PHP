
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
