# React PDF Kit Starter Toolkit in React.js, JavaScript and Vite

[![Open in StackBlitz](https://developer.stackblitz.com/img/open_in_stackblitz.svg)](https://stackblitz.com/github.com/react-pdf-kit/starter-rp-react-js-vite)

Welcome to the React PDF Kit Starter Toolkit! This repository provides a comprehensive guide on integrating React PDF with React, JavaScript and Vite. It showcases how React PDF can be integrated and rendered as part of a React.js project.

## Table of Contents

- [Usage](#usage)
  - [Project Setup](#project-setup)
  - [Running the Example Project](#running-the-example-project)
- [Examples](#examples)

## Usage

### Project Setup

1. **Clone the Repository**: If you haven't already, clone the repository and navigate into the project directory.

   ```bash
   git clone https://github.com/react-pdf-kit/starter-rp-react-js-vite.git
   cd starter-rp-react-js-vite
   ```

2. **Install Dependencies**: Install the necessary dependencies using npm, yarn, pnpm or bun.

   ```bash
   npm install
   # or
   yarn install
   # or
   pnpm install
   # or
   bun install
   ```

### Running the Example Project

This repository includes an example project to demonstrate React PDF Kit in action.

1. **Start the Development Server**: Use the following command to start the development server

   ```bash
   npm run start
   # or
   yarn start
   # or
   pnpm run start
   # or
   bun run start
   ```

2. **Open in Browser**: Open your browser and navigate to `http://localhost:5173` (or the port specified in your terminal) to see the example project in action

### Using the React PDF Component

Once the example project is running, you can explore the source code to see how the React PDF component is integrated. Here is a brief overview:

1.  **Import the component**: Import the desired React PDF component into your codes

```jsx
import {
  RPProvider,
  RPLayout,
  RPPages,
} from "@react-pdf-kit/viewer";

export const AppPdfViewer = (props) => {
  const { showToolbar = true, providerProps, defaultLayoutProps } = props;

  return (
    <RPProvider
      src="https://cdn.codewithmosh.com/image/upload/v1721763853/guides/web-roadmap.pdf"
      {...providerProps}
    >
      {showToolbar ? (
        <RPLayout toolbar {...defaultLayoutProps}>
          <RPPages />
        </RPLayout>
      ) : (
        <div style={{ width: "100%", height: "550px" }}>
          <RPPages/>
        </div>
      )}
    </RPProvider>
  );
};
```

2. **Use the component in the template**: Add the React PDF component to your template section

```jsx
import "./App.css";
import { RPConfig } from "@react-pdf-kit/viewer";
import { AppPdfViewer } from "./components/AppPdfViewer";

function App() {
  return (
    <RPConfig licenseKey="">
      <div className="container">
        <h1>React PDF Kit Starter Toolkit in React.js, JavaScript and Vite</h1>
        <br />
        <h2>Default Toolbar</h2>
        <AppPdfViewer />
        <h2>Without Toolbar</h2>
        <AppPdfViewer
          showToolbar={false}
          defaultLayoutProps={{
            style: { width: "100%", height: "550px" },
          }}
        />
        <h2>Mobile</h2>
        <AppPdfViewer
          defaultLayoutProps={{
            style: { width: "500px" },
          }}
        />
      </div>
    </RPConfig>
  );
}

export default App;
```

## Examples

For more examples, please refer to the `src/App.jsx` file in this repository:

- Default Toolbar
- Without Toolbar
- Mobile View

_Remark: If you would like more examples, feel free open an issue._

For more configurations, please check the [documentation](https://docs.react-pdf-kit.dev) site.

## Meta
- Homepage: [https://www.react-pdf-kit.dev](https://www.react-pdf-kit.dev)
- Docs: [https://docs.react-pdf-kit.dev](https://docs.react-pdf-kit.dev)

---

Thank you for using React PDF Kit! We hope this toolkit helps you build amazing React.js applications. If you have any questions or need further assistance on this example, please feel free to open an issue. Happy coding!
