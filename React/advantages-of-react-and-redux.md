### Why should we use React and Redux?

- a paradigm shift from MVC frameworks to component type framework/library. -- for React.
- Redux: a paradigm shift from 2-way data-binding (eg.Angular) to one-way data flow.
- all application logic is in pure functions: it makes it easy to keep track of the application state. The state is the store, the only way the state can change is through reducers.
- components: a component can be a simple function (functional components) -> functional components can be combined.
- separation of concerns with small stateless components and smart container components. -> Help to  keep track of the app logic.
- Redux store: application level state, React state local states.
- Virtual DOM --> helps to increase performance by optimizing DOM updates. We have control over how often and when the components should render --> we can increase performance.
