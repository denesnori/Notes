### Perspective

```
div {
  -webkit-perspective: 500px;
  perspective: 500px,
}
```

Note: the ```perspective``` property only affects 3D transformed elements.
- the prespective property defines how many pixels a 3D transformed element is placed from view.
- when you define the perspective porp on an element, the child elements are the ones that get the prespective view, not the element on which you defined the property.

### Backface-visbility

```
div {
  -webkit-backface-visibility: hidden;
  Backface-visbility: hidden;
}
```

- defines whether the element should be visible or not when NOT facing the screen.
- useful for rotating elements, when you don't want to see the back.
