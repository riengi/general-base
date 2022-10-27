# Easy-peasy state

## Installl
```pnpm install easy-peasy```

## Create store
```js
const store = createStore({
	// state
	value: 1
	// actions
	increment: action((state, payload) => {
		state.value += payload
	})
})
```

## Wrap top Component with Provider
```jsx
function App() {
	return (
		<StoreProvider store={store}>
			<Counter />
		</StoreProvider>
	);
}

## Use the store
```jsx
function Counter() {
	const value = useStoreState((state) => state.value);
	const increment = useStoreActions((actions) => actions.increment);
	return (
		<div>{value}</div>
		<button onClick={increment(10)}>Increment 10 />
	);
}
```
