# Gabarit _Person_

Le gabarit _Person_ pourrait être utilisé pour représenter les chorégraphes indépendants. La version actuelle du site de La danse sur les route décrit toutefois les chorégraphes indépendants avec le modèle [Organization](../Organization) car leur présence sur le site joue le même rôle que celui d'organisations, et qu'ils sont stockés comme tels. De futurs changements à la structure de la base de données pourrait mener à l'utiliser du gabarit Person dans ce cas, ou à l'ajout des descriptions des chorégraphes de façon générale (qu'ils soient associés à une organisation ou qu'ils soient indépendants).

[Voir le gabarit](person.json)

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
