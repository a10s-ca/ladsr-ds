# Gabarit _CreativeWork_

Le gabarit _CreativeWork_ est utilisé pour représenter les oeuvres choréographiques.

### `creator`

Si une oeuvre est liées à une compagnie, elle aura deux `creator` :
- la compagnie
- le chorégraphe

Si une oeuvre est liée à un chorégraphe idépendant, elle aura une seul `creator`, le chorégraphe.

### `abstract` vs `description`

\[...]

### videoObject

\[nous avons mis le `videoObject` à l'intérieur du `creativeWork`, il faudra vérifier si Google en fera des cartes enrichies de type vidéo quand même. Si ce n'est pas le cas, il faudra modifier le modèle pour avoir 2 modèles séparés sur la même page, un pour le `videoObject` et un pour le `creativeWork`.]

## À faire
- [ ] 

## Interrogations
- [ ] L'organisation devrait-elle aller dans @creator ou dans @producer ? sous-question: devrait-on toujours mettre le chorégraphe dans @creator ou devrait-on le mettre dans contributor quand on mets l'organisation dans @creator ?
- [ ] Est-ce que les Event seront toujours dans les modèles CreativeWork ? si oui, on ne serait pas mieux d'enlever ce gabarit complètement ?
