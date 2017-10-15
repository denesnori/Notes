### Element.classList

- read only property
- returns a DOMTokenList collection of the class attributes of an element.
- more convenient than ```element.classList```, which returns the classes as a space-delimited string.

Methods:
- add(string)
- remove(string)
- item(number) -> return class name at index
- toggle(string)
- contain(string)
- replace(oldClass,newClass)

### DOMTokenList
- represents a set of space separated tokens.
- indexed from 0.
- case sensitive.
- properties: length, value
- methods: item, contains, add,remove,replace, toggle, forEach
