# Gabarit _DanceEvent_

Le gabarit _DanceEvent_ est utilisé pour les représentations des oeuvres. Il s'agit d'une sous-classe de _Event_, le type générique pour les événements dans Schema.org.

[Voir le gabarit](dance_event.json)


## Notes sur l'utilisation

### Version courte

Typiquement, il serait préférable d'avoir une page web dédiée à chaque représentation, et donc un seul _DanceEvent_ par page. Cela n'est toutefois pas le cas sur le site de la DSR. Les objets _DanceEvent_ ne seront donc pas utilisés seuls, mais dans le contexte d'un [CreativeWork](../CreativeWork). Pour cette raison, on choisit d'utiliser un modèle court, qui ne reprend que les informations essentielles de la représentation:

* le modèle court ne contient donc pas d'information relative à l'oeuvre, parce que la représentation y est associée
* le modèle court ne contient même pas de lien vers l'oeuvre à travers la propriété `workPerformed`, parce qu'on prend pour hypothèse que le _DanceEvent_ sera intégré dans la description de l'oeuvre à travers sa clé `subjectOf`

Si le site venait à changer (une page par représentation), il pourrait être préférable d'utiliser un modèle long, par exemple inspiré de celui de la [Trousse TAI](https://github.com/a10s-ca/trousse-tai). Il serait également nécessaire d'utiliser la clé `workPerformed` pour créer un lien vers l'oeuvre.

### Propriété Location

Dans le gabarit, la propriété `location` utilisée représente un lieu physique, donc pour un spectacle en présentiel. Dans le cas d'un événement virtuel, la propriété `location` pourrait prendre la forme suivante:

```
"location": {
  "@type": "VirtualLocation",
  "url": "{{URL pour accéder à la représentation virtuelle}}"
}
```
