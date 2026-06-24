# MyComponent

A short, one-sentence description explaining exactly what this React component does (e.g., "A highly customizable, accessible button component with built-in loading states").

## 🚀 Features

- **Accessible:** Built following WAI-ARIA design patterns.
- **Type Safe:** Fully written in TypeScript.
- **Customizable:** Easily styled using Tailwind CSS or standard class names.
- **Lightweight:** Zero external runtime dependencies.

## 📦 Installation

Install the component package using your preferred package manager:

```bash
npm install my-react-component-library
# or
yarn add my-react-component-library
# or
pnpm add my-react-component-library
```

## 💻 Usage

Import the component into your React application and use it as shown below:

```tsx
import React from "react";
import { MyComponent } from "my-react-component-library";

function App() {
  return (
    <MyComponent variant="primary" onClick={() => console.log("Clicked!")}>
      Click Me
    </MyComponent>
  );
}

export default App;
```

## ⚙️ API Reference

### Props

The component accepts the following properties:

| Prop        | Type                                   | Default     | Description                                    |
| :---------- | :------------------------------------- | :---------- | :--------------------------------------------- |
| `variant`   | `'primary' \| 'secondary' \| 'danger'` | `'primary'` | Defines the visual style theme.                |
| `size`      | `'sm' \| 'md' \| 'lg'`                 | `'md'`      | Controls padding and font sizes.               |
| `disabled`  | `boolean`                              | `false`     | When true, disables user interaction.          |
| `isLoading` | `boolean`                              | `false`     | Displays a loading spinner inside the element. |
| `onClick`   | `(event: MouseEvent) => void`          | `undefined` | Callback function triggered on click.          |

---

## 🛠️ Development & Contribution

If you want to contribute to this component, follow these steps to set up your local environment:

### 1. Clone the Repository

```bash
git clone https://github.com
cd my-react-component-library
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Run a Local Development Environment

If you use [Storybook](https://js.org) or a local test server, start it up:

```bash
npm run dev
# or
npm run storybook
```

### 4. Run Tests

```bash
npm run test
```

## 📄 License

This component is open-source software licensed under the [MIT License](LICENSE).
