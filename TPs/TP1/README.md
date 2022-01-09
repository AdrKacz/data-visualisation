# TP 1 - Exploration de données avec Tableau

## Charger les données avec Tableau

### À quoi correspondent les icônes en tête de colonnes ?

Les icônes en têtes de colonnes nous informe sur le type de données déduis par Tableau, une [liste exhaustive](https://help.tableau.com/current/pro/desktop/en-us/datafields_typesandroles_datatypes.htm) est disponible dans la documentation.

![Exemple d'icônes](./assets/1.1.a.1.png)

### Lister les principaux types proposés.

- Text (string) values
- Date values
- Date & Time values
- Numerical values
- Boolean values (relational only)
- Geographic values (used with maps)
- Cluster Group (used with *Find Cluster in Data*)

### Quelles colonnes avez-vous dû corriger?

Colonne | Type d'origine | Type corrigé
-- | -- | --
Actualisation | Text | Date & Time
Département | Text | Geographic (State/Province)
Dep | Text | Geographic (Created From *Département*)
Incid Dc | Text | Numerical (decimal)
Incid Hosp | Text | Numerical (decimal)
Incid Rad | Text | Numerical (decimal)
Incid Rea | Text | Numerical (decimal)
Nb Orange | Text | Numerical (whole)
Nb Rouge | Text | Numerical (whole)
R | Text | Numerical (decimal)
Taux Occupation Sae | Text | Numerical (decimal)
Tx Incid | Text | Numerical (decimal)
Tx Pos | Text | Numerical (decimal)

> Dans la colonne **Actualisation**, les données brut (type *Text*) sont sous la forme `10/11/2020-20:09` alors que les données corrigées (type *Date & Time*) sont sous la forme `11/10/2020 20:09:00`. Tableau enregistre les dates sous le format `mm/dd/yyyy` alors que la notation française est `dd/mm/yyyy`.

### Quelles données sont manquantes ? Le sont-elles tout le temps ?

À l'aide d'un logiciel d'analyse de données (*Numbers*), nous obtenons le résultat suivant :

![Analyse des données manquantes](./assets/1.1.d.1.png)

Nous remarquons la majorité des colonnes sont presque vide (*médianne des valeurs vide à **73.29%** du nombre total d'observation*), et ne contiennent donc que très peu d'information.

## Voir les résultats sous forme de bar chart

Pour obtenir le graphique ci-dessous, nous sélectionnons *Jour > Exact Date > Continuous* en colonne, et *SUM(Hosp)* en ligne. Puis nous sélectionnons *Swap Rows and Columns*.

> Si nous avions sélectionné *Jour > Day > Continuous* comme demandé, le graphique aurait été bruité par des lignes verticales. Les données brut sont déjà aggrégé par jour (toutes les observations sont entrées à 20h09).

![Hospitalisation](./assets/1.2.a.1.png)

### Dans les données brut à quoi correspond une ligne d'hospitalisations.

*Pour un département français donné, pour un jour donné, le nombre de personnes hospitalisées en ce jour en ce département.*

### Comment Tableau a-t-il agrégé ?

Tableau a agrégé en sommant sur l'ensemble des département français. Comme nous avons selectionné *Exact Date*, Tableau ne groupe pas par jour.

### Dans quelle ordre les régions sont elles empilées ?

Les régions sont empilées, par défault, par ordre alphabétique.

*Ci-dessous le résultat après avoir changé l'ordre d'empilage par somme du nombre d'hospitalisation sur la période.*

![Hospitalisation](./assets/1.2.c.1.png)

## Sauvegarder et partager

La visualision précendente est disponible sur [Tableau Public - Adrien Kaczmarek - TP1](https://public.tableau.com/app/profile/adrien.kaczmarek/viz/TP1_16417315266490/TP1?publish=yes)

## Filtrer de manière basique

### Quelles régions/départements avez-vous filtré?