# Webservices
L'ensemble des données Ma ville sont accessibles via des webservices de type REST. Les données sont encodées en UTF-8.

Les réponses du services sont au format JSON, du coup, les en-têtes HTTP Content-Type devraient ressembler à ceci : Content-Type : application / json ; charset = utf-8






## Report
### GET Service Requests
Pour voir les remontées déjà faites

```
GET http://preprod-mas.makina-corpus.net/georeport/v2/requests.json
```

**Réponses possibles**

- 400 Erreur générale 
- Si tout va bien, retourne le JSON suivant :

```
[
  {
    "service_request_id": "87a3-14",
    "status": "closed",
    "service_code": "011",
    "service_name": "Litter Basket Complaint",
    "description": "Lorem Ipsum Lorem ipsum dolor sit amet, consectetur ing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,  quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo",
    "agency_responsible": null,
    "service_notice": null,
    "address_id": null,
    "requested_datetime": "2014-03-25T17:44:48+01:00",
    "updated_datetime": "2014-03-26T09:22:18+01:00",
    "address": "Centre, 50321 Brühl",
    "zipcode": null,
    "lat": 50.826873,
    "long": 6.900167,
    "media_url": "http://preprod-mas.makina-corpus.net/sites/default/files/styles/large/public/image_flickr_by_realname_garbage-tonal-decay.jpg?itok=T6h5HNvG"
  }
]
```

### POST Service Request
Pour déclarer une anomalie

```
POST http://preprod-mas.makina-corpus.net/georeport/v2/requests.json
```

- **service_code** L'ID des catégories. 
- **lat** en format WGS84 valide 
- **long** en format WGS84 valide 
- **device_id**
- **account_id** L'ID de l'utilisateur
- **description**
- **media_url**


**Réponses possibles**

- 400 Erreur générale 
- 404 service code introuvable
- Si tout va bien retourne le **service

### GET Service List
Pour récupérer la liste des catégories

```
GET http://preprod-mas.makina-corpus.net/georeport/v2/services.json
```

**Réponses possibles**

- 400 Erreur générale 
- Si tout va bien, retourne le JSON suivant :

```
[
  {
    "service_code": "010",
    "service_name": "Abandoned Cars",
    "metadata": "false",
    "type": "realtime",
    "description": "abandoned, wrecked, dismantled, or inoperative cars on private property",
    "keywords": "abandonedcar, cars, wreckedcar, car"
  }
]
```

### GET Fixed Services Number
TODO

### GET Services Number
TODO

### GET Actual Week Services Number
TODO

## Users
### Authentification
TODO
### Post add user
TODO
