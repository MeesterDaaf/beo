# Week 2 - Les 1 - Loops en Request Response Cycle
## Loops

Loops zijn een belangrijk concept in programmeren. Ze zorgen ervoor dat code meerdere keren wordt uitgevoerd.

```php
for ($i = 0; $i < 10; $i++) {
    echo $i;
}
```

### Opdracht 10
1. Maak een nieuwe pagina aan met de naam `opdracht10.php` in VS Code
2. Kopieer de array $pokemon_info (uit opdracht 9) naar deze pagina.
3. Maak een `for` loop die alle info van de pokemon in de pagina laat zien.

Er bestaan verschillende soorten loops. De belangrijkste zijn:
- `for` loop
- `while` loop
- `do-while` loop
- `foreach` loop

Wij gaan voornamelijk gebruik maken van de `foreach` loop. Dit is een loop die gebruikt wordt om door een array te lopen. De loop loopt door alle elementen van de array en doet iets met elk element.

```php
foreach ($pokemon_info as $pokemon) {
    echo $pokemon["naam"];
}
```

### Opdracht 11
1. Maak een nieuwe pagina aan met de naam `opdracht11.php` in VS Code
2. Kopieer de array $pokemon_info (uit opdracht 9) naar deze pagina.
3. Maak een `foreach` loop die alle info van de pokemon in de pagina laat zien.

### Opdracht 12
1. Neem je antwoord van opdracht 10 over en maak een nieuwe pagina aan met de naam `opdracht12.php` in VS Code
2. Voeg HTML toe zodat de pagina er netjes uitziet.

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

## Week 2 - Les 2 - Database

### Werken met een database

Als je goed hebt gekeken naar de afbeelding van de Request Response Cycle dan heb je gezien dat een PHP pagina kan communiceren met een database. Dat gaan we nu regelen. Er zijn verschillende manieren om dit te doen. Wij beginnen uiteraard met de eenvoudige wijze.  

### Database maken

Voor dit project hebben we een database nodig. Deze is al gemaakt en toegankelijk via phpmyadmin. http://localhost:8000/. Je ziet nu de database `pokemon_db` staan.

### Opdracht 18

1. Klik op de `pokemon_db` database en klik op de `sql` tabblad.
2. In de map `sql` vind je een bestand genaamd `pokemon-cards.sql`. De inhoud van dit bestand is een SQL query. Deze kun je kopiëren en plakken in het sql tabblad van phpmyadmin.
3. Klik op de `Starten` knop.
4. Als je dan op het tabblad Verkennen klikt, zie je de `cards` tabel staan met daarin de drie pokemon kaarten.

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
3. Zorg ervoor dat deze connectie pagina wordt meegegeven aan de `index.php` pagina middels een `require` statement.
4. Verwijder de statische data uit de `index.php` pagina (verwijder dus de oude $pokemon_info array)
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

1. Stijl de pokemon.php pagina met Tailwind CSS of je eigen stijl.

### Opdracht 22

1. We kunnen de data uit de database ook op andere wijzes tonen op het scherm.
2. Maak een nieuwe pagina an met de naam pokemon-table.php
3. Maak een tabel met de data van de pokemon.
4. Gebruik de `mysqli_fetch_all` functie om de data op te halen uit de database en sla deze op in een array.
5. Gebruik de `foreach` loop om de data in de tabel te tonen.
6. Stijl de pagina met Tailwind CSS.

### Opdracht 23

1. Voeg eens een paar nieuwe pokemon kaarten toe aan de database.
2. Zorg ervoor dat deze nieuwe pokemon kaarten ook in de `index.php` pagina worden getoond.
3. Zorg ervoor dat deze nieuwe pokemon kaarten ook in de `pokemon.php` pagina worden getoond.

