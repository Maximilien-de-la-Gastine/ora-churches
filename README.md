# ora-churches

Lieux de culte chrétiens hors de France, découpés par zone, pour la carte de l'application ORA.
Les églises de France sont dans la base de l'application, pas ici.

- `index.json` : liste des zones qui contiennent au moins une église (`deg` = taille d'une zone en degrés).
- `t/<lat>_<lng>.json.gz` : églises d'une zone (indices = `floor(coordonnée / deg)`), tableau JSON compressé en gzip ;
  chaque ligne : `[osm_id, nom, lat, lng, ville, confession, wikidata, wikipedia, image, site, horaires_ouverture, horaires_offices]`.

Servi par jsDelivr : `https://cdn.jsdelivr.net/gh/Maximilien-de-la-Gastine/ora-churches@main/index.json`

Régénération : `python -I tool/build_church_tiles.py <ce dossier>` depuis le dépôt de l'application, puis commit, push
et purge de `https://purge.jsdelivr.net/gh/Maximilien-de-la-Gastine/ora-churches@main/index.json`.

## Licence

Données © les contributeurs d'OpenStreetMap, disponibles sous licence
[Open Database License (ODbL) 1.0](https://opendatacommons.org/licenses/odbl/1-0/).
Voir https://www.openstreetmap.org/copyright
