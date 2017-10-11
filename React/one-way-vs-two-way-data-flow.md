## What is the difference between one-way data binding and two-way data binding?

1. Two-way data binding:
UI fields are bound to the model data dynamically. --> when the UI field changes it implies that the model data changes too, and vice-versa.
- two-way data flows can cause side-effects, harder to follow,debug
- Angular

2. One-way data flow:
- the model (eg. redux store) is the single source of truth.
- the data always flows in one direction --> easy to follow
- changes to the UI trigger actions, that tells the model (store) that we want to change the apps state.
- deterministic
- React
