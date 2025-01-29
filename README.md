# Ontwikkelomgeving Setup Guide

Deze handleiding helpt je bij het opzetten van je ontwikkelomgeving voor webontwikkeling. We behandelen de installatie en configuratie van Docker, Git en GitHub.

## Docker

### Wat is Docker?
Docker is een virtualisatietechniek die het mogelijk maakt om software in geïsoleerde containers te draaien. Voor webontwikkeling gebruiken we Docker om een webserver en databaseserver op te zetten zonder een volledig besturingssysteem te hoeven installeren.

### Installatie
1. Download Docker via [docker.com](https://www.docker.com/)
2. Volg de installatie-instructies voor jouw besturingssysteem
3. Start Docker en verifieer de installatie bij je docent

### Containers en Images
- Containers zijn geïsoleerde omgevingen waarin software draait
- Images zijn de blauwdrukken waaruit containers worden gemaakt
- Voor dit project worden specifieke images aangeleverd die automatisch geconfigureerd worden

## Git

### Wat is Git?
Git is een versiebeheersysteem dat wordt gebruikt om verschillende versies van je code bij te houden. Het is essentieel voor zowel individueel werk als teamprojecten.

### Installatie en Configuratie
1. Download Git via [git-scm.com](https://git-scm.com/)
2. Installeer Git met de aanbevolen (recommended) instellingen
3. Open een terminal in VS Code en configureer je gegevens:

```bash
git config --global user.name "Jouw Naam"
git config --global user.email "Jouw Email"
```

## GitHub

### Wat is GitHub?
GitHub is een platform waar je je Git-projecten (repositories) kunt opslaan en delen met anderen. Het is de standaard voor het delen van code en samenwerken aan projecten.

### Account Aanmaken
1. Ga naar [GitHub.com](https://github.com)
2. Maak een account aan met:
   - Een professionele gebruikersnaam
   - Je school- of persoonlijke e-mailadres

### Project Forken
Voordat je aan een project gaat werken, moet je eerst een eigen kopie (fork) maken van het project:

1. Log in bij GitHub.com
2. Ga naar de repository die je wilt forken (bijvoorbeeld: [mijn-eerste-project](https://github.com/NOVA-college-Haarlem/mijn-eerste-project))
3. Klik op de "Fork" knop (rechtsboven)
4. Geef je fork een naam (bijvoorbeeld "mijn-eerste-project" of een andere naam voor je project)
5. Klik op "Create Fork"
6. De repository staat nu in je eigen GitHub account onder je eigen repositories

## Belangrijke Git-terminologie

- **Repository (repo)**: Een project-directory waar Git de versiegeschiedenis bijhoudt
- **Commit**: Een momentopname van je code
- **Push**: Code uploaden naar GitHub
- **Pull**: Updates van GitHub downloaden
- **Clone**: Een kopie maken van een repository
- **Fork**: Een persoonlijke kopie maken van iemand anders' repository

## Projecten map aanmaken

1. Maak een map aan voor je ALLE projecten. Bijvoorbeeld: `C:\Projecten`
> !! Maak geen map aan op je ONEDRIVE !!
2. Voor deze lessenserie maken we gebruik van verschillende repositories. Die gaan we clonen naar de zojuist aangemaakt map.

## Project Clonen

Na het forken kun je jouw versie van de repository clonen

1. Open je projectmap in VS Code Terminal
2. Clone je geforkte repository naar je projectmap met het volgende commando:

```bash
# C:\Projecten
git clone https://github.com/[JOUW-GITHUB-GEBRUIKERSNAAM]/mijn-eerste-project
```

## Project Starten
3. Open Docker Desktop
4. Ga terug naar de terminal en voer het volgende commando uit 

```bash
docker-compose up -d
```

7. Open de browser en ga naar `http://localhost`

## PHP

### Wat is PHP?
PHP (PHP: Hypertext Preprocessor) is een veelgebruikte programmeertaal specifiek ontworpen voor webontwikkeling. Het wordt server-side uitgevoerd, wat betekent dat de code op de webserver wordt verwerkt voordat het resultaat naar de browser wordt gestuurd.

### Belangrijke kenmerken van PHP
- PHP-code wordt uitgevoerd op de server, niet in de browser
- Kan HTML genereren die naar de client wordt gestuurd
- Kan met databases werken (bijvoorbeeld MySQL)
- Ondersteunt belangrijke webprotocollen
- Werkt op verschillende platforms (Windows, Linux, Mac)

### Basis PHP-syntax
PHP-code wordt geschreven tussen `<?php` en `?>` tags:

```php
<?php
    echo "Hallo, wereld!";
    
    // Variabelen beginnen met $
    $naam = "Student";
    
    // String concatenatie met .
    echo "Welkom " . $naam;
    
    // if-statement voorbeeld
    if ($naam == "Student") {
        echo "Je bent een student";
    }
?>
```

### PHP in HTML

PHP kan direct in HTML-documenten worden gebruikt:

```php
<!DOCTYPE html>
<html>
<body>
    <h1><?php echo "Welkom op mijn website"; ?></h1>
    
    <?php
        $tijd = date("H:i");
        echo "<p>Het is nu: " . $tijd . "</p>";
    ?>
</body>
</html>
```

### Waarom PHP?

- Eenvoudig te leren voor beginners
- Grote community en veel beschikbare resources
- Uitgebreide documentatie
- Veel frameworks beschikbaar (Laravel, Symfony)
- Wordt gebruikt door veel grote websites (WordPress, Facebook)

## Coderen met PHP

### Opdracht 1

We gaan de `index.php` aanpassen zodat deze een eenvoudige PHP-pagina wordt. We gaan de `index.html` aanpassen naar `index.php`. Wat zie je als je deze pagina opent in de browser?
> Antwoord: geen verschil, het standaard antwoord van de server is HTML.


### Opdracht 2

We gaan nu de pagina aanpassen zodat deze dynamischer en beter te onderhouden wordt. We gaan een variable aanmaken en deze gebruiken in de HTML. Je ziet momenteel twee verschillende titels voorkomen in de code. 

1. Maak bovenaan de pagina een variable aan met de naam `title` en de waarde `Pokedex`.

```php
<?php
    $title = "Pokedex";
?>
```
> Tip: een regel wordt gescheiden door een `;`


2. Gebruik deze variable in de HTML.
```php
<title><?php echo $title; ?></title>

//code voor de navigatie
<div class="text-white text-2xl font-bold"><?php echo $title; ?></div>
```

> Met `echo` kunnen we _strings_ en _numbers_ weergeven (printen) op de pagina.

3. Open de pagina in de browser en kijk of de titel is veranderd.
4. Als we de titel willen wijzigen, hoeven we alleen de variable aan te passen en de pagina opnieuw te starten.

### Opdracht 3

1. Bekijk de broncode van de pagina (rechtermuisknop -> View Page Source). Je ziet helemaal geen variabelen of PHP tags staan. Dit komt omdat de server de code heeft afgehandeld en daarna het eindresultaat (HTML) van de code verstuurt.

### If-statements

If-statements zijn een belangrijk concept in programmeren. Ze zorgen ervoor dat code alleen wordt uitgevoerd als een bepaalde voorwaarde waar is.

```php
if ($leeftijd >= 18) {
    echo "Je bent een volwassene";
}
```
> Tip: `>=` betekent groter of gelijk aan.

### Opdracht 4

We gaan een if-statement toevoegen waarbij we de tijd controleren. En als het vroeger is dan 12 uur, dan zeggen we "Goedemorgen" en als het later is dan 12 uur, dan zeggen we "Goedemiddag".

```php
<?php
    $tijd = date("H:i");
    if ($tijd < 12) {
        echo "Goedemorgen het is nu: " . $tijd . " uur";
    } else {
        echo "Goedemiddag het is nu: " . $tijd . " uur";
    }
?>
```

1. Open `index.php` in VS Code
2. Wat vind jij een goeie plek om deze code te plaatsen?
3. Open de pagina in de browser en kijk of het goedemorgen of goedemiddag wordt weergegeven.

### Opdracht 5

1. Open `index.php` in VS Code
2. Maak een variable met `$bericht` en pas het if-statement aan zodat de tijd wordt opgeslagen in de variable.
3. Print deze variable in de HTML.


## Conditionele operatoren

| Operator                 | Voorbeeld | Resultaat                      |
| ------------------------ | --------- | ------------------------------ |
| Is gelijk aan            | $a == $b  | $a is gelijk aan $b            |
| Is groter dan            | $a > $b   | $a is groter dan $b            |
| Is groter of gelijk aan  | $a >= $b  | $a is groter of gelijk aan $b  |
| Is kleiner dan           | $a < $b   | $a is kleiner dan $b           |
| Is kleiner of gelijk aan | $a <= $b  | $a is kleiner of gelijk aan $b |
| Is niet gelijk aan       | $a != $b  | $a is niet gelijk aan $b       |

### Opdracht 6

1. Maak in de www map een nieuwe map aan genaamd `opdrachten`
2. Maak hiern een nieuwe pagina aan met de naam `opdracht6.php` 
3. Maak een script die controleert het aantal pokemon kaarten dat wordt weergegeven.  Momenteel zijn dat er 3.
4. Als het aantal pokemon kaarten kleiner is dan 10, dan wordt er een bericht weergegeven: "Er zijn weinig pokemon kaarten te zien."
5. Als het aantal pokemon kaarten groter is dan 10, dan wordt er een bericht weergegeven: "Er zijn veel pokemon kaarten te zien."
6. Als het aantal pokemon kaarten gelijk is aan 10, dan wordt er een bericht weergegeven: "Er zijn precies 10 pokemon kaarten te zien."

## Arrays

Ook in PHP kunnen we arrays gebruiken. Dit zijn verzamelingen van variabelen die we kunnen gebruiken om meerdere waarden op te slaan.

```php
$pokemon_namen = ["Pikachu", "Charmander", "Squirtle"];
```

Om deze dan te gebruiken in de HTML, kunnen we deze als volgt gebruiken:

```php
echo $pokemon_namen[0];//index 0 is de eerste pokemon in de array
```

### Opdracht 7

1. Maak in de map `opdrachten` een nieuwe pagina aan met de naam `opdracht7.php` in VS Code
2. Maak een array met de naam `pokemon_namen` en voeg de volgende pokemon toe: `Pikachu`, `Charmander`, `Squirtle`.
3. Echo deze array zodat de namen worden weergegeven in de HTML.

Het is natuurlijk ook mogelijk om arrays te gebruiken met meerdere dimensies. Dit zijn arrays die meerdere waarden opslaan. _een array in een array_

```php
$pokemon_info = [
    ["Pikachu", "Electric", "Pikachu is een elektrische pokemon"],
    ["Charmander", "Fire", "Charmander is een vuur pokemon"],
    ["Squirtle", "Water", "Squirtle is een water pokemon"]
];
```

Om de waarde van de array te gebruiken, kunnen we deze als volgt gebruiken:

```php
echo $pokemon_info[0][0];//index 0 is de eerste pokemon in de array, index 0 is de naam van de pokemon
```

### Opdracht 8

1. Maak een nieuwe pagina aan met de naam `opdracht8.php` in VS Code
2. Maak een array met de naam `pokemon_info` en voeg de bovenstaande pokemon_info toe.
3. Bekijk het resultaat in de browser en kijk of de pokemon namen en types worden weergegeven.

We kunnen de bovestaande array ook anders schrijven. Dit is een meer uitgebreide manier om dezelfde informatie op te slaan.

> Dit noemen wij een __multidimensionale associatieve array__.


```php
$pokemon_info = [
    0 => [
        "naam" => "Pikachu",
        "type" => "Electric", 
        "beschrijving" => "De mascotte van Pokemon"
    ],
    1 => [
        "naam" => "Charmander",
        "type" => "Fire",
        "beschrijving" => "Een vurige starter pokemon"
    ],
    2 => [
        "naam" => "Squirtle", 
        "type" => "Water",
        "beschrijving" => "Een water starter pokemon"
    ]
];
```
Om nu de waarde van de array te gebruiken, kunnen we deze als volgt gebruiken:

```php
echo $pokemon_info[0]["naam"];//index 0 is de eerste pokemon in de array, index naam is de naam van de pokemon
```

### Opdracht 9

1. Maak een nieuwe pagina aan met de naam `opdracht9.php` in VS Code
2. Herschrijf de array `pokemon_info` zodat deze een multidimensionale associatieve array is.
3. Print deze array in de HTML op de plekken waar je de pokemon namen, types en beschrijvingen wilt weergeven.

## Loops

Loops zijn een belangrijk concept in programmeren. Ze zorgen ervoor dat code meerdere keren wordt uitgevoerd.

```php
for ($i = 0; $i < 10; $i++) {
    echo $i;
}
```

Er bestaan verschillende soorten loops. De belangrijkste zijn:
- `for` loop
- `while` loop
- `do-while` loop
- `foreach` loop

Wij gaan voornamelijk gebruik maken van de `foreach` loop. Dit is een loop die gebruikt wordt om door een array te lopen.

```php
foreach ($pokemon_info as $pokemon) {
    echo $pokemon["naam"];
}
```

#### Opdracht 10

1. Maak een nieuwe pagina aan met de naam `opdracht10.php` in VS Code
2. Maak een `foreach` loop die alle info van de pokemon in de pagina laat zien.

#### Opdracht 11
1. Neem je antwoord van opdracht 10 over en maak een nieuwe pagina aan met de naam `opdracht11.php` in VS Code
2. Voeg HTML toe zodat de pagina er netjes uitziet.

### Opdracht 12
1. Kun je kijken of je opdracht 11 kunt verwerken in de `index.php`?

## ingebouwde functies

PHP heeft veel ingebouwde functies die je kunt gebruiken. Hier zijn enkele veelgebruikte functies:

String functies:
- `strlen()` - Geeft de lengte van een string terug
- `strtoupper()` - Zet een string om naar hoofdletters
- `strtolower()` - Zet een string om naar kleine letters
- `substr()` - Haalt een deel van een string op
- `str_replace()` - Vervangt tekst in een string

Array functies:
- `count()` - Telt het aantal elementen in een array
- `array_push()` - Voegt een element toe aan het einde van een array
- `array_pop()` - Verwijdert en retourneert het laatste element van een array
- `sort()` - Sorteert een array
- `array_merge()` - Voegt arrays samen

Datum/tijd functies:
- `date()` - Formatteert een datum/tijd
- `time()` - Geeft de huidige Unix timestamp
- `strtotime()` - Zet een datum string om naar een timestamp

Debugging:
- `var_dump()` - Geeft de inhoud van een variabele weer
- `print_r()` - Geeft de inhoud van een array weer
- `die()` - Stopt de uitvoering van het script en geeft een foutmelding weer

### Opdracht 13

1. Maak een nieuwe pagina aan met de naam `opdracht13.php` in VS Code
2. Maak een `foreach` loop die alle info van de pokemon in de pagina laat zien.
3. Gebruik de functie `count()` om het aantal pokemon in de array te tellen.
4. Gebruik de functie `strtoupper()` om de naam van de pokemon in hoofdletters te zetten.

#### Opdracht 14

1. Maak een nieuwe pagina aan met de naam `opdracht14.php` in VS Code
2. Maak gebruik van `$pokemon_info` 
3. Gebruik var_dump() om de array te printen in de HTML.
4. Bekijk het resultaat in de browser
5. Bekijk de broncode van de pagina

## Request Response Cycle

Elke keer als je een website bezoekt dan doe je een verzoek (request) aan de server. Je zegt eigenlijk "hoi, mag ik deze pagina en deze content van je hebben?" en dan krijg je, als het goed is antwoord (response): "Ja hoor dat mag, alsjeblieft!". 
Dit wordt ook wel de Request-Response Cycle genoemd. Dat ziet er zo uit:

![Request Response Cycle](https://s3.amazonaws.com/media-p.slid.es/uploads/165506/images/7187932/request-response-cycle.png)

### REQUESTS

Er bestaan verschillende soorten requests (verzoeken aan de server). Deze requests zijn onderdeel van Hyper Text Transfer Protocol (HTTP). HTTPS is de Secure versie daarvan. HTTP is een van de application layers van het Internet Protocol suite (TCP/IP).

De belangrijkste requests zijn:
- GET
- POST

Vergelijk het weer eens met een ober. Er bestaan twee manieren om een bestelling te plaatsen in een café:
- Via de ober (vergelijkbaar met GET request)
- Via de beschikbare app/qr-code (vergelijkbaar met POST request)

### GET REQUEST

Een GET request is een verzoek, vaak via de adressenbalk, waarmee informatie van een server verkregen kan worden. Je kunt hier via de adresbalk data meegeven om zo specifieke informatie op te vragen. Omdat het hier om URLs gaat kun je deze verzoeken bijvoorbeeld bookmarken (opslaan) om zo later er weer terug te keren.

### POST REQUEST

Een POST request is een verzoek, vaak via een formulier, waarmee informatie naar een server verzonden kan worden. Je kunt hier via een formulier data meegeven om zo specifieke informatie op te sturen.

### Vier nieuwe pagina's

1. Maak een nieuwe pagina aan met de naam `mijn-verzameling.php` in VS Code in de map `www`
2. Maak een nieuwe pagina aan met de naam `zeldzame-pokemon.php` in VS Code in de map `www`
3. Maak een nieuwe pagina aan met de naam `over-ons.php` in VS Code in de map `www`
4. Maak een nieuwe pagina aan met de naam `contact.php` in VS Code in de map `www`
5. Pas de navigatie (`<nav>`) in `index.php` aan zodat deze deze pagina's bevat.

De bovenstaande pagina's kunnen nog leeg blijven. 

Om deze pagina's te testen kun je deze openen in de browser en kijken of deze pagina's worden weergegeven. We doen dit door de URL te wijzigen in de adresbalk van de browser. __Dit is een GET request.__

### Pokemon detailpagina's

Stel nu dat we ook detailpagina's willen maken voor de pokemon. Dit zijn pagina's die specifieke informatie over een pokemon tonen. Nu hebben we nog maar drie pokemon en zouden we voor elke pokemon een aparte pagina maken. Dit is natuurlijk niet handig en daarom kunnen we gebruik maken van een dynamische URL. Dit is een URL die een variabele bevat. We kunnen deze variabele gebruiken om specifieke informatie op te vragen.

Dit doen we met een GET request. We gebruiken deze request om specifieke informatie op te vragen. Hoe kun je een variabele meegeven aan de URL? 

```php
<a href="pokemon.php?id=1">Squirtle</a>
```

> Tip: Met een `?` kun je een variabele meegeven aan de URL.

Momenteel hebben we nog geen pokemon.php pagina. We gaan deze nu aanmaken.

### Opdracht 15

1. Maak een nieuwe pagina aan met de naam `pokemon.php` in VS Code in de map `www`
2. Zorg ervoor dat je naar deze pagina verwijst bij elke pokemon in de `index.php` pagina. (een link maken)

Stel nu dat we een stukje data willen meegeven aan de URL. Dit is een GET request. We kunnen deze data gebruiken om specifieke informatie op te vragen.

```php
<a href="pokemon.php?naam=squirtle">Squirtle</a>
```

### Opdracht 16

1. Wijzig de url zodat bij elke pokemon in index.php de url wordt aangepast zodat de naam van de pokemon wordt meegegeven aan de URL.
2. Als we dan een GET-request doen naar pokemon.php met de naam van de pokemon, dan kunnen we deze data gebruiken om specifieke informatie op te vragen. Dit doen we met de `$_GET` superglobal.

```php
echo $_GET["naam"];
```

> Tip: De $_GET superglobal is een array die alle data bevat die is meegegeven aan de URL.

Zoals je kunt zien is het mogelijk om data mee te geven en diezelfde data te gebruiken op de andere pagina. Dit is een voorbeeld van een dynamische URL.

### Index dynamisch maken

Als programmeur wil je coderen volgens het DRY-principe. Dit betekent dat je code niet herhaalt (DONT REPEAT YOURSELF). Als je kijkt op regel 44 (het pokemon-grid) dan zie je dat er 3 pokemon kaarten worden weergegeven. Dit is niet handig en daarom kunnen we deze code dynamisch maken. Dit is niet handing want als we meer pokemon zouden toevoegen, dan zouden we de dezelfde code opnieuw moeten toevoegen.

We gaan dit nu aanpassen.

### Opdracht 17

1. We laten de eerste pokemon kaart staan en verwijderen de overige twee.
2. We maken kopieren de eerder gemaakte $pokemon_info array en zetten deze helemaal bovenin de index.php pagina.

```php
$pokemon_info = [
    0 => [
        "naam" => "Pikachu",
        "type" => "Electric", 
        "beschrijving" => "De mascotte van Pokemon"
    ],
    1 => [
        "naam" => "Charmander",
        "type" => "Fire",
        "beschrijving" => "Een vurige starter pokemon"
    ],
    2 => [
        "naam" => "Squirtle", 
        "type" => "Water",
        "beschrijving" => "Een water starter pokemon"
    ]
];
```
3. We maken een `foreach` loop net boven het begin van de eerste pokemon kaart.

```php
 <!-- Pokemon Card 1 -->
<?php
foreach ($pokemon_info as $pokemon) { ?>
   <div class="bg-white rounded-lg shadow-lg overflow-hidden">
      <img src="https://assets.pokemon.com/assets/cms2/img/pokedex/full/025.png" alt="Pikachu"
         class="w-full h-64 object-cover">
      <div class="p-6">
         <h3 class="text-xl font-bold mb-2">Pikachu</h3>
         <p class="text-gray-600 mb-4">Elektrisch type Pokémon</p>
         <a href="#" class="text-blue-600 hover:text-blue-800">Meer informatie →</a>
      </div>
   </div>

<?php } ?>
```
4. Deze kaart wordt nu drie keer weergegeven. Dat is natuurlijk niet de bedoeling. We willen dat een kaart wordt weergegeven voor elke pokemon in de array.
5. We passen de naam van de pokemon in de kaart aan.
```php
<h3 class="text-xl font-bold mb-2"><?php echo $pokemon["naam"]; ?></h3>
```
6. We passen het type van de pokemon in de kaart aan.
```php
<p class="text-gray-600 mb-4"><?php echo $pokemon["type"]; ?></p>
```
7. Dan passen we de URL ook nog aan zodat deze dynamisch is.
```php
<a href="pokemon.php?naam=<?php echo $pokemon["naam"]; ?>" class="text-blue-600 hover:text-blue-800">Meer informatie →</a>
```

8. Op de pokemon.php pagina kunnen we deze data gebruiken om specifieke informatie op te vragen. Dit doen we met de `$_GET` superglobal.

```php
echo $_GET["naam"];
```

## Werken met een database

Als je goed hebt gekeken naar de afbeelding van de Request Response Cycle dan heb je gezien dat een PHP pagina kan communiceren met een database. Dat gaan we nu regelen. Er zijn verschillende manieren om dit te doen. Wij beginnen uiteraard met de eenvoudige wijze.  

### DATABASE

Voor dit project hebben we een database nodig. Deze is al gemaakt en toegankelijk via phpmyadmin. http://localhost:8000/. Je ziet nu de database `pokemon_db` staan.

### Opdracht 18

1. Klik op de `pokemon_db` database en klik op de `sql` tabblad.
2. Kopieer en plak de inhoud van de `pokemon-cards.sql` file in het sql tabblad van phpmyadmin.
3. Klik op de `Starten` knop.
4. Als je dan op het tabblad Verkennen klikt, zie je de `cards` tabel staan met daarin de drie pokemon.

### Database connectie

Om tussen je webapplicatie en de database te communiceren hebben we een connectie nodig. Dit is een verbinding tussen de database en de webapplicatie. We gebruiken hiervoor de `mysqli` extensie. We maken hiervoor een nieuwe pagina aan met de naam `database_connection.php`.

De onderstaande code maakt een connectie met de database.

```php
$conn = mysqli_connect("mariadb", "root", "password", "pokemon_db");
```

Als we een database connectie willen gebruiken in een andere pagina, dan moeten we deze pagina includen. Dit doen we met de `require` functie.

```php
require "database_connection.php";
```

Nu kunnen we de connectie gebruiken om data uit de database te halen.

```php
$query = "SELECT * FROM cards"; // selecteer alle data uit de cards tabel
$result = mysqli_query($conn, $query); // voer de query uit
$pokemon_info = mysqli_fetch_all($result, MYSQLI_ASSOC); // haal de data op en sla deze op in een array
```

### Opdracht 19

1. Maak een nieuwe pagina aan met de naam `database_connection.php` in VS Code in de map `www`
2. Maak een connectie met de database in deze pagina.
3. Zorg ervoor dat deze connectie pagina wordt meegegeven aan de `index.php` pagina.
4. Verwijder de statische data uit de `index.php` pagina (verwijder dus de ouder $pokemon_info array)
5. Maak gebruik van de `mysqli_fetch_all` functie om de data op te halen uit de database en sla deze op in een array.
6. De code is wat aangepast, maar het resultaat is nog steeds hetzelfde.

### Opdracht 20

1. We gaan nu de pokemon.php pagina aanpassen. We willen dat deze pagina de specifieke informatie van een pokemon toont. We hadden al dynamische links gemaakt in de `index.php` pagina. We gaan deze een klein beetje aanpassen, in plaats van de naam van de pokemon gebruiken we de id.

```php
<a href="pokemon.php?id=<?php echo $pokemon['id']; ?>" class="text-blue-600 hover:text-blue-800">Meer informatie →</a>
```

Als we dan op een link klikken, dan krijgen we de volgende URL: `http://localhost:8000/pokemon.php?id=1`. Dit is een GET request. We kunnen deze data gebruiken om specifieke informatie op te vragen. Dit doen we met de `$_GET` superglobal. 

2. Pas de pokemon.php pagina aan zodat deze de specifieke informatie van een pokemon toont.

```php
echo $_GET["id"];
```

3. Echter willen we deze data gebruiken om specifieke informatie op te vragen. Dit doen we met een query.

```php
$id = $_GET['id'];//we halen de id op uit de URL
$query = "SELECT * FROM cards WHERE id = $id";
$result = mysqli_query($conn, $query);
$pokemon = mysqli_fetch_assoc($result);//fetch_assoc() is een functie die een enkele rij uit de database ophaalt en deze opslaat in een associatieve array.
```

4. Nu kunnen we alle data van deze pokemon tonen in de pokemon.php pagina.

```php
echo $pokemon['name'];
echo $pokemon['type'];
echo $pokemon['description'];
```

### Opdracht 21

1. Stijl de pokemon.php pagina met Tailwind CSS.

### Opdracht 22

1. We kunnen de data uit de database ook op andere wijzes tonen op het scherm.
2. Maak een nieuwe pagina an met de naam pokemon-table.php
3. Maak een tabel met de data van de pokemon.
4. Gebruik de `mysqli_fetch_all` functie om de data op te halen uit de database en sla deze op in een array.
5. Gebruik de `foreach` loop om de data in de tabel te tonen.
6. Stijl de pagina met Tailwind CSS.

