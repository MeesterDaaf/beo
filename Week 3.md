**# Week 3 - Les 2 - Array functies

PHP heeft veel ingebouwde functies die je kunt gebruiken. Hier zijn enkele veelgebruikte functies:

String functies:
> - `strlen()` - Geeft de lengte van een string terug
> - `strtoupper()` - Zet een string om naar hoofdletters
> - `strtolower()` - Zet een string om naar kleine letters
> - `substr()` - Haalt een deel van een string op
> - `str_replace()` - Vervangt tekst in een string

Array functies:
> - `count()` - Telt het aantal elementen in een array
> - `array_push()` - Voegt een element toe aan het einde van een array
> - `array_pop()` - Verwijdert en retourneert het laatste element van een array
> - `sort()` - Sorteert een array
> - `array_merge()` - Voegt arrays samen

Datum/tijd functies:
> - `date()` - Formatteert een datum/tijd
> - `time()` - Geeft de huidige Unix timestamp
> - `strtotime()` - Zet een datum string om naar een timestamp

Debugging:
> - `var_dump()` - Geeft de inhoud van een variabele weer
> - `print_r()` - Geeft de inhoud van een array weer
> - `die()` - Stopt de uitvoering van het script en geeft een foutmelding weer


## Opdracht 1

1. Maak een nieuwe pagina aan met de naam `opdracht100.php` in VS Code
2. Kopieer de volgende array naar deze pagina:

```php
$donald_duck_info = [
    ['name' => 'Donald Duck', 'age' => 85, 'city' => 'Oranjewoud'],
    ['name' => 'Dagobert Duck', 'age' => 50, 'city' => 'Elsene'],
    ['name' => 'Katrien Duck', 'age' => 45, 'city' => 'Elsene'],
];
```

3. Gebruik de functie `count()` om het aantal elementen in de array te tellen.
4. Toon het aantal elementen in de array in de HTML.
5. Gebruik de functie `array_push()` om een nieuw element (['name' => 'Guus Geluk', 'age' => 55, 'city' => 'Den Haag']) toe te voegen aan de array.
6. Itereer over de array en toon de naam, leeftijd en woonplaats van elke persoon in de HTML.

## Opdracht 2

1. Maak een nieuwe pagina aan met de naam `opdracht200.php` in VS Code
2. Maak gebruik van de in opdracht 1 gemaakte array.
3. Gebruik de functie `array_pop()` om het laatste element uit de array te verwijderen.
4. Itereer over de array en toon de naam, leeftijd en woonplaats van elke persoon in de HTML.

## Opdracht 3
1. Maak een nieuwe pagina aan met de naam `opdracht300.php` in VS Code
2. Codeer de volgende arrays:

```php
$groente_lijst = [ 
    'appel',
    'peer',
    'banaan',
    'kers',
    'peer',
    'banaan',
    'kers',
];

$slager_lijst = [
    'worst',
    'kippenvleugel',
    'schnitzel',
    'lamsvlees',
];
```
1. Gebruik de functie `sort()` om beide arrays te sorteren.
2. Gebruik de functie `array_merge()` om beide arrays samen te voegen.
3. Toon de samengevoegde array in de HTML met behulp van een foreach loop. En wat Html en CSS

### Opdracht 4

1. Maak een nieuwe pagina aan met de naam `opdracht400.php` in VS Code
2. Codeer de volgende twee variabelen:

```php
$voornaam = 'guus';
$achternaam = 'geluk';
```

3. Gebruik de functie `strtoupper()` om de voornaam en achternaam in hoofdletters te zetten.

#### Opdracht 5
1. Maak een nieuwe pagina aan met de naam `opdracht500.php` in VS Code
2. Codeer de volgende variabelen:

```php
$voornaam = 'HARRY';
$achternaam = 'POTTER';
```

3. Gebruik de functie `strtolower()` om de voornaam en achternaam in kleine letters te zetten.

#### Opdracht 6

De `substr()` functie in PHP wordt gebruikt om een deel van een tekst (string) te selecteren. Je kunt een specifiek deel van een tekst krijgen door het aangeven van:
1. De startpositie (offset)
2. De lengte (optioneel)

##### Basis Syntax
```php
substr(string $string, int $start [, int $length ])
```
1. Maak een nieuwe pagina aan met de naam `opdracht600.php` in VS Code
2. Codeer de volgende variabelen:

```php
$boek = 'Bitcoin Standard';
```
3. Gebruik de functie `substr()` om het woord 'Bitcoin' te tonen
4. Gebruik de functie `substr()` om het woord 'Standard' te tonen
5. Gebruik de functie `str_replace()` om het woord 'Standard' te vervangen door 'Standaard'.
6. Toon de waardes op het scherm.

#### Opdracht 7

1. Maak een nieuwe pagina aan met de naam `opdracht700.php` in VS Code
2. Codeer de volgende variabele:

```php
$bestandsnaam = "document.pdf";
```
3. Maak gebruik van de functie substr() om de extensie van het bestand op te halen
4. Zet de extensie in een variabele genaamd $extensie
5. Toon de waarde van de variabele $extensie op het scherm.


#### Opdracht 8

1. Maak een nieuwe pagina aan met de naam `opdracht800.php` in VS Code
2. Codeer de volgende variabele:

```php
$datum = '2025-01-01';
```
3. Gebruik de functie `strtotime()` om de tijd in een timestamp variable te zetten, $tijd
4. Toon de waarde van de variabele $tijd op het scherm.
5. Gebruik vervolgens de `date()` functie om de timestamp weer om te zetten naar een leesbare datum in het formaat "d-m-Y"


#### Opdracht 9

1. Maak een nieuwe pagina aan met de naam `opdracht900.php` in VS Code
2. Neem de onderstaande code over in deze pagina:

```php
$donald_duck_info = [
    ['name' => 'Donald Duck', 'age' => 85, 'city' => 'Oranjewoud'],
    ['name' => 'Dagobert Duck', 'age' => 50, 'city' => 'Elsene'],
    ['name' => 'Katrien Duck', 'age' => 45, 'city' => 'Elsene'],
];

print_r($donald_duck_info);

$tiktok_info = [
        [   "naam" => "Guus Geluk",
            "volgers" => 100000,
            "likes" => 40,
            "comments" => 10,
            "shares" => 2300,
            "views" => 10000000,
        ],
        [   "naam" => "Donald Duck",
            "volgers" => 10,
            "likes" => 10,
            "comments" => 10000,
            "shares" => 45,
            "views" => 50,
        ],
        [   "naam" => "Dagobert Duck",
            "volgers" => 2,
            "likes" => 0,
            "comments" => NULL,
            "shares" => NULL,
            "views" => NULL,
        ],
        [   "naam" => "Katrien Duck",
            "volgers" => 25,
            "likes" => 23,
            "comments" => 5,
            "shares" => 23,
            "views" => 100,
        ]
];

print_r($tiktok_info);
```

3. Bekijk je de output van deze code in je browser.
4. Zet de functie die() vlakvoor het aanmaken van de variabele $tiktok_info en bekijk de output.
5. Vervang de functie print_r() met var_dump() en bekijk de output.

**