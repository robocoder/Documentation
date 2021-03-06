# REST API: POST collection miniviews

Warning: You are viewing the documentation for the old REST API. We recommend 
using [version 2](../restv2/rest-api.md) of the REST API.

In order to create a new selection using the REST API, you need to send 
a HTTP POST request to the following URL. The selection will then be 
created, nested underneath the collection.

`https://api.copernica.com/v1/collection/$id/miniviews?access_token=xxxx`

In this, `$id` should be replaced by the numerical identifier, the ID, of 
the collection you want to add a selection to. The name of the selection 
is not in the URL, as it needs to be added to the message body of the 
HTTP request. After a successful call the ID of the created request is returned.

## Available parameters

The following variables can be added to the body of the HTTP POST call:

- **name**: The name of the selection that is to be created. (mandatory)
- **description**: an optional description of the new selection.
- **parent-type**: used to display whether a selection is placed directly under a collection, or nested under another selection
- **parent-id**: ID of the parent selection/collection

## PHP example

The following example demonstrates how to use the API method:

```php
// dependencies
require_once('copernica_rest_api.php');

// change this into your access token
$api = new CopernicaRestApi("your-access-token");

// data to pass to the call
$data = array(
    'name'      =>  'my-selection',
    'description'	=> 'example selection',
);

// do the call
$api->post("collection/1234/miniviews", $data);
```

The example above requires the [CopernicaRestApi class](rest-php).

## More information

- [Overview of all API calls](rest-api)
- [GET collection miniviews](rest-get-collection-miniviews)
- [GET miniview rules](rest-get-miniview-rules)
- [POST miniview rules](rest-post-miniview-rules)
