# Gabarits de données structurées de La danse sur les routes du Québec


Ce dépôt contient les gabarits de données structurées utilisés par le [site web de La danse sur les routes du Québec](https://ladansesurlesroutes.com/).

Il s'agit de gabarits de données structurées au format [JSON-LD](https://json-ld.org/) s'appuyant sur le vocabulaire [Schema.org](https://schema.org/).

## Contenu

Les gabarits contiennent :

* le contenu exigé par Google dans sa [documentation sur les données structurées](https://developers.google.com/search/docs/guides/intro-structured-data?hl=fr), lorsque cela s'applique
* des clés supplémentaires, conformes au vocabulaire [Schema.org](https://schema.org/), correspondant à des suggestions d'ajouts pour mieux décrire les objets concernés.


## Conventions

### Identification des valeurs à modifier dans le gabarit

Les gabarits sont rendus disponibles sous forme de fichier contenant des données au format JSON-LD.

Pour faciliter leur compréhension, des notes ou des explications ont été incluses comme valeur pour certaines clés. Lorsque c'est le cas, elles ont été placées entre crochets doubles (`{{}}`). Par exemple:

```
"url": "{{url complète vers la page web concernée}}"
```

Une fois le gabarit utilisé et rempli avec des données, il ne devrait plus contenir de crochets doubles. Par exemple:

```
"url": "https://ladansesurlesroutes.com/"
```

### Utilisation des tableaux

La syntaxe JSON-LD/Schema.org permet d'indiquer un object, plutôt qu'un tableau d'objets, pour les clés où le tableau contient un seul item. Pour faciliter la lecture, les gabarits présentent toujours des tableaux lorsqu'il est possible d'inclure plusieurs valeurs pour une clé.

Donc, même si le passage suivant est valide:

```
"sameAs": "https://www.facebook.com/ladansesurlesroutes"
```

Le gabarit sera plutôt présenté comme ceci, pour clarifier le fait qu'il est possible d'inclure plusieurs valeurs à la clé `sameAs`:

```
"sameAs": ["https://www.facebook.com/ladansesurlesroutes"]
```


## Accès aux gabarits

* [Organization](/Organization), pour les organisations (diffuseurs, agences, compagnies)
* DanceEvent, pour les spectacles (à venir)
* CreativeWork, pour les oeuvres chorégraphiques (à venir)
