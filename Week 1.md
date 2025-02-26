# Week 1 - Les 1 - PHP Intro & Arrays

We gaan alle projecten in deze lessenserie opslaan in de map `C:\Projecten`

## Projecten map aanmaken

1. Maak een map aan voor je ALLE projecten. Bijvoorbeeld: `C:\Projecten`
> !! Maak geen map aan op je ONEDRIVE !!
2. Voor deze lessenserie maken we gebruik van verschillende repositories. Die gaan we clonen naar de zojuist aangemaakt map.

## Project starten

### Project Forken

Voordat je aan een project gaat werken, moet je eerst een eigen kopie (fork) maken van het project:

1. Log in bij GitHub.com
2. Ga naar de repository die je wilt forken (bijvoorbeeld: [mijn-eerste-project](https://github.com/NOVA-college-Haarlem/mijn-eerste-project))
3. Klik op de "Fork" knop (rechtsboven)
4. Geef je fork een naam (bijvoorbeeld "mijn-eerste-project" of een andere naam voor je project)
5. Klik op "Create Fork"
6. De repository staat nu in je eigen GitHub account onder je eigen repositories


### Project Clonen

Na het forken kun je jouw versie van de repository clonen

1. Open je projectmap in VS Code Terminal
2. Clone je geforkte repository naar je projectmap met het volgende commando:

```bash
# C:\Projecten
git clone https://github.com/[JOUW-GITHUB-GEBRUIKERSNAAM]/mijn-eerste-project
```

### Project Starten

3. Open Docker Desktop
4. Ga terug naar de terminal en voer het volgende commando uit 

```bash
docker-compose up -d
```

7. Open de browser en ga naar `http://localhost`

## PHP

### Wat is PHP?

PHP (PHP: Hypertext Preprocessor) is een veelgebruikte programmeertaal specifiek ontworpen voor webontwikkeling. Het wordt server-side uitgevoerd, wat betekent dat de code op de webserver wordt verwerkt voordat het resultaat naar de browser wordt gestuurd.

#### Belangrijke kenmerken van PHP

- PHP-code wordt uitgevoerd op de server, niet in de browser
- Kan HTML genereren die naar de client wordt gestuurd
- Kan met databases werken (bijvoorbeeld MySQL)
- Ondersteunt belangrijke webprotocollen
- Werkt op verschillende platforms (Windows, Linux, Mac)

#### Basis PHP-syntax

Regels voor PHP-code:

- PHP-code wordt geschreven tussen `<?php` en `?>` tags:
- Variabelen beginnen met `$`
- String concatenatie met `.` (aan elkaar plakken)
- if-statement krijgt altijd een `{` en `}`
- echo is de functie die gebruikt wordt om te printen op het scherm


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

#### PHP in HTML

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

##### Waarom PHP?

- Eenvoudig te leren voor beginners
- Grote community en veel beschikbare resources
- Uitgebreide documentatie
- Veel frameworks beschikbaar (Laravel, Symfony)
- Wordt gebruikt door veel grote websites (WordPress, Facebook)

##### Coderen met PHP
###### Opdracht 1

 We gaan de `index.html` aanpassen naar `index.php`. Wat zie je als je deze pagina opent in de browser?
> Antwoord: geen verschil, het standaard antwoord van de server is HTML.

###### Opdracht 2

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

###### Opdracht 3

1. Bekijk de broncode van de pagina (rechtermuisknop -> View Page Source). Je ziet helemaal geen variabelen of PHP tags staan. Dit komt omdat de server de code heeft afgehandeld en daarna het eindresultaat (HTML) van de code verstuurt.

### If-statements

If-statements zijn een belangrijk concept in programmeren. Ze zorgen ervoor dat code alleen wordt uitgevoerd als een bepaalde voorwaarde waar is.

```php
if ($leeftijd >= 18) {
    echo "Je bent een volwassene";
}
```
> Tip: `>=` betekent groter of gelijk aan.

###### Opdracht 4

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

###### Opdracht 5

1. Open `index.php` in VS Code
2. Maak een variable met `$bericht` en pas het if-statement aan zodat de tijd wordt opgeslagen in de variable.
3. Print deze variable in de HTML.


### Conditionele operatoren

| Operator                 | Voorbeeld | Resultaat                      |
| ------------------------ | --------- | ------------------------------ |
| Is gelijk aan            | $a == $b  | $a is gelijk aan $b            |
| Is groter dan            | $a > $b   | $a is groter dan $b            |
| Is groter of gelijk aan  | $a >= $b  | $a is groter of gelijk aan $b  |
| Is kleiner dan           | $a < $b   | $a is kleiner dan $b           |
| Is kleiner of gelijk aan | $a <= $b  | $a is kleiner of gelijk aan $b |
| Is niet gelijk aan       | $a != $b  | $a is niet gelijk aan $b       |

###### Opdracht 6

1. Maak in de www map een nieuwe map aan genaamd `opdrachten`
2. Maak hiern een nieuwe pagina aan met de naam `opdracht6.php` 
3. Maak een script die controleert het aantal pokemon kaarten dat wordt weergegeven.  Momenteel zijn dat er 3.
4. Als het aantal pokemon kaarten kleiner is dan 10, dan wordt er een bericht weergegeven: "Er zijn weinig pokemon kaarten te zien."
5. Als het aantal pokemon kaarten groter is dan 10, dan wordt er een bericht weergegeven: "Er zijn veel pokemon kaarten te zien."
6. Als het aantal pokemon kaarten gelijk is aan 10, dan wordt er een bericht weergegeven: "Er zijn precies 10 pokemon kaarten te zien."

> Tip: Gebruik een if-statement om deze controle uit te voeren.

# Week 1 - Les 2

## Arrays

Ook in PHP kunnen we arrays gebruiken. Dit zijn verzamelingen van variabelen die we kunnen gebruiken om meerdere waarden op te slaan.

```php
$pokemon_namen = ["Pikachu", "Charmander", "Squirtle"];
```

Om deze dan te gebruiken in de HTML, kunnen we deze als volgt gebruiken:

```php
echo $pokemon_namen[0];//index 0 is de eerste pokemon in de array
```

#### Opdracht 7

1. Maak in de map `opdrachten` een nieuwe pagina aan met de naam `opdracht7.php` in VS Code
2. Maak een array met de naam `pokemon_namen` en voeg de volgende pokemon toe: `Pikachu`, `Charmander`, `Squirtle`.
3. Echo deze array zodat de namen worden weergegeven in de HTML.

Het is natuurlijk ook mogelijk om arrays te gebruiken met meerdere dimensies. Dit zijn arrays die meerdere waarden opslaan. _een array in een array_

```php
$boodschappen = [
    ["appel", 2],
    ["peer", 3],
    ["banana", 4]
];
```

Om de waarde van de array te gebruiken, kunnen we deze als volgt gebruiken:

```php
echo $boodschappen[0][0];//index 0 is de eerste boodschap in de array, index 0 is de naam van de boodschap, appel
```

### Opdracht 8

1. Maak een nieuwe pagina aan met de naam `opdracht8.php` in VS Code
2. Maak een array met de naam `pokemon_info` en voeg de onderstaande pokemon_info toe.
3. Toon de waardes van Charmander met de naam, type en beschrijving in de HTML.

```php
$pokemon_info = [
    ["Pikachu", "Electric", "Pikachu is een elektrische pokemon"],
    ["Charmander", "Fire", "Charmander is een vuur pokemon"],
    ["Squirtle", "Water", "Squirtle is een water pokemon"]
];
```

We kunnen de boodschappen array ook anders schrijven. Dit is een meer uitgebreide manier om dezelfde informatie op te slaan.

```php
$boodschappen = [
    0 =>[
        "naam" => "appel",
        "aantal" => 2
    ],
    1 =>   [
        "naam" => "peer",
        "aantal" => 3
    ],
    2 => [
        "naam" => "banana",
        "aantal" => 4
    ]
];
```

> Dit noemen wij een __multidimensionale associatieve array__.


Om nu de waarde van de array te gebruiken, kunnen we deze als volgt gebruiken:

```php
echo $boodschappen[0]["naam"];//index 0 is de eerste boodschap in de array, index naam is de naam van de boodschap
```

### Opdracht 9

1. Maak een nieuwe pagina aan met de naam `opdracht9.php` in VS Code
2. Herschrijf de array `pokemon_info` zodat deze een multidimensionale associatieve array is.

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
3. Print deze array in de HTML op de plekken waar je de pokemon namen, types en beschrijvingen wilt weergeven.
