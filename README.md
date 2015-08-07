# QueryString
A Singleton URL Query String handler for PHP

# Usage
$query = QueryString::getInstance();

$query -> add ('foo=bar&testing2=testing2&testing=testing&bilal=ghouri'); // Add some elements to the query string
echo $query -> get();
Output: ?foo=bar&testing2=testing2&testing=testing&bilal=ghouri

$query -> remove('testing'); // remove a single element
$query -> add ('foo=blah&newkey=newvalue', false); // do not overwrite values
echo $query -> get();
Output: ?foo=bar&testing2=testing2&bilal=ghouri&newkey=newvalue

$query -> remove('testing2', 'foo'); // remove multiple elements
echo $query -> get();
Output: ?bilal=ghouri&newkey=newvalue

$query -> setQueryString('Fresh=Vals'); // Set a new query string
echo $query -> get();
Output: ?Fresh=Vals

$query -> add(array('key1' => 'val1', 'key2' => 'val2')); // add values from an array
echo $query -> get();
Output: ?Fresh=Vals&key1=val1&key2=val2
