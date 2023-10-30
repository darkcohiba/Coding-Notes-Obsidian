---
tags:
  - javascript
  - react
type: react hook
---

# Basics
- useState is one of react's many hooks.
- [Documentation](https://react.dev/reference/react/useState)
- `useState` is a React Hook that lets you add a [state variable](https://react.dev/learn/state-a-components-memory) to your component.

```javascript
const [state, setState] = useState(initialState);
```

#### Parameters [](https://react.dev/reference/react/useState#parameters "Link for Parameters")

- `initialState`: The value you want the state to be initially. It can be a value of any type, but there is a special behavior for functions. This argument is ignored after the initial render.
    - If you pass a function as `initialState`, it will be treated as an _initializer function_. It should be pure, should take no arguments, and should return a value of any type. React will call your initializer function when initializing the component, and store its return value as the initial state. 

#### Returns [](https://react.dev/reference/react/useState#returns "Link for Returns")

`useState` returns an array with exactly two values:

1. The current state. During the first render, it will match the `initialState` you have passed.
2. The [`set` function](https://react.dev/reference/react/useState#setstate) that lets you update the state to a different value and trigger a re-render.

#### Caveats [](https://react.dev/reference/react/useState#caveats "Link for Caveats")

- `useState` is a Hook, so you can only call it **at the top level of your component** or your own Hooks. You can’t call it inside loops or conditions. If you need that, extract a new component and move the state into it.
- In Strict Mode, React will **call your initializer function twice** in order to [help you find accidental impurities.](https://react.dev/reference/react/useState#my-initializer-or-updater-function-runs-twice) This is development-only behavior and does not affect production. If your initializer function is pure (as it should be), this should not affect the behavior. The result from one of the calls will be ignored.
