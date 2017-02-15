
[//]: # "purpose: demo file for version control" 
[//]: # "author : Luuk Dijkhuis" 

# GIT4OPS
## Waarom versiebeheer met een SCM tool

- single source of truth
- gestructureerde opslag en historie van wijzigingen
- PRECIES weten wat er is veranderd en altijd terug kunnen
- met meer dan 1 persoon aan dezelfde code werken
- hotfixes/bugfixes parallel aan onderhanden werk 
- "aanwijsbaar" maakt "testbaar en herhaalbaar" mogelijk

### Single source of truth
De Waarheid staat in de Repository, niet hier of daar op een directory.  
Misschien heeft wel iemand ergens werk onderhanden, maar zolang het niet in de repo staat is het niet De Waarheid
Ook de hele historie en het commentaar bij de historie staat in de repository, niet in een directory .old, .hist, .save of .20160408


### Gestructureerde opslag en historie van wijzigingen
Er is een vaste structuur, je gebruikt altijd dezelfde technische manier van opslaan (namelijk in je SCM tool).
Iedere wijziging wordt van een id voorzien, en de verschillen met de vorige variant wordt bijgehouden. Zo heb
je altijd een logboek van wat er is aangepast, wanneer, en door wie. Als je kleine wijzigingen incheckt
(microcommits) en je altijd betekenisvol commentaar toevoegt kun je precies zien wat de gedachtengang is geweest achter een
wijziging.

### PRECIES weten wat er is veranderd en altijd terug kunnen
Omdat iedere verandering gestructureerd wordt vastgelegd kun je ook altijd terugrollen naar een vorige samenstelling van de code.
Dat krijg je er allemaal gratis bij. Daar heb je het meest aan als je alle tussenstapjes die je maakt ook commit.

### Met meer dan 1 persoon aan dezelfde code werken
Doordat de tool bijhoudt wie wat het laatst heeft ingechecked, en checkt of er verschillen en conflicten zijn kun je met meerdere
personen aan dezelfde code werken zonder dat je elkaars werk zomaar overschrijft. De wijzigingen van beide bijdragers 
kunnen worden gemerged, en als er een conflict is word je daar op gewezen zodat je heel gecontroleerd de correcte situatie kunt bepalen.

### afhankelijkheden beheren met versies van andere code


### hotfixes/bugfixes parallel aan onderhanden werk 
Doordat je controle hebt over alle microstappen in de ontwikkeling vand de code kun je heel precies bijhouden  welke versie je in productie hebt staan. Je kunt dan precies verschil maken tussen wat je aan het doorontwikkelen bent en op welke versie je een eventuele productie-hotfix moet  uitrollen. Ook alle afhankelijke data testcases en -scripts passen precies op die versie, dus je kunt altijd met een consistente samenhangende set software en configuratie aan het werk.

### "aanwijsbaar" maakt "testbaar en herhaalbaar" mogelijk
Als je niet weet over welke code je het precies hebt, dan kun je op je buik schrijven dat je precies weet wat het in productie gaat doen.



