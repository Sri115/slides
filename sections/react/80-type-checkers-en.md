# Type checkers for React

## Type checkers for React

Declaring types can be useful, especially when it comes to component props and events

possibilities:

- using TypeScript as a language
- library _prop-types_

## React with TypeScript

creating a new project:

```bash
npx create-react-app my-app --template typescript
```

## TypeScript

TypeScript basics: see presentation on [TypeScript](./typescript-en.html)

## React with TypeScript

extensive resource: https://github.com/typescript-cheatsheets/react-typescript-cheatsheet

<!--

redux with typescript:

- https://github.com/piotrwitek/react-redux-typescript-guide
- https://medium.com/@resir014/a-type-safe-approach-to-redux-stores-in-typescript-6474e012b81e
- https://www.carlrippon.com/strongly-typed-react-redux-code-with-typescript/

-->

## Props with TypeScript (function components)

```tsx
type TodoListProps = {
  todos: Array<TodoType>;
  onToggle: (id: number) => void;
  onDelete: (id: number) => void;
};

const TodoList = (props: TodoListProps) => {
  // ...
};
```

## useState with TypeScript

often no annotation is necessary:

```ts
const [filterText, setFilterText] = useState('');
```

with annotation:

```ts
const [todos, setTodos] = useState<Array<TodoType>>([]);
```

## Event types

With inline event handlers no event type must be declared:

```jsx
<button
  onClick={(event) => {
    event.stopPropagation();
  }}
>
  test
</button>
```

## Event types

Event types for event handlers that are defined separately:

- `React.FormEvent`
- `React.FormEvent<HTMLFormElement>`
- `React.ChangeEvent<HTMLInputElement>`
- `React.MouseEvent<HTMLDivElement>`

## prop-types

library for annotating React component properties in JavaScript

## prop-types

example:

```js
import PropTypes from 'prop-types';

// definition of Rating component here

Rating.propTypes = {
  stars: PropTypes.number.isRequired,
  onStarsChange: PropTypes.func,
};
```

## prop-types in VS Code

Plugin: _React PropTypes IntelliSense_
