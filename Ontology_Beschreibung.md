## Ontology description 


| Web Ontology Language      | Bedeutung |Standard |
| ------------------| ----------- |----------- |
| owl:Class         | A group of individuals that belong together because they share some properties       | Class |
| owl:NamedIndividual| Instances of classes.      | Indiviual        |
| owl:ObjectProperty | Relations between pairs of individuals.  | Relation        |
| owl:DataProperty   | Relations between individuals and data values.   | Attribute        |
| rdfs:domain  | A domain of a property limits the individuals to which the property can be applied. 특정 ObjectProperty 또는 DatatypeProperty의 주어가 될 수 있는 클래스를 한정  | Domain        |
| rdfs:range   | The range of a property limits the individuals that the property may have as its value.   특정 ObjectProperty의 목적어가 될 수 있는 클래스를 한정 | Range        |

## Ontology

 - Class 

 | CLASS             | LABEL       |description | super class  | sub class|
 | ------------------| ----------- |----------- |-------------|--------- |
 | dioc:Place        | Place      |Immobile things or locations.| AdministrativeArea|
 | dioc:AdministrativeArea        | AdministrativeArea        |A geographical region, typically under the jurisdiction of a particular government.|jurisdiction|Place|
 | dioc:Jurisdiction | Jurisdiction |Indicates a legal jurisdiction, e.g. of some legislation, or where some government service is based.|religious administrative entity|AdministrativeArea|
 | dioc:Religious administrative entity | Religious administrative entity |entity with control over a religion or part of a religion.|Ecclesiastical_Region|Jurisdiction|
 | dioc:Ecclesiastical_Region|Ecclesiastical_Region |geographical group of dioceses, ecclesiastical provinces or parishes|Diocesis|Religious administrative entity|
 | dioc:Diocesis | Diocesis |Christian district or see under the supervision of a bishop|Metropolitan, Suffragan|Ecclesiastical_Region|
 | dioc:Archdiocese        | Archdiocese     |district or see under the supervision of a bishop, with more significance than a diocese| |Diocesis|
 | dioc:Suffragan          | Suffragan       |one of the dioceses other than the metropolitan archdiocese that constitute an ecclesiastical province| |Diocesis|
 | dioc:collegiata          | collegiata       |church where the daily office of worship is maintained by a college of canons| |Ecclesiastical_Region|
 | dioc:abbey          | abbey       |monastery or convent, under the authority of an abbot or an abbess| |Ecclesiastical_Region|
 | dioc:patriarchate          | patriarchate       |office or jurisdiction of a patriarch| |Ecclesiastical_Region|




| CLASS             | LABEL       |description | super class  | sub class|
 | ------------------| ----------- |----------- |-------------|--------- |
 | dioc:Change       | Change     |The Change concept is the super class of all types of change| FeatureChange|
 | dioc:FeatureChange       | FeatureChange     |The Change concept is the super class of all types of change| IdentificationChange|Change|
 | dioc:IdentificationChange        | IdentificationChange      |The IdentificationChange concept describes change(s) that modify the identifier, name, acronym and/or description attributs|Renomination|FeatureChange| 
 | dioc:Renomination       | Renomination     |diocese or metropolis changing name| |IdentificationChange|
 | dioc:arise       | Renomination     |dioceses resulting from the union of other dioceses | |IdentificationChange|
 | dioc:decay       | decay     |diocese or metropolis that continues to exist but is not active or is in an occupied territory | |IdentificationChange|



- Object property

| OBJECT PROPERTY   | LABEL       |DOMAIN  |RANGE  | 
| ------------------| ----------- |----------- |-------------|
| foaf:member 	    | member      |dioc:Diocesis| dioc:Ecclesiastical_Region|
| dcterms:type 	 	  | type        |dioc:Suffragan| dioc:Diocesis|
| dcterms:type 	 	  | type        |dioc:Archdiocese| dioc:Diocesis|
| owl:hasOfficialName 	| hasOfficialName     |dioc:name| dioc:Diocesis|


- Data property

| DATA PROPERTY     | LABEL       |DOMAIN | RANGE  | 
| ------------------| ----------- |----------- |---|
| dioc:name       | name     |dioc:change| xsd:string|
| dioc:date       | date     |dioc:change| xsd:integer|
