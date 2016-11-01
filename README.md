#Dynamique des connaissances
*Raisonnement dans le web sémantique*


## Conception du graphe de connaissances
Au départ, nos obels sont à plat. Nous allons leur donner la structure suivante :

![schema](OWL_minetrace.png)

Voici le code pour mettre en place un tel schéma :

```SPARQL
-- PickupItem and DropItem are ItemObsel

PREFIX db: <https://liris-ktbs01.insa-lyon.fr:8000/public/master-ia-2016/zguyl/model1#>
PREFIX w3: <http://www.w3.org/2000/01/rdf-schema#>

INSERT DATA {
  db:PickupItem w3:subClassOf db:ItemObsel .
}

INSERT DATA {
db:DropItem
w3:subClassOf
db:ItemObsel . }


-- PickupBlock and DropBlock are BlockObsel
INSERT DATA {
db:DropBlock
w3:subClassOf
db:BlockObsel . }


INSERT DATA {
db:PickupBlock
w3:subClassOf
db:BlockObsel . }


-- ItemObsel and BlockObsel are ObjectObsel
INSERT DATA {
db:BlockObsel
w3:subClassOf
db:ObjectObsel . }


INSERT DATA {
db:ItemObsel
w3:subClassOf
db:ObjectObsel . }


-- PlayerJoin, PlayerKick and PlayerQuit are NetworkObsel
INSERT DATA {
db:PlayerJoin
w3:subClassOf
db:NetworkObsel . }


INSERT DATA {
db:PlayerQuit
w3:subClassOf
db:NetworkObsel . }


INSERT DATA {
db:PlayerKick
w3:subClassOf
db:NetworkObsel . }


-- NetworkObsel, PlayerDamage and PlayerDeath are PlayerObsel
INSERT DATA {
db:NetworkObsel
w3:subClassOf
db:PlayerObsel . }


INSERT DATA {
db:PlayerDamage
w3:subClassOf
db:PlayerObsel . }


INSERT DATA {
db:PlayerDeath
w3:subClassOf
db:PlayerObsel . }


-- PlayerObsel, ObjectObsel and Craft are MinecraftObsel
INSERT DATA {
db:PlayerObsel
w3:subClassOf
db:MinecraftObsel . }


INSERT DATA {
db:ObjectObsel
w3:subClassOf
db:MinecraftObsel . }


INSERT DATA {
db:Craft
w3:subClassOf
db:MinecraftObsel . }


-- MinecraftObsel is ObselType
INSERT DATA {
db:MinecraftObsel
w3:subClassOf
db:ObselType . }


-- Properties
INSERT DATA {
db:ObselType
w3:property
db:end . }


INSERT DATA {
db:ObselType
w3:property
db:begin . }


INSERT DATA {
db:ObselType
w3:property
db:@id . }


INSERT DATA {
db:ObselType
w3:property
db:playerName . }


INSERT DATA {
db:ObjectObsel
w3:property
db:data . }


INSERT DATA {
db:BlockObsel
w3:property
db:blockName . }


INSERT DATA {
db:ItemObsel
w3:property
db:itemName . }


INSERT DATA {
db:MinecraftObsel
w3:property
db:x . }


INSERT DATA {
db:MinecraftObsel
w3:property
db:y . }


INSERT DATA {
db:MinecraftObsel
w3:property
db:z . }


INSERT DATA {
db:MinecraftObsel
w3:property
db:playerName . }





```
