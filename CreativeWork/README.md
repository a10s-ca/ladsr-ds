# Gabarit _CreativeWork_

Le gabarit _CreativeWork_ est utilisé pour représenter les oeuvres choréographiques.

## Propriété _creator_

Si une oeuvre est liées à une compagnie, elle aura deux `creator` :
- la compagnie
- le chorégraphe

Si une oeuvre est liée à un chorégraphe idépendant, elle aura un seul `creator`, le chorégraphe.

## Propriété _subjectOf_

La propriété ``subjectOf`` présentée dans le gabarit est vide. Il faudra y insérer une liste des représentations associées à l'oeuvre choréographique, en utilisant le modèle _DanceEvent_.

## Précisions

### _abstract_ vs _description_

Il est généralement conseillé que la propriété ``description`` soit brève. Certaines sources suggèrent de rester en dessous de 500 caractères, d'autres en dessous de 160.

La propriété ``abstract`` peut quant à elle contenir le synopsis complet de l'oeuvre.

En l'absence d'une description plus brève à inclure dans ``description`` on peut simplement mettre le même synopsis dans les deux propriétés.

## videoObject

Dans le cadre de ce projet, nous avons mis le type `videoObject` à l'intérieur du type `creativeWork`. Lors des mesures d'impact, nous vérifierons si Google en fera des cartes enrichies de type vidéo quand même. Si ce n'est pas le cas, il faudra modifier le modèle pour avoir 2 modèles séparés sur la même page, un pour le `videoObject` et un pour le `creativeWork`.

### Propriété _description_

Il s'agit ici de présenter le vidéo, et non pas l'œuvre. Toutefois, si aucune description du vidéo n'est disponible, la description de l'oeuvre peut être utilisée à la place.
