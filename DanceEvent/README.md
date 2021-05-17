# Gabarit _DanceEvent_

Le gabarit _DanceEvent_ est utilisé pour les représentations des oeuvres. Il s'agit d'une sous-classe de _Event_, le type générique pour les événements dans Schema.org.

[Voir le gabarit](dance_event.json)

## Propriété _performer_

S'il s'agit d'un chorégraphe indépendant, ne pas inclure la propriété `performer`.

## Version courte

Typiquement, il serait préférable d'avoir une page web dédiée à chaque représentation, et donc un seul _DanceEvent_ par page. Cela n'est toutefois pas le cas sur le site de la DSR. Les objets _DanceEvent_ ne seront donc pas utilisés seuls, mais dans le contexte d'un [CreativeWork](../CreativeWork) (dans le répertoire des oeuvres) ou d'une [Organization](../Organization) (dans les répertoire des diffuseurs, des agences et agents, ou des compagnies et chorégraphes). Pour cette raison, on choisit d'utiliser un modèle court, qui ne reprend que les informations essentielles de la représentation, et donne plutôt les informations:

* sur l'oeuvre à travers la propriété `workPerformed`
* sur le diffuseur, à travers la propriété `organizer`
* sur la compagnie ou le chorégraphe, à travers la propriété `performer`

Si le site venait à changer (une page par représentation), il pourrait être préférable d'utiliser un modèle long, par exemple inspiré de celui de la [Trousse TAI](https://github.com/a10s-ca/trousse-tai).

### Utilisation au sein du gabarit _creativeWork_

Enlever la propriété ``workPerformed``.

### Utilisation au sein du gabarit _organization_ d'un diffuseur

Enlever la propriété ``organizer``

### Utilisation au sein du gabarit _organization_ d'une compagnie de danse

Enlever la propriété ``performer``

### Utilisation au sein du gabarit _organization_ d'une agence

Conserver toutes les propriétés.

## Précisions

### Propriété _name_

 Cette propriété s'applique à la représentation, elle n'est donc pas obligée de contenir le titre de l'oeuvre présentée.

### Propriété _location_

Dans le gabarit, la propriété `location` utilisée représente un lieu physique, donc pour un spectacle en présentiel. Dans le cas d'un événement virtuel, la propriété `location` pourrait prendre la forme suivante:

```
"location": {
  "@type": "VirtualLocation",
  "url": "{{URL pour accéder à la représentation virtuelle}}"
}
```

### Propriété _offers_

Dans le cas où il est possible d'acheter des billets pour la représentation (quand il y a un lien d'achat présenté), la clé _offers_ sera incluse dans le gabarit, sinon elle peut être retirée.

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

(!) Suggestion : comme l'info n'est pas dans la BD, je proposerais de mettre directement eventScheduled et Offline dans le modèle au lieu d'offrir le choix.

## Questions pour Stéphanie

- [ ] Peut-on trouver une façon de faire un lien entre l'oeuvre et l'agence ou l'agent?
- [ ] Quelle clé est plus pertinente pour le chorégraphe : `director` ou `contributor` ? 
- Contributor : A secondary contributor to the CreativeWork or Event.
- Director : A director of e.g. tv, radio, movie, video gaming etc. content, or of an event.
- [ ] Quelle clé est plus pertinente pour la compagnie : `performer` ou `contributor` ? 
- Performer : A performer at the event—for example, a presenter, musician, musical group or actor. Supersedes performers.
- Contributor : A secondary contributor to the CreativeWork or Event.
- [ ] Adapter la clé `performer` si jamais on a des chorégraphes représentés par Person et pas Organization
- [ ] Est-ce qu'on a l'info sur le lieu (nom et/ou adresse) dans la BD ? Parce que ça n'apparait pas dans le tableua des représentations. Si on ne l'a pas, il faut enlever la propriété `location`.
- [ ] idem pour la propriété `offers`.
