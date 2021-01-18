## Ontology description

The ontology  aims at describing changes that occured from administrative territories of catholic dioceses and their changes overtime (i.e., partition of the territory) and its subsequent (change in territorial units boundaries to reflect an administrative reorganisation).



| Web Ontology Language      | Bedeutung |Standard |
| ------------------| ----------- |----------- |
| owl:Class         | A group of individuals that belong together because they share some properties       | Class |
| owl:NamedIndividual| Instances of classes.      | Indiviual        |
| owl:ObjectProperty | Relations between pairs of individuals.  | Relation        |
| owl:DataProperty   | Relations between individuals and data values.   | Attribute        |
| rdfs:domain  | A domain of a property limits the individuals to which the property can be applied. | Domain        |
| rdfs:range   | The range of a property limits the individuals that the property may have as its value. | Range        |

## Ontology

 - Class 1) Religious administrative Unit

 | CLASS             | LABEL       |description | super class  | sub class|
 | ------------------| ----------- |----------- |-------------|--------- |
 | dioc:Place        | Place      |Immobile things or locations.| AdministrativeArea|
 | dioc:AdministrativeArea        | AdministrativeArea        |A geographical region, typically under the jurisdiction of a particular government.|jurisdiction|Place|
 | dioc:Jurisdiction | Jurisdiction |Indicates a legal jurisdiction, e.g. of some legislation, or where some government service is based.|ReligiousAdministrativeEntity|AdministrativeArea|
 | dioc:ReligiousAdministrativeEntity | ReligiousAdministrativeEntity |entity with control over a religion or part of a religion.|Arcieparchia, Abbey, Collegiata, Prepositura, Prelate, Plebania, Ecclesiastical_Province|Jurisdiction|
 | dioc:Ecclesiastical_Province|Ecclesiastical_Province |Geographical group of dioceses, ecclesiastical provinces or parishes|Diocesis|ReligiousAdministrativeEntity|
 | dioc:Diocese | Diocese |Christian district or see under the supervision of a bishop|Metropolitan, Suffragan, Archdiocese|Ecclesiastical_Region|
 | dioc:Archdiocese        | Archdiocese     |District or see under the supervision of a bishop, with more significance than a diocese| |Diocese|
 | dioc:Suffragan          | Suffragan       |One of the dioceses other than the metropolitan archdiocese that constitute an ecclesiastical province| |Diocese|
 | dioc:Collegiata          | Collegiata       |Church where the daily office of worship is maintained by a college of canons| |ReligiousAdministrativeEntity|
 | dioc:Abbey          | Abbey       |Monastery or convent, under the authority of an abbot or an abbess| |ReligiousAdministrativeEntity|
 | dioc:Prepositure          | prepositure       |The office or dignity of a provost; a provostship| |ReligiousAdministrativeEntity|
 | dioc:Arcieparchia          | Arcieparchia       | A diocese of the Eastern Christian Church| |ReligiousAdministrativeEntity|
 | dioc:Prelate          | Prelate       |High-ranking member of the clergy| |ReligiousAdministrativeEntity|
 | dioc:Plebania          | Plebania       || |ReligiousAdministrativeEntity|
 | dioc: Apostolic see          | Apostolic see       |	Episcopal see whose foundation is attributed to one or more of the apostles of Jesus or to one of their close associates|  |Ecclesiastical_Region|
 | dioc: Holy See         | Holy See      |	Episcopal jurisdiction of the Catholic Church in Rome, Italy| |Ecclesiastical_Region|




 - Class 2) TerritoryChange


 | CLASS             | LABEL       |description | super class  | sub class|
 | ------------------| ----------- |----------- |-------------|--------- |
 | dioc:Change       | Change     |The Change concept is the super class of all types of change| FeatureChange|
 | dioc:FeatureChange       | FeatureChange     |The FeatureChange concept describes one or a set of changes that occur simultaneously and affect resource | HierarchyChange|Change|
 | dioc:HierarchyChange        | HierarchyChange      |The HierarchyChange concept describes modification of the position of administrative entity| UnitHierarchyChange |FeatureChange|
 | dioc:TerritoryChange        | TerritoryChange      |The TerritoryChange concept describes modification of the Territory of Feature | Expansion, Reshaping, Contraction, Reduction |FeatureChange|
 | dioc:StatusChange        | StatusChange      |The StatusChange concept describes change(s) that modify the territorial status|Appearance, Inactiv, Reactive|FeatureChange|
 | dioc:UnitHierarchyChange        | UnitHierarchyChange      |The UnitHierarchyChange concept describes changes that affect Features that are of type administrative entity . It describes changes of the Unit position within the hierarchy | |HierarchyChange|
 | dioc:Appearance        | Appearance      |The Appearance concept describes the appearance (or creation) of a new Feature | |StatusChange|
 | dioc:Inactive       | Inactive     |The Disappearance concept describes the disappearance (or end) of a Feature that comes as an input resource to the change event | |StatusChange|
 | dioc:Reactive       | Reactive     |diocese or metropolis that continues to exist but is not active or is in an occupied territory | |StatusChange|
 | dioc:Expansion       | Expansion     |Expansion of a territoryfeature, in terms of shape, means its size increase between the input territory and the output territory.  | |TerritoryChange|
 | dioc:Reshaping       | Reshaping     |Reshaping describes modification without size change between the input territory and the output territory.  | |TerritoryChange|
 | dioc:Contraction       | Contraction     |Contraction of a Feature, in terms of shape, means its size decrease between the input territory and the output territory. | |TerritoryChange|
 | dioc:Fusion       | Fusion     |The Fusion concept describes the merge of two or more territory Features into a single new territory Feature| |TerritoryChange|


- Object property

| OBJECT PROPERTY   | LABEL       |DOMAIN  |RANGE  |
| ------------------| ----------- |----------- |-------------|
| governedBy  	 	  | governedBy         |dioc:Holy See| dioc:ReligiousAdministrativeEntity|
| governedBy  	 	  | governedBy         |dioc:Diocese| dioc:Ecclesiastical_Province|
| was_affected_by	 	  | was_affected_by        |dioc:ReligiousAdministrativeEntity| dioc:UnitHierarchyChange |
| renomination 	 	  | renomination        |dioc:ReligiousAdministrativeEntity| dioc:Name|
| owl:was_erected_by 	| was_erected_by     |dioc:ReligiousAdministrativeEntity| dioc:Appearance |
| owl:was_decay_by 	| was_decay_by     |dioc:ReligiousAdministrativeEntity| dioc:Inactive|
| owl:was_reinstated_by 	| was_reinstated_by     |dioc:ReligiousAdministrativeEntity| dioc:Reactive|
| owl:was_incorporated 	| was_incorporated     |dioc:ReligiousAdministrativeEntity| dioc:Expansion|
| owl:was_modificated 	| was_modificated     |dioc:ReligiousAdministrativeEntity| dioc:Reshaping|
| owl:was_united 	| was_united     |dioc:ReligiousAdministrativeEntity| dioc:Fusion|
| owl:was_lost 	| was_lost     |dioc:ReligiousAdministrativeEntity| dioc:Reduction|
| owl:has prefered identifier 	| has prefered identifier     |dioc:Place|dioc:Identifier|
| owl:hasCoordinate 	| hasCoordinate     |dioc:Place|dioc:GeoCoordinates|


- Data property

| DATA PROPERTY     | LABEL       |DOMAIN | RANGE  |
| ------------------| ----------- |----------- |---|
| dioc:HasOfficialName       | HasOfficialName     |dioc:Place| xsd:string|
| dioc:HasAliasName       | HasAliasName     |dioc:Place| xsd:string|
| dioc:longitude	       | longitude	     |dioc:dioc:Place| xsd:float|
| dioc:laitude	       | laitude	     |dioc:dioc:Place| xsd:float|
| dioc:has_note	       | has_note	     |dioc:Identifier| xsd:string|
| dioc:HasLabelBefore	       | HasLabelBefore	     |dioc:UnitHierarchyChange | rdfs:Literal|
| dioc:HasLabelAfter	       | HasLabelAfter	     |dioc:UnitHierarchyChange| rdfs:Literal|
| dioc:has_date	       | has_date	     |dioc:Change| xsd:date|
| dioc:before_name	       | before_name	     |dioc:Name| xsd:string|
| dioc:after_name	       | after_name	     |dioc:Name| xsd:string|
