# Answers

Nom : Jacquin 
Prénom : Théo
NB : 1

# 1.
A quoi sert l'A/B testing ?
L'A/B testing sert à comparer deux versions en divisant le traffic sur les deux versions. On observe alors les performances des deux versions et on sélectionne celle qui nous convient.

Comment appliquer de l'A/B testing grâce à Istio ?
Istio est une open plateform pour manager les micro-services, elle va permettre de manager le traffic entre les différentes versions. Elle repartira le traffic sur les deux routes en leurs attribuant un poids compris entre 0 et 100 et dont la somme doit être égale à 100.
 

# 2.
Comment simuler un problème de timeout avec Istio ?
En utilisant un outil qui permettra de faire du fault injection. 
Cet outil permet de simuler un problème de timeout. 
Il va tester la "résistance" de notre application en y simulant un problème.

Comment le résoudre ?
En augmentant le timeout dans les configurations de la /productpage ou en diminuant le timeout du reviews to rating service
Il faut ensuite stopper et redémarrer le micro-service puis vérifier que la /productpage ne contient plus d'erreurs.

# 3.
Qu'est-ce que le canary release ?
Lorsqu'on a créé une nouvelle version, au lieu de migrer tout le traffic en une fois sur cette nouvelle version, 
on va migrer seulement une petite partie du traffic pour tester la nouvelle version. On appelle cette approche "canary release".

En quoi est-ce utile ?
Cela permet de déployer plus vite une nouvelle version, sans forcément passer par tous les tests et sans passer trop de temps à chercher les potentielles erreures possibles. La petite partie du traffic redirigée va permettre de tester la nouvelle version, sans que tout le traffic soit impactée.

Comment l'implémenter dans Istio ?
On l'implémente de la même manière qu'on manage le traffic dans l'A/B testing, mais avec un rapport plus élevé entre les deux routes (exemple : 95/5)

# 4.

# 5.
Qu'est-ce qu'un Circuit Breaker ?
Le circuit breaker permet le fonctionnement de l'application, même lorsqu'un des services comporte une erreur. Ce pattern va limiter l'impacte des effets indésirables (pics de latence, erreurs...) en stoppant les requêtes vers le service comportant le problème tout en affichant les autres services fonctionnels.

Comment l'implémenter dans un contexte Kubernetes ?
On implémente un circuit breaker en allant dans les configurations de Kubernetes. On y instaure des régles qui déclencheront les circuit breaker.

# 6.
Pourquoi avoir besoin de mirrorer le traffic vers un autre composant ?
(Pas sûr) mirrorer le traffic vers un autre composant permet de tester cet autre composant en prenant le moins de risque possible. C'est à dire que les requetes vont être envoyées aux deux composants, mais l'autre composant ne donnera pas de réponse, cela permet d'utiliser le traffic pour tester ses autres composants en environnement de prod (et en env. de non-prod)

# 7.
Pourquoi bloquer le traffic vers un service ?
Lorsqu'un service contient une erreur ou met trop de temps à répondre, les services qui sont reliés ou qui dépendent de ce service vont être eux aussi impactés. En bloquant le traffic vers ce service on empêche le ralentissement dû à l'accumulation des temps de réponse.

Comment l'implémenter simplement avec Istio ?
Rate limit va permettre de limiter dynamiquement le trafic vers le service en question, on aura alors configuré le nombre maximum de requête et le memquota qui vont activer le rate limit. 

# 8.
Quel est la problématique de tracing distribué ?

Quel est la spécification du tracing distribué et son implémentation dans Istio ?

# 9.
Comment s'appelle l'outil de récupération des métrics ?
Prometheus, puis les données sont rassemblées dans Zipkin

# 10.

# 11.
Comment s'appelle l'outil de visualisation des métrics ?
Grafana

# 12.
A quoi sert un servicegraph ?
Un servicegraph sert à avoir une représentation de tous les services et des appels entre ces services. On a alors un aperçu globale des services, permettant la compréhension de "l'architecture" de l'application et des services qui la composent.

Quel serait l'utilité dans le quotidien d'un ops ?
Un ops doit garantir la stabilité de son système, le servicegraph l'aidera à détecter les changements apportés à l'application afin qu'il puisse les contrôler. 