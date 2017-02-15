#onderwerpen
## wat is git
git is een tool die je tegen jezelf en tegen anderen beschermt. Je kunt je scripts veranderen, stukmaken, verbeteren, wat je maar wilt. En je kunt altijd weer terug omdat je steeds tussentijds elke toestand opslaat. Met git kun je zonder zorgen met meerdere mensen tegelijk aan code werken. Maar het helpt je ook in je eentje. Het is een vangnet tegen vergissingen, daardoor ga je makkelijker mooie dingen proberen: het kan toch geen kwaad, tot je het publiceert.

Git beschermt je tegen chaos door je creatie proces in veilige stappen te verdelen. Elke stap krijgt een label dat uniek is over de hele codebase heen.

## install, identificatie
Na installatie (kies zelf eentje) moet je jezelf bekend maken als user.

>VOER UIT:

```
$ git config --global user.name "John Doe"
$ git config --global user.email johndoe@example.com
```
> voer deze commando's uit in je eigen omgeving. Gebruik je UMCG email adres, dan kun je straks vanzelf bij de echte omgeving.

Met git config kun je nog veel meer dingen regelen, zoals allerlei default gedrag, je standaard editor, je diff tool etc. Dat laten we nu even voor wat het is.
   
## een nieuwe repository aanmaken of een bestaande gebruiken 
### een nieuwe repo aanmaken
Git organiseert alles van een product/project in een "repository". Je kunt een nieuwe aanmaken, of meegaan op een al bestaande voor dat product.
Laten we een nieuwe aanmaken: git init (van "initialize")

``` 
git init 
```
> dit maakt van je current directory een git repository

```
git init directorynaam
```
> maakt een directory aan en maakt daar een git repo van 

### een bestaande repo gebruiken
Als er al een repository bestaat voor dit product kun je er mee gaan werken door ``` git clone reponaam ```
Je krijgt dan de hele inhoud van de repo naar je toegestuurd, inclusief alle status en historie. 

>VOER UIT:

``` git clone https://dinges/danges/git4opstraining ```

Je hebt nu een kopie van de trainings repo lokaal. Nu kun je aan het werk.



## status
## de staging area
## add en rm
## commit en commitmessage
## remote
## push
## fetch, merge, pull
## conflicten
## branch en merge
## cherrypicking
## oh shit, git

