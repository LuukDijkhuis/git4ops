#git4ops
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
   
## een nieuwe repository aanmaken of een bestaande gebruiken: init en clone
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

@@@ AANMAKEN en voeg een README.txt toe @@@

Je hebt een kopie van de trainings repo lokaal staan: Nu kun je aan het werk.


## hoe staan we er voor: status
Je kunt nu files aanmaken op je lokale repo directory. Met ``` git status ``` kun je kijken in welke toestand die files zich bevinden. Kent git de file al of niet, heb je iets veranderd waar git nog niet van weet etc. 
> VOER UIT:

``` git status ```

Je ziet nu:

``` 
On branch master
nothing to commit, working directory clean
```
Wat staat er in:  (dir of ls)

```
/dev/work/git4opstraining(master)$ ls
README.txt
```

Maak nu een file aan met iets er in. Bijvoorbeeld ``` echo 'Hello world!' >> hithere.txt ``` 

Nog een keer ``` git status ```   en je ziet:

``` On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)

	hithere.txt

nothing added to commit but untracked files present (use "git add" to track)

```
De uitleg spreekt voor zich: we zien een file in de repo directory staan die git nog niet kent. Verder een aantal tips voor wat je nu kunt doen. 

## uitleg: de staging area
Even een uitstapje naar wat er nu gebeurt. 
## klaarzetten: add en rm
## tussenstand bewaren: commit en commitmessage
## voor jezelf of ook voor anderen: remote
## publiceren: push
## werk van anderen ophalen: fetch, merge, pull
## uitleg: conflicten
## even parallel iets repareren: branch en merge
## ehbo: oh shit, git

