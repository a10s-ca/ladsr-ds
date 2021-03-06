# Gabarit _CreativeWork_

Le gabarit _CreativeWork_ est utilisé pour représenter les oeuvres choréographiques.

[Voir le gabarit](creative_work.json)

## Notes

Les usages de _CreativeWork_ sont encore rares et il n'existe pas de pratiques généralement répandues. Nous proposons donc une sélection de propriétés inspirées des données disponibles dans le site de la DSR. Le lecteur est invité à l'adapter selon son contexte.

## Propriété _creator_

Si une oeuvre est liées à une compagnie, elle aura deux `creator` :
- la compagnie
- le chorégraphe

Si une oeuvre est liée à un chorégraphe indépendant, elle aura un seul `creator`, le chorégraphe.

## Propriété _subjectOf_

La propriété ``subjectOf`` présentée dans le gabarit est vide. Il faudra y insérer une liste des représentations associées à l'oeuvre choréographique, en utilisant le modèle _Event_.

## Précisions

### _abstract_ vs _description_

Il est généralement conseillé que la propriété ``description`` soit brève. Certaines sources suggèrent de rester en dessous de 500 caractères, d'autres en dessous de 160.

La propriété ``abstract`` peut quant à elle contenir le synopsis complet de l'oeuvre.

En l'absence d'une description plus brève à inclure dans ``description`` on peut simplement mettre le même synopsis dans les deux propriétés.

## videoObject

Dans le cadre de ce projet, nous avons mis le type `videoObject` à l'intérieur du type `creativeWork`. Nos observations suite à l'indexation par Google de nos pages démontrent que ce moteur de recherche est en mesure d'identifier les vidéos dans ce contexte. Il n'apparaît donc pas nécessairement d'inclure un objet distinct pour la vidéo.

### Propriété _description_

Il s'agit ici de présenter la vidéo, et non pas l'œuvre. Toutefois, si aucune description du vidéo n'est disponible, la description de l'oeuvre peut être utilisée à la place.
