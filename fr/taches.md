# CLEF 2024 SimpleText: Tâches

[Accueil](./) | [Appel à communications](./CFD.md) | [Dates importantes](./dates.md) | [Tâches](./taches.md)  | [Outils](./outils.md) | 
[Programme](./programme.md) | [Publications](./publications.md) | [Organisateurs](./organisateurs.md) | [Contact](./contact.md) | [CLEF-2023](https://simpletext-project.com/2023/clef/)

---

## Comment participer
Pour participer, vous devez vous inscrire sur le site web [CLEF](https://clef2024.clef-initiative.eu/index.php) : [http://clef2024-labs-registration.dei.unipd.it/](http://clef2023-labs-registration.dei.unipd.it/).

Tous les membres de l'équipe doivent s'inscrire à la liste de diffusion SimpleText :
[https://groups.google.com/g/simpletext](https://groups.google.com/g/simpletext).

Les données seront mises à la disposition de tous les participants inscrits.

## Tâche 1 : Récupérer des passages à inclure dans un résumé simplifié

A partir d'un article de vulgarisation scientifique destiné à un large public, cette tâche vise à récupérer des passages qui peuvent aider à comprendre cet article, à partir d'un large corpus de résumés académiques et de métadonnées bibliographiques. Les passages pertinents doivent se rapporter à l'un des sujets de l'article source. Ces passages peuvent être complexes et nécessiter une simplification supplémentaire qui sera effectuée dans les tâches 2 et 3. La tâche 1 se concentre sur la recherche de contenu.

### Données
Nous utilisons des articles de vulgarisation scientifique comme source pour les types de sujets qui intéressent le grand public et comme validation du niveau de lecture qui leur convient. Le corpus principal est un vaste ensemble de résumés scientifiques et de métadonnées associées couvrant le domaine de l'informatique et de l'ingénierie. Nous réutilisons la collection de résumés universitaires du Citation Network Dataset ([12e version publiée en 2020] (https://www.aminer.cn/citation)). Cette collection a été extraite de DBLP, ACM, MAG (Microsoft Academic Graph) et d'autres sources. Les requêtes de recherche sont basées sur des articles de presse populaires destinés à un public général, basés sur _The Guardian_ et _Tech Xplore_. Chacun de ces articles de vulgarisation scientifique représente un sujet général qui doit être analysé pour extraire les informations scientifiques pertinentes du corpus. Nous fournissons les URL des articles originaux, le titre et le contenu textuel de chaque article de vulgarisation scientifique en tant que sujet général. Chaque sujet général a également été enrichi d'un ou plusieurs mots-clés spécifiques extraits manuellement de leur contenu, créant ainsi une tâche familière de recherche d'informations classant les passages ou les résumés en réponse à une requête.

### Évaluation
La pertinence thématique a été évaluée l'année dernière à l'aide d'une note de 0 à 2 sur le degré de pertinence par rapport au contenu de l'article original. En 2023, nous avons fourni une première analyse de la complexité du texte (basée sur des mesures de lisibilité) et de la crédibilité (basée sur des mesures d'impact académique). En 2024, nous prévoyons de fournir des mesures d'évaluation supplémentaires sur la pertinence thématique et la complexité/crédibilité. Bien que ces critères puissent fournir différents niveaux de comparaison entre les systèmes, nous continuerons à fournir des notes de classement standard basées sur le NDCG.

## Tâche 2 : Identifier et expliquer les concepts difficiles

L'objectif de cette tâche est de déterminer quels concepts dans les résumés scientifiques nécessitent une explication et une mise en contexte afin d'aider le lecteur à comprendre le texte scientifique. La tâche se déroule en deux étapes :

i) retrouver jusqu'à 5 termes difficiles dans un passage donné d'un résumé scientifique
ii) fournir une définition ou une explication, ou les deux, de ces termes difficiles.

Le corpus de la tâche 2 est basé sur les phrases des résumés les mieux classés pour les demandes de la tâche 1.

### Évaluation
Nous évaluerons le repérage de concepts complexes en termes de complexité et d'étendue des concepts détectés. Nous évaluerons automatiquement les explications fournies en les comparant à des références (par exemple ROUGE, similarité cosinus, etc.). En outre, nous évaluerons manuellement les explications fournies en termes d'utilité par rapport à une requête ainsi que de complexité pour un public général. Notons que les explications fournies peuvent prendre différentes formes, par exemple le déchiffrage d'abréviations, des exemples, des cas d'utilisation, etc.

## Tâche 3 : Simplifier un texte scientifique

L'objectif de cette tâche est de fournir une version simplifiée de phrases extraites de résumés scientifiques. Les participants recevront les articles et les requêtes de vulgarisation scientifique ainsi que les résumés correspondants d'articles scientifiques, divisés en phrases individuelles.

### Données
3 utilise le même corpus basé sur les phrases des résumés les mieux classés pour les requêtes de la tâche 1. Nos données d'entraînement sont un corpus véritablement parallèle de phrases directement simplifiées provenant de résumés scientifiques du DBLP Citation Network Dataset pour _Computer Science_ et d'articles de Google Scholar et PubMed sur _Health and Medicine_. En 2024, nous élargirons les données de formation et d'évaluation. En plus de la simplification du texte au niveau de la phrase, nous fournirons des simplifications d'entrée et de référence au niveau du passage.

### Évaluation
Nous mettrons l'accent sur les mesures d'évaluation automatique à grande échelle (SARI, ROUGE, compression, lisibilité) qui fournissent une collection de tests réutilisable. Cette évaluation automatique sera complétée par une évaluation humaine détaillée d'autres aspects, essentiels pour une analyse plus approfondie. Nous évaluons la complexité des simplifications fournies en termes de vocabulaire et de syntaxe ainsi que les erreurs (syntaxe incorrecte, anaphore non résolue due à la simplification, répétition/itération inutile, erreurs d'orthographe, de typographie ou de ponctuation). Lors des éditions précédentes, presque tous les participants ont utilisé des modèles génératifs pour la simplification des textes, mais les mesures d'évaluation existantes ne tiennent pas compte des hallucinations potentielles avec un contenu supplémentaire ou déformé. En 2024, nous fournirons de nouvelles mesures d'évaluation qui détecteront et quantifieront les hallucinations dans les résultats.

## Tâche 4 : Suivre l'état de l'art dans les publications scientifiques
Dans le domaine de l'intelligence artificielle (IA), un objectif de recherche commun est le développement de nouveaux modèles capables de rendre compte des performances de l'état de l'art (SOTA). Le rapport comprend généralement quatre éléments intégraux : La tâche, l'ensemble de données, la métrique et le score. Ces tuples (tâche, ensemble de données, métrique, score) provenant de divers documents de recherche en IA alimentent les tableaux de bord de la communauté. Les tableaux de classement, qui s'apparentent à des tableaux d'affichage, traditionnellement gérés par la communauté, sont des plateformes affichant les scores de divers modèles d'IA pour des tâches, des ensembles de données et des métriques spécifiques. Parmi les exemples de ces plateformes, on peut citer la fonction "benchmarks" de l'Open Research Knowledge Graph et Papers with Code (PwC). L'utilisation de techniques d'exploration de texte permet de passer de la curation conventionnelle des tableaux de classement basée sur la communauté à une approche d'exploration de texte automatisée. Par conséquent, l'objectif de la tâche 4 est de développer des systèmes qui, à partir du texte complet d'un article d'IA, sont capables de reconnaître si un article d'IA entrant rapporte effectivement des scores de modèle sur des ensembles de données de référence et, si c'est le cas, d'extraire tous les tuples pertinents (tâche, ensemble de données, métrique, score) présentés dans l'article.

Veuillez consulter le [site web de la tâche 4] (https://sites.google.com/view/simpletext-sota/home) pour obtenir des informations sur l'inscription, les modalités de participation, le calendrier de la tâche et les liens de téléchargement des ensembles de données.
### Données
Les ensembles de données d'entraînement et de test pour cette tâche sont dérivés des annotations (T, D, M, S) créées par la communauté pour des milliers d'articles sur l'IA disponibles sur PwC (CC BY-SA). Ces articles, provenant à l'origine d'arXiv sous licence CC-BY, sont disponibles au format TEI XML, chacun accompagné d'une ou plusieurs annotations (T, D, M, S) de PwC. L'ensemble de test ne comprendra stratégiquement que les articles avec des TDM vus dans l'ensemble d'entraînement, créant ainsi un petit échantillon de l'ensemble de test.
dans l'ensemble d'apprentissage, créant ainsi un cadre d'évaluation à quelques reprises. En plus de l'évaluation à quelques reprises, nous avons l'intention d'introduire un deuxième cadre d'évaluation pour la tâche 4, en évaluant les modèles dans un contexte à zéro coup, pour lequel un nouvel ensemble de données de test sera créé. Cet ensemble de données sera enrichi d'articles qui ne font pas état de classements afin d'entraîner les systèmes des participants à attribuer des étiquettes correctes à des articles provenant d'autres domaines.

### Évaluation
Les systèmes des participants seront évalués dans deux contextes :

Pour l'évaluation __Few-shot__, les systèmes formés devront prédire les annotations (T, D, M, S) sur une nouvelle collection d'articles en texte intégral. Les étiquettes de l'ensemble de données de référence ne comprendront que les annotations (T, D, M, S) vues au moins une fois au cours de la formation.
Pour l'évaluation __Zero-shot__, la tâche est la même que ci-dessus avec une collection différente d'articles, qui ont (T, D, M, S) avec T, D, ou M non vus dans l'ensemble d'entraînement.

Dans les deux cas, les mesures standard de rappel, de précision et de score F seront utilisées pour communiquer les résultats aux systèmes participants.
