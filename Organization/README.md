# Gabarit _Organization_

Le gabarit _Organization_ est utilisé pour représenter les membres de la DSR qui sont des diffuseurs, des compagnies de danse ou des agences.

Le gabarit doit être utilisé sur la page dédiée au membre.

[Voir le gabarit](organization.json)


## Propriété _event_

La propriété `event` présentée dans le gabarit est vide. Il faudra y insérer une liste des représentations associées à l'organisation, en utilisant le modèle [Event](../Event).

## Précisions

### Propriété _NAICS_

North American Industry Classification System (NAICS)

Définitions :
- NAICS Code 711120 - Dance Companies
- NAICS Code 711310 - Promoters of Performing Arts, Sports, and Similar Events with Facilities
- NAICS Code 711320 - Promoters of Performing Arts, Sports, and Similar Events without Facilities

Utilisation suggérée :
Pour les compagnies de danse, utiliser 711120, pour les autres organisations, enlever la propriété.

### Propriété _telephone_

Exclue car redondante avec ``contact point``
