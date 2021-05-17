# Gabarit _CreativeWork_

Le gabarit _CreativeWork_ est utilisé pour représenter les oeuvres choréographiques.

### Propriété _creator_

Si une oeuvre est liées à une compagnie, elle aura deux `creator` :
- la compagnie
- le chorégraphe

Si une oeuvre est liée à un chorégraphe idépendant, elle aura un seul `creator`, le chorégraphe.

### Propriété _subjectOf_

La propriété ``subjectOf`` présentée dans le gabarit est vide. Il faudra y insérer une liste des représentations associées à l'oeuvre choréographique, en utilisant le modèle _DanceEvent_.

### _abstract_ vs _description_

Il est généralement conseillé que la propriété ``description`` soit brève. 

### videoObject

\[nous avons mis le `videoObject` à l'intérieur du `creativeWork`, il faudra vérifier si Google en fera des cartes enrichies de type vidéo quand même. Si ce n'est pas le cas, il faudra modifier le modèle pour avoir 2 modèles séparés sur la même page, un pour le `videoObject` et un pour le `creativeWork`.]
