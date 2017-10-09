### R.propEq()

String -> a -> object -> boolean

```
import * as R from 'ramda';

var car = { wheels: 4, colour: 'red' };
var bicycle = {wheels: 2, colour: 'blue'};
var rollerSkate = wheels:8,colour:'blue'};

var collection = [car, bicycle, rollerSkate];
var isBlue = R.propEq('colour','blue');
R.filter(isBlue, collection)
```

### R.findIndex

(a -> Boolean ) -> [a] -> Number

Works in the same way an ```.indexOf()```, return the index of the first match, or ```-1``` id no match is found.

```
import * as R from 'ramda';

var test = [{a: 1}, {b:2},{c:3}];
R.findIndex(R.propEq('b',2))(test); // => 1
R.findIndex(R.propEq('b',3))(test); // => -1
```
