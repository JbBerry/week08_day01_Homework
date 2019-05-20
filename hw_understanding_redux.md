# Homework: Getting Familiar with Redux
##### 1. What are actions used for?
`Actions` are used to pass data from the app to the store.
##### 2. What type of object must an action be?
An `Action` is a plain Javascript object.
##### 3. At a minimum, what is the one property the action should have? And what is this property used for?
It must contain at least a `{type:   }` key:value pair.
##### 4. What is the responsibility of the reducer?
A `Reducer` takes in the payload from an `Action` and specifies how the state is to be changed.
##### 5. What is the responsibility of the store?
The `Store` is a repository for the state. It allows that state to the updated.

#### Part 2

When working with Redux, the reducers must be pure functions. One of the qualities that makes a function pure is that is doesn't modify (or 'mutate') objects outside their scope. When a reducer is passed the state, it must not mutate the state, but instead return a newly created state object. Read the following page on common ways patterns for not mutating state in reducers:

[https://redux.js.org/recipes/structuring-reducers/immutable-update-patterns](https://redux.js.org/recipes/structuring-reducers/immutable-update-patterns)

Which of the following functions are pure:
```js
/* PURE FUNCTION */
const reducer1 = (action, state) => {
  return state + 1;
}
```
```js
/* NOT PURE FUNCTION */
const reducer2 = (action, state) => {
  state.push("Cat");
  return state;
}
```
```js
/* PURE FUNCTION */
const reducer3 = (action, state) => {
  return [...state, "Dog"];
}
```
```js
/* NOT PURE FUNCTION */
const reducer4 = (action, state) => {
  return state.map(pet => {
    pet.price /= 2;
    return pet;
  });
}
```
```js
/* PURE FUNCTION */
const reducer5 = (action, state) => {
  return state.map(pet => {
    return { ...pet, pet.price: pet.price / 2 }
  });
}
```

### Extensions

Do one (or all!) of the following:

- Create another Redux application from scratch.
- Add additional features the to applications we have been building today.
- Complete the [basics tutorial on the Redux website](https://redux.js.org/basics/basic-tutorial).
