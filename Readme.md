# TP 4 : Introduction au Service Mesh
Ce TP est une première introduction aux problématiques rencontrées lors de la création et de la manipulation de micro-services dans un contexte Kubernetes.

## Mise à jour
Après avoir forké le repo, pour se mettre à jour avec la dernière version, exécuter les commandes suivantes:
```bash
git remote add parent https://github.com/cours-ece/tp3.git
git pull
```

## Instructions
Les réponses aux questions posées dans cet énoncé sont attendues dans un fichier **answers.md** situé dans le repo mentionné ci-dessus.

## Rappel/Présentation des outils

* Kubernetes
* Istio (Service mesh)

## 1 : Premiers pas avec Istio
### 1.0: Installation de Istio sur son poste
https://istio.io/docs/setup/kubernetes/download-release/

### 1.1: Installation de Helm sur son poste
https://github.com/helm/helm/blob/master/docs/install.md

### 1.1: Installation de Istio sur le cluster Kubernetes
https://istio.io/docs/setup/kubernetes/helm-install/

### 1.2: Déployer l'application exemple
https://istio.io/docs/examples/bookinfo/

## 2 : Utilisation de Istio dans un déploiement Kubernetes
Le reste du tp vous fait suivre les différentes étapes de déploiement applicatif via kubernetes et les différentes actions permettant de collecter des informations à propos des applicatifs.
Cliquer sur chaque lien, et suivre les commandes affichées dans les readme.

> Ne pas oublier de remplir le ficher **answers.md** tout au long du tp.

[A/B testing](readmes/1-ab-testing.md)

[Fault injection](readmes/2-fault-injection.md)

[Traffic shifting](readmes/3-traffic-shifting.md)

[Request timeout](readmes/4-request-timeout.md)

[Circuit breaking](readmes/5-circuit-breaking.md)

[Mirorring](readmes/6-mirorring.md)

[Rate limits](readmes/7-rate-limit.md)

[Distributed tracing](readmes/8-distributed-tracing.md)

[Collect metrics and logs](readmes/9-collect-metrics-logs.md)

[Query metrics](readmes/10-query-metrics.md)

[Visualizing metrics](readmes/11-visualizing-metrics.md)

