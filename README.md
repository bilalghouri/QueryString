# QueryString
A Singleton URL Query String handler for PHP

# Usage
``` php
$query = QueryString::getInstance();

// Add some elements to the query string
$query -> add ('foo=bar&testing2=testing2&testing=testing&bilal=ghouri');
echo $query -> get();

// Output: ?foo=bar&testing2=testing2&testing=testing&bilal=ghouri

$query -> remove('testing'); // remove a single element
$query -> add ('foo=blah&newkey=newvalue', false); // do not overwrite values
echo $query -> get();

//Output: ?foo=bar&testing2=testing2&bilal=ghouri&newkey=newvalue

// remove multiple elements
$query -> remove('testing2', 'foo');
echo $query -> get();

// Output: ?bilal=ghouri&newkey=newvalue

// Set a new query string
$query -> setQueryString('Fresh=Vals');
echo $query -> get();

// Output: ?Fresh=Vals

// add values from an array
$query -> add(array('key1' => 'val1', 'key2' => 'val2'));
echo $query -> get();

// Output: ?Fresh=Vals&key1=val1&key2=val2
```
