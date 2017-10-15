## all the possible ways to create a new div, dynamically change it


- creation
```
const div = document.createElement('div');
```
- addition
  document.body.appendChild('div');
- style manipulation
  - postions
    ```
    div.style.left = '32px';
    div.style.top = '-16px';
    ```
  - classes
    ```
    div.className = 'ui-modal';
    ```
  - add to classList
    ```
    div.classList.append('myClass');
    ```
- modification
  - id
    ```
    div.id = 'test'
    ```
  - content (using HTML)
    ```
    div.innerHTML = '<span>Hello</span>'
    ```
  - contents using text
    ```
    div.textContent = 'Hello'
    ```
- removal
  ```
  div.parentNode.removeChild('div')
  ```
- accessing
  - by id
  ```
  var div = document.getElementById('test')
  ```
  - by tags
  ```
  var array = document.getElementsByTagName('div')
  ```
  - by class
  ```
  var array = document.getElementsByClassName('myDiv')
  ```
  - by CSS selector (single)
  ```
  var div = document.querySelector('div #test .myDiv')
  ```
  - by CSS selector (multiple)
  ```
  var array = document.querySelectorAll('div')
  ```
- relations (text nodes included)
  - children:
  ```
  var node = div.childNodes[i]
  ```
  - sibling
  ```
  var node = div.nextSibling;
  ```
- relations (HTML nodes only)
  - children
  ```
  var element = div.children[i]
  ```
  - var element = div.nextElementSibling
