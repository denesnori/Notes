### focus

- elements that accept keyboard events, or alter user inputs can have focus.
- anchor tags (with href), input, select, textarea, button (if not disabled), any element with tabIndex
```
input:focus {
  backgorund-color: yellow;
}
```

### blur events

- for the ```blur``` event to fire on an element, it has to receive ```focus``` first.
- ```div ``` elements don't receive focus by default. You can add ```tabIndex = 0``` to the ```div``` so it can get focus.

#### tabIndex poroperty
- the tab order of the element, when the tab button is used to navigate.
- if the tabIndex < 0, it is removed from the tab order.
