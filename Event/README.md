# Gabarit _Event_

Le gabarit _Event_ est utilisé pour les représentations des oeuvres.

[Voir le gabarit](event.json)

## Notes sur le choix de la classe

La classe _DanceEvent_, sous classe de _Event_, n'a pas été retenue. En effet, sa description fait référence à une danse «sociale». Nous avons toutefois choisi d'indiquer une propriété `additionalType` pour préciser que les données décrivent un spectacle de danse.

_Pour plus de détails sur le sujet, nous vous invitons à lire [Les données structurées Schema et les représentations de spectacles](https://linkeddigitalfuture.ca/fr/2021/10/25/donnees-structurees-schema-et-spectacles/) de Frédéric Julien sur le blogue du projet [Un avenir numérique lié](https://linkeddigitalfuture.ca/fr/accueil/).

## Propriété _performer_

S'il s'agit d'un chorégraphe indépendant, ne pas inclure la propriété `performer`.

## Version courte

Typiquement, il serait préférable d'avoir une page web dédiée à chaque représentation, et donc un seul _Event_ par page. Cela n'est toutefois pas le cas sur le site de la DSR. Les objets _Event_ ne seront donc pas utilisés seuls, mais dans le contexte d'un [CreativeWork](../CreativeWork) (dans le répertoire des oeuvres) ou d'une [Organization](../Organization) (dans les répertoire des diffuseurs, des agences et agents, ou des compagnies et chorégraphes). Pour cette raison, on choisit d'utiliser un modèle court, qui ne reprend que les informations essentielles de la représentation, et donne plutôt les informations:

* sur l'oeuvre à travers la propriété `workPerformed`
* sur le diffuseur, à travers la propriété `organizer`
* sur la compagnie ou le chorégraphe, à travers la propriété `performer`

Si le site venait à changer (une page par représentation), il pourrait être préférable d'utiliser un modèle long, par exemple inspiré de celui de la [Trousse TAI](https://github.com/a10s-ca/trousse-tai).

### Utilisation au sein du gabarit _creativeWork_

Enlever la propriété ``workPerformed``.

### Utilisation au sein du gabarit _organization_ d'un diffuseur

Enlever la propriété ``organizer``.

### Utilisation au sein du gabarit _organization_ d'une compagnie de danse

Enlever la propriété ``performer``.

### Utilisation au sein du gabarit _organization_ d'une agence

Conserver toutes les propriétés.

## Précisions

### Propriété _name_

Cette propriété s'applique à la représentation, il n'est donc pas obligatoire qu'elle contienne le titre de l'oeuvre présentée.

### Propriété _location_

Dans le gabarit, la propriété `location` utilisée représente un lieu physique, donc pour un spectacle en présentiel. Dans le cas d'un événement virtuel, la propriété `location` pourrait prendre la forme suivante:

```
"location": {
  "@type": "VirtualLocation",
  "url": "{{URL pour accéder à la représentation virtuelle}}"
}
```

### Propriété _offers_

Dans le cas où il est possible d'acheter des billets pour la représentation (quand il y a un lien d'achat présenté), la clé ``offers`` sera incluse dans le gabarit, sinon elle peut être retirée.

### Propriété _eventStatus_

La liste des options possibles se trouve ici : https://schema.org/EventStatusType

La syntaxe à utiliser est la suivante :

```
"eventStatus": "https://schema.org/EventScheduled"
```

### Propriété _eventAttendanceMode_

La liste des options possibles se trouve ici : https://schema.org/EventAttendanceModeEnumeration

La syntaxe à utiliser est la suivante :

```
"eventStatus": "https://schema.org/OfflineEventAttendanceMode"
```

### Propriété _description_

Il s'agit ici de présenter l'événement, et non pas l'œuvre. Toutefois, si aucune description de l'événement n'est disponible, la description de l'oeuvre peut être utilisée à la place.

Il n'y a pas de longueur maximale pour la description de l'événement. Gardez toutefois en tête que la description sera tronquée lorsqu'elle sera affichée, assurez-vous donc de mettre les informations les plus pertinentes au début. Par exemple, dans le Google Event finder, les descriptions sont coupées après environ 195 caractères. Certaines sources suggèrent de rester en dessous de 500 caractères, d'autres en dessous de 160.

Il n'est pas recommandé de répéter des informations qui se trouvent dans d'autres propriétés, comme la date ou le lieu.

## Questions restantes

### Pour Stéphanie

- [ ] Peut-on trouver une façon de faire un lien entre l'oeuvre et l'agence ou l'agent?
- [ ] Quelle clé est plus pertinente pour le chorégraphe : `director` ou `contributor` ?
- Contributor : A secondary contributor to the CreativeWork or Event.
- Director : A director of e.g. tv, radio, movie, video gaming etc. content, or of an event.
- [ ] Quelle clé est plus pertinente pour la compagnie : `performer` ou `contributor` ?
- Performer : A performer at the event—for example, a presenter, musician, musical group or actor. Supersedes performers.
- Contributor : A secondary contributor to the CreativeWork or Event.
- [ ] Est-ce qu'on a l'info sur le lieu (nom et/ou adresse) dans la BD ? Parce que ça n'apparait pas dans le tableau des représentations. Si on ne l'a pas, il faut enlever la propriété `location`. Idem pour la propriété `offers`.

### Générales

Est-ce que est bien la bonne URI pour le additionalType?
