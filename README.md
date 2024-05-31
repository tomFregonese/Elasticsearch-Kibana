# Atelier 1 - Elasticsearch & Kibana — Tom Frégonese

<br>

### Prérequis :
- Docker et docker-compose installés
- Accès à internet

<br> 

## - Partie 1: Installation et Configuration du Cluster Elasticsearch

Dans cet atelier, nous utiliserons Elasticsearch via des conteneurs Docker. Pour les lancer, il faut exécuter la commande suivante :

```bash 
docker compose up -d
```

<br>

## - Partie 2: Premiers Pas avec le Cluster Elasticsearch

Pour interagir avec Elasticsearch, il suffit d'envoyer les commandes via curl :

### Créer un index nommé test01
```bash 
curl -X PUT "localhost:9200/test01"
```

### Vérifier que cet index est maintenant présent
```bash 
curl "localhost:9200/_cat/indices?v"
```

### Créer ce document dans cet index
```bash 
curl -X POST "localhost:9200/test01/_doc/1" -H 'Content-Type: application/json' -d'
{
    "titre": "Premier document",
    "description": "C'est la première fois que je crée un document dans ES.",
    "quantité": 12,
    "date_creation": "10-05-2024"
}'
```

### Afficher ce document
```bash
curl "localhost:9200/test01/_doc/1"
```

### Afficher quel mapping a été appliqué par défaut
```bash
curl "localhost:9200/test01/_mapping"
```

### Créer un nouvel index test02
```bash
curl -X PUT "localhost:9200/test02"
```

### Appliquer un mapping plus adapté aux données du document ci-dessus
```bash
curl -X PUT "localhost:9200/test02/_mapping" -H 'Content-Type: application/json' -d'
{
    "properties": {
        "titre": { "type": "text" },
        "description": { "type": "text" },
        "quantité": { "type": "integer" },
        "date_creation": { "type": "date", "format": "dd-MM-yyyy" }
    }
}'
```

### Afficher la manière dont le texte de la description du document a été traité par l'analyzer
```bash
curl "localhost:9200/test02/_analyze" -H 'Content-Type: application/json' -d'
{
    "field": "description",
    "text": "C'est la première fois que je crée un document dans ES."
}'
```

### Créer un index test03 qui intègre le mapping ci-dessus
```bash
curl -X PUT "localhost:9200/test03" -H 'Content-Type: application/json' -d'
{
    "mappings": {
        "properties": {
            "titre": { "type": "text" },
            "description": { "type": "text" },
            "quantité": { "type": "integer" },
            "date_creation": { "type": "date", "format": "dd-MM-yyyy" }
        }
    }
}'
```


- Partie 3: Intégration de Kibana
...

