# REST API: requesting data from a database

A method to request all metadata from a database. This method does not support parameters. It is called using the following address:
 `GET https://api.copernica.com/database/$id?access_token=xxxx`

## Returned fields
**ID**: unique numerical identifier
**name**: name of the database
**description**: description of the database
**archived**: whether or not the database is archived
**created**: when the database was created
**fields**: array of fields in the database
**interests**: array met interests in the database
**collections**: array met de collections in the database

Fields, interests and collections are returned as arrays of objects. If you want to know how these arrays are built, you can check out the pages of these API methods, which return similar data:

- [Requesting fields](rest-get-database-fields)
- [Requesting interests](rest-get-database-interests)
- [Requesting collections](rest-get-database-collections)

## PHP example

The following example demonstrates how to use this method:

```PHP
// dependencies
require_once('copernica_rest_api.php');

// change this into your access token
$api = new CopernicaRestApi("your-access-token");

// do the call, and print result
print_r($api->get("database/1234"));
```
This example uses the [CopernicaRestAPi class](rest-php).

## More information
- [Overview of all REST API methods](rest-api)