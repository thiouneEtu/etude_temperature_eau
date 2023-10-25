# etude_temperature_eau

## Description du projet 

Dans le cadre d’un projet visant l’étude des cours d’eau et plus particulièrement la Touques (Fleuve de basse 
Normandie), 4 sondes placées en amont et aval le long du fleuve ont relevé les températures de l’eau le long du 
fleuve de la Touques. Ces sondes sont en général attachées aux racines des arbres de la sylvestre et immergées
dans l’eau àune profondeur leurs permettant d’enregistrer la température quelle que soit la saison.
La température de l’eau présente une variabilité saisonnière tandis que l'eau est généralement plus froide au fond 
(En raison de l'apport d'eau souterraine) et plus chaude à la surface (en raison de la température de l'air plus 
élevée). 

Dans cette étude, nous nous intéressons à comprendre la **variabilité de la température** de l’eau (variable 
dépendante que nous cherchons à expliquer), en fonction de **trois variables indépendantes ou 
explicatives** présentes dans la base de données. Ces variables explicatives sont :
- La température de l’air
- Le volume de pluie
- Le type de sonde utilisé
- Le type de sond

La base de données comprend **93 832 observations** (sur une période allant de 2013 à 2018) et comprend **6 
variables**, présentées sur l'image ci-dessous.

<img src="https://github.com/thiouneEtu/etude_temperature_eau/blob/main/temp_eau1.PNG" width="500" />

## Experimentations

### Statistiques descriptives

Les statistiques descriptives permettent d’avoir un aperçu général des données.
La température de l’eau varie selon le type de sonde qui prend la mesure. Le tableau 2 rend compte de la 
variabilité de la température (en particulier les valeurs extrêmes à savoir le minimum et le maximum). Le tableau 
présente également d’autres statistiques telles que la médiane, l’écart relatif, l’écart type, ainsi que le premier et 
troisième quartile).
Si l’on se concentre uniquement sur les valeurs extrêmes (min et max), nous pouvons constater que, toutes sondes 
confondues, la température minimum observée est de 1,897 et le maximum de température enregistré est de 
21,135. Ces deux mesures (minimales et maximales) ont été enregistrées par la sonde 830. En revanche, la sonde 
825 a enregistré une température minimale de 3,799 (soit la plus forte valeur de toutes les mesures prises par les 
sondes) et une température maximale de 17,809 (soit la plus faible valeur enregistrée pour le maximum de 
température).
Si l’on se réfère à une autre statistique importante, la moyenne, on peut noter que :
En moyenne, la température relevée par la sonde 825 est 2,14 % moins élevée que celle prise par lasonde 827.
La température enregistrée, en moyenne par la sonde 827 est 1,61% moins élevée que celle prise par la sonde
828. Et enfin, la température moyenne relevée par cette dernière est 4,05% moins élevée que celle prise par la
sonde 830. Ces résultats suggèrent donc que la température la plus baisse est enregistrée par la sonde posée en 
amont.

<img src="https://github.com/thiouneEtu/etude_temperature_eau/blob/main/temp_eau2.PNG" width="500" />

### Analyse en composantes indépendantes (ACI)

L'analyse en composantes indépendantes (ICA), quant à elle, est une méthode permettant d'identifier 
automatiquement les facteurs sous-jacents dans un ensemble de données donné (Stone, 2002). Il s’agit d’une 
technique statistique qui a pour objectif de décomposer un signal aléatoire multivariée en une combinaison 
linéaire de signaux indépendants.

<img src="https://github.com/thiouneEtu/etude_temperature_eau/blob/main/temp_eau3.PNG" width="500" />

<img src="https://github.com/thiouneEtu/etude_temperature_eau/blob/main/temp_eau4.PNG" width="500" />

On observe qu’il existe une saisonnalité des composantes (figure 1). Nous pouvons constater que C2 semble 
décliner le plus par rapport à C1, prenant des valeurs extrêmes en 2015. Une des raisons pouvant expliquer cette 
observation est peut-être l’avènement de plusieurs variations météorologiques brusques.
Le déphasage des courbes (Figure 2) semble montrer que le signal d’une composante variant en premier pourrait 
être celui de la température de l’air (courbe bleu) et celui qui le suit (courbe rouge) serait celle de l’eau. Ceci 
semble cohérent étant donné que l’air se réchauffe relativement vite comparé à l’eau.

### Analyse en composantes principales (ACP)

L'analyse en composantes principales (ACP) est une technique de la statistique multivariée. Elle consiste qui 
consiste à transformer des variables liées entre elles ou corrélées en nouvelles variables décorrélées les unes des 
autres. En effet, l’objectif de l’ACP est d'extraire les informations importantes de la base de données et de les 
représenter sous la forme d'un ensemble de nouvelles variables orthogonales. Ces dernières sont appelées 
composantes principales (Abdi and Williams, 2010). La mise en place de l’ACP nous permet de vérifier la corrélation existante entre les variables et de découvrir puis d’expliquer assez nettement nos composantes extraites de l’ACI.

<img src="https://github.com/thiouneEtu/etude_temperature_eau/blob/main/temp_eau5.PNG" width="500" />

Ainsi, l’ACP proposée (Figure 3) résume 92 % de l’information. Celle-ci est portée par l’axe 1 à
71 % et par l’axe 2 à 21%. Il y a 7 variables qui sont utilisées : 5 actives (C1/C2/Tw/Ta/D) et 2
supplémentaires (PE/P), Les variables actives participent à la fixation des axes et celles
supplémentaires ne contribuent pas à la fixation des axes mais permettent de mieux interpréter notre
graphique.
Deux tendances semblent se dégager : la dimension une (Dim1) est portée par Tw, Ta et D(Tw-Ta) à
74% tandis que la dimension deux (Dim2) est fixée par C1 et C2 à 95 %. Ces valeurs nous proviennent
du tableau des contributions issues de l’ACP.
Certaines variables apparaissent très liées comme Ta et Tw désignant respectivement la températurede 
l’air et de l’eau, la matrice des corrélations vient confirmer ce rapprochement car les deux variables
ont une corrélation de 0,91.
Il apparaît bien une corrélation nulle entre les deux composantes C1 et C2 provenant de l’ACI donc
indépendantes et dont les faisceaux sont parfaitement orthogonaux dès lors que les deux variables sont 
bien représentées dans le plan (1,2) à 0,90 et 0,99 respectivement pour C1 et C2 d’après le tableau des 
cosinus carrées désignant les qualités de représentation.
Les Ta et la composante C1 sont opposées. Ces deux variables sont fortement corrélées mais
négativement (-0,78 d’après la matrice des corrélations). Cette négativité traduit le fait que lorsque
l’une augmente, l’autre diminue.
Les variables PE et P pourraient ne pas être assez bien représentées car très proches du centre du cercle.

## Conclusion 

Dans cette étude, nous nous sommes basés sur un dataset comprenant plusieurs milliers d’observations 
sur la température de l’eau de la Touques entre 2013 et 2018. L’objectif de cette étude est de 
comprendre dans quelle mesures certains facteurs tel que celui que l’on vient de citer (température de 
l’air) et d’autres facteurs (type de sonde, pluviométrie) peuvent expliquer la variation de la température 
de l’eau. Afin d’y répondre nous avons utilisé deux techniques principales : l’ACI et l’ACP. Les 
principaux résultats de cette étude montrent que les phénomènes météorologiques influent fortement 
sur la température de l’eau.
