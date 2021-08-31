# ProjetNLP
Catégorisation des documents

## Problématique:

Dans ce projet, on devait lier des documents contenant des commentaires sportifs au groupe de sport auxquel ils appartiennent. 
Le but principal c'était de faire le feature extraction pour des données textuelles et évaluer la pertinence des features obtenus pour des modèles ML.

## Méthodologie
Modèle ML

1. Decision Tree
2. Naive - Bayes
3. RandomForest
4. Logistic
5. Neural Network

## Stratégie de feature extraction:

# TF-IDF avec n-gram de 3 mots maximum

# Autres stratégies

 Latent Dirichlet Allocation
 Utilisation de word cloud pour identifier des stopwords

# Métriques utilisé:

f1-score

# Autres informations dans le développment des modèles:

Dataset non-balancé. On utilise une stratégie de undersampling pour contrecarrer ce problème.
Utilisation de cross-validation pour minimiser le risque de overfitting

# Résultats

## Performance : Prédiction

1. Toutes les algorithmes ont produit un f1-score très élevé (97%-98%).

2. Le Random Forest et le Logistic Regression ont produit des f1-score plus élevés.

3. Le Decision Tree a eu la perfomance la moins bonne avec un f1-score moyen de 89%.

4. Performance : Temps training
En terme de temps de training, tous les modèles ont pris entre 0-5 seconds, sauf le Random Forest qui a pris entre 10-30 fois plus de temps pour le training.
Performance en terme de consistence
Le RF et le logistic regression ont la plus petite variance de f1-score

5. LDA : Le latent Dirichlet a permis d'identifier des regroupements possible. Le cricket et Rugby était les sports pour lequel plus de regroupements ont été identifiés

6. Classes plus difficile à prédire
Le football et le rugby ont été le plus difficile à prédire. Dans le logistic regression, qui avait une très bonne performance, on a eu une mauvaise classification entre les sports de balle football, rugby,le cricket le tennis. C'est plus souvent le football qui est mal prédit.On peut le noter dans les f1-score pour le football qui est généralement plus bas.

### Conclusions
Apart le Décision Tree, tous les autres modèles ML qu'on a testé ont produit des très bonne performances dans ce problème de classification de documents sportifs. Ces performancesm, mesuré avec le f1-score, ont tournés autours de 97-98% pour les quatre meilleurs modèles. Le Logistic Regression et le Random Forest classifier (RFC) ont été les meilleurs, si on se fie au critère de consistence et la performance.

Cependant, si on considère aussi le temps de training comme paramètre de performance, le RF a eu une performance beacoup moins bonne que tous les autres algorithmes avec dès fois, un temps de training 30 fois plus long. Ainsi, si on évalue un modèle conjointement par sa performance de classification et de temps requis pour le training, c'est le Logistic Regression qui offre des meilleurs résultats sur ces deux critères.

Finalement,on note aussi que les documents sur le football ont été les plus vulnérables aux mauvaises catégorisations. Il se trouve qu'ils contiennent des termes assez communs avec les autres sports de balles et pas asssez de termes puissants qui pourraient les distingués uniquement des autres sports de balles. Ainsi le football est quelque fois mal prédit.
