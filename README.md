# Gabarits de données structurées de La danse sur les routes du Québec


Ce dépôt contient les gabarits de données structurées utilisés par le [site web de La danse sur les routes du Québec](https://ladansesurlesroutes.com/).

Il s'agit de gabarits de données structurées au format [JSON-LD](https://json-ld.org/) s'appuyant sur le vocabulaire [Schema.org](https://schema.org/).

## Contenu

Les gabarits contiennent :

* le contenu exigé par Google dans sa [documentation sur les données structurées](https://developers.google.com/search/docs/guides/intro-structured-data?hl=fr), lorsque cela s'applique
* des clés supplémentaires, conformes au vocabulaire [Schema.org](https://schema.org/), correspondant à des suggestions d'ajouts pour mieux décrire les objets concernés.

Ces gabarits ont été construits dans le contexte du site de La danse sur les routes du Québec. Bien qu'ils comportent des références à des données qui ne sont pas disponibles sur ce site, ils sont dans l'ensemble adapté à sa structure et ses contraintes. Il faut donc faire preuve de discernement pour les utiliser dans un autre contexte.

Par ailleurs, dans cet esprit, les différentes notes du présent document, et les notes accompagnant les gabarits, font parfois référence à des spécificités de l'architecture et de la technologie du site de La danse sur les routes. Encore une fois, le lecteur est invité à adapter la documentation et les gabarits à son propre contexte.


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

La syntaxe JSON-LD/Schema.org permet d'indiquer un objet, plutôt qu'un tableau d'objets, pour les clés où le tableau contient un seul item. Pour faciliter la lecture, les gabarits présentent toujours des tableaux lorsqu'il est possible d'inclure plusieurs valeurs pour une clé.

Donc, même si le passage suivant est valide:

```
"sameAs": "https://www.facebook.com/ladansesurlesroutes"
```

Le gabarit sera plutôt présenté comme ceci, pour clarifier le fait qu'il est possible d'inclure plusieurs valeurs à la clé `sameAs`:

```
"sameAs": ["https://www.facebook.com/ladansesurlesroutes"]
```

### Identifiants

Les identifiants utilisés pour les clés `@id` de différents gabarits peuvent être de n'importe quel format.

Toutefois, pour rendre les choses simple et respecter une convention souvent utilisée dans les données structurées et liées, nous suggérons d'utiliser dans la mesure du possible une URI identique à l'URL comme identifiant, en ajoutant un _anchor_ au besoin.

Ainsi, comme les oeuvres, les compagnies et les chorégraphes disposent chacun d'une URL unique, le `@id` pourrait être l'URL en question.

Pour les représentations, qui ne disposent pas d'une URL unique, le `@id` pourrait être l'URL de l'oeuvre, suivi d'un _anchor_ correspondant à la représentation, par exemple par son numéro d'enregistrement Airtable.

D'un modèle à l'autre, les `@id` doivent être cohérents, c'est à dire que si une URI est utilisée comme `@id` sur la page d'un chorégraphe, c'est cette même URI qui doit être utilisée lorsque le chorégraphe est mentionné comme `creator` dans `creativeWork` ou comme `director` dans `Event`.

### ISNI, VIAF et autres identifiants

L'ajout d'identifiants externes est facultatif mais recommandé.

## Accès aux gabarits

* [Organization](/Organization), pour les organisations (diffuseurs, agences, compagnies de danse)
* [Person](/Person), pour les chorégraphes indépendants
* [CreativeWork](/CreativeWork), pour les oeuvres chorégraphiques
* [Event](/Event), pour les représentations
