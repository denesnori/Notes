## What is the diiference between classical inheritance and prototypal inheritance?

#### Class inheritance
- instances inherit from classes (like a  blueprint, a description of the class) and create sub class relationships --> hierarchical class taxonomies.
- instances are typically instantiated via cunstructor functions with the ```new``` keyword.
- class inheritance may or may not use the ```class``` keyword (introduced by ES6).
- creates tight coupling, rigid hierarchies.

#### Prototypal inheritance
- instances inherit directly from other objects.
- instances are instantiated vis *factory functions* or ```Object.create()```.
- easy selective inheritance: an object can have more than one ancestor, they can be composed of many different objects.
- JS: protypal inheritance is more flexile and simpler than class inheritance.

Subtypes:
- concatenative inheritance (```Object.assign()```)
- prototype delegation
- functional inheritance
- object composition

## Favour object composition over class inheritance

"It means that code reuse should be achieved by assembling smaller units of functionality into new objects, instead of inheriting from classes and creating abject taxonomies."

Prefer ```can-do```, ```has-a```, or ```uses-a``` relationships over the ```is-a``` relationship.

- avoid class hierarchies and rigid taxonomies
- avoid the brittle base class problem
- object composition makes code more flexible


## When is calassical inheritance the right choice?

- almost never
- never more than one level. One level is OK, eg.: for a framwork base class like ```React.Component```
- multi-level class hierarchies are anti-pattern.
- favour object composition over class inheritance
