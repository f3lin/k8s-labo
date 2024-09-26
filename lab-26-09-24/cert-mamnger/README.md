# Kubernetes Cert-Manager et Let's Encrypt

**Cert-manager**, un projet open-source jetstack.io, est un contrôleur de gestion de certificats ISA x509 natif de Kubernetes. En tant qu'outil d'automatisation, cert-manager réduit la charge de « travail de routine » des ingénieurs, permettant aux experts hautement rémunérés de se concentrer là où ils peuvent ajouter le plus de valeur. Il simplifie la gestion, l'émission et le renouvellement des certificats, sécurisant le trafic des applications - une fonction essentielle dans le Web contemporain. L'automatisation du processus de certification fait gagner du temps aux ingénieurs et améliore la sécurité en supprimant le risque d'erreur humaine.

Cert-manager a été construit autour des CustomResourceDefinitions de Kubernetes, ce qui a conduit à une flexibilité beaucoup plus grande en matière de configuration. Les capacités de débogage ont également été améliorées et prennent désormais en charge une plus large gamme d'autorités de certification que Let's Encrypt en tant qu'outil autonome.

Cert-Manager automatise la fourniture des certificats au sein des clusters Kubernetes. Il fournit un ensemble de ressources personnalisées pour émettre des certificats et les attacher aux services. L'un des cas d'utilisation les plus courants est la sécurisation des applications Web et des API avec des certificats SSL de [Let's Encrypt](https://letsencrypt.org/fr/docs/).

# [installation](https://cert-manager.io/docs/installation/helm/) 


# Composants Cert-Manager

Les CRD (CustomResourceDefinitions) installés par Cert-Manager vont donc étendre l'api de Kubernetes et de nouveau objets verront le jour :

1. Les Issuer qui représentent une autorité de certification auprès de laquelle des certificats x509 signés peuvent être obtenus, tels que Let's Encrypt– l'outil de provisionnement de certificats de jetstack.io pour les ressources Kubernetes Ingress.

2. Les ClusterIssuer qui sont des ressources similaires aux Issuer. Ils sont spécifiés exactement de la même façon , mais il n'appartient pas à un seul Namespace comme les Issuer et peuvent être référencé par des ressources de certificat à partir de plusieurs Namespaces différents.

3. Les certificat qui sont des ressources qui appartiennent à un Namespace qui fait référence à un Issuer ou à un CusterIssuer pour obtenir des informations sur la manière d'obtenir le certificat.


# exemples

* [kuard](https://cert-manager.io/docs/tutorials/acme/nginx-ingress/)
* [nginx-web](https://ruanbekker.hashnode.dev/cert-manager-dns-challenge-with-cloudflare-on-kubernetes)

# sources
[datascientest](https://learn.datascientest.com/)


# commandes:

```bash
   kubectl get crd
   kubectl get clusterissuers
   kubectl get certificate
   kubectl get challenges
```