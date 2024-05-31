Atelier 1 - Elasticsearch & Kibana

Partie 1: Installation et Configuration du Cluster Elasticsearch
Objectifs

    Créer un cluster Elasticsearch sur un seul serveur ou via Docker.
    Comprendre l'architecture de Elasticsearch et les principes de clustering.

Étapes à Réaliser

    Choix de l'Environnement :
        Décider si le cluster sera configuré sur un serveur unique ou dans des conteneurs Docker.

    Installation de Elasticsearch :
        Installer Elasticsearch localement ou via des images Docker.

    Configuration du Cluster :
        Configurer plusieurs instances de Elasticsearch pour qu'elles fonctionnent en mode cluster.

    Démarrage du Cluster :
        Lancer les instances Elasticsearch configurées pour former un cluster.

Restitution

    Documenter l'architecture choisie, les étapes réalisées et le code de déploiement du cluster Elasticsearch.


Partie 2: Premiers Pas avec le Cluster Elasticsearch
Objectifs

    Comprendre les opérations de base
    Appréhender le mapping de données

Étapes à Réaliser

    Créer un index nommé test01
    Vérifier que cet index est maintenant présent
    Créer ce document dans cet index

    {
      "titre": "Premier document",
      "description": "C'est la première fois que je crée un document dans ES.",
      "quantité": 12,
      "date_creation": "10-05-2024"
    }

    Afficher ce document
    Afficher quel mapping a été appliqué par défaut. Est-il optimal ?
    Essayer de modifier le mapping pour le champ date_creation, pour un plus adapté
    Créer un nouvel index test02
    Appliquer un mapping plus adapté aux données du document ci-dessus
    Afficher la manière dont le texte de la description du document a été traité par l'analyzer
    Créer un index test03 qui :
    intègre le mapping ci-dessus
    indexera la description sans l'altérer
    indexera la description en supprimant les mots sans valeur ajoutée
    Faire un import multiple de 4 documents en une seule requête

Restitution

    Documenter les commandes exécutées, les réponses aux questions et les résultats obtenus.



Partie 3: Intégration de Kibana
Objectifs

    Utiliser Kibana comme interface de visualisation.

Étapes à Réaliser

    Intégrer les données factices fournies:
        Peupler le cluster avec les trois jeux de données d'exemple
        .

    S'essayer aux requêtes :
        Lister les vols dont le prix moyen est entre 300€ et 450€
        Lister les vols annulés
        Lister les vols ou il pleut à l'arrivée ou au départ. Les vols avec de la pluie à l'arrivée devront sortir avant les autres.
        Lister les vols partant d'Allemagne et à destination de France
        Lister les vols ayant eu lieu entre le 1er avril 2024 et le 20 mai 2024

Restitution

    Présenter les actions menées et les requêtes réalisées.