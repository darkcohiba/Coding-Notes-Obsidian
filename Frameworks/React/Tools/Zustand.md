---
tags:
  - react
  - javascript
type: react tool
---
# Basics
## Installation[documentation](https://docs.pmnd.rs/zustand/getting-started/introduction#installation)
- Zustand is available as a package on NPM for use:

```bash
# NPM
npm install zustand

# Yarn
yarn add zustand
```
## First create a store[documentation](https://docs.pmnd.rs/zustand/getting-started/introduction#first-create-a-store)

- Your store is a hook! You can put anything in it: primitives, objects, functions. The `set` function _merges_ state.

```js
import { create } from 'zustand'

const useStore = create((set) => ({
  bears: 0,
  increasePopulation: () => set((state) => ({ bears: state.bears + 1 })),
  removeAllBears: () => set({ bears: 0 }),
}))
```
## Then bind your components, and that's it!
You can use the hook anywhere, without the need of providers. Select your state and the consuming component will re-render when that state changes.

```jsx
function BearCounter() {
  const bears = useStore((state) => state.bears)
  return <h1>{bears} around here...</h1>
}

function Controls() {
  const increasePopulation = useStore((state) => state.increasePopulation)
  return <button onClick={increasePopulation}>one up</button>
}
```

# Advanced Usage
## Example Array Store
- This Zustand store has full CRUD on the items array. It can delete and replace/update items by ID

```javascript
import { create } from 'zustand';


const itemStore = create(set => ({
    items: [],
    setItems: (newItems) => set({ items: newItems }),
    addItems: (item) => set(state => ({ items: [...state.items, item] })),
    clearItems: () => set({ items: [] }),
    deleteItemById: (id) => set(state => ({
        items: state.items.filter(item => item.id !== id)
    })),

    replaceItemById: (id, newItem) => set(state => ({
        items: state.items.map(item => item.id === id ? newItem : item)
    }))
}))

export default itemStore;
```

- These are two examples of the same user store, these stores only allow us to add users to the users array but it does persist.
```javascript
// EXAMPLE ONE
import { create } from 'zustand';
import {devtools, persist} from 'zustand/middleware'
const userStore = (set) => ({
    //user state
    users: [],
    addUser: (user) => set((state)=> ({
        users: [user, ...state.users]
    })),
})
const useUserStore = create(
    devtools(
        persist(userStore, {
            name: "users",
        })
    )
)
export default useUserStore;

// EXAMPLE TWO
import { create } from 'zustand';
import { devtools, persist } from 'zustand/middleware';

const useUserStore = create(
    devtools(
        persist(
            (set) => ({
                users: [],
                addUser: (user) => set((state) => ({ users: [user, ...state.users] }))
            }),
            { name: "users" }
        )
    )
);

export default useUserStore;
```

## Example Form Store
- This Zustand store saves data to the form by the key and value passed into it.

```javascript
import { create } from 'zustand';
import {devtools, persist} from 'zustand/middleware'

const formStore = (set) => ({
    form: {},
    addForm: (key, value) => set((state)=> ({
        form: {
            ...state.form,
            [key] : value
        },

    })),
    clearForm: () => set({ form: {} }),  // Clear form data

})

const useFormStore = create(
    devtools(
        persist(formStore, {
            name: "forms",
        })
    )
)

export default useFormStore;
```