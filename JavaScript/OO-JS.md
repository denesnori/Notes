## Object Oriented JavaScript

### Creating Objects

#### literal notation:
creates a single object
```
var House = {
  windows: 5,
  bathroom: 1,
  bedroom: 2,
}
```



#### Factory functions = Factory Object Creation pattern

```
function createHouse(window, bedroom){
  var house = {};
  house.window = window;
  house.bedroom = bedroom;
  house.isBigEnough =  function (minRooms){
    return minRooms >= this.bedroom;
  };
  return house;
}
```
Cons:
- every object created by the factory functions has the same methods -> can be redundant

#### constructor functions
  - template for creating multiple Objects
  - by convention it is capitalized
  - instances are created with the ```new``` keyword

```
function House(windows, bathroom, bedroom){
  this.windows = windows;
  this.bathroom = bathroom;
  this.bedroom = bedroom;
  this.isBigEnough =  function (minRooms){
    return minRooms >= this.bedroom;
  }
}

var myHome = new House(5,1,3);

```

Step when the constructor function is invoked with new:
1. new object is created
2. 'this' inside the function is pointed to the new object
3. the code inside the function is executed
4. object is returned

## Pseudo-classical pattern

- arguments are passed into the constructor function to set the initial state
- BUT, shared behaviour is added to the constructor's protoype object --> it is shared among Objects

```
function House(windows, bedroom){
  this.windows = windows;
  this.bedroom = bedroom;
}

Game.protoype.isBigEnough = function (num){
  return this.bedroom >= num;
}

var myHouse = new House(5,2);
myHouse.isBigEnough(2);
```

## OLOO - ( Objects Linking to Other Objects )

 - dispense with the class based approach to object creation
 - instead relies on ```Object.create()``` and a template object (naming convention capitalized 1st letter)
 - ```init()``` function can be used to initialize the state

 ```
 car Car = {
   this.type = "";
   this.year = "";
   this.description: ()=> `This is a ${this.type} from ${this.year}`;
   init: (type,year) => {
     this.type = type;
     this.year = year;
     return this;
   }
 }


var Honda = Object.create(Car).init("Honda",2006);

Honda.isPrototypeOf(Car); //true
```

### references
(launch school- oo  js)[https://medium.com/launch-school/object-oriented-javascript-3e14787905ad]
(Dan Jackson - OO JS)[https://medium.com/@justtoconfirm/object-oriented-javascript-d61fe073ca86]
()[https://stackoverflow.com/questions/29788181/kyle-simpsons-oloo-pattern-vs-prototype-design-pattern]
