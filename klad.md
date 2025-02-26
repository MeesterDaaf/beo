## ingebouwde functies

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


We willen elke pokemon kaart een afbeelding geven. In de onderstaande opdrachten gaan we deze afbeeldingen toevoegen.

## Opdracht 1

1. Maak een nieuwe map aan in de map `www` genaamd `images`.
2. Download de afbeeldingen van de pokemon kaarten en sla deze op in de map `images`.
3. Wijzig eventueel de bestandsnamen zodat ze hetzelfde zijn als de naam van de pokemon. Let op! Behoud de extensie van het orginele bestand. Bijvoorbeeld `pikachu.png`.

## Opdracht 2

1. Zorg ervoor dat de afbeeldingen in de `index.php` pagina worden getoond.
2. Zorg ervoor dat de afbeeldingen in de `pokemon.php` pagina worden getoond.
3. Zorg ervoor dat de afbeeldingen in de `pokemon-table.php` pagina worden getoond.