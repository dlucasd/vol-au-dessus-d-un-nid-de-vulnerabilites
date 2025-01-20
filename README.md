# Vol au-dessus d’un nid de vulnérabilités

## Générer les slides en local

1. Télécharger `reveal.js`, le dézipper dans le répertoire `slides` et nommer le répertoire `reveal.js` : https://github.com/hakimel/reveal.js/archive/master.zip


2. Lancer les commandes suivantes :
```
docker container run --rm -ti -u $(id -u):$(id -g) -v $(pwd):/documents asciidoctor/docker-asciidoctor:1.80 asciidoctor-revealjs index.adoc
```

3. Ouvrir le fichier index.html généré.

## Résumé

Avez-vous déjà eu un audit de sécurité sur votre projet ? Nous aussi, et pour faire simple, nous n'étions pas très bons pour mettre à jour nos dépendances tierces.

Après avoir automatisé ce processus, nous nous sommes demandés comment scanner régulièrement nos dépendances à la recherche de vulnérabilités. C'est ainsi que nous avons découvert le Software Bill Of Materials (SBOM) : l'inventaire des dépendances qui constituent notre logiciel.

Saviez-vous que depuis 2021, les fournisseurs de logiciels pour le gouvernement fédéral des États-Unis doivent obligatoirement fournir un SBOM ? Et l’Europe commence à y réfléchir.

Durant ce talk, je vous présenterai les deux formats de SBOM existants : CycloneDX, soutenu par l'OWASP, et SPDX, par la Linux Foundation. Je vous expliquerai également comment nous avons automatisé leur génération depuis notre CI, ainsi que leur exploitation via DependencyTrack.

N’attendez pas plus longtemps pour ajouter une couche de sécurité logicielle supplémentaire à votre projet !

## Plan (45 minutes)

- Émergence du Software Bill Of Materials - 3 minutes
- Présentation des deux formats : CycloneDX et SPDX - 5 minutes
- Outils permettant de générer un SBOM (Trivy, Syft, SBOM Tools ...) et intégration dans la CI - 15 minutes
- Détection des vulnérabilités - 3 minutes
- Contamination de licences - 2 minutes
- Outils permettant d'exploiter un SBOM (DependencyTrack) - 11 minutes
- Ouverture sur les autres BOM : Cryptography BOM (CBOM), Hardware BOM (HBOM) ... - 3 minutes
- Questions - 3 minutes

## Pourquoi ce talk ?

- Comprendre et implémenter un SBOM permet de mieux gérer les vulnérabilités et d'améliorer la sécurité globale de vos projets.
- Fournir un SBOM peut renforcer la confiance de vos clients et partenaires en montrant votre engagement envers la transparence et la sécurité.
- Le SBOM est devenu crucial avec les nouvelles réglementations, notamment aux États-Unis, et l'Europe suit le mouvement.

## Liens utiles

* Exemples de BOM : https://github.com/CycloneDX/bom-examples

### Outils

SPDX : https://spdx.dev/use/spdx-tools/
CycloneDX : https://cyclonedx.org/tool-center/

### Support Spring Boot

* https://spring.io/blog/2024/05/24/sbom-support-in-spring-boot-3-3

### Support Quarkus

* https://quarkus.io/guides/cyclonedx
* https://quarkus.io/extensions/io.quarkus/quarkus-cyclonedx/

