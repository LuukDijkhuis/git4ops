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

Maak nu een file aan met iets er in.  
>VOER UIT:

``` echo 'Hello world!' >> hithere_your-name.txt ``` (dus met jouw naam ingevuld)

Nog een keer ``` git status ```   en je ziet:

``` On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)

	hithere_your-name.txt

nothing added to commit but untracked files present (use "git add" to track)

```
De uitleg spreekt voor zich: we zien een file in de repo directory staan die git nog niet kent. Verder een aantal tips voor wat je nu kunt doen. 

## uitleg: de staging area
Even een uitstapje naar wat er nu gebeurt. (whiteboard)

bouwen, testen, klaarzetten en tussenstand bewaren, cyclus, samenhangend brokje af: publiceren.

@@@ PLAATJE @@@


## klaarzetten: add
We willen niet alleen die file toevoegen, we willen ook iets aan de README.txt veranderen. 
>VOER UIT:

Voeg een willekeurige tekst toe aan de README.txt

```git status```

Goed, we zijn even tevreden met wat we gedaan hebben en willen een tussenstand bewaren. Nu hebben we twee heel verschillende dingen gedaan, en dat willen we eigenlijk onthouden. Dus gaan we die twee dingen apart als actie in de tussenstand zetten.

>VOER UIT:

``` git add hithere_your-name.txt ```

Wat je daarmee doet is: "ik voeg aan de tussenstand-bewaar-actie dit bestand toe, want die hoort bij de verandering die ik gedaan heb". Die README.txt actie deed je om een heel andere reden, dus die doen we straks. 

## tussenstand bewaren: commit en commitmessage
Je hebt nu klaargezet wat je wilt bewaren, dus daar gaan we dan:

>VOER UIT:

``` git commit -m "Adds hello world message" ```

Met git commit stuur je het setje changes dat je met git add had toegevoegd naar de staging area (zie plaatje). 
> Een correcte commit message (``` -m "commit message" ``` ) is echt SU-PERbelangrijk. Je kunt daarmee, samen met het selectieve klaarzetten voor commit (```git add```), later in de log precies terugzien wat de reden was van deze verandering en welke files daarvoor geraakt zijn. Iets waar je heel blij mee zult zijn zodra je het nodig hebt. En je gaat het nodig hebben :-)

<br/>
> VOER UIT:

```git status```

O ja, we waren nog niet klaar, we hadden nog iets veranderd. 
>VOER UIT:

```
git commit -a -m "adds remark to the README for educational purposes"
git status
```

>De -a flag voegt in één klap alle nog openstaande wijzigingen toe aan de commit. >Wees daar voorzichtig mee, maar het is wel heel handig als je een heleboel files hebt geraakt voor één logische wijziging, dan hoef je ze niet allemaal per stuk toe te voegen, waardoor je minder makkelijk eentje vergeet. 

>Het is conventie om code comments en git commit comments in het Engels te schrijven, zodat iedereen later kan lezen wat er aan de hand is. Als je het heel netjes wilt doen (en dat willen we) dan schrijf je in de derde persoon: [this change] "adds remark to" of als imperatief "add remark to" etc. Je ziet beide in de praktijk. Kies als team één stijl.

Je ziet dat alles nu "schoon" is: de huidige status van je werkdirectory is gelijk aan de staging area. 

>VOER UIT:<br/>
>maak een aantal wijzigingen in je omgeving. Voeg files toe, edit wat in die files. Vervang een woord, wissel woorden om etc. Add en commit steeds tussendoor met een **betekenisvolle** commitmessage, zodat je straks een setje commits hebt om doorheen te bladeren. 

## wat is er allemaal gebeurd: git log
>VOER UIT:

``` git log ```

Je ziet nu al je commits langskomen. ```git log``` heeft een heel rijke syntax waarmee je de meest uitgebreide manieren krijgt om de historie te bekijken. 

In de output zie je de naam van de commit ("hash"), de auteur, datum en tijd, en de (eerste regel van de) commit message. Die info is belangrijk voor het geval dat je vergissingen wilt herstellen. Je kunt dan met de naam van de commit precies de staat van de codebase aanwijzen op een bepaald moment. Al deze "vlaggetjes" worden gedeeld met iedereen die aan de codebase werkt.


>VOER UIT:

``` git help log ```

Je ziet, heel veel opties om de log vorm te geven.
Probeer een paar log opties, bijvoorbeeld ```git log --pretty=oneline``` of 
```git log --pretty=format:"%h %ar [%an] - %s"```


## wat is er veranderd in een commit: git diff
>VOER UIT:

```
git status	
git log
```

Als je nog uncommitted changes hebt: ```git diff``` om de verschillen met de huidige kop van de index te zien.

Anders:
Kijk naar de output van ```git log```
Kies een commit uit. Voer uit ```git diff [commit-hash]```
>Je hoeft niet de hele hash in te kloppen, de eerste 7 tekens zijn al uniek genoeg

Wat je ziet is het verschil van je huidige staat met de gekozen commit. Je kunt ook twee commits met elkaar vergelijken ```git diff [hash1] [hash2]```

Ook bij ```diff```: veel opties. Default laat diff van vrij grote blokken de verschillen zien, dat is niet per se overzichtelijk. Met ```diff -w``` negeer je whitespace (pas op met python scripts! :-)) en met ```diff --word-diff``` toon je de verschillen binnen het tekstblok. Probeer maar

>Voer uit:
>
``` git diff -w --word-diff [commit2] [commit1] ```

Speel wat met andere diff opties.


## alleen voor jezelf of ook voor anderen: remote
UITLEG: Whiteboard!
remote, origin, master

!["git remote add origin"](./git_remote.png)

## werk van anderen ophalen: fetch, merge, pull
Vóór je gaat publiceren naar remote haal je eerst de huidige stand van zaken op. Het kan immers zijn dat anderen wijzigingen hebben aangebracht in files waar jij ook net mee bezig was. Als die veranderingen op andere plekken in het bestand zitten dan worden die veranderingen in elkaar geschoven: dat heet een "merge". De bijbehorende (automatische) tests worden natuurlijk ook mee ge-update dus als je na het in elkaar schuiven van de nieuwe situatie je tests weer runt zou alles moeten werken. Mochten die wijzigingen elkaar negatief beïnvloeden dan heb je nu tijd om dat na te gaan en lokaal te repareren.



 


## publiceren: push
Als je een aantal commits hebt verzameld die samen een logisch samenhangend brokje functionaliteit vormen dan kun je publiceren wat je hebt gemaakt. Hoe groot dat brokje is hangt van de context af, bij een bugfix is het soms maar één character :-) In het algemeen is de richtlijn: mik op KLEINE brokjes, oftewel: wacht niet te lang met publiceren. Hoe eerder de integratie, hoe kleiner de kans op uit elkaar lopen van versies.

Git beschermt de repo tegen het blindelings opsturen van een toestand die niet is gemerged.

>Voer uit:

```git push```


## uitleg: conflicten
## een stukje ontwikkeling tijdelijk isoleren: branch
## even tussendoor iets repareren: stash
## ehbo: oh shit, git

