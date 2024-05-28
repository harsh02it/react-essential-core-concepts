# React Essentials - Components, JSX, Props, State & More

This project is part of the "React - The Complete Guide (incl Hooks, React Router, Redux)" course on Udemy. Below, I will detail the key concepts learned in this section, including where and how they were implemented, along with some code snippets for better understanding.

## Topics Covered

### React Components

**Introduction to Components**: I learned about the fundamental building blocks in React known as components. They allow for the modular and reusable parts of the UI.

- **Creating Components**:
  - Implemented by creating the `Header` component:
    ```jsx
    function Header() {
      return (
        <header>
          <h1>Welcome to My React App</h1>
        </header>
      );
    }
    ```

**Component Composition**:

- Nesting and composing components was practiced by including the `Header` component within the `App` component:
  ```jsx
  function App() {
    return (
      <div>
        <Header />
        <p>This is my first React app!</p>
      </div>
    );
  }
  ```

### JSX (JavaScript XML)

**JSX Syntax**: Writing HTML-like syntax in JavaScript files.

- **Embedding Expressions**:
  - Utilized JSX syntax to embed expressions:
    ```jsx
    const userName = "John Doe";
    return <h2>Hello, {userName}</h2>;
    ```

**JSX Transformations**:

- Learned how JSX is transformed into `React.createElement` calls by Babel to render elements.

### Props

**Passing Props**:

- Implemented by passing data to child components via props:

  ```jsx
  function Greeting(props) {
    return <h1>Hello, {props.name}</h1>;
  }

  function App() {
    return (
      <div>
        <Greeting name="Alice" />
      </div>
    );
  }
  ```

**Props.children**:

- Learned to use `props.children` to pass components or elements as children to other components.

  ```jsx
  function Wrapper(props) {
    return <div className="wrapper">{props.children}</div>;
  }

  function App() {
    return (
      <Wrapper>
        <Header />
        <p>This content is wrapped!</p>
      </Wrapper>
    );
  }
  ```

### State Management

**Component State**:

- Introduced to state management within components to keep track of changes.
- **useState Hook**:

  - Utilized to manage state in functional components:

    ```jsx
    function Counter() {
      const [count, setCount] = useState(0);

      return (
        <div>
          <p>Count: {count}</p>
          <button onClick={() => setCount(count + 1)}>Increment</button>
        </div>
      );
    }
    ```

### Handling Events

**Event Handling**:

- Added and managed event handlers in React components:

  ```jsx
  function Button() {
    function handleClick() {
      alert("Button was clicked!");
    }

    return <button onClick={handleClick}>Click Me</button>;
  }
  ```

### Conditional Rendering

**Conditional Rendering Techniques**:

- Implemented different ways to conditionally render components or elements:
  ```jsx
  function UserGreeting(props) {
    if (props.isLoggedIn) {
      return <h1>Welcome back!</h1>;
    }
    return <h1>Please sign up.</h1>;
  }
  ```

### Lists and Keys

**Rendering Lists**:

- Rendered lists of data using `map` function:

  ```jsx
  const numbers = [1, 2, 3, 4, 5];
  const listItems = numbers.map((number) => (
    <li key={number.toString()}>{number}</li>
  ));

  return <ul>{listItems}</ul>;
  ```

**Keys in React**:

- Understood the importance of keys in list rendering for efficient updates and re-renders.

### Prerequisites

- Node.js and npm installed on your machine.

### Installation

1. Clone the repository:
   ```sh
   git clone <repository-url>
   ```
