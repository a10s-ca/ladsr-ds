# Gabarit _Person_

Le gabarit _Person_ est utilisé pour représenter les chorégraphes indépendants.

## Précisions

### name, givenName, familyName

Si le nom du chorégraphe est disponible dans la base de données en deux champs (nom et prénom) il est possible d'utiliser les propriétés `givenName` et `familyName` en plus de la propriété `name`.

### Propriétés exclues

#### ``isicV4``
ISIC Code 9000 - Creative, Arts And Entertainment Activities

#### ``jobTitle``
redondant avec la propriété hasOccupation et moins important selon la littérature

trop vague

exemple :
``
"isicV4": " 9000",
``
