# Component props

## State & props

- state = internal to the component
- props = parameters that are passed down from the parent

## Props in custom components

Example:

```jsx
<Rating stars={3} />
```

<img src="assets/rating.png" style="width: 16em" />

## Props in function components

example (simple Rating component):

```jsx
const Rating = (props) => (
  <div className="rating">
    {'★'.repeat(props.stars) + '☆'.repeat(5 - props.stars)}
  </div>
);
```

with object destructuring for props:

```jsx
const Rating = ({ stars }) => (
  <div className="rating">
    {'★'.repeat(stars) + '☆'.repeat(5 - stars)}
  </div>
);
```

## props.children

A component may receive content to be displayed via `props.children`

Example: a `Bordered` component:

```jsx
<Bordered>lorem ipsum</Bordered>
```

Defining the component:

```jsx
const Bordered = (props) => (
  <div className="bordered">{props.children}</div>
);
```
