# REST API: opvragen interesses in een database

Een overzicht van alle beschikbare interesses in een database kun je opvragen
met de volgende URL:

`https://api.copernica.com/database/$id/interests?access_token=xxx`

De variabele $id moet je vervangen door de nummerieke identifier of de naam
van de database waar je de interesses van wilt opvragen.

## Beschikbare parameters

De volgende parameters kunnen aan de URL als variabelen worden toegevoegd:

* **start**: eerste interesse die wordt opgevraagd
* **limit**: lengte van de batch die wordt opgevraagd
* **total**: toon wel/niet het totaal aantal interesses in de output

Meer informatie over de betekenis van deze parameters vind je in het
[artikel over paging](rest-paging).


## Geretourneerde velden

De methode retourneert een lijst van interesses in de database. Voor elke interesse
worden de volgende eigenschappen teruggegeven:

* **ID**: nummeriek ID van de interesse
* **name**: naam van de interesse
* **group**: naam van de interessegroep waar de interesse bij hoort

## Voorbeeld in PHP

Het volgende PHP script demonstreert hoe je de API methode kunt aanroepen:

    // dependencies
    require_once('copernica_rest_api.php');
    
    // change this into your access token
    $api = new CopernicaRestApi("your-access-token");

    // parameters to pass to the call
    $parameters = array(
        'limit'     =>  100
    );
    
    // do the call, and print result
    print_r($api->get("database/1234/interests", $parameters));

Voor bovenstaand voorbeeld heb je de [CopernicaRestApi klasse](rest-php) nodig.
    

## Meer informatie

* [Overzicht van alle API calls](rest-reference)
* [Interesse toevoegen aan een database](rest-post-database-interests)
* [Interesse bijwerken](rest-put-database-interest)
* [Interesse verwijderen](rest-delete-database-interest)