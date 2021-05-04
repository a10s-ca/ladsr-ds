# Gabarit _DanceEvent_

Le gabarit _DanceEvent_ est utilisé pour les représentations des oeuvres. Il s'agit d'une sous-classe de _Event_, le type générique pour les événements dans Schema.org.

[Voir le gabarit](dance_event.json)


## Notes sur l'utilisation

### Version courte

Typiquement, il serait préférable d'avoir une page web dédiée à chaque représentation, et donc un seul _DanceEvent_ par page. Cela n'est toutefois pas le cas sur le site de la DSR. Les objets _DanceEvent_ ne seront donc pas utilisés seuls, mais dans le contexte d'un [CreativeWork](../CreativeWork) (dans le répertoire des oeuvres) ou d'une [Organization](../Organization) (dans les répertoire des diffuseurs, des agences et agents, ou des compagnies et chorégraphes). Pour cette raison, on choisit d'utiliser un modèle court, qui ne reprend que les informations essentielles de la représentation, et donne plutôt les informations:

* sur l'oeuvre à travers la propriété `workPerformed`
* sur le diffuseur, à travers la propriété `organizer`
* sur la compagnie ou le chorégraphe, à travers la propriété `performer`

Dans tous les cas, il s'agit de simple lien vers l'identifiant et l'URL de l'oeuvre. Selon le contexte d'utilisation du _DanceEvent_, il se peut que l'information soit redondante (il ne serait pas nécessaire de mettre le `workPerformed` puisque la représentation sera dans une énumération `objectOf` de l'oeuvre). Nous avons préféré éviter de faire des variantes qui évite ces redondances partielles pour éviter d'augmenter la complexité d'utilisation du gabarit en contexte réel.

Si le site venait à changer (une page par représentation), il pourrait être préférable d'utiliser un modèle long, par exemple inspiré de celui de la [Trousse TAI](https://github.com/a10s-ca/trousse-tai).

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

## À faire

- [ ] Peut-on trouver une façon de faire un lien entre l'oeuvre et l'agence ou l'agent?
- [ ] Adapter la clé `performer` si jamais on a des chorégraphes représentés par Person et pas Organization
