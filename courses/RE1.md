### [D1-REACT TUTORIAL - DAVE GRAY](https://www.youtube.com/playlist?list=PL0Zuz27SZ-6PrE9srvEn8nbhOOyxnWXfp)

<details>
  <summary>1. Create React App</summary>

# Create React App

<img width="977" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/72c7bd60-0dec-408f-aa2b-cb68733d52e9">
<img width="1159" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/733b183d-9c73-450c-b930-befb787dd6e4">

# Check node version

```bs
node -v
```

# Create App myapp

```bs
npx create-react-app .
npx create-react-app myapp
```

# Start App:

```bs
cd myapp
npm start
```

# Stop App:

```bs
ctrl + c
```

### x-dave-gray/myapp/src/index.js:

```js
import React from "react";
import ReactDOM from "react-dom/client";
import "./index.css";
import App from "./App";

const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);
```

### x-dave-gray/myapp/src/App.js:

```js
import logo from "./logo.svg";
import "./App.css";

function App() {
  return (
    <div className="App">
      <header className="App-header">
        <img src={logo} className="App-logo" alt="logo" />
        <p>
          Edit <code>src/App.js</code> and save to see changes.
        </p>
        <a
          className="App-link"
          href="https://reactjs.org"
          target="_blank"
          rel="noopener noreferrer"
        >
          Learn React
        </a>
      </header>
    </div>
  );
}

export default App;
```

# #End  </details>

<details>
  <summary>2. HandleNameChange Function</summary>

# HandleNameChange Function

<img width="972" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/0a7de29b-3ae6-45fb-82bb-d64439e6727e">
<img width="1158" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/167cea6a-feab-42d9-8515-2d12b419a4df">

### x-dave-gray/myapp/src/App.js:

```js
import logo from "./logo.svg";
import "./App.css";

function App() {
  const handleNameChange = () => {
    const names = ["Dave", "Sally", "Ben", "Andrew"];
    const int = Math.floor(Math.random() * names.length);
    return names[int];
  };

  return (
    <div className="App">
      <header className="App-header">
        <img src={logo} className="App-logo" alt="logo" />
        <p>Hello {handleNameChange()}!</p>
      </header>
    </div>
  );
}

export default App;
```

# #End  </details>

<details>
  <summary>3. Using React Functional Components</summary>

# Using React Functional Components

<img width="977" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/4f7308fd-a44f-40b8-bd92-fb6bff029db5">
<img width="1158" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/4b461b3b-04ec-4154-8861-8f07e2b82756">

### x-dave-gray/myapp/src/App.js:

```js
import "./App.css";
import Header from "./Header";
import Content from "./Content";
import Footer from "./Footer";

function App() {
  return (
    <div className="App">
      <Header />
      <Content />
      <Footer />
    </div>
  );
}

export default App;
```

### x-dave-gray/myapp/src/Header.js:

```js
import React from "react";

const Header = () => {
  return (
    <header>
      <h1>Groceries List</h1>
    </header>
  );
};

export default Header;

```

### x-dave-gray/myapp/src/Content.js:

```js
import React from "react";

const Content = () => {
  const handleChange = () => {
    const names = ["Dave", "Sally", "Ben", "Andrew"];
    const indexPos = Math.floor(Math.random() * names.length);
    return names[indexPos];
  };

  return (
    <main>
      <p>Hello, {handleChange()}!</p>
    </main>
  );
};

export default Content;

```

### x-dave-gray/myapp/src/Footer.js:

```js
import React from "react";

const Footer = () => {
  const today = new Date();

  return (
    <footer>
      <p>Copyright &copy; {today.getFullYear()}</p>
    </footer>
  );
};

export default Footer;

```

# #End  </details>

<details>
  <summary>4. Styling Components</summary>

# Styling Components

<img width="977" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/e1b5995b-e3e3-40f7-bf81-54c2f026f81a">
<img width="1157" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/4d1abe89-e81f-4270-9aac-fe0f619e3719">

### x-dave-gray/myapp/src/index.js:

```js
import React from "react";
import ReactDOM from "react-dom/client";
import "./index.css";
import App from "./App";

const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);

```

### x-dave-gray/myapp/src/App.js:

```js
import Header from "./Header";
import Content from "./Content";
import Footer from "./Footer";

function App() {
  return (
    <div className="App">
      <Header />
      <Content />
      <Footer />
    </div>
  );
}

export default App;
```

### x-dave-gray/myapp/src/Header.js:

```js
import React from "react";

const Header = () => {
  const headerStyle = {
    backgroundColor: "royalblue",
    color: "#fff",
  };

  return (
    <header style={headerStyle}>
      <h1>Groceries List</h1>
    </header>
  );
};

export default Header;
```

### x-dave-gray/myapp/src/index.css:

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  font-size: 22px;
}

body {
  min-height: 100vh;
  font-family: "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Fira Sans",
    "Droid Sans", "Helvetica Neue", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.App {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100vh;
  width: 100%;
  max-width: 500px;
  border: 1px solid mediumblue;
  margin: auto;
}

header {
  width: 100%;
  padding: 0 0.25em;
  background-color: mediumblue;
  color: aliceblue;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

main {
  width: 100%;
  display: flex;
  flex-direction: column;
  flex-grow: 1;
  justify-content: flex-start;
  align-items: space-around;
  overflow-y: auto;
}

footer {
  width: 100%;
  padding: 0.25em;
  background-color: mediumblue;
  color: aliceblue;
  display: grid;
  place-content: center;
}

```

# #End  </details>

<details>
  <summary>5. React onClick Events</summary>

# React onClick Events

<img width="978" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/899644b5-a98c-4d77-ad8f-beb82c98307e">
<img width="1157" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/c57decdf-91d2-4ef2-bfd8-7c6557e8b01f">

### x-dave-gray/myapp/src/App.js:

```js
import Header from "./Header";
import Content from "./Content";
import Footer from "./Footer";

function App() {
  return (
    <div className="App">
      <Header />
      <Content />
      <Footer />
    </div>
  );
}

export default App;

```

### x-dave-gray/myapp/src/Content.js:

```js
import React from "react";

const Content = () => {
  const handleChange = () => {
    const names = ["Dave", "Sally", "Ben", "Andrew"];
    const int = Math.floor(Math.random() * names.length);
    return names[int];
  };

  const handleClick = () => {
    console.log("Click 1 button was clicked.");
  };

  const handleClick2 = (name) => {
    console.log(`Click 2 button with name "${name}" was clicked.`);
  };

  const handleClick3 = (e) => {
    console.log(e.target.innerText);
  };

  const handleDoubleClick = () => {
    console.log("The Item was clicked twice!");
  };

  return (
    <main>
      <p onDoubleClick={handleDoubleClick}>Hello, {handleChange()}!</p>
      <button onClick={handleClick}>Click 1</button>
      <button onClick={() => handleClick2("David")}>Click 2</button>
      <button onClick={(e) => handleClick3(e)}>Click 3</button>
    </main>
  );
};

export default Content;
```

# Other applications of Single And DoubleClick function

```js
import { useState, useEffect } from "react";

function useSingleAndDoubleClick(
  actionSimpleClick,
  actionDoubleClick,
  delay = 250
) {
  const [click, setClick] = useState(0);

  useEffect(() => {
    const timer = setTimeout(() => {
      // simple click
      if (click === 1) actionSimpleClick();
      setClick(0);
    }, delay);

    // the duration between this click and the previous one
    // is less than the value of delay = double-click
    if (click === 2) actionDoubleClick();

    return () => clearTimeout(timer);
  }, [click]);

  return () => setClick((prev) => prev + 1);
}

const click = useSingleAndDoubleClick(callbackClick, callbackDoubleClick);

<button onClick={click}>click</button>;

```

```js
const handleClick = (e) => {
  switch (e.detail) {
    case 1:
      console.log("click");
      break;
    case 2:
      console.log("double click");
      break;
    case 3:
      console.log("triple click");
      break;
  }
};

return <button onClick={handleClick}>Click me</button>;
```

# #End  </details>

<details>
  <summary>6. Using React useState Hooks</summary>

# Using React useState Hooks

<img width="978" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/ffd66132-3a7f-4186-a704-218f34e4d3b5">
<img width="1158" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/85aa594a-6c2a-4393-b031-c89b58108218">

### x-dave-gray/myapp/src/App.js:

```js
import Header from "./Header";
import Content from "./Content";
import Footer from "./Footer";

function App() {
  return (
    <div className="App">
      <Header />
      <Content />
      <Footer />
    </div>
  );
}

export default App;
```

### x-dave-gray/myapp/src/Content.js:

```js
import React, { useState } from "react";

const Content = () => {
  const [name, setName] = useState("Dave");
  const [count, setCount] = useState(0);

  const handleNameChange = () => {
    const names = ["Dave", "Sally", "Ben", "Andrew"];
    const int = Math.floor(Math.random() * names.length);
    setName(names[int]);
  };

  const handleCount = () => {
    setCount((count) => count + 1);
  };

  const handleReset = () => {
    setCount(0);
  };

  return (
    <main>
      <h1>Hello, {name}!</h1>
      <h2>Count: {count}</h2>
      <button onClick={handleNameChange}>Change Name</button>
      <button onClick={handleCount}>Count</button>
      <button onClick={handleReset}>Reset</button>
    </main>
  );
};

export default Content;
```

# #End  </details>

<details>
  <summary>7. Rendering Lists + adding Items to LocalStorage</summary>

# Rendering Lists + adding Items to LocalStorage

<img width="976" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/c9fb229d-23d4-41f3-951f-b6d22950050c">
<img width="1158" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/87a3d8d1-4575-4b76-b031-e8c853787111">

# Install React-Icons

```bs
npm i react-icons -D
npm install react-icons --save
```

### x-dave-gray/myapp/src/App.js:

```js
import Header from "./Header";
import Content from "./Content";
import Footer from "./Footer";

function App() {
  return (
    <div className="App">
      <Header />
      <Content />
      <Footer />
    </div>
  );
}

export default App;
```

### x-dave-gray/myapp/src/Content.js:

```js
import React, { useState } from "react";
import { FaTrashAlt } from "react-icons/fa";

const Content = () => {
  const [items, setItems] = useState([
    {
      id: 1,
      checked: false,
      item: "Item 1",
    },
    {
      id: 2,
      checked: false,
      item: "Item 2",
    },
    {
      id: 3,
      checked: false,
      item: "Item 3",
    },
  ]);

  const handleCheck = (id) => {
    const listItems = items.map((item) =>
      item.id === id ? { ...item, checked: !item.checked } : item
    );
    setItems(listItems);
    localStorage.setItem("shoppinglist", JSON.stringify(listItems));
  };

  return (
    <main>
      {items.map((item) => (
        <li className="item" key={item.id}>
          <input
            onChange={() => handleCheck(item.id)}
            type="checkbox"
            checked={item.checked}
          />
          <label
            style={
              item.checked
                ? { textDecoration: "line-through" }
                : { textDecoration: "none" }
            }
            onDoubleClick={() => handleCheck(item.id)}
          >
            {item.item}
          </label>
          <FaTrashAlt role="button" tabIndex="0" />
        </li>
      ))}
    </main>
  );
};

export default Content;
```

### x-dave-gray/myapp/src/index.css:

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  font-size: 22px;
}

body {
  min-height: 100vh;
  font-family: "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Fira Sans",
    "Droid Sans", "Helvetica Neue", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.App {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100vh;
  width: 100%;
  max-width: 500px;
  border: 1px solid mediumblue;
  margin: auto;
}

header {
  width: 100%;
  padding: 0 0.25em;
  background-color: mediumblue;
  color: aliceblue;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

main {
  width: 100%;
  display: flex;
  flex-direction: column;
  flex-grow: 1;
  justify-content: flex-start;
  align-items: space-around;
  overflow-y: auto;
}

footer {
  width: 100%;
  padding: 0.25em;
  background-color: mediumblue;
  color: aliceblue;
  display: grid;
  place-content: center;
}

ul {
  width: 100%;
  list-style: none;
  padding: 0 0.25rem 0.25rem;
}

ul li::before {
  content: "\200B";
}

.item {
  display: flex;
  justify-content: flex-start;
  align-items: center;
  padding: 0.5rem 0 0.5rem 0.5rem;
  margin: 0.25rem 0;
  background-color: #eee;
}

.item:first-child {
  margin: 0;
}

.item input[type="checkbox"] {
  text-align: center;
  width: 2.5rem;
  width: 48px;
  min-width: 48px;
  height: 2.5rem;
  height: 48px;
  min-height: 48px;
  cursor: pointer;
  margin-right: 0.5rem;
}

.item input[type="checkbox"]:focus + label {
  text-decoration: underline;
}

.item > label {
  font-size: 0.75rem;
  flex-grow: 1;
}

.item svg {
  width: 48px;
  min-width: 48px;
  height: 36px;
  font-size: 1rem;
  color: steelblue;
  cursor: pointer;
}

.item svg:focus,
.item svg:hover {
  color: red;
  outline: none;
}

```

# #End  </details>

<details>
  <summary>8. Deleting Items + Removing Items from LocalStorage </summary>

# Deleting Items + Removing Items from LocalStorage

<img width="976" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/ab504664-b70b-4ab1-a351-cf59aa4260a8">
<img width="1161" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/e087edfc-dd7c-4e10-ac79-48ae3cc5655b">
<img width="1161" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/7c26bf09-bb4a-44e9-9fc3-700077ee39e7">

### x-dave-gray/myapp/src/App.js:

```js
import Header from "./Header";
import Content from "./Content";
import Footer from "./Footer";

function App() {
  return (
    <div className="App">
      <Header />
      <Content />
      <Footer />
    </div>
  );
}

export default App;

```

### x-dave-gray/myapp/src/Content.js:

```js
import React, { useState } from "react";
import { FaTrashAlt } from "react-icons/fa";

const Content = () => {
  const [items, setItems] = useState([
    {
      id: 1,
      checked: false,
      item: "Item 1",
    },
    {
      id: 2,
      checked: false,
      item: "Item 2",
    },
    {
      id: 3,
      checked: false,
      item: "Item 3",
    },
  ]);

  const handleCheck = (id) => {
    const listItems = items.map((item) =>
      item.id === id ? { ...item, checked: !item.checked } : item
    );
    setItems(listItems);
    localStorage.setItem("shoppinglist", JSON.stringify(listItems));
  };

  const handleDelete = (id) => {
    const listItems = items.filter((item) => item.id !== id);
    setItems(listItems);
    localStorage.setItem("shoppinglist", JSON.stringify(listItems));
  };

  return (
    <main>
      {items.length ? (
        <ul>
          {items.map((item) => (
            <li className="item" key={item.id}>
              <input
                onChange={() => handleCheck(item.id)}
                type="checkbox"
                checked={item.checked}
              />
              <label
                style={
                  item.checked
                    ? { textDecoration: "line-through" }
                    : { textDecoration: "none" }
                }
                onDoubleClick={() => handleCheck(item.id)}
              >
                {item.item}
              </label>
              <FaTrashAlt
                onClick={() => handleDelete(item.id)}
                role="button"
                tabIndex="0"
              />
            </li>
          ))}
        </ul>
      ) : (
        <p style={{ textAlign: "center" }}>No Items to display!</p>
      )}
    </main>
  );
};

export default Content;
```

# #End  </details>

<details>
  <summary>9. Passing Props to Components</summary>

# Passing Props to Components

<img width="977" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/faa23f27-fc82-4f83-9e90-8540ae36743b">
<img width="977" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/ab42f489-6408-49f9-a440-516c020603ad">
<img width="1161" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/df5fe0a7-da44-4a9d-a3d6-dc2e5bd68b73">

### x-dave-gray/myapp/src/App.js:

```js
import React, { useState } from "react";

import Header from "./Header";
import Content from "./Content";
import Footer from "./Footer";

function App() {
  const [items, setItems] = useState([
    {
      id: 1,
      checked: false,
      item: "Item 1",
    },
    {
      id: 2,
      checked: false,
      item: "Item 2",
    },
    {
      id: 3,
      checked: false,
      item: "Item 3",
    },
  ]);

  const handleCheck = (id) => {
    const listItems = items.map((item) =>
      item.id === id ? { ...item, checked: !item.checked } : item
    );
    setItems(listItems);
    localStorage.setItem("shoppinglist", JSON.stringify(listItems));
  };

  const handleDelete = (id) => {
    const listItems = items.filter((item) => item.id !== id);
    setItems(listItems);
    localStorage.setItem("shoppinglist", JSON.stringify(listItems));
  };

  return (
    <div className="App">
      <Header title="My Grocery List" />
      <Content
        items={items}
        handleCheck={handleCheck}
        handleDelete={handleDelete}
      />
      <Footer itemLength={items.length} />
    </div>
  );
}

export default App;
```

### x-dave-gray/myapp/src/Header.js:

```js
import React from "react";

const Header = ({ title }) => {
  return (
    <header>
      <h1>{title}</h1>
    </header>
  );
};

Header.defaultProps = {
  title: "Default Title",
};

export default Header;
```

### x-dave-gray/myapp/src/Content.js:

```js
import React from "react";
import { FaTrashAlt } from "react-icons/fa";

const Content = ({ items, handleCheck, handleDelete }) => {
  return (
    <main>
      {items.length ? (
        <ul>
          {items.map((item) => (
            <li className="item" key={item.id}>
              <input
                onChange={() => handleCheck(item.id)}
                type="checkbox"
                checked={item.checked}
              />
              <label
                style={
                  item.checked
                    ? { textDecoration: "line-through" }
                    : { textDecoration: "none" }
                }
                onDoubleClick={() => handleCheck(item.id)}
              >
                {item.item}
              </label>
              <FaTrashAlt
                onClick={() => handleDelete(item.id)}
                role="button"
                tabIndex="0"
              />
            </li>
          ))}
        </ul>
      ) : (
        <p style={{ textAlign: "center" }}>No Items to display!</p>
      )}
    </main>
  );
};

export default Content;
```

### x-dave-gray/myapp/src/Footer.js:

```js
import React from "react";

const Footer = ({ itemLength }) => {
  const today = new Date();

  const centerText = {
    textAlign: "center",
  };

  return (
    <footer>
      <p style={centerText}>
        {itemLength} List {itemLength === 1 ? "item" : "items"}
      </p>
      <p style={centerText}>Copyright &copy; {today.getFullYear()}</p>
    </footer>
  );
};

export default Footer;
```

# #End  </details>

<details>
  <summary>10. Create ItemList and LineItem Components </summary>

# Create ItemList and LineItem Components

App.js -> Content.js -> ItemList.js -> LineItem.js

<img width="977" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/7c640ba2-1c7f-42a1-bfc7-4a2ca2861371">
<img width="1162" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/5d19c5b0-5df0-44a7-8a69-d5a89aa285a6">

### x-dave-gray/myapp/src/App.js:

```js
import React, { useState } from "react";

import Header from "./Header";
import Content from "./Content";
import Footer from "./Footer";

function App() {
  const [items, setItems] = useState([
    {
      id: 1,
      checked: false,
      item: "Item 1",
    },
    {
      id: 2,
      checked: false,
      item: "Item 2",
    },
    {
      id: 3,
      checked: false,
      item: "Item 3",
    },
  ]);

  const handleCheck = (id) => {
    const listItems = items.map((item) =>
      item.id === id ? { ...item, checked: !item.checked } : item
    );
    setItems(listItems);
    localStorage.setItem("shoppinglist", JSON.stringify(listItems));
  };

  const handleDelete = (id) => {
    const listItems = items.filter((item) => item.id !== id);
    setItems(listItems);
    localStorage.setItem("shoppinglist", JSON.stringify(listItems));
  };

  return (
    <div className="App">
      <Header title="My Grocery List" />
      <Content
        items={items}
        handleCheck={handleCheck}
        handleDelete={handleDelete}
      />
      <Footer itemLength={items.length} />
    </div>
  );
}

export default App;
```

### x-dave-gray/myapp/src/Content.js:

```js
import React from "react";
import ItemList from "./ItemList";

const Content = ({ items, handleCheck, handleDelete }) => {
  return (
    <main>
      {items.length ? (
        <ItemList
          items={items}
          handleCheck={handleCheck}
          handleDelete={handleDelete}
        />
      ) : (
        <p style={{ textAlign: "center" }}>No Items to display!</p>
      )}
    </main>
  );
};

export default Content;
```

### x-dave-gray/myapp/src/ItemList.js:

```js
import React from "react";
import LineItem from "./LineItem";

const ItemList = ({ items, handleCheck, handleDelete }) => {
  return (
    <ul>
      {items.map((item) => (
        <LineItem
          key={item.id}
          item={item}
          handleCheck={handleCheck}
          handleDelete={handleDelete}
        />
      ))}
    </ul>
  );
};

export default ItemList;
```

### x-dave-gray/myapp/src/LineItem.js:

```js
import React from "react";
import { FaTrashAlt } from "react-icons/fa";

const LineItem = ({ item, handleCheck, handleDelete }) => {
  return (
    <li className="item">
      <input
        onChange={() => handleCheck(item.id)}
        type="checkbox"
        checked={item.checked}
      />
      <label
        style={
          item.checked
            ? { textDecoration: "line-through" }
            : { textDecoration: "none" }
        }
        onDoubleClick={() => handleCheck(item.id)}
      >
        {item.item}
      </label>
      <FaTrashAlt
        onClick={() => handleDelete(item.id)}
        role="button"
        tabIndex="0"
        aria-label={`Delete ${item.id}`}
      />
    </li>
  );
};

export default LineItem;
```

# #End  </details>

<details>
  <summary>11. Controlled Input - Add Items with React Forms </summary>

# Add Items with React Forms

<img width="978" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/082a9e01-2931-4329-8dcc-9800fe8dcfb1">
<img width="978" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/cb3acfad-a2f2-4032-bdc6-b73e005fc8a9">
<img width="1100" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/a859efee-774f-4ba9-bdd0-c633aff33d5d">

# Move React icons to Production Dependency:

```bs
npm i react-icons --save-prod
```

### x-dave-gray/myapp/src/App.js:

```js
import React, { useState } from "react";
import AddItem from "./AddItem";
import Header from "./Header";
import Content from "./Content";
import Footer from "./Footer";

function App() {
  const [items, setItems] = useState([
    {
      id: 1,
      checked: false,
      item: "Item 1",
    },
    {
      id: 2,
      checked: false,
      item: "Item 2",
    },
    {
      id: 3,
      checked: false,
      item: "Item 3",
    },
  ]);

  const [newItem, setNewItem] = useState("");

  const setAndSaveItems = (newItems) => {
    setItems(newItems);
    localStorage.setItem("shoppinglist", JSON.stringify(newItems));
  };

  const addItem = (item) => {
    const id = items.length ? items[items.length - 1].id + 1 : 1;
    const myNewItem = { id, checked: false, item };
    const listItems = [...items, myNewItem];
    setAndSaveItems(listItems);
  };

  const handleSubmit = (e) => {
    e.preventDefault();
    if (!newItem) return;
    addItem(newItem);
    setNewItem("");
  };

  const handleCheck = (id) => {
    const listItems = items.map((item) =>
      item.id === id ? { ...item, checked: !item.checked } : item
    );
    setAndSaveItems(listItems);
  };

  const handleDelete = (id) => {
    const listItems = items.filter((item) => item.id !== id);
    setAndSaveItems(listItems);
  };

  return (
    <div className="App">
      <Header title="My Grocery List" />
      <AddItem
        newItem={newItem}
        setNewItem={setNewItem}
        handleSubmit={handleSubmit}
      />
      <Content
        items={items}
        handleCheck={handleCheck}
        handleDelete={handleDelete}
      />
      <Footer itemLength={items.length} />
    </div>
  );
}

export default App;

```

### x-dave-gray/myapp/src/AddItem.js:

```js
import React from "react";
import { FaPlus } from "react-icons/fa";

const AddItem = ({ newItem, setNewItem, handleSubmit }) => {
  return (
    <form onSubmit={handleSubmit} className="addForm">
      <label htmlFor="addItem">Add Item</label>
      <input
        type="text"
        id="addItem"
        placeholder="Add Item"
        autoFocus
        required
        value={newItem}
        onChange={(e) => setNewItem(e.target.value)}
      />
      <button type="submit" arai-label="Add Item">
        <FaPlus />
      </button>
    </form>
  );
};

export default AddItem;

```

### x-dave-gray/myapp/src/index.css:

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  font-size: 22px;
}

body {
  min-height: 100vh;
  font-family: "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Fira Sans",
    "Droid Sans", "Helvetica Neue", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.App {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100vh;
  width: 100%;
  max-width: 500px;
  border: 1px solid mediumblue;
  margin: auto;
}

header {
  width: 100%;
  padding: 0 0.25em;
  background-color: mediumblue;
  color: aliceblue;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

main {
  width: 100%;
  display: flex;
  flex-direction: column;
  flex-grow: 1;
  justify-content: flex-start;
  align-items: space-around;
  overflow-y: auto;
}

footer {
  width: 100%;
  padding: 0.25em;
  background-color: mediumblue;
  color: aliceblue;
  display: grid;
  place-content: center;
}

ul {
  width: 100%;
  list-style: none;
  padding: 0 0.25rem 0.25rem;
}

ul li::before {
  content: "\200B";
}

.item {
  display: flex;
  justify-content: flex-start;
  align-items: center;
  padding: 0.5rem 0 0.5rem 0.5rem;
  margin: 0.25rem 0;
  background-color: #eee;
}

.item:first-child {
  margin: 0;
}

.item input[type="checkbox"] {
  text-align: center;
  width: 2.5rem;
  width: 48px;
  min-width: 48px;
  height: 2.5rem;
  height: 48px;
  min-height: 48px;
  cursor: pointer;
  margin-right: 0.5rem;
}

.item input[type="checkbox"]:focus + label {
  text-decoration: underline;
}

.item > label {
  font-size: 0.75rem;
  flex-grow: 1;
}

.item svg {
  width: 48px;
  min-width: 48px;
  height: 36px;
  font-size: 1rem;
  color: steelblue;
  cursor: pointer;
}

.item svg:focus,
.item svg:hover {
  color: red;
  outline: none;
}

.addForm {
  width: 100%;
  display: flex;
  justify-content: flex-start;
  margin: 0.5rem 0 0;
  padding: 0 0.5rem 0.25rem;
  border-bottom: 1px solid #eee;
}

.addForm label {
  position: absolute;
  left: -99999px;
}

.addForm input[type="text"] {
  flex-grow: 1;
  max-width: calc(100% - 50px);
  min-height: 48px;
  font-size: 1rem;
  padding: 0.25rem;
  border-radius: 0.25rem;
  margin-right: 0.25rem;
  outline: none;
}

button {
  height: 48px;
  min-width: 48px;
  border-radius: 0.25rem;
  padding: 0.5rem;
  font-size: 1rem;
  background-color: aliceblue;
  color: mediumblue;
  cursor: pointer;
}

button:focus,
button:hover {
  color: white;
  background-color: limegreen;
  outline: none;
}

```

# #End  </details>

<details>
  <summary>12. Fetch Items from LocalStorage Database</summary>

# Fetch Items from LocalStorage Database

<img width="976" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/89eb2c7f-6455-4c1a-938a-e5dd93751bcc">
<img width="1100" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/9e3bdfb8-b4c2-435f-a95e-5c3af7f260d3">

### x-dave-gray/myapp/src/App.js:

```jsbs
const [items, setItems] = useState(
  JSON.parse(localStorage.getItem("shoppinglist"))
);
```

```js
import React, { useState } from "react";
import AddItem from "./AddItem";
import Header from "./Header";
import Content from "./Content";
import Footer from "./Footer";

function App() {
  const [items, setItems] = useState(
    JSON.parse(localStorage.getItem("shoppinglist"))
  );

  const [newItem, setNewItem] = useState("");

  const setAndSaveItems = (newItems) => {
    setItems(newItems);
    localStorage.setItem("shoppinglist", JSON.stringify(newItems));
  };

  const addItem = (item) => {
    const id = items.length ? items[items.length - 1].id + 1 : 1;
    const myNewItem = { id, checked: false, item };
    const listItems = [...items, myNewItem];
    setAndSaveItems(listItems);
  };

  const handleSubmit = (e) => {
    e.preventDefault();
    if (!newItem) return;
    addItem(newItem);
    setNewItem("");
  };

  const handleCheck = (id) => {
    const listItems = items.map((item) =>
      item.id === id ? { ...item, checked: !item.checked } : item
    );
    setAndSaveItems(listItems);
  };

  const handleDelete = (id) => {
    const listItems = items.filter((item) => item.id !== id);
    setAndSaveItems(listItems);
  };

  return (
    <div className="App">
      <Header title="My Grocery List" />
      <AddItem
        newItem={newItem}
        setNewItem={setNewItem}
        handleSubmit={handleSubmit}
      />
      <Content
        items={items}
        handleCheck={handleCheck}
        handleDelete={handleDelete}
      />
      <Footer itemLength={items.length} />
    </div>
  );
}

export default App;

```

# #End  </details>

<details>
  <summary>13. Search Functionality with SearchItem Component </summary>

# Search Functionality with SearchItem Component

<img width="976" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/44e9a8a1-9e58-4c49-a2b5-b959d4dad1cd">
<img width="1108" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/cb582bcf-a589-4bad-aeb2-58b8d418d7ad">
<img width="1108" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/74315192-c3a5-46f6-9795-ce5e07337a89">

### x-dave-gray/myapp/src/App.js:

```js
import React, { useState } from "react";
import AddItem from "./AddItem";
import SearchItem from "./SearchItem";
import Header from "./Header";
import Content from "./Content";
import Footer from "./Footer";

function App() {
  const [items, setItems] = useState(
    JSON.parse(localStorage.getItem("shoppinglist"))
  );

  const [newItem, setNewItem] = useState("");
  const [search, setSearch] = useState("");

  const setAndSaveItems = (newItems) => {
    setItems(newItems);
    localStorage.setItem("shoppinglist", JSON.stringify(newItems));
  };

  const addItem = (item) => {
    const id = items.length ? items[items.length - 1].id + 1 : 1;
    const myNewItem = { id, checked: false, item };
    const listItems = [...items, myNewItem];
    setAndSaveItems(listItems);
  };

  const handleSubmit = (e) => {
    e.preventDefault();
    if (!newItem) return;
    addItem(newItem);
    setNewItem("");
  };

  const handleCheck = (id) => {
    const listItems = items.map((item) =>
      item.id === id ? { ...item, checked: !item.checked } : item
    );
    setAndSaveItems(listItems);
  };

  const handleDelete = (id) => {
    const listItems = items.filter((item) => item.id !== id);
    setAndSaveItems(listItems);
  };

  return (
    <div className="App">
      <Header title="My Grocery List" />
      <AddItem
        newItem={newItem}
        setNewItem={setNewItem}
        handleSubmit={handleSubmit}
      />
      <SearchItem search={search} setSearch={setSearch} />
      <Content
        items={items.filter((item) =>
          item.item.toLowerCase().includes(search.toLowerCase())
        )}
        handleCheck={handleCheck}
        handleDelete={handleDelete}
      />
      <Footer itemLength={items.length} />
    </div>
  );
}

export default App;

```

### x-dave-gray/myapp/src/SearchItem.js:

```js
import React from "react";

const SearchItem = ({ search, setSearch }) => {
  return (
    <form className="searchForm" onSubmit={(e) => e.preventDefault()}>
      <label htmlFor="search">Search</label>
      <input
        type="text"
        id="search"
        role="searchbox"
        placeholder="Search Items"
        value={search}
        onChange={(e) => setSearch(e.target.value)}
      />
    </form>
  );
};

export default SearchItem;

```

### x-dave-gray/myapp/src/index.css:

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  font-size: 22px;
}

body {
  min-height: 100vh;
  font-family: "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Fira Sans",
    "Droid Sans", "Helvetica Neue", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.App {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100vh;
  width: 100%;
  max-width: 500px;
  border: 1px solid mediumblue;
  margin: auto;
}

header {
  width: 100%;
  padding: 0 0.25em;
  background-color: mediumblue;
  color: aliceblue;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

main {
  width: 100%;
  display: flex;
  flex-direction: column;
  flex-grow: 1;
  justify-content: flex-start;
  align-items: space-around;
  overflow-y: auto;
}

footer {
  width: 100%;
  padding: 0.25em;
  background-color: mediumblue;
  color: aliceblue;
  display: grid;
  place-content: center;
}

ul {
  width: 100%;
  list-style: none;
  padding: 0 0.25rem 0.25rem;
}

ul li::before {
  content: "\200B";
}

.item {
  display: flex;
  justify-content: flex-start;
  align-items: center;
  padding: 0.5rem 0 0.5rem 0.5rem;
  margin: 0.25rem 0;
  background-color: #eee;
}

.item:first-child {
  margin: 0;
}

.item input[type="checkbox"] {
  text-align: center;
  width: 2.5rem;
  width: 48px;
  min-width: 48px;
  height: 2.5rem;
  height: 48px;
  min-height: 48px;
  cursor: pointer;
  margin-right: 0.5rem;
}

.item input[type="checkbox"]:focus + label {
  text-decoration: underline;
}

.item > label {
  font-size: 0.75rem;
  flex-grow: 1;
}

.item svg {
  width: 48px;
  min-width: 48px;
  height: 36px;
  font-size: 1rem;
  color: steelblue;
  cursor: pointer;
}

.item svg:focus,
.item svg:hover {
  color: red;
  outline: none;
}

.addForm {
  width: 100%;
  display: flex;
  justify-content: flex-start;
  margin: 0.5rem 0 0;
  padding: 0 0.5rem 0.25rem;
  border-bottom: 1px solid #eee;
}

.addForm label {
  position: absolute;
  left: -99999px;
}

.addForm input[type="text"] {
  flex-grow: 1;
  max-width: calc(100% - 50px);
  min-height: 48px;
  font-size: 1rem;
  padding: 0.25rem;
  border-radius: 0.25rem;
  margin-right: 0.25rem;
  outline: none;
}

button {
  height: 48px;
  min-width: 48px;
  border-radius: 0.25rem;
  padding: 0.5rem;
  font-size: 1rem;
  background-color: aliceblue;
  color: mediumblue;
  cursor: pointer;
}

button:focus,
button:hover {
  color: white;
  background-color: limegreen;
  outline: none;
}

.searchForm {
  width: 100%;
  display: flex;
  justify-content: flex-start;
  margin: 0.25rem 0 0;
  padding: 0 0.5rem 0.25rem;
  border-bottom: 1px solid #eee;
}

.searchForm label {
  position: absolute;
  left: -99999px;
}

.searchForm input[type="text"] {
  flex-grow: 1;
  max-width: 100%;
  min-height: 48px;
  font-size: 1rem;
  padding: 0.25rem;
  border-radius: 0.25rem;
  outline: none;
}

```

# #End  </details>

<details>
  <summary>14. Using useRef Hook to manage Input Focus</summary>

# Using useRef Hook to manage Input Focus

<img width="977" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/dc3f40c5-c753-4d91-aa0d-6c87b1a05819">
<img width="1108" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/641eaab1-c4ce-46da-ae31-247a712ad266">

### x-dave-gray/myapp/src/AddItem.js:

```js
import React, { useRef } from "react";
import { FaPlus } from "react-icons/fa";

const AddItem = ({ newItem, setNewItem, handleSubmit }) => {
  const inputRef = useRef();

  return (
    <form onSubmit={handleSubmit} className="addForm">
      <label htmlFor="addItem">Add Item</label>
      <input
        type="text"
        ref={inputRef}
        id="addItem"
        placeholder="Add Item"
        autoFocus
        required
        value={newItem}
        onChange={(e) => setNewItem(e.target.value)}
      />
      <button
        type="submit"
        arai-label="Add Item"
        onClick={() => inputRef.current.focus()}
      >
        <FaPlus />
      </button>
    </form>
  );
};

export default AddItem;

```

# #End  </details>

+COLOR SELECTOR APP

<details>
  <summary>15. Color Selector App - Introduction</summary>

# Introduction

<img width="977" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/42a12964-6cd8-4818-993a-0909425c3fa3">
<img width="1107" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/238d607f-5a91-49b9-8226-d3f2cafc0639">

# Install React App:

```bs
npx create-react-app .
npx create-react-app color-selector
```

### x-dave-gray/color-selector/src/index.js:

```js
import React from "react";
import ReactDOM from "react-dom/client";
import "./index.css";
import App from "./App";

const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);
```

### x-dave-gray/color-selector/src/App.js:

```js
import React from "react";

import Square from "./Square";
import Input from "./Input";

function App() {
  return (
    <div className="App">
      <Square />
      <Input />
    </div>
  );
}

export default App;

```

### x-dave-gray/color-selector/src/Square.js:

```js
import React from "react";

const Square = () => {
  return <h2>Square</h2>;
};

export default Square;
```

### x-dave-gray/color-selector/src/Input.js:

```js
import React from "react";

const Input = () => {
  return <h2>Input</h2>;
};

export default Input;
```

# #End  </details>

<details>
  <summary>16. Color Selector App - Style Square and Input Components</summary>

# Style Square and Input Components

<img width="977" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/43c4a2a5-9901-4333-81a2-20ab98620a51">
<img width="1107" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/9e6ccaea-36c5-4bf1-862a-be1ec92ce507">
<img width="1107" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/60ee5c1a-b01b-41f9-8645-c1e6233e0003">
<img width="1107" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/50ac974d-54dc-44f6-9f9e-f13e5d0dea20">
<img width="1107" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/91f76af7-31d7-4e3b-bc52-da67a928a64e">

### x-dave-gray/color-selector/src/colors.json:

```json
{
  "lilac": "#c8a2c8"
}
```

### x-dave-gray/color-selector/src/App.js:

```js
import React, { useState } from "react";
import Square from "./Square";
import Input from "./Input";
import colors from "./colors.json";

function App() {
  const [colorValue, setColorValue] = useState("");

  return (
    <div className="App">
      <Square colorValue={colorValue} colors={colors} />
      <Input colorValue={colorValue} setColorValue={setColorValue} />
    </div>
  );
}

export default App;
```

### x-dave-gray/color-selector/src/Square.js:

```js
import React from "react";

const Square = ({ colorValue, colors }) => {
  return (
    <section
      className="square"
      style={{ backgroundColor: colors[colorValue] || colorValue }}
    >
      <p>{colorValue ? colorValue : "Empty Value"}</p>
    </section>
  );
};

Square.defaultProps = {
  colorValue: "Empty Color Value",
};

export default Square;
```

### x-dave-gray/color-selector/src/Input.js:

```js
import React from "react";

const Input = ({ colorValue, setColorValue }) => {
  return (
    <form onSubmit={(e) => e.preventDefault()}>
      <label htmlFor="">Add Color Name:</label>
      <input
        type="text"
        placeholder="Add color name"
        value={colorValue}
        onChange={(e) => setColorValue(e.target.value)}
        autoFocus
        required
      />
    </form>
  );
};

export default Input;
```

### x-dave-gray/color-selector/src/index.css:

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  font-size: 36px;
}

body {
  min-height: 100vh;
  font-family: "Roboto", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.App {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.square {
  width: 400px;
  height: 400px;
  border: 2px solid #000;
  box-shadow: 2px 2px 5px #000;
  border-radius: 0.25rem;
  display: grid;
  place-content: center;
}

.square p {
  text-align: center;
}

form {
  width: 400px;
}

label {
  position: absolute;
  left: -99999px;
}

input[type="text"] {
  margin-top: 0.5rem;
  padding: 0.25rem;
  width: 100%;
  font-size: 1rem;
  box-shadow: 2px 2px 5px #000;
  border-radius: 0.25rem;
  outline: none;
}

button {
  width: 100%;
  min-height: 48px;
  margin-top: 0.5rem;
  font-size: 1rem;
  border-radius: 0.25rem;
  box-shadow: 2px 2px 5px #000;
  padding: 0.25rem;
}
```

# #End  </details>

<details>
  <summary>17. Color Selector App - Color Names to Hex Values</summary>

# Color Names to Hex Values

<img width="977" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/8ee4ccb6-e9f9-4ab8-933d-36ac57a45e85">
<img width="1107" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/39610ac3-ac87-49d7-b5be-b46fdb4445ae">
<img width="1107" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/7ba4e921-15f5-4c8e-8806-4b08c4ac5168">


# Install Colornames module

```bs
npm i colornames -S
```

### x-dave-gray/color-selector/src/App.js:

```js
import React, { useState } from "react";

import Square from "./Square";
import Input from "./Input";
import colors from "./colors.json";

function App() {
  const [colorValue, setColorValue] = useState("");
  const [hexValue, setHexValue] = useState("");

  return (
    <div className="App">
      <Square colorValue={colorValue} hexValue={hexValue} colors={colors} />
      <Input
        colorValue={colorValue}
        setColorValue={setColorValue}
        setHexValue={setHexValue}
        colors={colors}
      />
    </div>
  );
}

export default App;

```

### x-dave-gray/color-selector/src/Square.js:

```js
import React from "react";

const Square = ({ colorValue, colors, hexValue }) => {
  return (
    <section
      className="square"
      style={{ backgroundColor: colors[colorValue] || colorValue }}
    >
      <p>{colorValue ? colorValue : "Empty Value"}</p>
      <p>{hexValue && hexValue}</p>
    </section>
  );
};

Square.defaultProps = {
  colorValue: "Empty Color Value",
};

export default Square;
```

### x-dave-gray/color-selector/src/Input.js:

```js
import React from "react";
import colorNames from "colornames";

const Input = ({ colorValue, setColorValue, setHexValue, colors }) => {
  return (
    <form onSubmit={(e) => e.preventDefault()}>
      <label htmlFor="">Add Color Name:</label>
      <input
        type="text"
        placeholder="Add color name"
        value={colorValue}
        onChange={(e) => {
          setColorValue(e.target.value);
          setHexValue(colorNames(e.target.value) || colors[e.target.value]);
        }}
        autoFocus
        required
      />
    </form>
  );
};

export default Input;
```

### x-dave-gray/color-selector/src/colors.json:

```js
{
  "lilac": "#c8a2c8",
  "rose": "#ff007f"
}
```

# #End  </details>

<details>
  <summary>18. Color Selector App - Toggling Black and White Text</summary>

# Toggling Black and White Text

<img width="977" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/3a244918-d021-4571-a17e-a72c71d7e43f">
<img width="1106" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/bb740896-2e7a-467a-bb4b-fe6c662337d1">
<img width="1106" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/ce3a9399-e1f9-4f77-8456-87dcb7a21a88">

### x-dave-gray/color-selector/src/App.js:

```js
import React, { useState } from "react";
import Square from "./Square";
import Input from "./Input";
import colors from "./colors.json";

function App() {
  const [colorValue, setColorValue] = useState("");
  const [hexValue, setHexValue] = useState("");
  const [isDarktext, setIsDarktext] = useState(true);

  return (
    <div className="App">
      <Square
        colorValue={colorValue}
        hexValue={hexValue}
        colors={colors}
        isDarktext={isDarktext}
      />
      <Input
        colorValue={colorValue}
        setColorValue={setColorValue}
        setHexValue={setHexValue}
        colors={colors}
        isDarktext={isDarktext}
        setIsDarktext={setIsDarktext}
      />
    </div>
  );
}

export default App;
```

### x-dave-gray/color-selector/src/Square.js:

```js
import React from "react";

const Square = ({ colorValue, colors, hexValue, isDarktext }) => {
  return (
    <section
      className="square"
      style={{
        backgroundColor: colors[colorValue] || colorValue,
        color: isDarktext ? "#000" : "#fff",
      }}
    >
      <p>{colorValue ? colorValue : "Empty Value"}</p>
      <p>{hexValue && hexValue}</p>
    </section>
  );
};

Square.defaultProps = {
  colorValue: "Empty Color Value",
};

export default Square;
```

### x-dave-gray/color-selector/src/Input.js:

```js
import React from "react";
import colorNames from "colornames";

const Input = ({
  colorValue,
  setColorValue,
  setHexValue,
  colors,
  isDarktext,
  setIsDarktext,
}) => {
  return (
    <form onSubmit={(e) => e.preventDefault()}>
      <label htmlFor="">Add Color Name:</label>
      <input
        type="text"
        placeholder="Add color name"
        value={colorValue}
        onChange={(e) => {
          setColorValue(e.target.value);
          setHexValue(colorNames(e.target.value) || colors[e.target.value]);
        }}
        autoFocus
        required
      />
      <button type="button" onClick={() => setIsDarktext(!isDarktext)}>
        Toggle Text Color
      </button>
    </form>
  );
};

export default Input;
```

### x-dave-gray/color-selector/src/index.css:

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  font-size: 36px;
}

body {
  min-height: 100vh;
  font-family: "Roboto", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.App {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.square {
  width: 400px;
  height: 400px;
  border: 2px solid #000;
  box-shadow: 2px 2px 5px #000;
  border-radius: 0.25rem;
  display: grid;
  place-content: center;
}

.square p {
  text-align: center;
}

form {
  width: 400px;
}

label {
  position: absolute;
  left: -99999px;
}

input[type="text"] {
  margin-top: 0.5rem;
  padding: 0.25rem;
  width: 100%;
  font-size: 1rem;
  box-shadow: 2px 2px 5px #000;
  border-radius: 0.25rem;
  outline: none;
}

button {
  width: 100%;
  min-height: 48px;
  margin-top: 0.5rem;
  font-size: 1rem;
  border-radius: 0.25rem;
  box-shadow: 2px 2px 5px #000;
  padding: 0.25rem;
}

```

# #End  </details>

+JSON-SERVER

<details>
  <summary>19. Using useEffect to set Data</summary>

<img width="978" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/085ec7e9-1b3c-44da-b53c-8954f4b343ff">

<img width="1244" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/6b6d24d5-18cd-4861-a02b-06e0b2ad369b">

### x-dave-gray/myapp/src/App.js:

```js
import Header from "./Header";
import AddItem from "./AddItem";
import SearchItem from "./SearchItem";
import Content from "./Content";
import Footer from "./Footer";
import React, { useState, useEffect } from "react";

function App() {
  const [items, setItems] = useState(
    JSON.parse(localStorage.getItem("shoppinglist")) || []
  );
  const [newItem, setNewItem] = useState("");
  const [search, setSearch] = useState("");

  useEffect(() => {
    localStorage.setItem("shoppinglist", JSON.stringify(items));
  }, [items]);

  const handleCheck = (id) => {
    const listItems = items.map((item) =>
      item.id === id ? { ...item, checked: !item.checked } : item
    );
    setItems(listItems);
  };

  const handleDelete = (id) => {
    const listItems = items.filter((item) => item.id !== id);
    setItems(listItems);
  };

  const addItem = (item) => {
    const id = items.length ? items[items.length - 1].id + 1 : 1;
    const myNewItem = { id, checked: false, item };
    const listItems = [...items, myNewItem];
    setItems(listItems);
  };

  const handleSubmit = (e) => {
    e.preventDefault();
    if (!newItem) return;
    // addItem
    addItem(newItem);
    setNewItem("");
  };

  return (
    <div className="App">
      <Header title="Groceries List" />
      <AddItem
        newItem={newItem}
        setNewItem={setNewItem}
        handleSubmit={handleSubmit}
      />
      <SearchItem search={search} setSearch={setSearch} />
      <Content
        items={items.filter((item) =>
          item.item.toLowerCase().includes(search.toLowerCase())
        )}
        handleCheck={handleCheck}
        handleDelete={handleDelete}
      />
      <Footer itemLength={items.length} />
    </div>
  );
}

export default App;

```

# #End  </details>

<details>
  <summary>20. JSON sever - Using JSON Server</summary>

# Using JSON Server

<img width="978" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/88054acd-04c3-4785-a2c7-57c701d4244b">
<img width="1243" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/d958c0fe-6638-4922-b266-99991b98337d">
<img width="1243" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/722df0fe-272b-41c8-b653-041cfa969e6d">

# Install and start JSON Server:

```bs
npm i json-server
json-server -p 3500 --watch data/db.json
```

```bs
npx json-server -p 3500 -w data/db.json
```

### x-dave-gray/myapp/data/db.json:

```json
{
  "items": [
    {
      "id": 1,
      "checked": false,
      "item": "Almonds, Unsalted, in the blue bag"
    },
    {
      "id": 2,
      "checked": false,
      "item": "Pizza"
    },
    {
      "id": 3,
      "checked": false,
      "item": "Bread"
    }
  ]
}
```

# Fetch JSON Server for item 1:

```bs
http://localhost:3500/items/1
```

```js
// {
// "id": 1,
// "checked": false,
// "item": "Almonds, Unsalted, in the blue bag"
// }
```

# #End  </details>

<details>
  <summary>21. JSON sever - Fetch JSON API Data </summary>

# Fetch JSON API Data

<img width="978" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/4d55270a-cf52-4d43-ab27-47886d9879f0">
<img width="1243" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/c6755f13-a965-43c9-a612-c2c9136ae96d">
<img width="1244" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/6a933933-68b5-4338-9403-65f095644b07">

### x-dave-gray/myapp/src/App.js:

```js
import Header from "./Header";
import AddItem from "./AddItem";
import SearchItem from "./SearchItem";
import Content from "./Content";
import Footer from "./Footer";
import React, { useState, useEffect } from "react";

function App() {
  const API_URL = "http://localhost:3500/items";

  const [items, setItems] = useState(
    JSON.parse(localStorage.getItem("shoppinglist")) || []
  );
  const [newItem, setNewItem] = useState("");
  const [search, setSearch] = useState("");
  const [fetchError, setFetchError] = useState(null);

  useEffect(() => {
    const fetchItems = async () => {
      try {
        const response = await fetch(API_URL);
        if (!response.ok) throw new Error("Did not receive Data from API");
        const listItems = await response.json();
        console.log(listItems);
        setItems(listItems);
        setFetchError(null);
      } catch (err) {
        // console.log(err.stack);
        // console.log(err.message);
        setFetchError(err.message);
      }
    };

    fetchItems();
    //(async () => await fetchItems())();
  }, []);

  const handleCheck = (id) => {
    const listItems = items.map((item) =>
      item.id === id ? { ...item, checked: !item.checked } : item
    );
    setItems(listItems);
  };

  const handleDelete = (id) => {
    const listItems = items.filter((item) => item.id !== id);
    setItems(listItems);
  };

  const addItem = (item) => {
    const id = items.length ? items[items.length - 1].id + 1 : 1;
    const myNewItem = { id, checked: false, item };
    const listItems = [...items, myNewItem];
    setItems(listItems);
  };

  const handleSubmit = (e) => {
    e.preventDefault();
    if (!newItem) return;
    // addItem
    addItem(newItem);
    setNewItem("");
  };

  return (
    <div className="App">
      <Header title="Groceries List" />
      <AddItem
        newItem={newItem}
        setNewItem={setNewItem}
        handleSubmit={handleSubmit}
      />
      <SearchItem search={search} setSearch={setSearch} />
      <main>
        {fetchError && (
          <p
            style={{ color: "red", textAlign: "center" }}
          >{`Error: ${fetchError}`}</p>
        )}
        {!fetchError && (
          <Content
            items={items.filter((item) =>
              item.item?.toLowerCase().includes(search.toLowerCase())
            )}
            handleCheck={handleCheck}
            handleDelete={handleDelete}
          />
        )}
      </main>
      <Footer itemLength={items.length} />
    </div>
  );
}

export default App;

```

### x-dave-gray/myapp/src/Content.js:

```js
import ItemList from "./ItemList";

const Content = ({ items, handleCheck, handleDelete }) => {
  return (
    <>
      {items.length ? (
        <ItemList
          items={items}
          handleCheck={handleCheck}
          handleDelete={handleDelete}
        />
      ) : (
        <p style={{ marginTop: "2rem" }}>Your List is empty!</p>
      )}
    </>
  );
};

export default Content;
```

# #End  </details>

<details>
  <summary>22. JSON sever - SetTimeout to simulate a slow REST API Response</summary>

# SetTimeout to simulate a slow REST API Response

<img width="980" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/ed1656cd-48a6-4834-b8a2-8ce45b3d0b6b">

### x-dave-gray/myapp/src/App.js:

```bs
setTimeout(() => {
  fetchItems();
  //(async () => await fetchItems())();
}, 2000);
```

```js
import Header from "./Header";
import AddItem from "./AddItem";
import SearchItem from "./SearchItem";
import Content from "./Content";
import Footer from "./Footer";
import React, { useState, useEffect } from "react";

function App() {
  const API_URL = "http://localhost:3500/items";

  const [items, setItems] = useState([]);
  const [newItem, setNewItem] = useState("");
  const [search, setSearch] = useState("");
  const [fetchError, setFetchError] = useState(null);

  useEffect(() => {
    const fetchItems = async () => {
      try {
        const response = await fetch(API_URL);
        if (!response.ok) throw new Error("No Data Found");
        const listItems = await response.json();
        setItems(listItems);
        setFetchError(null);
      } catch (err) {
        //console.log(err.message);
        setFetchError(err.message);
      }
    };

    setTimeout(() => {
      fetchItems();
      //(async () => await fetchItems())();
    }, 2000);
  }, []);

  const handleCheck = (id) => {
    const listItems = items.map((item) =>
      item.id === id ? { ...item, checked: !item.checked } : item
    );
    setItems(listItems);
  };

  const handleDelete = (id) => {
    const listItems = items.filter((item) => item.id !== id);
    setItems(listItems);
  };

  const addItem = (item) => {
    const id = items.length ? items[items.length - 1].id + 1 : 1;
    const myNewItem = { id, checked: false, item };
    const listItems = [...items, myNewItem];
    setItems(listItems);
  };

  const handleSubmit = (e) => {
    e.preventDefault();
    if (!newItem) return;
    // addItem
    addItem(newItem);
    setNewItem("");
  };

  return (
    <div className="App">
      <Header title="Groceries List" />
      <AddItem
        newItem={newItem}
        setNewItem={setNewItem}
        handleSubmit={handleSubmit}
      />
      <SearchItem search={search} setSearch={setSearch} />
      <main>
        {fetchError && <p style={{ color: "red" }}>{`Error: ${fetchError}`}</p>}
        {!fetchError && (
          <Content
            items={items.filter((item) =>
              item.item?.toLowerCase().includes(search.toLowerCase())
            )}
            handleCheck={handleCheck}
            handleDelete={handleDelete}
          />
        )}
      </main>

      <Footer itemLength={items.length} />
    </div>
  );
}

export default App;
```

# #End  </details>

<details>
  <summary>23. JSON sever - Set isLoading Hook</summary>

# Set isLoading Hook

<img width="980" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/72166225-d84d-4589-9ffb-116c3ffca57d">
<img width="1244" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/de26770d-1cca-47d6-a579-f050d8679b8d">

### x-dave-gray/myapp/src/App.js:

```js
import Header from "./Header";
import AddItem from "./AddItem";
import SearchItem from "./SearchItem";
import Content from "./Content";
import Footer from "./Footer";
import React, { useState, useEffect } from "react";

function App() {
  const API_URL = "http://localhost:3500/items";

  const [items, setItems] = useState([]);
  const [newItem, setNewItem] = useState("");
  const [search, setSearch] = useState("");
  const [fetchError, setFetchError] = useState(null);
  const [isLoading, setIsLoading] = useState(true);

  useEffect(() => {
    const fetchItems = async () => {
      try {
        const response = await fetch(API_URL);
        if (!response.ok) throw new Error("No Data Found");
        const listItems = await response.json();
        setItems(listItems);
        setFetchError(null);
      } catch (err) {
        //console.log(err.message);
        setFetchError(err.message);
      } finally {
        setIsLoading(false);
      }
    };

    setTimeout(() => {
      fetchItems();
      //(async () => await fetchItems())();
    }, 2000);
  }, []);

  const handleCheck = (id) => {
    const listItems = items.map((item) =>
      item.id === id ? { ...item, checked: !item.checked } : item
    );
    setItems(listItems);
  };

  const handleDelete = (id) => {
    const listItems = items.filter((item) => item.id !== id);
    setItems(listItems);
  };

  const addItem = (item) => {
    const id = items.length ? items[items.length - 1].id + 1 : 1;
    const myNewItem = { id, checked: false, item };
    const listItems = [...items, myNewItem];
    setItems(listItems);
  };

  const handleSubmit = (e) => {
    e.preventDefault();
    if (!newItem) return;
    // addItem
    addItem(newItem);
    setNewItem("");
  };

  return (
    <div className="App">
      <Header title="Groceries List" />
      <AddItem
        newItem={newItem}
        setNewItem={setNewItem}
        handleSubmit={handleSubmit}
      />
      <SearchItem search={search} setSearch={setSearch} />
      <main>
        {isLoading && <p>Loading Items...</p>}
        {fetchError && <p style={{ color: "red" }}>{`Error: ${fetchError}`}</p>}
        {!fetchError && !isLoading && (
          <Content
            items={items.filter((item) =>
              item.item?.toLowerCase().includes(search.toLowerCase())
            )}
            handleCheck={handleCheck}
            handleDelete={handleDelete}
          />
        )}
      </main>

      <Footer itemLength={items.length} />
    </div>
  );
}

export default App;
```

# #End  </details>

<details>
  <summary>24. JSON server - Building API Request Function for CRUD </summary>

# Building API Request Function for CRUD

<img width="974" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/1c56e19d-bed8-4f87-8034-d5d4a16912c4">

### x-dave-gray/myapp/src/apiRequest.js:

```js
const apiRequest = async (url = "", optionsObj = null, errMsg = null) => {
  try {
    const response = await fetch(url, optionsObj);
    if (!response.ok) throw Error("Error, Please reload the app");
  } catch (err) {
    errMsg = err.message;
  } finally {
    return errMsg;
  }
};

export default apiRequest;
```

# #End  </details>

<details>
  <summary>25. JSON server - Create or POST a new Item to DB </summary>

# Create or POST a new Item to DB

<img width="971" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/1c979fbd-abc6-474c-bb39-b5f1a705c1bf">
<img width="1245" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/2b049c94-c8a2-4efa-a342-08804dc29821">
<img width="1245" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/e07cc1b7-6b65-45a2-a942-7415ca267616">

### x-dave-gray/myapp/src/App.js:

```bs
//Create/POST a new item to DB
  const addItem = async (item) => {
    const id = items.length ? items[items.length - 1].id + 1 : 1;
    const myNewItem = { id, checked: false, item };
    const listItems = [...items, myNewItem];
    setItems(listItems);

    const postOptions = {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
      },
      body: JSON.stringify(myNewItem),
    };

    const result = await apiRequest(API_URL, postOptions);
    if (result) setFetchError(result);
  };
```

```js
import Header from "./Header";
import AddItem from "./AddItem";
import SearchItem from "./SearchItem";
import Content from "./Content";
import Footer from "./Footer";
import React, { useState, useEffect } from "react";
import apiRequest from "./apiRequest";

function App() {
  const API_URL = "http://localhost:3500/items";

  const [items, setItems] = useState([]);
  const [newItem, setNewItem] = useState("");
  const [search, setSearch] = useState("");
  const [fetchError, setFetchError] = useState(null);
  const [isLoading, setIsLoading] = useState(true);

  useEffect(() => {
    const fetchItems = async () => {
      try {
        const response = await fetch(API_URL);
        if (!response.ok) throw new Error("No Data Found");
        const listItems = await response.json();
        setItems(listItems);
        setFetchError(null);
      } catch (err) {
        setFetchError(err.message);
      } finally {
        setIsLoading(false);
      }
    };

    setTimeout(() => {
      fetchItems();
    }, 2000);
  }, []);

  const handleCheck = (id) => {
    const listItems = items.map((item) =>
      item.id === id ? { ...item, checked: !item.checked } : item
    );
    setItems(listItems);
  };

  const handleDelete = (id) => {
    const listItems = items.filter((item) => item.id !== id);
    setItems(listItems);
  };

  //Create/POST a new item to DB
  const addItem = async (item) => {
    const id = items.length ? items[items.length - 1].id + 1 : 1;
    const myNewItem = { id, checked: false, item };
    const listItems = [...items, myNewItem];
    setItems(listItems);

    const postOptions = {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
      },
      body: JSON.stringify(myNewItem),
    };

    const result = await apiRequest(API_URL, postOptions);
    if (result) setFetchError(result);
  };

  const handleSubmit = (e) => {
    e.preventDefault();
    if (!newItem) return;
    addItem(newItem);
    setNewItem("");
  };

  return (
    <div className="App">
      <Header title="Groceries List" />
      <AddItem
        newItem={newItem}
        setNewItem={setNewItem}
        handleSubmit={handleSubmit}
      />
      <SearchItem search={search} setSearch={setSearch} />
      <main>
        {isLoading && <p>Loading Items...</p>}
        {fetchError && <p style={{ color: "red" }}>{`Error: ${fetchError}`}</p>}
        {!fetchError && !isLoading && (
          <Content
            items={items.filter((item) =>
              item.item?.toLowerCase().includes(search.toLowerCase())
            )}
            handleCheck={handleCheck}
            handleDelete={handleDelete}
          />
        )}
      </main>

      <Footer itemLength={items.length} />
    </div>
  );
}

export default App;
```

### x-dave-gray/myapp/data/db.json:

```json
{
  "items": [
    {
      "id": 1,
      "checked": false,
      "item": "Almonds, Unsalted, in the blue bag"
    },
    {
      "id": 2,
      "checked": false,
      "item": "Pizza"
    },
    {
      "id": 3,
      "checked": false,
      "item": "Bread"
    },
    {
      "id": 4,
      "checked": false,
      "item": "See the Doctor"
    }
  ]
}
```

# #End  </details>

<details>
  <summary>26. JSON server - Update an Item in DB</summary>

# Update an Item in DB

<img width="976" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/9606f17a-b9c5-4e08-8ae3-dd23609710b2">
<img width="1245" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/f3817c3f-cd3a-4f13-8e86-513ececce3d0">
<img width="1245" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/6942de4b-ad48-4bbe-877a-d9ccc86c3974">

### x-dave-gray/myapp/src/App.js:

```bs
//Update an item in DB
  const handleCheck = async (id) => {
    const listItems = items.map((item) =>
      item.id === id ? { ...item, checked: !item.checked } : item
    );
    setItems(listItems);

    const myItem = listItems.filter((item) => item.id === id);
    const updateOptions = {
      method: "PATCH",
      headers: {
        "Content-Type": "application/json",
      },
      body: JSON.stringify({ checked: myItem[0].checked }),
    };
    const reqUrl = `${API_URL}/${id}`;
    const result = await apiRequest(reqUrl, updateOptions);
    if (result) setFetchError(result);
  };
```

```js
import Header from "./Header";
import AddItem from "./AddItem";
import SearchItem from "./SearchItem";
import Content from "./Content";
import Footer from "./Footer";
import React, { useState, useEffect } from "react";
import apiRequest from "./apiRequest";

function App() {
  const API_URL = "http://localhost:3500/items";

  const [items, setItems] = useState([]);
  const [newItem, setNewItem] = useState("");
  const [search, setSearch] = useState("");
  const [fetchError, setFetchError] = useState(null);
  const [isLoading, setIsLoading] = useState(true);

  useEffect(() => {
    const fetchItems = async () => {
      try {
        const response = await fetch(API_URL);
        if (!response.ok) throw new Error("No Data Found");
        const listItems = await response.json();
        setItems(listItems);
        setFetchError(null);
      } catch (err) {
        setFetchError(err.message);
      } finally {
        setIsLoading(false);
      }
    };

    setTimeout(() => {
      fetchItems();
    }, 2000);
  }, []);

  //Update an item in DB
  const handleCheck = async (id) => {
    const listItems = items.map((item) =>
      item.id === id ? { ...item, checked: !item.checked } : item
    );
    setItems(listItems);

    const myItem = listItems.filter((item) => item.id === id);
    const updateOptions = {
      method: "PATCH",
      headers: {
        "Content-Type": "application/json",
      },
      body: JSON.stringify({ checked: myItem[0].checked }),
    };
    const reqUrl = `${API_URL}/${id}`;
    const result = await apiRequest(reqUrl, updateOptions);
    if (result) setFetchError(result);
  };

  const handleDelete = (id) => {
    const listItems = items.filter((item) => item.id !== id);
    setItems(listItems);
  };

  //Create/POST a new item to DB
  const addItem = async (item) => {
    const id = items.length ? items[items.length - 1].id + 1 : 1;
    const myNewItem = { id, checked: false, item };
    const listItems = [...items, myNewItem];
    setItems(listItems);

    const postOptions = {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
      },
      body: JSON.stringify(myNewItem),
    };

    const result = await apiRequest(API_URL, postOptions);
    if (result) setFetchError(result);
  };

  const handleSubmit = (e) => {
    e.preventDefault();
    if (!newItem) return;
    addItem(newItem);
    setNewItem("");
  };

  return (
    <div className="App">
      <Header title="Groceries List" />
      <AddItem
        newItem={newItem}
        setNewItem={setNewItem}
        handleSubmit={handleSubmit}
      />
      <SearchItem search={search} setSearch={setSearch} />
      <main>
        {isLoading && <p>Loading Items...</p>}
        {fetchError && <p style={{ color: "red" }}>{`Error: ${fetchError}`}</p>}
        {!fetchError && !isLoading && (
          <Content
            items={items.filter((item) =>
              item.item?.toLowerCase().includes(search.toLowerCase())
            )}
            handleCheck={handleCheck}
            handleDelete={handleDelete}
          />
        )}
      </main>

      <Footer itemLength={items.length} />
    </div>
  );
}

export default App;
```

### x-dave-gray/myapp/data/db.json:

```json
{
  "items": [
    {
      "id": 1,
      "checked": false,
      "item": "Almonds, Unsalted, in the blue bag"
    },
    {
      "id": 2,
      "checked": false,
      "item": "Pizza"
    },
    {
      "id": 3,
      "checked": false,
      "item": "Bread"
    },
    {
      "id": 4,
      "checked": true,
      "item": "See the Doctor"
    }
  ]
}
```

# #End  </details>

<details>
  <summary>27. JSON server - Delete an Item in DB</summary>

# Delete an Item in DB

<img width="976" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/f1f11c84-6714-4540-8f47-e84aee44e68b">
<img width="1245" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/42e27550-3300-4cc0-86be-a53083a68394">
<img width="1245" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/ac903aa0-f461-4252-8a65-8b7c5c0adb47">

### x-dave-gray/myapp/src/App.js:

```bs
//Delete an item in DB
  const handleDelete = async (id) => {
    const listItems = items.filter((item) => item.id !== id);
    setItems(listItems);

    const deleteOptions = { method: "DELETE" };
    const reqUrl = `${API_URL}/${id}`;
    const result = await apiRequest(reqUrl, deleteOptions);
    if (result) setFetchError(result);
  };
```

```js
import Header from "./Header";
import AddItem from "./AddItem";
import SearchItem from "./SearchItem";
import Content from "./Content";
import Footer from "./Footer";
import React, { useState, useEffect } from "react";
import apiRequest from "./apiRequest";

function App() {
  const API_URL = "http://localhost:3500/items";

  const [items, setItems] = useState([]);
  const [newItem, setNewItem] = useState("");
  const [search, setSearch] = useState("");
  const [fetchError, setFetchError] = useState(null);
  const [isLoading, setIsLoading] = useState(true);

  useEffect(() => {
    const fetchItems = async () => {
      try {
        const response = await fetch(API_URL);
        if (!response.ok) throw new Error("No Data Found");
        const listItems = await response.json();
        setItems(listItems);
        setFetchError(null);
      } catch (err) {
        setFetchError(err.message);
      } finally {
        setIsLoading(false);
      }
    };

    setTimeout(() => {
      fetchItems();
    }, 2000);
  }, []);

  //Delete an item in DB
  const handleDelete = async (id) => {
    const listItems = items.filter((item) => item.id !== id);
    setItems(listItems);

    const deleteOptions = { method: "DELETE" };
    const reqUrl = `${API_URL}/${id}`;
    const result = await apiRequest(reqUrl, deleteOptions);
    if (result) setFetchError(result);
  };

  //Update an item in DB
  const handleCheck = async (id) => {
    const listItems = items.map((item) =>
      item.id === id ? { ...item, checked: !item.checked } : item
    );
    setItems(listItems);

    const myItem = listItems.filter((item) => item.id === id);
    const updateOptions = {
      method: "PATCH",
      headers: {
        "Content-Type": "application/json",
      },
      body: JSON.stringify({ checked: myItem[0].checked }),
    };
    const reqUrl = `${API_URL}/${id}`;
    const result = await apiRequest(reqUrl, updateOptions);
    if (result) setFetchError(result);
  };

  //Create/POST a new item to DB
  const addItem = async (item) => {
    const id = items.length ? items[items.length - 1].id + 1 : 1;
    const myNewItem = { id, checked: false, item };
    const listItems = [...items, myNewItem];
    setItems(listItems);

    const postOptions = {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
      },
      body: JSON.stringify(myNewItem),
    };

    const result = await apiRequest(API_URL, postOptions);
    if (result) setFetchError(result);
  };

  const handleSubmit = (e) => {
    e.preventDefault();
    if (!newItem) return;
    addItem(newItem);
    setNewItem("");
  };

  return (
    <div className="App">
      <Header title="Groceries List" />
      <AddItem
        newItem={newItem}
        setNewItem={setNewItem}
        handleSubmit={handleSubmit}
      />
      <SearchItem search={search} setSearch={setSearch} />
      <main>
        {isLoading && <p>Loading Items...</p>}
        {fetchError && <p style={{ color: "red" }}>{`Error: ${fetchError}`}</p>}
        {!fetchError && !isLoading && (
          <Content
            items={items.filter((item) =>
              item.item?.toLowerCase().includes(search.toLowerCase())
            )}
            handleCheck={handleCheck}
            handleDelete={handleDelete}
          />
        )}
      </main>

      <Footer itemLength={items.length} />
    </div>
  );
}

export default App;
```

### x-dave-gray/myapp/data/db.json:

```json
{
  "items": [
    {
      "id": 1,
      "checked": false,
      "item": "Almonds, Unsalted, in the blue bag"
    },
    {
      "id": 2,
      "checked": false,
      "item": "Pizza"
    },
    {
      "id": 3,
      "checked": false,
      "item": "Bread"
    }
  ]
}
```

# #End  </details>

+FETCH API TASK WITH JSONPLACEHOLDER

<details>
  <summary>28. Fetch API Task with JSONPLACEHOLDER - Introduction </summary>

# Fetch API Task with JSONPLACEHOLDER - Introduction

<img width="1245" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/59f95f15-11e3-4a51-9851-e1cc664bad31">
<img width="1245" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/1d3cd93c-63de-47c0-b6d6-1ba5c276bbeb">
<img width="1245" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/321c2427-ab8d-49fe-9bd8-488f58974ec3">
<img width="1245" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/0e4ad0b2-1c1e-48a8-a2f6-3cb1977b5d4b">

# Endpoints

```bs
https://jsonplaceholder.typicode.com/
https://jsonplaceholder.typicode.com/users
https://jsonplaceholder.typicode.com/posts
https://jsonplaceholder.typicode.com/comments
https://jsonplaceholder.typicode.com/albums
https://jsonplaceholder.typicode.com/photos
https://jsonplaceholder.typicode.com/todos
```

```bs
/posts	  100 posts
/comments	500 comments
/albums	  100 albums
/photos	  5000 photos
/todos	  200 todos
/users	  10 users
```

# HTTP Methods

```bs
GET	    /posts
GET	    /posts/1
GET	    /posts/1/comments
GET	    /comments?postId=1
POST	  /posts
PUT	    /posts/1
PATCH	  /posts/1
DELETE	/posts/1
```

# Fetch a Todo Item

```bs
fetch('https://jsonplaceholder.typicode.com/todos/1')
      .then(response => response.json())
      .then(json => console.log(json))
```

# #End  </details>

<details>
  <summary>29. Fetch API Task with JSONPLACEHOLDER - Create Challenge App</summary>

# Create Challenge App

<img width="977" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/dabbec9b-89a9-42c3-a8bf-bdf257f5af0b">
<img width="1245" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/07821a44-4640-48fd-b0d7-f82fb12e6bdb">

# Install React App

```jsbs
npx create-react-app challenge
yarn create react-app challenge
```

### x-dave-gray/challenge/src/index.js:

```js
import React from "react";
import ReactDOM from "react-dom/client";
import "./index.css";
import App from "./App";

const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);
```

### x-dave-gray/challenge/src/App.js:

```js
import React from "react";

function App() {
  return (
    <div className="App">
      <h1>Challenge Page</h1>
    </div>
  );
}

export default App;
```

# #End  </details>

<details>
  <summary>30. Fetch API Task with JSONPLACEHOLDER - Challenge 1</summary>

# Challenge 1 - Fetch and display users, posts and comments data

<img width="977" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/54325a43-d917-4677-8df5-7ee7deb12c1c">
<img width="1245" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/089fd607-9e1e-412a-8994-239f5eb619c9">
<img width="1245" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/ce4a79d9-238a-428b-8b7e-f3afff4c1335">
<img width="1245" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/7b54df53-9ab6-41db-852f-fe9cebfe6c72">

### x-dave-gray/challenge/src/App.js:

```js
import { useState, useEffect } from "react";

function App() {
  const API_URL = "https://jsonplaceholder.typicode.com/";
  const [reqType, setReqType] = useState("users");
  const [items, setItems] = useState([]);
  const [errMsg, setErrMsg] = useState("");

  useEffect(() => {
    const fetchItems = async () => {
      try {
        setErrMsg("");
        const response = await fetch(`${API_URL}${reqType}`);
        if (!response.ok) throw new Error("No Data!");
        const data = await response.json();
        setItems(data);
      } catch (err) {
        setErrMsg(`Error: ${err.message}`);
      } finally {
        //
      }
    };

    fetchItems();
  }, [reqType]);

  return (
    <div className="App">
      <header className="header">
        <button onClick={(e) => setReqType(e.target.innerHTML)}>users</button>
        <button onClick={(e) => setReqType(e.target.innerHTML)}>posts</button>
        <button onClick={(e) => setReqType(e.target.innerHTML)}>
          comments
        </button>
      </header>
      <main>
        <h2 style={{ color: "red" }}>{errMsg}</h2>
        <ul>
          {!errMsg && items.map((item) => <li>{JSON.stringify(item)}</li>)}
        </ul>
      </main>
    </div>
  );
}

export default App;
```

### x-dave-gray/challenge/src/index.css:

```css
body {
  margin: 0;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto",
    "Oxygen", "Ubuntu", "Cantarell", "Fira Sans", "Droid Sans",
    "Helvetica Neue", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

code {
  font-family: source-code-pro, Menlo, Monaco, Consolas, "Courier New",
    monospace;
}

.header {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
}

.header > button {
  cursor: pointer;
  padding: 1rem;
}

button:focus,
button:active,
button:hover {
  background-color: #141414;
  color: #fff;
}
```

# #End  </details>

<details>
  <summary>31. Fetch API Task with JSONPLACEHOLDER - Challenge 2</summary>

# Challenge 2 - Create Components to organise app

<img width="976" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/ff368da4-9ff6-4b17-8eac-9aabe35c5023">
<img width="1226" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/dc2bc101-e160-4ee0-bfd4-485580f4caf9">
<img width="1226" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/ecb2344c-b8dd-44c7-977e-102f20e10b02">
<img width="1226" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/f28e3340-73ab-4cab-b953-2dbd83a1269e">

### x-dave-gray/challenge/src/App.js:

```js
import { useState, useEffect } from "react";
import Form from "./Form";
import List from "./List";

function App() {
  const API_URL = "https://jsonplaceholder.typicode.com/";
  const [reqType, setReqType] = useState("users");
  const [items, setItems] = useState([]);
  const [errMsg, setErrMsg] = useState("");

  useEffect(() => {
    const fetchItems = async () => {
      try {
        setErrMsg("");
        const response = await fetch(`${API_URL}${reqType}`);
        if (!response.ok) throw new Error("No Data!");
        const data = await response.json();
        setItems(data);
      } catch (err) {
        setErrMsg(`Error: ${err.message}`);
      } finally {
        //
      }
    };

    fetchItems();
  }, [reqType]);

  return (
    <div className="App">
      <Form reqType={reqType} setReqType={setReqType} />
      <List items={items} errMsg={errMsg} />
    </div>
  );
}

export default App;
```

### x-dave-gray/challenge/src/Form.js:

```js
import React from "react";
import Button from "./Button";

const Form = ({ reqType, setReqType }) => {
  return (
    <form onSubmit={(e) => e.preventDefault()}>
      <Button buttonText="users" reqType={reqType} setReqType={setReqType} />
      <Button buttonText="posts" reqType={reqType} setReqType={setReqType} />
      <Button buttonText="comments" reqType={reqType} setReqType={setReqType} />
    </form>
  );
};

export default Form;
```

### x-dave-gray/challenge/src/Button.js:

```js
import React from "react";

const Button = ({ buttonText, reqType, setReqType }) => {
  return (
    <button
      className={buttonText === reqType ? "selected" : null}
      type="button"
      onClick={(e) => setReqType(buttonText)}
    >
      {buttonText}
    </button>
  );
};

export default Button;
```

### x-dave-gray/challenge/src/List.js:

```js
import React from "react";
import ListItem from "./ListItem";

const List = ({ items, errMsg }) => {
  return (
    <main>
      <h2 style={{ color: "red" }}>{errMsg}</h2>
      <ul>
        {!errMsg && items.map((item) => <ListItem key={item.id} item={item} />)}
      </ul>
    </main>
  );
};

export default List;
```

### x-dave-gray/challenge/src/ListItem.js:

```js
import React from "react";

const ListItem = ({ item }) => {
  return <li>{JSON.stringify(item)}</li>;
};

export default ListItem;
```

### x-dave-gray/challenge/src/index.css:

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  font-size: 22px;
}

body {
  min-height: 100vh;
  font-family: "Roboto", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

form {
  width: 100%;
  position: fixed;
}

button {
  width: 33.33%;
  padding: 0.5rem;
  font-size: 1rem;
}

button.selected {
  background-color: #000;
  color: #fff;
}

ul {
  padding: 3rem 2rem 1rem;
}

li {
  margin-bottom: 1rem;
}

.table-container {
  width: 100%;
  overflow-y: auto;
  padding-top: 52px;
}

td {
  border: 1px solid #000;
  padding: 0.25rem;
}
```

# #End  </details>

<details>
  <summary>32. Fetch API Task with JSONPLACEHOLDER - Challenge 3</summary>

# Challenge 3 - Sort data into Table

<img width="977" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/94989216-6930-48cc-b096-22e3138f227f">
<img width="1214" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/71a3a101-def4-41ab-8c01-0781b35f7c94">
<img width="1214" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/9a43f1d5-4b28-4073-929d-58a1545c7541">
<img width="1214" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/0710751b-2bfc-4953-abfe-cb81306f29ac">

### x-dave-gray/challenge/src/App.js:

```js
import { useState, useEffect } from "react";
import Form from "./Form";
// import List from "./List";
import Table from "./Table";

function App() {
  const API_URL = "https://jsonplaceholder.typicode.com/";
  const [reqType, setReqType] = useState("users");
  const [items, setItems] = useState([]);
  const [errMsg, setErrMsg] = useState("");

  useEffect(() => {
    const fetchItems = async () => {
      try {
        setErrMsg("");
        const response = await fetch(`${API_URL}${reqType}`);
        if (!response.ok) throw new Error("No Data!");
        const data = await response.json();
        setItems(data);
      } catch (err) {
        setErrMsg(`Error: ${err.message}`);
      } finally {
        //
      }
    };

    fetchItems();
  }, [reqType]);

  return (
    <div className="App">
      <Form reqType={reqType} setReqType={setReqType} />
      {/* <List items={items} errMsg={errMsg} /> */}
      <Table items={items} errMsg={errMsg} />
    </div>
  );
}

export default App;
```

### x-dave-gray/challenge/src/Table.js:

```js
import React from "react";
import Row from "./Row";

const Table = ({ items, errMsg }) => {
  return (
    <div className="table-container">
      <h2 style={{ color: "red" }}>{errMsg}</h2>
      <table>
        <tbody>
          {items.map((item) => (
            <Row key={item.id} item={item} />
          ))}
        </tbody>
      </table>
    </div>
  );
};

export default Table;
```

### x-dave-gray/challenge/src/Row.js:

```js
import React from "react";
import Cell from "./Cell";

const Row = ({ item }) => {
  return (
    <tr>
      {Object.entries(item).map(([key, value]) => (
        <Cell key={key} cellData={JSON.stringify(value)} />
      ))}
    </tr>
  );
};

export default Row;
```

### x-dave-gray/challenge/src/Cell.js:

```js
import React from "react";

const Cell = ({ cellData }) => {
  return <td>{cellData}</td>;
};

export default Cell;
```

### x-dave-gray/challenge/src/index.css:

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  font-size: 22px;
}

body {
  min-height: 100vh;
  font-family: "Roboto", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

form {
  width: 100%;
  position: fixed;
}

button {
  width: 33.33%;
  padding: 0.5rem;
  font-size: 1rem;
}

button.selected {
  background-color: #000;
  color: #fff;
}

ul {
  padding: 3rem 2rem 1rem;
}

li {
  margin-bottom: 1rem;
}

.table-container {
  width: 100%;
  overflow-y: auto;
  padding-top: 52px;
}

td {
  border: 1px solid #000;
  padding: 0.25rem;
}
```

# #End  </details>

+BLOG APP

<details>
  <summary>33. Blog App - Setup App with React-Router-DOM</summary>

# Setup App with React-Router-DOM

<img width="976" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/eb868864-0055-41cd-9413-0c9ac46e7660">
<img width="1215" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/f7786ca5-5dee-42e9-94f2-9efba3e50a6a">

# Create React App:

```bs
npx create-react-app .
npx create-react-app blogapp
yarn create react-app blogapp
```

# Install React-Router-DOM:

```bs
npm i react-router-dom -S
npm i react-router-dom@6 -S
```

# Update React-Router-DOM:

```bs
npm update react-router-dom
```

# Run React Server:

```bs
npm start
npm run start
```

### x-dave-gray/blogapp/src/index.js:

```js
import React from "react";
import ReactDOM from "react-dom/client";
import "./index.css";
import App from "./App";
import { BrowserRouter as Router, Routes, Route } from "react-router-dom";

const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(
  <React.StrictMode>
    <Router>
      <Routes>
        <Route path="/*" element={<App />} />
      </Routes>
    </Router>
  </React.StrictMode>
);

```

### x-dave-gray/blogapp/src/App.js:

```js
import React from "react";

function App() {
  return (
    <div className="App">
      <h1>Blog App</h1>
    </div>
  );
}

export default App;
```

# #End  </details>

<details>
  <summary>34. Blog App - Routing Components</summary>

# Routing Components

<img width="979" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/3103c4bc-e046-4033-ba52-48199bcf3f83">

# http://localhost:3000/

<img width="1215" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/7c7a0ba5-f7a0-4b54-a56f-a4014c06165b">

# http://localhost:3000/post

<img width="1215" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/9d0c07fb-e0c4-4c7d-aae8-5105cf5eacb0">

# http://localhost:3000/post/1

<img width="1215" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/069d8785-3ae1-4ca2-afbc-4cbf8a81d764">

# http://localhost:3000/about

<img width="1215" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/20cda8b3-0783-49fc-9b22-6c2675458a28">

### x-dave-gray/blogapp/src/index.js:

```js
import React from "react";
import ReactDOM from "react-dom/client";
import "./index.css";
import App from "./App";
import { BrowserRouter as Router, Routes, Route } from "react-router-dom";

const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(
  <React.StrictMode>
    <Router>
      <Routes>
        <Route path="/*" element={<App />} />
      </Routes>
    </Router>
  </React.StrictMode>
);
```

### x-dave-gray/blogapp/src/App.js:

```js
import { useState, useEffect } from "react";
import { Route, Routes, useNavigate } from "react-router-dom";
import Header from "./Header";
import Nav from "./Nav";
import Footer from "./Footer";
import Home from "./Home";
import NewPost from "./NewPost";
import PostPage from "./PostPage";
import About from "./About";
import Missing from "./Missing";

function App() {
  return (
    <div className="App">
      <Header />
      <Nav />
      <Routes>
        <Route exact path="/" element={<Home />} />
        <Route exact path="/post" element={<NewPost />} />
        <Route path="/post/:id" element={<PostPage />} />
        <Route path="/about" element={<About />} />
        <Route path="*" element={<Missing />} />
      </Routes>
      <Footer />
    </div>
  );
}

export default App;
```

### x-dave-gray/blogapp/src/Header.js:

```js
import React from "react";

const Header = () => {
  return (
    <header>
      <h1>Header</h1>
    </header>
  );
};

export default Header;
```

### x-dave-gray/blogapp/src/Nav.js:

```js
import React from "react";

const Nav = () => {
  return (
    <nav>
      <h1>Nav</h1>
    </nav>
  );
};

export default Nav;
```

### x-dave-gray/blogapp/src/Home.js:

```js
import React from "react";

const Home = () => {
  return (
    <main>
      <h1>Home</h1>
    </main>
  );
};

export default Home;
```

### x-dave-gray/blogapp/src/NewPost.js:

```js
import React from "react";

const NewPost = () => {
  return (
    <main>
      <h1>NewPost</h1>
    </main>
  );
};

export default NewPost;
```

### x-dave-gray/blogapp/src/PostPage.js:

```js
import React from "react";

const PostPage = () => {
  return (
    <main>
      <h1>PostPage</h1>
    </main>
  );
};

export default PostPage;
```

### x-dave-gray/blogapp/src/About.js:

```js
import React from "react";

const About = () => {
  return (
    <main>
      <h1>About</h1>
    </main>
  );
};

export default About;
```

### x-dave-gray/blogapp/src/Missing.js:

```js
import React from "react";

const Missing = () => {
  return (
    <main>
      <h1>Missing</h1>
    </main>
  );
};

export default Missing;
```

### x-dave-gray/blogapp/src/Footer.js:

```js
import React from "react";

const Footer = () => {
  return (
    <footer>
      <h1>Footer</h1>
    </footer>
  );
};

export default Footer;
```

# #End  </details>

<details>
  <summary>35. Blog App - Customising Header Component </summary>

# Customising Header Component

<img width="979" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/0667513d-9f8f-4f4c-a520-8a18c0afc7ce">
<img width="1215" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/4b87395d-c3de-42a1-bccc-851ea67d71e9">

### x-dave-gray/blogapp/src/App.js:

```js
import { useState, useEffect } from "react";
import { Route, Routes, useNavigate } from "react-router-dom";
import Header from "./Header";
import Nav from "./Nav";
import Footer from "./Footer";
import Home from "./Home";
import NewPost from "./NewPost";
import PostPage from "./PostPage";
import About from "./About";
import Missing from "./Missing";

function App() {
  return (
    <div className="App">
      <Header title="React JS Blog" />
      <Nav />
      <Routes>
        <Route exact path="/" element={<Home />} />
        <Route exact path="/post" element={<NewPost />} />
        <Route path="/post/:id" element={<PostPage />} />
        <Route path="/about" element={<About />} />
        <Route path="*" element={<Missing />} />
      </Routes>
      <Footer />
    </div>
  );
}

export default App;
```

### x-dave-gray/blogapp/src/Header.js:

```js
import React from "react";

const Header = ({ title }) => {
  return (
    <header className="Header">
      <h1>{title}</h1>
    </header>
  );
};

export default Header;
```

### x-dave-gray/blogapp/src/index.css:

```css
@import url("https://fonts.googleapis.com/css2?family=Open+Sans&display=swap");

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  font-size: 16px;
}

body {
  min-height: 100vh;
  font-family: "Open Sans", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: flex;
  background-color: #efefef;
}

#root {
  flex-grow: 1;
  display: flex;
  justify-content: center;
  align-items: center;
}

.App {
  width: 100%;
  max-width: 800px;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
  border: 1px solid #333;
  box-shadow: 0px 0px 15px gray;
}

.Header,
.Footer {
  width: 100%;
  background-color: #66d8f5;
  padding: 1rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.Header h1 {
  font-size: 1.5rem;
}

.Header svg {
  font-size: 2rem;
}

.Footer {
  padding: 0.75rem;
  display: grid;
  place-content: center;
}

.Nav {
  width: 100%;
  background-color: #333;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: flex-start;
}

.searchForm {
  width: 80%;
  padding: 1rem 0 0 0.75rem;
}

.searchForm input[type="text"] {
  font-family: "Open Sans", sans-serif;
  width: 100%;
  min-height: 48px;
  font-size: 1rem;
  padding: 0.25rem;
  border-radius: 0.25rem;
  outline: none;
}

.searchForm label {
  position: absolute;
  left: -99999px;
}

.Nav ul {
  color: #fff;
  list-style-type: none;
  display: flex;
  flex-wrap: nowrap;
  align-items: center;
}

.Nav li {
  padding: 1rem;
}

.Nav li:hover,
.Nav li:focus {
  padding: 1rem;
}

.Nav li a {
  color: #fff;
  text-decoration: none;
}

.Nav li:hover,
.Nav li:focus,
.Nav li:hover a,
.Nav li:focus a {
  background-color: #eee;
  color: #333;
}

.Nav li:hover a,
.Nav li:focus a {
  cursor: pointer;
}

.Home,
.NewPost,
.PostPage,
.About,
.Missing {
  width: 100%;
  flex-grow: 1;
  padding: 1rem;
  overflow-y: auto;
  background-color: #fff;
}

.post {
  margin-top: 1rem;
  padding-bottom: 1rem;
  border-bottom: 1px solid lightgray;
}

.Home .post a {
  text-decoration: none;
}

.Home .post a,
.Home .post a:visited {
  color: #000;
}

.post:first-child {
  margin-top: 0;
}

.post:last-child {
  border-bottom: none;
}

.postDate {
  font-size: 0.75rem;
  margin-top: 0.25rem;
}

.postBody {
  margin: 1rem 0;
}

.newPostForm {
  display: flex;
  flex-direction: column;
}

.newPostForm label {
  margin-top: 1rem;
}

.newPostForm input[type="text"],
.newPostForm textarea {
  font-family: "Open Sans", sans-serif;
  width: 100%;
  min-height: 48px;
  font-size: 1rem;
  padding: 0.25rem;
  border-radius: 0.25rem;
  margin-right: 0.25rem;
  outline: none;
}

.newPostForm textarea {
  height: 100px;
}

.newPostForm button {
  margin-top: 1rem;
  height: 48px;
  min-width: 48px;
  border-radius: 10px;
  padding: 0.5rem;
  font-size: 1rem;
  cursor: pointer;
}

.Missing h2,
.PostPage h2,
.Missing p,
.PostPage p {
  margin-bottom: 1rem;
}

.PostPage button {
  height: 48px;
  min-width: 48px;
  border-radius: 0.25rem;
  padding: 0.5rem;
  font-size: 1rem;
  background-color: red;
  color: #fff;
  cursor: pointer;
}

.statusMsg {
  margin-top: 2rem;
}

@media only screen and (min-width: 610px) {
  html {
    font-size: 22px;
  }

  .Header h1 {
    font-size: 2rem;
  }

  .Nav {
    flex-direction: row;
    flex-wrap: nowrap;
    justify-content: space-between;
    align-items: center;
  }

  .Nav ul {
    text-align: right;
  }

  .Nav li:hover,
  .Nav li:focus,
  .Nav li:hover a,
  .Nav li:focus a {
    background-color: #eee;
    color: #333;
  }

  .searchForm {
    width: 50%;
    padding: 0.5rem 0;
  }

  .searchForm input[type="text"] {
    margin-left: 0.5rem;
  }

  .newPostForm textarea {
    height: 300px;
  }
}

@media only screen and (min-width: 992px) {
  .Header svg {
    font-size: 3rem;
  }
}
```

# #End  </details>

<details>
  <summary>36. Blog App - Customizing Nav Component</summary>

# Customizing Nav Component

<img width="978" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/7b590a02-0c18-4ac6-813e-5abcc149489e">
<img width="1213" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/ef3a3b91-7c5a-4a2a-a36d-a3d59d380e27">

### x-dave-gray/blogapp/src/App.js:

```js
import { useState, useEffect } from "react";
import { Route, Routes, useNavigate } from "react-router-dom";
import Header from "./Header";
import Nav from "./Nav";
import Footer from "./Footer";
import Home from "./Home";
import NewPost from "./NewPost";
import PostPage from "./PostPage";
import About from "./About";
import Missing from "./Missing";

function App() {
  const [search, setSearch] = useState("");
  const [searchResults, setSearchResults] = useState([]);
  const [posts, setPosts] = useState([
    {
      id: 1,
      title: "My First Post",
      datetime: "July 01, 2021 11:17:36 AM",
      body: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis consequatur expedita, assumenda similique non optio! Modi nesciunt excepturi corrupti atque blanditiis quo nobis, non optio quae possimus illum exercitationem ipsa!",
    },
    {
      id: 2,
      title: "My 2nd Post",
      datetime: "July 01, 2021 11:17:36 AM",
      body: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis consequatur expedita, assumenda similique non optio! Modi nesciunt excepturi corrupti atque blanditiis quo nobis, non optio quae possimus illum exercitationem ipsa!",
    },
    {
      id: 3,
      title: "My 3rd Post",
      datetime: "July 01, 2021 11:17:36 AM",
      body: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis consequatur expedita, assumenda similique non optio! Modi nesciunt excepturi corrupti atque blanditiis quo nobis, non optio quae possimus illum exercitationem ipsa!",
    },
    {
      id: 4,
      title: "My Fourth Post",
      datetime: "July 01, 2021 11:17:36 AM",
      body: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis consequatur expedita, assumenda similique non optio! Modi nesciunt excepturi corrupti atque blanditiis quo nobis, non optio quae possimus illum exercitationem ipsa!",
    },
  ]);

  return (
    <div className="App">
      <Header title="React JS Blog" />
      <Nav search={search} setSearch={setSearch} />
      <Routes>
        <Route exact path="/" element={<Home />} />
        <Route exact path="/post" element={<NewPost />} />
        <Route path="/post/:id" element={<PostPage />} />
        <Route path="/about" element={<About />} />
        <Route path="*" element={<Missing />} />
      </Routes>
      <Footer />
    </div>
  );
}

export default App;
```

### x-dave-gray/blogapp/src/Nav.js:

```js
import React from "react";
import { Link } from "react-router-dom";

const Nav = ({ search, setSearch }) => {
  return (
    <nav className="Nav">
      <form className="searchForm" onSubmit={(e) => e.preventDefault()}>
        <label htmlFor="search">Search Posts</label>
        <input
          id="search"
          type="text"
          placeholder="Search Posts"
          value={search}
          onChange={(e) => setSearch(e.target.value)}
        />
      </form>
      <ul>
        <li>
          <Link to="/">Home</Link>
        </li>
        <li>
          <Link to="/post">Post</Link>
        </li>
        <li>
          <Link to="/about">About</Link>
        </li>
      </ul>
    </nav>
  );
};

export default Nav;
```

### x-dave-gray/blogapp/src/index.css:

```css
@import url("https://fonts.googleapis.com/css2?family=Open+Sans&display=swap");

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  font-size: 16px;
}

body {
  min-height: 100vh;
  font-family: "Open Sans", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: flex;
  background-color: #efefef;
}

#root {
  flex-grow: 1;
  display: flex;
  justify-content: center;
  align-items: center;
}

.App {
  width: 100%;
  max-width: 800px;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
  border: 1px solid #333;
  box-shadow: 0px 0px 15px gray;
}

.Header,
.Footer {
  width: 100%;
  background-color: #66d8f5;
  padding: 1rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.Header h1 {
  font-size: 1.5rem;
}

.Header svg {
  font-size: 2rem;
}

.Footer {
  padding: 0.75rem;
  display: grid;
  place-content: center;
}

.Nav {
  width: 100%;
  background-color: #333;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: flex-start;
}

.searchForm {
  width: 80%;
  padding: 1rem 0 0 0.75rem;
}

.searchForm input[type="text"] {
  font-family: "Open Sans", sans-serif;
  width: 100%;
  min-height: 48px;
  font-size: 1rem;
  padding: 0.25rem;
  border-radius: 0.25rem;
  outline: none;
}

.searchForm label {
  position: absolute;
  left: -99999px;
}

.Nav ul {
  color: #fff;
  list-style-type: none;
  display: flex;
  flex-wrap: nowrap;
  align-items: center;
}

.Nav li {
  padding: 1rem;
}

.Nav li:hover,
.Nav li:focus {
  padding: 1rem;
}

.Nav li a {
  color: #fff;
  text-decoration: none;
}

.Nav li:hover,
.Nav li:focus,
.Nav li:hover a,
.Nav li:focus a {
  background-color: #eee;
  color: #333;
}

.Nav li:hover a,
.Nav li:focus a {
  cursor: pointer;
}

.Home,
.NewPost,
.PostPage,
.About,
.Missing {
  width: 100%;
  flex-grow: 1;
  padding: 1rem;
  overflow-y: auto;
  background-color: #fff;
}

.post {
  margin-top: 1rem;
  padding-bottom: 1rem;
  border-bottom: 1px solid lightgray;
}

.Home .post a {
  text-decoration: none;
}

.Home .post a,
.Home .post a:visited {
  color: #000;
}

.post:first-child {
  margin-top: 0;
}

.post:last-child {
  border-bottom: none;
}

.postDate {
  font-size: 0.75rem;
  margin-top: 0.25rem;
}

.postBody {
  margin: 1rem 0;
}

.newPostForm {
  display: flex;
  flex-direction: column;
}

.newPostForm label {
  margin-top: 1rem;
}

.newPostForm input[type="text"],
.newPostForm textarea {
  font-family: "Open Sans", sans-serif;
  width: 100%;
  min-height: 48px;
  font-size: 1rem;
  padding: 0.25rem;
  border-radius: 0.25rem;
  margin-right: 0.25rem;
  outline: none;
}

.newPostForm textarea {
  height: 100px;
}

.newPostForm button {
  margin-top: 1rem;
  height: 48px;
  min-width: 48px;
  border-radius: 10px;
  padding: 0.5rem;
  font-size: 1rem;
  cursor: pointer;
}

.Missing h2,
.PostPage h2,
.Missing p,
.PostPage p {
  margin-bottom: 1rem;
}

.PostPage button {
  height: 48px;
  min-width: 48px;
  border-radius: 0.25rem;
  padding: 0.5rem;
  font-size: 1rem;
  background-color: red;
  color: #fff;
  cursor: pointer;
}

.statusMsg {
  margin-top: 2rem;
}

@media only screen and (min-width: 610px) {
  html {
    font-size: 22px;
  }

  .Header h1 {
    font-size: 2rem;
  }

  .Nav {
    flex-direction: row;
    flex-wrap: nowrap;
    justify-content: space-between;
    align-items: center;
  }

  .Nav ul {
    text-align: right;
  }

  .Nav li:hover,
  .Nav li:focus,
  .Nav li:hover a,
  .Nav li:focus a {
    background-color: #eee;
    color: #333;
  }

  .searchForm {
    width: 50%;
    padding: 0.5rem 0;
  }

  .searchForm input[type="text"] {
    margin-left: 0.5rem;
  }

  .newPostForm textarea {
    height: 300px;
  }
}

@media only screen and (min-width: 992px) {
  .Header svg {
    font-size: 3rem;
  }
}

```

# #End  </details>

<details>
  <summary>37. Blog App - Customising Home, Feed and Post Components (Displaying all Posts) </summary>

# Customising Home, Feed and Post Components (Displaying all Posts)

<img width="975" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/e859a990-c46a-47f1-af00-30b879c47af7">
<img width="1214" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/253130cb-9958-4bab-9700-5c2ba8181097">
<img width="1214" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/4d19cde0-a110-4c82-b66a-b71886886653">

### x-dave-gray/blogapp/src/App.js:

```js
import { useState, useEffect } from "react";
import { Route, Routes, useNavigate } from "react-router-dom";
import Header from "./Header";
import Nav from "./Nav";
import Footer from "./Footer";
import Home from "./Home";
import NewPost from "./NewPost";
import PostPage from "./PostPage";
import About from "./About";
import Missing from "./Missing";

function App() {
  const [search, setSearch] = useState("");
  const [searchResults, setSearchResults] = useState([]);
  const [posts, setPosts] = useState([
    {
      id: 1,
      title: "My First Post",
      datetime: "July 01, 2021 11:17:36 AM",
      body: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis consequatur expedita, assumenda similique non optio! Modi nesciunt excepturi corrupti atque blanditiis quo nobis, non optio quae possimus illum exercitationem ipsa!",
    },
    {
      id: 2,
      title: "My 2nd Post",
      datetime: "July 01, 2021 11:17:36 AM",
      body: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis consequatur expedita, assumenda similique non optio! Modi nesciunt excepturi corrupti atque blanditiis quo nobis, non optio quae possimus illum exercitationem ipsa!",
    },
    {
      id: 3,
      title: "My 3rd Post",
      datetime: "July 01, 2021 11:17:36 AM",
      body: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis consequatur expedita, assumenda similique non optio! Modi nesciunt excepturi corrupti atque blanditiis quo nobis, non optio quae possimus illum exercitationem ipsa!",
    },
    {
      id: 4,
      title: "My Fourth Post",
      datetime: "July 01, 2021 11:17:36 AM",
      body: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis consequatur expedita, assumenda similique non optio! Modi nesciunt excepturi corrupti atque blanditiis quo nobis, non optio quae possimus illum exercitationem ipsa!",
    },
  ]);

  return (
    <div className="App">
      <Header title="React JS Blog" />
      <Nav search={search} setSearch={setSearch} />
      <Routes>
        <Route exact path="/" element={<Home posts={posts} />} />
        <Route exact path="/post" element={<NewPost />} />
        <Route path="/post/:id" element={<PostPage />} />
        <Route path="/about" element={<About />} />
        <Route path="*" element={<Missing />} />
      </Routes>
      <Footer />
    </div>
  );
}

export default App;
```

### x-dave-gray/blogapp/src/Home.js:

```js
import React from "react";
import Feed from "./Feed";

const Home = ({ posts }) => {
  return (
    <main className="Home">
      {posts.length ? (
        <Feed posts={posts} />
      ) : (
        <p style={{ marginTop: "2rem" }}>No Posts to display.</p>
      )}
    </main>
  );
};

export default Home;
```

### x-dave-gray/blogapp/src/Feed.js:

```js
import React from "react";
import Post from "./Post";

const Feed = ({ posts }) => {
  return (
    <>{posts.map((post) => <Post key={post.id} post={post} />).reverse()}</>
  );
};

export default Feed;
```

### x-dave-gray/blogapp/src/Post.js:

```js
import React from "react";
import { Link } from "react-router-dom";

const Post = ({ post }) => {
  return (
    <article className="post">
      <Link to={`/post/${post.id}`}>
        <h2>{post.title}</h2>
        <p className="postDate">{post.datetime}</p>
      </Link>
      <p>
        {post.body.length <= 25 ? post.body : `${post.body.slice(0, 25)}...`}
      </p>
    </article>
  );
};

export default Post;
```

### x-dave-gray/blogapp/src/index.css:

```css
@import url("https://fonts.googleapis.com/css2?family=Open+Sans&display=swap");

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  font-size: 16px;
}

body {
  min-height: 100vh;
  font-family: "Open Sans", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: flex;
  background-color: #efefef;
}

#root {
  flex-grow: 1;
  display: flex;
  justify-content: center;
  align-items: center;
}

.App {
  width: 100%;
  max-width: 800px;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
  border: 1px solid #333;
  box-shadow: 0px 0px 15px gray;
}

.Header,
.Footer {
  width: 100%;
  background-color: #66d8f5;
  padding: 1rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.Header h1 {
  font-size: 1.5rem;
}

.Header svg {
  font-size: 2rem;
}

.Footer {
  padding: 0.75rem;
  display: grid;
  place-content: center;
}

.Nav {
  width: 100%;
  background-color: #333;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: flex-start;
}

.searchForm {
  width: 80%;
  padding: 1rem 0 0 0.75rem;
}

.searchForm input[type="text"] {
  font-family: "Open Sans", sans-serif;
  width: 100%;
  min-height: 48px;
  font-size: 1rem;
  padding: 0.25rem;
  border-radius: 0.25rem;
  outline: none;
}

.searchForm label {
  position: absolute;
  left: -99999px;
}

.Nav ul {
  color: #fff;
  list-style-type: none;
  display: flex;
  flex-wrap: nowrap;
  align-items: center;
}

.Nav li {
  padding: 1rem;
}

.Nav li:hover,
.Nav li:focus {
  padding: 1rem;
}

.Nav li a {
  color: #fff;
  text-decoration: none;
}

.Nav li:hover,
.Nav li:focus,
.Nav li:hover a,
.Nav li:focus a {
  background-color: #eee;
  color: #333;
}

.Nav li:hover a,
.Nav li:focus a {
  cursor: pointer;
}

.Home,
.NewPost,
.PostPage,
.About,
.Missing {
  width: 100%;
  flex-grow: 1;
  padding: 1rem;
  overflow-y: auto;
  background-color: #fff;
}

.post {
  margin-top: 1rem;
  padding-bottom: 1rem;
  border-bottom: 1px solid lightgray;
}

.Home .post a {
  text-decoration: none;
}

.Home .post a,
.Home .post a:visited {
  color: #000;
}

.post:first-child {
  margin-top: 0;
}

.post:last-child {
  border-bottom: none;
}

.postDate {
  font-size: 0.75rem;
  margin-top: 0.25rem;
}

.postBody {
  margin: 1rem 0;
}

.newPostForm {
  display: flex;
  flex-direction: column;
}

.newPostForm label {
  margin-top: 1rem;
}

.newPostForm input[type="text"],
.newPostForm textarea {
  font-family: "Open Sans", sans-serif;
  width: 100%;
  min-height: 48px;
  font-size: 1rem;
  padding: 0.25rem;
  border-radius: 0.25rem;
  margin-right: 0.25rem;
  outline: none;
}

.newPostForm textarea {
  height: 100px;
}

.newPostForm button {
  margin-top: 1rem;
  height: 48px;
  min-width: 48px;
  border-radius: 10px;
  padding: 0.5rem;
  font-size: 1rem;
  cursor: pointer;
}

.Missing h2,
.PostPage h2,
.Missing p,
.PostPage p {
  margin-bottom: 1rem;
}

.PostPage button {
  height: 48px;
  min-width: 48px;
  border-radius: 0.25rem;
  padding: 0.5rem;
  font-size: 1rem;
  background-color: red;
  color: #fff;
  cursor: pointer;
}

.statusMsg {
  margin-top: 2rem;
}

@media only screen and (min-width: 610px) {
  html {
    font-size: 22px;
  }

  .Header h1 {
    font-size: 2rem;
  }

  .Nav {
    flex-direction: row;
    flex-wrap: nowrap;
    justify-content: space-between;
    align-items: center;
  }

  .Nav ul {
    text-align: right;
  }

  .Nav li:hover,
  .Nav li:focus,
  .Nav li:hover a,
  .Nav li:focus a {
    background-color: #eee;
    color: #333;
  }

  .searchForm {
    width: 50%;
    padding: 0.5rem 0;
  }

  .searchForm input[type="text"] {
    margin-left: 0.5rem;
  }

  .newPostForm textarea {
    height: 300px;
  }
}

@media only screen and (min-width: 992px) {
  .Header svg {
    font-size: 3rem;
  }
}
```

# #End  </details>

<details>
  <summary>38. Blog App - Customising PostPage Component with useParams Hook (Displaying a single Post)</summary>

# Customising PostPage Component with useParams Hook (Displaying a single Post)

<img width="970" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/989f28a3-e3b1-48f4-9ca6-3dbd68e3e5d3">
<img width="1213" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/783046fe-c232-4959-a0ff-dcdbaf420ea2">

### x-dave-gray/blogapp/src/App.js:

```js
import { useState, useEffect } from "react";
import { Route, Routes, useNavigate } from "react-router-dom";
import Header from "./Header";
import Nav from "./Nav";
import Footer from "./Footer";
import Home from "./Home";
import NewPost from "./NewPost";
import PostPage from "./PostPage";
import About from "./About";
import Missing from "./Missing";

function App() {
  const [search, setSearch] = useState("");
  const [searchResults, setSearchResults] = useState([]);
  const [posts, setPosts] = useState([
    {
      id: 1,
      title: "My First Post",
      datetime: "July 01, 2021 11:17:36 AM",
      body: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis consequatur expedita, assumenda similique non optio! Modi nesciunt excepturi corrupti atque blanditiis quo nobis, non optio quae possimus illum exercitationem ipsa!",
    },
    {
      id: 2,
      title: "My 2nd Post",
      datetime: "July 01, 2021 11:17:36 AM",
      body: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis consequatur expedita, assumenda similique non optio! Modi nesciunt excepturi corrupti atque blanditiis quo nobis, non optio quae possimus illum exercitationem ipsa!",
    },
    {
      id: 3,
      title: "My 3rd Post",
      datetime: "July 01, 2021 11:17:36 AM",
      body: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis consequatur expedita, assumenda similique non optio! Modi nesciunt excepturi corrupti atque blanditiis quo nobis, non optio quae possimus illum exercitationem ipsa!",
    },
    {
      id: 4,
      title: "My Fourth Post",
      datetime: "July 01, 2021 11:17:36 AM",
      body: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis consequatur expedita, assumenda similique non optio! Modi nesciunt excepturi corrupti atque blanditiis quo nobis, non optio quae possimus illum exercitationem ipsa!",
    },
  ]);

  return (
    <div className="App">
      <Header title="React JS Blog" />
      <Nav search={search} setSearch={setSearch} />
      <Routes>
        <Route exact path="/" element={<Home posts={posts} />} />
        <Route exact path="/post" element={<NewPost />} />
        <Route path="/post/:id" element={<PostPage posts={posts} />} />
        <Route path="/about" element={<About />} />
        <Route path="*" element={<Missing />} />
      </Routes>
      <Footer />
    </div>
  );
}

export default App;
```

### x-dave-gray/blogapp/src/PostPage.js:

```js
import React from "react";
import { useParams, Link } from "react-router-dom";

const PostPage = ({ posts }) => {
  const { id } = useParams();
  const post = posts.find((post) => post.id.toString() === id);

  return (
    <main className="PostPage">
      <article className="post">
        {post ? (
          <>
            <h2>{post.title}</h2>
            <p className="postDate">{post.datetime}</p>
            <p className="postBody">{post.body}</p>
          </>
        ) : (
          <>
            <h2>Post Not Found</h2>
            <p>Well, that's disappointing.</p>
            <p>
              <Link to="/">Visit our Home Page</Link>
            </p>
          </>
        )}
      </article>
    </main>
  );
};

export default PostPage;
```

### x-dave-gray/blogapp/src/index.css:

```css
@import url("https://fonts.googleapis.com/css2?family=Open+Sans&display=swap");

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  font-size: 16px;
}

body {
  min-height: 100vh;
  font-family: "Open Sans", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: flex;
  background-color: #efefef;
}

#root {
  flex-grow: 1;
  display: flex;
  justify-content: center;
  align-items: center;
}

.App {
  width: 100%;
  max-width: 800px;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
  border: 1px solid #333;
  box-shadow: 0px 0px 15px gray;
}

.Header,
.Footer {
  width: 100%;
  background-color: #66d8f5;
  padding: 1rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.Header h1 {
  font-size: 1.5rem;
}

.Header svg {
  font-size: 2rem;
}

.Footer {
  padding: 0.75rem;
  display: grid;
  place-content: center;
}

.Nav {
  width: 100%;
  background-color: #333;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: flex-start;
}

.searchForm {
  width: 80%;
  padding: 1rem 0 0 0.75rem;
}

.searchForm input[type="text"] {
  font-family: "Open Sans", sans-serif;
  width: 100%;
  min-height: 48px;
  font-size: 1rem;
  padding: 0.25rem;
  border-radius: 0.25rem;
  outline: none;
}

.searchForm label {
  position: absolute;
  left: -99999px;
}

.Nav ul {
  color: #fff;
  list-style-type: none;
  display: flex;
  flex-wrap: nowrap;
  align-items: center;
}

.Nav li {
  padding: 1rem;
}

.Nav li:hover,
.Nav li:focus {
  padding: 1rem;
}

.Nav li a {
  color: #fff;
  text-decoration: none;
}

.Nav li:hover,
.Nav li:focus,
.Nav li:hover a,
.Nav li:focus a {
  background-color: #eee;
  color: #333;
}

.Nav li:hover a,
.Nav li:focus a {
  cursor: pointer;
}

.Home,
.NewPost,
.PostPage,
.About,
.Missing {
  width: 100%;
  flex-grow: 1;
  padding: 1rem;
  overflow-y: auto;
  background-color: #fff;
}

.post {
  margin-top: 1rem;
  padding-bottom: 1rem;
  border-bottom: 1px solid lightgray;
}

.Home .post a {
  text-decoration: none;
}

.Home .post a,
.Home .post a:visited {
  color: #000;
}

.post:first-child {
  margin-top: 0;
}

.post:last-child {
  border-bottom: none;
}

.postDate {
  font-size: 0.75rem;
  margin-top: 0.25rem;
}

.postBody {
  margin: 1rem 0;
}

.newPostForm {
  display: flex;
  flex-direction: column;
}

.newPostForm label {
  margin-top: 1rem;
}

.newPostForm input[type="text"],
.newPostForm textarea {
  font-family: "Open Sans", sans-serif;
  width: 100%;
  min-height: 48px;
  font-size: 1rem;
  padding: 0.25rem;
  border-radius: 0.25rem;
  margin-right: 0.25rem;
  outline: none;
}

.newPostForm textarea {
  height: 100px;
}

.newPostForm button {
  margin-top: 1rem;
  height: 48px;
  min-width: 48px;
  border-radius: 10px;
  padding: 0.5rem;
  font-size: 1rem;
  cursor: pointer;
}

.Missing h2,
.PostPage h2,
.Missing p,
.PostPage p {
  margin-bottom: 1rem;
}

.PostPage button {
  height: 48px;
  min-width: 48px;
  border-radius: 0.25rem;
  padding: 0.5rem;
  font-size: 1rem;
  background-color: red;
  color: #fff;
  cursor: pointer;
}

.statusMsg {
  margin-top: 2rem;
}

@media only screen and (min-width: 610px) {
  html {
    font-size: 22px;
  }

  .Header h1 {
    font-size: 2rem;
  }

  .Nav {
    flex-direction: row;
    flex-wrap: nowrap;
    justify-content: space-between;
    align-items: center;
  }

  .Nav ul {
    text-align: right;
  }

  .Nav li:hover,
  .Nav li:focus,
  .Nav li:hover a,
  .Nav li:focus a {
    background-color: #eee;
    color: #333;
  }

  .searchForm {
    width: 50%;
    padding: 0.5rem 0;
  }

  .searchForm input[type="text"] {
    margin-left: 0.5rem;
  }

  .newPostForm textarea {
    height: 300px;
  }
}

@media only screen and (min-width: 992px) {
  .Header svg {
    font-size: 3rem;
  }
}
```

# #End  </details>

<details>
  <summary>39. Blog App - Deleting a Blog and useNavigate()</summary>

#  Deleting a Blog and useNavigate()

<img width="976" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/452133db-2300-487d-bada-20b47cdbf9c6">
<img width="1213" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/eaa26d79-8349-445c-93c7-fc29a1b4ee0f">
<img width="1213" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/2467e41c-6615-4d1a-95fa-6435396b2fc8">

### x-dave-gray/blogapp/src/App.js:

```js
import { useState, useEffect } from "react";
import { Route, Routes, useNavigate } from "react-router-dom";
import Header from "./Header";
import Nav from "./Nav";
import Footer from "./Footer";
import Home from "./Home";
import NewPost from "./NewPost";
import PostPage from "./PostPage";
import About from "./About";
import Missing from "./Missing";

function App() {
  const [search, setSearch] = useState("");
  const [searchResults, setSearchResults] = useState([]);
  const [posts, setPosts] = useState([
    {
      id: 1,
      title: "My First Post",
      datetime: "July 01, 2021 11:17:36 AM",
      body: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis consequatur expedita, assumenda similique non optio! Modi nesciunt excepturi corrupti atque blanditiis quo nobis, non optio quae possimus illum exercitationem ipsa!",
    },
    {
      id: 2,
      title: "My 2nd Post",
      datetime: "July 01, 2021 11:17:36 AM",
      body: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis consequatur expedita, assumenda similique non optio! Modi nesciunt excepturi corrupti atque blanditiis quo nobis, non optio quae possimus illum exercitationem ipsa!",
    },
    {
      id: 3,
      title: "My 3rd Post",
      datetime: "July 01, 2021 11:17:36 AM",
      body: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis consequatur expedita, assumenda similique non optio! Modi nesciunt excepturi corrupti atque blanditiis quo nobis, non optio quae possimus illum exercitationem ipsa!",
    },
    {
      id: 4,
      title: "My Fourth Post",
      datetime: "July 01, 2021 11:17:36 AM",
      body: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis consequatur expedita, assumenda similique non optio! Modi nesciunt excepturi corrupti atque blanditiis quo nobis, non optio quae possimus illum exercitationem ipsa!",
    },
  ]);

  const navigate = useNavigate();

  const handleDelete = (id) => {
    const postList = posts.filter((post) => post.id !== id);
    setPosts(postList);
    navigate("/");
  };

  return (
    <div className="App">
      <Header title="React JS Blog" />
      <Nav search={search} setSearch={setSearch} />
      <Routes>
        <Route exact path="/" element={<Home posts={posts} />} />
        <Route exact path="/post" element={<NewPost />} />
        <Route
          path="/post/:id"
          element={<PostPage posts={posts} handleDelete={handleDelete} />}
        />
        <Route path="/about" element={<About />} />
        <Route path="*" element={<Missing />} />
      </Routes>
      <Footer />
    </div>
  );
}

export default App;
```

### x-dave-gray/blogapp/src/PostPage.js:

```js
import React from "react";
import { useParams, Link } from "react-router-dom";

const PostPage = ({ posts, handleDelete }) => {
  const { id } = useParams();
  const post = posts.find((post) => post.id.toString() === id);

  return (
    <main className="PostPage">
      <article className="post">
        {post ? (
          <>
            <h2>{post.title}</h2>
            <p className="postDate">{post.datetime}</p>
            <p className="postBody">{post.body}</p>
            <button onClick={() => handleDelete(post.id)}>Delete Post</button>
          </>
        ) : (
          <>
            <h2>Post Not Found</h2>
            <p>Well, that's disappointing.</p>
            <p>
              <Link to="/">Visit our Home Page</Link>
            </p>
          </>
        )}
      </article>
    </main>
  );
};

export default PostPage;
```

### x-dave-gray/blogapp/src/index.css:

```css
@import url("https://fonts.googleapis.com/css2?family=Open+Sans&display=swap");

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  font-size: 16px;
}

body {
  min-height: 100vh;
  font-family: "Open Sans", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: flex;
  background-color: #efefef;
}

#root {
  flex-grow: 1;
  display: flex;
  justify-content: center;
  align-items: center;
}

.App {
  width: 100%;
  max-width: 800px;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
  border: 1px solid #333;
  box-shadow: 0px 0px 15px gray;
}

.Header,
.Footer {
  width: 100%;
  background-color: #66d8f5;
  padding: 1rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.Header h1 {
  font-size: 1.5rem;
}

.Header svg {
  font-size: 2rem;
}

.Footer {
  padding: 0.75rem;
  display: grid;
  place-content: center;
}

.Nav {
  width: 100%;
  background-color: #333;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: flex-start;
}

.searchForm {
  width: 80%;
  padding: 1rem 0 0 0.75rem;
}

.searchForm input[type="text"] {
  font-family: "Open Sans", sans-serif;
  width: 100%;
  min-height: 48px;
  font-size: 1rem;
  padding: 0.25rem;
  border-radius: 0.25rem;
  outline: none;
}

.searchForm label {
  position: absolute;
  left: -99999px;
}

.Nav ul {
  color: #fff;
  list-style-type: none;
  display: flex;
  flex-wrap: nowrap;
  align-items: center;
}

.Nav li {
  padding: 1rem;
}

.Nav li:hover,
.Nav li:focus {
  padding: 1rem;
}

.Nav li a {
  color: #fff;
  text-decoration: none;
}

.Nav li:hover,
.Nav li:focus,
.Nav li:hover a,
.Nav li:focus a {
  background-color: #eee;
  color: #333;
}

.Nav li:hover a,
.Nav li:focus a {
  cursor: pointer;
}

.Home,
.NewPost,
.PostPage,
.About,
.Missing {
  width: 100%;
  flex-grow: 1;
  padding: 1rem;
  overflow-y: auto;
  background-color: #fff;
}

.post {
  margin-top: 1rem;
  padding-bottom: 1rem;
  border-bottom: 1px solid lightgray;
}

.Home .post a {
  text-decoration: none;
}

.Home .post a,
.Home .post a:visited {
  color: #000;
}

.post:first-child {
  margin-top: 0;
}

.post:last-child {
  border-bottom: none;
}

.postDate {
  font-size: 0.75rem;
  margin-top: 0.25rem;
}

.postBody {
  margin: 1rem 0;
}

.newPostForm {
  display: flex;
  flex-direction: column;
}

.newPostForm label {
  margin-top: 1rem;
}

.newPostForm input[type="text"],
.newPostForm textarea {
  font-family: "Open Sans", sans-serif;
  width: 100%;
  min-height: 48px;
  font-size: 1rem;
  padding: 0.25rem;
  border-radius: 0.25rem;
  margin-right: 0.25rem;
  outline: none;
}

.newPostForm textarea {
  height: 100px;
}

.newPostForm button {
  margin-top: 1rem;
  height: 48px;
  min-width: 48px;
  border-radius: 10px;
  padding: 0.5rem;
  font-size: 1rem;
  cursor: pointer;
}

.Missing h2,
.PostPage h2,
.Missing p,
.PostPage p {
  margin-bottom: 1rem;
}

.PostPage button {
  height: 48px;
  min-width: 48px;
  border-radius: 0.25rem;
  padding: 0.5rem;
  font-size: 1rem;
  background-color: red;
  color: #fff;
  cursor: pointer;
}

.statusMsg {
  margin-top: 2rem;
}

@media only screen and (min-width: 610px) {
  html {
    font-size: 22px;
  }

  .Header h1 {
    font-size: 2rem;
  }

  .Nav {
    flex-direction: row;
    flex-wrap: nowrap;
    justify-content: space-between;
    align-items: center;
  }

  .Nav ul {
    text-align: right;
  }

  .Nav li:hover,
  .Nav li:focus,
  .Nav li:hover a,
  .Nav li:focus a {
    background-color: #eee;
    color: #333;
  }

  .searchForm {
    width: 50%;
    padding: 0.5rem 0;
  }

  .searchForm input[type="text"] {
    margin-left: 0.5rem;
  }

  .newPostForm textarea {
    height: 300px;
  }
}

@media only screen and (min-width: 992px) {
  .Header svg {
    font-size: 3rem;
  }
}
```

# #End  </details>

<details>
  <summary>40. Blog App - Customise NewPost Component</summary>

# Customise NewPost Component

<img width="976" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/5614fde7-bb18-4fab-9e0a-9bb06af20bcb">
<img width="1215" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/ab80483d-fe05-4a06-b108-038f51d3cd70">

### x-dave-gray/blogapp/src/App.js:

```js
import { useState, useEffect } from "react";
import { Route, Routes, useNavigate } from "react-router-dom";
import Header from "./Header";
import Nav from "./Nav";
import Footer from "./Footer";
import Home from "./Home";
import NewPost from "./NewPost";
import PostPage from "./PostPage";
import About from "./About";
import Missing from "./Missing";

function App() {
  const [search, setSearch] = useState("");
  const [searchResults, setSearchResults] = useState([]);
  const [postTitle, setPostTitle] = useState("");
  const [postBody, setPostBody] = useState("");
  const [posts, setPosts] = useState([
    {
      id: 1,
      title: "My First Post",
      datetime: "July 01, 2021 11:17:36 AM",
      body: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis consequatur expedita, assumenda similique non optio! Modi nesciunt excepturi corrupti atque blanditiis quo nobis, non optio quae possimus illum exercitationem ipsa!",
    },
    {
      id: 2,
      title: "My 2nd Post",
      datetime: "July 01, 2021 11:17:36 AM",
      body: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis consequatur expedita, assumenda similique non optio! Modi nesciunt excepturi corrupti atque blanditiis quo nobis, non optio quae possimus illum exercitationem ipsa!",
    },
    {
      id: 3,
      title: "My 3rd Post",
      datetime: "July 01, 2021 11:17:36 AM",
      body: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis consequatur expedita, assumenda similique non optio! Modi nesciunt excepturi corrupti atque blanditiis quo nobis, non optio quae possimus illum exercitationem ipsa!",
    },
    {
      id: 4,
      title: "My Fourth Post",
      datetime: "July 01, 2021 11:17:36 AM",
      body: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis consequatur expedita, assumenda similique non optio! Modi nesciunt excepturi corrupti atque blanditiis quo nobis, non optio quae possimus illum exercitationem ipsa!",
    },
  ]);

  const navigate = useNavigate();

  const handleDelete = (id) => {
    const postList = posts.filter((post) => post.id !== id);
    setPosts(postList);
    navigate("/");
  };

  return (
    <div className="App">
      <Header title="React JS Blog" />
      <Nav search={search} setSearch={setSearch} />
      <Routes>
        <Route exact path="/" element={<Home posts={posts} />} />
        <Route
          exact
          path="/post"
          element={
            <NewPost
              postTitle={postTitle}
              setPostTitle={setPostTitle}
              postBody={postBody}
              setPostBody={setPostBody}
            />
          }
        />
        <Route
          path="/post/:id"
          element={<PostPage posts={posts} handleDelete={handleDelete} />}
        />
        <Route path="/about" element={<About />} />
        <Route path="*" element={<Missing />} />
      </Routes>
      <Footer />
    </div>
  );
}

export default App;
```

### x-dave-gray/blogapp/src/NewPost.js:

```js
import React from "react";

const NewPost = ({ postTitle, setPostTitle, postBody, setPostBody }) => {
  return (
    <main className="NewPost">
      <h2>NewPost</h2>
      <form className="newPostForm">
        <label htmlFor="postTitle">Title:</label>
        <input
          type="text"
          id="postTitle"
          value={postTitle}
          onChange={(e) => setPostTitle(e.target.value)}
          required
        />
        <label htmlFor="postBody">Post:</label>
        <textarea
          id="postBody"
          value={postBody}
          onChange={(e) => setPostBody(e.target.value)}
          // cols="10"
          // rows="30"
          required
        />
        <button type="submit">Submit</button>
      </form>
    </main>
  );
};

export default NewPost;
```

```css
@import url("https://fonts.googleapis.com/css2?family=Open+Sans&display=swap");

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  font-size: 16px;
}

body {
  min-height: 100vh;
  font-family: "Open Sans", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: flex;
  background-color: #efefef;
}

#root {
  flex-grow: 1;
  display: flex;
  justify-content: center;
  align-items: center;
}

.App {
  width: 100%;
  max-width: 800px;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
  border: 1px solid #333;
  box-shadow: 0px 0px 15px gray;
}

.Header,
.Footer {
  width: 100%;
  background-color: #66d8f5;
  padding: 1rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.Header h1 {
  font-size: 1.5rem;
}

.Header svg {
  font-size: 2rem;
}

.Footer {
  padding: 0.75rem;
  display: grid;
  place-content: center;
}

.Nav {
  width: 100%;
  background-color: #333;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: flex-start;
}

.searchForm {
  width: 80%;
  padding: 1rem 0 0 0.75rem;
}

.searchForm input[type="text"] {
  font-family: "Open Sans", sans-serif;
  width: 100%;
  min-height: 48px;
  font-size: 1rem;
  padding: 0.25rem;
  border-radius: 0.25rem;
  outline: none;
}

.searchForm label {
  position: absolute;
  left: -99999px;
}

.Nav ul {
  color: #fff;
  list-style-type: none;
  display: flex;
  flex-wrap: nowrap;
  align-items: center;
}

.Nav li {
  padding: 1rem;
}

.Nav li:hover,
.Nav li:focus {
  padding: 1rem;
}

.Nav li a {
  color: #fff;
  text-decoration: none;
}

.Nav li:hover,
.Nav li:focus,
.Nav li:hover a,
.Nav li:focus a {
  background-color: #eee;
  color: #333;
}

.Nav li:hover a,
.Nav li:focus a {
  cursor: pointer;
}

.Home,
.NewPost,
.PostPage,
.About,
.Missing {
  width: 100%;
  flex-grow: 1;
  padding: 1rem;
  overflow-y: auto;
  background-color: #fff;
}

.post {
  margin-top: 1rem;
  padding-bottom: 1rem;
  border-bottom: 1px solid lightgray;
}

.Home .post a {
  text-decoration: none;
}

.Home .post a,
.Home .post a:visited {
  color: #000;
}

.post:first-child {
  margin-top: 0;
}

.post:last-child {
  border-bottom: none;
}

.postDate {
  font-size: 0.75rem;
  margin-top: 0.25rem;
}

.postBody {
  margin: 1rem 0;
}

.newPostForm {
  display: flex;
  flex-direction: column;
}

.newPostForm label {
  margin-top: 1rem;
}

.newPostForm input[type="text"],
.newPostForm textarea {
  font-family: "Open Sans", sans-serif;
  width: 100%;
  min-height: 48px;
  font-size: 1rem;
  padding: 0.25rem;
  border-radius: 0.25rem;
  margin-right: 0.25rem;
  outline: none;
}

.newPostForm textarea {
  height: 100px;
}

.newPostForm button {
  margin-top: 1rem;
  height: 48px;
  min-width: 48px;
  border-radius: 10px;
  padding: 0.5rem;
  font-size: 1rem;
  cursor: pointer;
}

.Missing h2,
.PostPage h2,
.Missing p,
.PostPage p {
  margin-bottom: 1rem;
}

.PostPage button {
  height: 48px;
  min-width: 48px;
  border-radius: 0.25rem;
  padding: 0.5rem;
  font-size: 1rem;
  background-color: red;
  color: #fff;
  cursor: pointer;
}

.statusMsg {
  margin-top: 2rem;
}

@media only screen and (min-width: 610px) {
  html {
    font-size: 22px;
  }

  .Header h1 {
    font-size: 2rem;
  }

  .Nav {
    flex-direction: row;
    flex-wrap: nowrap;
    justify-content: space-between;
    align-items: center;
  }

  .Nav ul {
    text-align: right;
  }

  .Nav li:hover,
  .Nav li:focus,
  .Nav li:hover a,
  .Nav li:focus a {
    background-color: #eee;
    color: #333;
  }

  .searchForm {
    width: 50%;
    padding: 0.5rem 0;
  }

  .searchForm input[type="text"] {
    margin-left: 0.5rem;
  }

  .newPostForm textarea {
    height: 300px;
  }
}

@media only screen and (min-width: 992px) {
  .Header svg {
    font-size: 3rem;
  }
}
```

# #End  </details>

<details>
  <summary>41. Blog App - Adding New Post (handleSubmit) Functionality </summary>

# Blog App - Adding New Post (handleSubmit) Functionality

<img width="974" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/ec6e53c1-4569-46af-a3c8-86fc6d0b3424">
<img width="1213" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/1c357e57-2ec1-4ab4-9cc7-3a150c6e9581">
<img width="1213" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/c503845c-bb3a-41e5-81bd-29f31ac44d80">
<img width="1213" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/563a2b4a-30e3-4e02-ada3-3afd81841f18">
<img width="1213" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/866228f4-9f43-408a-b7c8-c186e2b1b720">

# Install Date-Functions Module:

```bs
npm i date-fns -S
```

### x-dave-gray/blogapp/src/App.js:

```js
import { useState, useEffect } from "react";
import { Route, Routes, useNavigate } from "react-router-dom";
import { format } from "date-fns";
import Header from "./Header";
import Nav from "./Nav";
import Footer from "./Footer";
import Home from "./Home";
import NewPost from "./NewPost";
import PostPage from "./PostPage";
import About from "./About";
import Missing from "./Missing";

function App() {
  const [posts, setPosts] = useState([
    {
      id: 1,
      title: "My First Post",
      datetime: "July 01, 2021 11:17:36 AM",
      body: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis consequatur expedita, assumenda similique non optio! Modi nesciunt excepturi corrupti atque blanditiis quo nobis, non optio quae possimus illum exercitationem ipsa!",
    },
    {
      id: 2,
      title: "My 2nd Post",
      datetime: "July 01, 2021 11:17:36 AM",
      body: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis consequatur expedita, assumenda similique non optio! Modi nesciunt excepturi corrupti atque blanditiis quo nobis, non optio quae possimus illum exercitationem ipsa!",
    },
    {
      id: 3,
      title: "My 3rd Post",
      datetime: "July 01, 2021 11:17:36 AM",
      body: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis consequatur expedita, assumenda similique non optio! Modi nesciunt excepturi corrupti atque blanditiis quo nobis, non optio quae possimus illum exercitationem ipsa!",
    },
    {
      id: 4,
      title: "My Fourth Post",
      datetime: "July 01, 2021 11:17:36 AM",
      body: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis consequatur expedita, assumenda similique non optio! Modi nesciunt excepturi corrupti atque blanditiis quo nobis, non optio quae possimus illum exercitationem ipsa!",
    },
  ]);
  const [search, setSearch] = useState("");
  const [searchResults, setSearchResults] = useState([]);
  const [postTitle, setPostTitle] = useState("");
  const [postBody, setPostBody] = useState("");
  const navigate = useNavigate();

  const handleDelete = (id) => {
    const postList = posts.filter((post) => post.id !== id);
    setPosts(postList);
    navigate("/");
  };

  const handleSubmit = (e) => {
    e.preventDefault();
    const id = posts.length ? posts[posts.length - 1].id + 1 : 1;
    const datetime = format(new Date(), "MMMM dd, yyyy pp");
    //const datetime = format(new Date(), "yyyy-MM-dd HH:mm:ss");
    const newPost = { id, title: postTitle, datetime, body: postBody };
    const allPosts = [...posts, newPost];
    setPosts(allPosts);
    setPostTitle("");
    setPostBody("");
    navigate("/");
  };

  return (
    <div className="App">
      <Header title="React JS Blog" />
      <Nav search={search} setSearch={setSearch} />
      <Routes>
        <Route exact path="/" element={<Home posts={posts} />} />
        <Route
          exact
          path="/post"
          element={
            <NewPost
              handleSubmit={handleSubmit}
              postTitle={postTitle}
              setPostTitle={setPostTitle}
              postBody={postBody}
              setPostBody={setPostBody}
            />
          }
        />
        <Route
          path="/post/:id"
          element={<PostPage posts={posts} handleDelete={handleDelete} />}
        />
        <Route path="/about" element={<About />} />
        <Route path="*" element={<Missing />} />
      </Routes>
      <Footer />
    </div>
  );
}

export default App;
```

### x-dave-gray/blogapp/src/NewPost.js:

```js
import React from "react";

const NewPost = ({
  handleSubmit,
  postTitle,
  setPostTitle,
  postBody,
  setPostBody,
}) => {
  return (
    <main className="NewPost">
      <h2>NewPost</h2>
      <form className="newPostForm" onSubmit={handleSubmit}>
        <label htmlFor="postTitle">Title:</label>
        <input
          type="text"
          id="postTitle"
          value={postTitle}
          onChange={(e) => setPostTitle(e.target.value)}
          required
        />
        <label htmlFor="postBody">Post:</label>
        <textarea
          id="postBody"
          value={postBody}
          onChange={(e) => setPostBody(e.target.value)}
          // cols="10"
          // rows="30"
          required
        />
        <button type="submit">Submit</button>
      </form>
    </main>
  );
};

export default NewPost;
```

# #End  </details>

<details>
  <summary>42. Blog App - Adding Search Functionality with useEffect</summary>

# Adding Search Functionality with useEffect

<img width="972" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/1cbba03e-ec58-4b43-80b3-27277e8ca89b">
<img width="1213" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/04b75d28-dfea-4230-8168-e3327da5e5b0">
<img width="1213" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/008f8191-19f8-46cf-9d54-e639c88bc773">

### x-dave-gray/blogapp/src/App.js:

```js
import { useState, useEffect } from "react";
import { Route, Routes, useNavigate } from "react-router-dom";
import { format } from "date-fns";
import Header from "./Header";
import Nav from "./Nav";
import Footer from "./Footer";
import Home from "./Home";
import NewPost from "./NewPost";
import PostPage from "./PostPage";
import About from "./About";
import Missing from "./Missing";

function App() {
  const [posts, setPosts] = useState([
    {
      id: 1,
      title: "My First Post",
      datetime: "July 01, 2021 11:17:36 AM",
      body: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis consequatur expedita, assumenda similique non optio! Modi nesciunt excepturi corrupti atque blanditiis quo nobis, non optio quae possimus illum exercitationem ipsa!",
    },
    {
      id: 2,
      title: "My 2nd Post",
      datetime: "July 01, 2021 11:17:36 AM",
      body: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis consequatur expedita, assumenda similique non optio! Modi nesciunt excepturi corrupti atque blanditiis quo nobis, non optio quae possimus illum exercitationem ipsa!",
    },
    {
      id: 3,
      title: "My 3rd Post",
      datetime: "July 01, 2021 11:17:36 AM",
      body: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis consequatur expedita, assumenda similique non optio! Modi nesciunt excepturi corrupti atque blanditiis quo nobis, non optio quae possimus illum exercitationem ipsa!",
    },
    {
      id: 4,
      title: "My Fourth Post",
      datetime: "July 01, 2021 11:17:36 AM",
      body: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis consequatur expedita, assumenda similique non optio! Modi nesciunt excepturi corrupti atque blanditiis quo nobis, non optio quae possimus illum exercitationem ipsa!",
    },
  ]);
  const [search, setSearch] = useState("");
  const [searchResults, setSearchResults] = useState([]);
  const [postTitle, setPostTitle] = useState("");
  const [postBody, setPostBody] = useState("");
  const navigate = useNavigate();

  useEffect(() => {
    const filteredResults = posts.filter(
      (post) =>
        post.body.toLowerCase().includes(search.toLowerCase()) ||
        post.title.toLowerCase().includes(search.toLowerCase())
    );

    setSearchResults(filteredResults.reverse());
  }, [posts, search]);

  const handleSubmit = (e) => {
    e.preventDefault();
    const id = posts.length ? posts[posts.length - 1].id + 1 : 1;
    const datetime = format(new Date(), "MMMM dd, yyyy pp");
    //const datetime = format(new Date(), "yyyy-MM-dd HH:mm:ss");
    const newPost = { id, title: postTitle, datetime, body: postBody };
    const allPosts = [...posts, newPost];
    setPosts(allPosts);
    setPostTitle("");
    setPostBody("");
    navigate("/");
  };

  const handleDelete = (id) => {
    const postList = posts.filter((post) => post.id !== id);
    setPosts(postList);
    navigate("/");
  };

  return (
    <div className="App">
      <Header title="React JS Blog" />
      <Nav search={search} setSearch={setSearch} />
      <Routes>
        <Route exact path="/" element={<Home posts={searchResults} />} />
        <Route
          exact
          path="/post"
          element={
            <NewPost
              handleSubmit={handleSubmit}
              postTitle={postTitle}
              setPostTitle={setPostTitle}
              postBody={postBody}
              setPostBody={setPostBody}
            />
          }
        />
        <Route
          path="/post/:id"
          element={<PostPage posts={posts} handleDelete={handleDelete} />}
        />
        <Route path="/about" element={<About />} />
        <Route path="*" element={<Missing />} />
      </Routes>
      <Footer />
    </div>
  );
}

export default App;
```

# #End  </details>

<details>
  <summary>43. Blog App - Customise Page Not Found (Missing) Component</summary>

# Customise Page Not Found (Missing) Component

<img width="972" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/1e7c825e-fa92-416f-b07f-98265e0841b8">
<img width="1215" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/e057f8f8-abfb-484f-9353-d19aacb7eacb">

### x-dave-gray/blogapp/src/App.js:

```js
import { useState, useEffect } from "react";
import { Route, Routes, useNavigate } from "react-router-dom";
import { format } from "date-fns";
import Header from "./Header";
import Nav from "./Nav";
import Footer from "./Footer";
import Home from "./Home";
import NewPost from "./NewPost";
import PostPage from "./PostPage";
import About from "./About";
import Missing from "./Missing";

function App() {
  const [posts, setPosts] = useState([
    {
      id: 1,
      title: "My First Post",
      datetime: "July 01, 2021 11:17:36 AM",
      body: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis consequatur expedita, assumenda similique non optio! Modi nesciunt excepturi corrupti atque blanditiis quo nobis, non optio quae possimus illum exercitationem ipsa!",
    },
    {
      id: 2,
      title: "My 2nd Post",
      datetime: "July 01, 2021 11:17:36 AM",
      body: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis consequatur expedita, assumenda similique non optio! Modi nesciunt excepturi corrupti atque blanditiis quo nobis, non optio quae possimus illum exercitationem ipsa!",
    },
    {
      id: 3,
      title: "My 3rd Post",
      datetime: "July 01, 2021 11:17:36 AM",
      body: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis consequatur expedita, assumenda similique non optio! Modi nesciunt excepturi corrupti atque blanditiis quo nobis, non optio quae possimus illum exercitationem ipsa!",
    },
    {
      id: 4,
      title: "My Fourth Post",
      datetime: "July 01, 2021 11:17:36 AM",
      body: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis consequatur expedita, assumenda similique non optio! Modi nesciunt excepturi corrupti atque blanditiis quo nobis, non optio quae possimus illum exercitationem ipsa!",
    },
  ]);
  const [search, setSearch] = useState("");
  const [searchResults, setSearchResults] = useState([]);
  const [postTitle, setPostTitle] = useState("");
  const [postBody, setPostBody] = useState("");
  const navigate = useNavigate();

  useEffect(() => {
    const filteredResults = posts.filter(
      (post) =>
        post.body.toLowerCase().includes(search.toLowerCase()) ||
        post.title.toLowerCase().includes(search.toLowerCase())
    );

    setSearchResults(filteredResults.reverse());
  }, [posts, search]);

  const handleSubmit = (e) => {
    e.preventDefault();
    const id = posts.length ? posts[posts.length - 1].id + 1 : 1;
    const datetime = format(new Date(), "MMMM dd, yyyy pp");
    //const datetime = format(new Date(), "yyyy-MM-dd HH:mm:ss");
    const newPost = { id, title: postTitle, datetime, body: postBody };
    const allPosts = [...posts, newPost];
    setPosts(allPosts);
    setPostTitle("");
    setPostBody("");
    navigate("/");
  };

  const handleDelete = (id) => {
    const postList = posts.filter((post) => post.id !== id);
    setPosts(postList);
    navigate("/");
  };

  return (
    <div className="App">
      <Header title="React JS Blog" />
      <Nav search={search} setSearch={setSearch} />
      <Routes>
        <Route exact path="/" element={<Home posts={searchResults} />} />
        <Route
          exact
          path="/post"
          element={
            <NewPost
              handleSubmit={handleSubmit}
              postTitle={postTitle}
              setPostTitle={setPostTitle}
              postBody={postBody}
              setPostBody={setPostBody}
            />
          }
        />
        <Route
          path="/post/:id"
          element={<PostPage posts={posts} handleDelete={handleDelete} />}
        />
        <Route path="/about" element={<About />} />
        <Route path="*" element={<Missing />} />
      </Routes>
      <Footer />
    </div>
  );
}

export default App;
```

### x-dave-gray/blogapp/src/Missing.js:

```js
import React from "react";
import { Link } from "react-router-dom";

const Missing = () => {
  return (
    <main className="Missing">
      <h2>Page Not Found</h2>
      <p>Well, that's disappointing.</p>
      <p>
        <Link to="/">Visit Our Homepage</Link>
      </p>
    </main>
  );
};

export default Missing;
```

# #End  </details>

<details>
  <summary>44. Blog App - Customise Footer Component</summary>

# Customise Footer Component

<img width="970" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/1e00db3a-c6b7-4898-acde-0f3ec4223711">
<img width="1215" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/5fe9654f-624c-43c4-876c-2ed5c0c1fd7c">

### x-dave-gray/blogapp/src/App.js:

```js
import { useState, useEffect } from "react";
import { Route, Routes, useNavigate } from "react-router-dom";
import { format } from "date-fns";
import Header from "./Header";
import Nav from "./Nav";
import Footer from "./Footer";
import Home from "./Home";
import NewPost from "./NewPost";
import PostPage from "./PostPage";
import About from "./About";
import Missing from "./Missing";

function App() {
  const [posts, setPosts] = useState([
    {
      id: 1,
      title: "My First Post",
      datetime: "July 01, 2021 11:17:36 AM",
      body: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis consequatur expedita, assumenda similique non optio! Modi nesciunt excepturi corrupti atque blanditiis quo nobis, non optio quae possimus illum exercitationem ipsa!",
    },
    {
      id: 2,
      title: "My 2nd Post",
      datetime: "July 01, 2021 11:17:36 AM",
      body: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis consequatur expedita, assumenda similique non optio! Modi nesciunt excepturi corrupti atque blanditiis quo nobis, non optio quae possimus illum exercitationem ipsa!",
    },
    {
      id: 3,
      title: "My 3rd Post",
      datetime: "July 01, 2021 11:17:36 AM",
      body: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis consequatur expedita, assumenda similique non optio! Modi nesciunt excepturi corrupti atque blanditiis quo nobis, non optio quae possimus illum exercitationem ipsa!",
    },
    {
      id: 4,
      title: "My Fourth Post",
      datetime: "July 01, 2021 11:17:36 AM",
      body: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis consequatur expedita, assumenda similique non optio! Modi nesciunt excepturi corrupti atque blanditiis quo nobis, non optio quae possimus illum exercitationem ipsa!",
    },
  ]);
  const [search, setSearch] = useState("");
  const [searchResults, setSearchResults] = useState([]);
  const [postTitle, setPostTitle] = useState("");
  const [postBody, setPostBody] = useState("");
  const navigate = useNavigate();

  useEffect(() => {
    const filteredResults = posts.filter(
      (post) =>
        post.body.toLowerCase().includes(search.toLowerCase()) ||
        post.title.toLowerCase().includes(search.toLowerCase())
    );

    setSearchResults(filteredResults.reverse());
  }, [posts, search]);

  const handleSubmit = (e) => {
    e.preventDefault();
    const id = posts.length ? posts[posts.length - 1].id + 1 : 1;
    const datetime = format(new Date(), "MMMM dd, yyyy pp");
    //const datetime = format(new Date(), "yyyy-MM-dd HH:mm:ss");
    const newPost = { id, title: postTitle, datetime, body: postBody };
    const allPosts = [...posts, newPost];
    setPosts(allPosts);
    setPostTitle("");
    setPostBody("");
    navigate("/");
  };

  const handleDelete = (id) => {
    const postList = posts.filter((post) => post.id !== id);
    setPosts(postList);
    navigate("/");
  };

  return (
    <div className="App">
      <Header title="React JS Blog" />
      <Nav search={search} setSearch={setSearch} />
      <Routes>
        <Route exact path="/" element={<Home posts={searchResults} />} />
        <Route
          exact
          path="/post"
          element={
            <NewPost
              handleSubmit={handleSubmit}
              postTitle={postTitle}
              setPostTitle={setPostTitle}
              postBody={postBody}
              setPostBody={setPostBody}
            />
          }
        />
        <Route
          path="/post/:id"
          element={<PostPage posts={posts} handleDelete={handleDelete} />}
        />
        <Route path="/about" element={<About />} />
        <Route path="*" element={<Missing />} />
      </Routes>
      <Footer />
    </div>
  );
}

export default App;
```

### x-dave-gray/blogapp/src/Footer.js:

```js
import React from "react";

const Footer = () => {
  const today = new Date();

  return (
    <footer className="Footer">
      <p>Copyright &copy; {today.getFullYear()}</p>
    </footer>
  );
};

export default Footer;
```

# #End  </details>

<details>
  <summary>45. Blog App - Customise About Component</summary>

# Customise About Component

<img width="970" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/603a5c37-6bd1-470b-8611-4209116f9a4d">
<img width="1213" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/92960296-8bff-4fdd-bfd9-a63b52bf3a90">

### x-dave-gray/blogapp/src/App.js:

```js
import { useState, useEffect } from "react";
import { Route, Routes, useNavigate } from "react-router-dom";
import { format } from "date-fns";
import Header from "./Header";
import Nav from "./Nav";
import Footer from "./Footer";
import Home from "./Home";
import NewPost from "./NewPost";
import PostPage from "./PostPage";
import About from "./About";
import Missing from "./Missing";

function App() {
  const [posts, setPosts] = useState([
    {
      id: 1,
      title: "My First Post",
      datetime: "July 01, 2021 11:17:36 AM",
      body: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis consequatur expedita, assumenda similique non optio! Modi nesciunt excepturi corrupti atque blanditiis quo nobis, non optio quae possimus illum exercitationem ipsa!",
    },
    {
      id: 2,
      title: "My 2nd Post",
      datetime: "July 01, 2021 11:17:36 AM",
      body: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis consequatur expedita, assumenda similique non optio! Modi nesciunt excepturi corrupti atque blanditiis quo nobis, non optio quae possimus illum exercitationem ipsa!",
    },
    {
      id: 3,
      title: "My 3rd Post",
      datetime: "July 01, 2021 11:17:36 AM",
      body: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis consequatur expedita, assumenda similique non optio! Modi nesciunt excepturi corrupti atque blanditiis quo nobis, non optio quae possimus illum exercitationem ipsa!",
    },
    {
      id: 4,
      title: "My Fourth Post",
      datetime: "July 01, 2021 11:17:36 AM",
      body: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis consequatur expedita, assumenda similique non optio! Modi nesciunt excepturi corrupti atque blanditiis quo nobis, non optio quae possimus illum exercitationem ipsa!",
    },
  ]);
  const [search, setSearch] = useState("");
  const [searchResults, setSearchResults] = useState([]);
  const [postTitle, setPostTitle] = useState("");
  const [postBody, setPostBody] = useState("");
  const navigate = useNavigate();

  useEffect(() => {
    const filteredResults = posts.filter(
      (post) =>
        post.body.toLowerCase().includes(search.toLowerCase()) ||
        post.title.toLowerCase().includes(search.toLowerCase())
    );

    setSearchResults(filteredResults.reverse());
  }, [posts, search]);

  const handleSubmit = (e) => {
    e.preventDefault();
    const id = posts.length ? posts[posts.length - 1].id + 1 : 1;
    const datetime = format(new Date(), "MMMM dd, yyyy pp");
    //const datetime = format(new Date(), "yyyy-MM-dd HH:mm:ss");
    const newPost = { id, title: postTitle, datetime, body: postBody };
    const allPosts = [...posts, newPost];
    setPosts(allPosts);
    setPostTitle("");
    setPostBody("");
    navigate("/");
  };

  const handleDelete = (id) => {
    const postList = posts.filter((post) => post.id !== id);
    setPosts(postList);
    navigate("/");
  };

  return (
    <div className="App">
      <Header title="React JS Blog" />
      <Nav search={search} setSearch={setSearch} />
      <Routes>
        <Route exact path="/" element={<Home posts={searchResults} />} />
        <Route
          exact
          path="/post"
          element={
            <NewPost
              handleSubmit={handleSubmit}
              postTitle={postTitle}
              setPostTitle={setPostTitle}
              postBody={postBody}
              setPostBody={setPostBody}
            />
          }
        />
        <Route
          path="/post/:id"
          element={<PostPage posts={posts} handleDelete={handleDelete} />}
        />
        <Route path="/about" element={<About />} />
        <Route path="*" element={<Missing />} />
      </Routes>
      <Footer />
    </div>
  );
}

export default App;
```

### x-dave-gray/blogapp/src/About.js:

```js
import React from "react";

const About = () => {
  return (
    <main className="About">
      <h2>About</h2>
      <p style={{ marginTop: "1rem" }}>
        This is a Blog app project in Learn React App Series.
      </p>
    </main>
  );
};

export default About;
```

# #End  </details>

<details>
  <summary>46. Blog App - Customise CSS Width and Height Properties</summary>

# Customise CSS Width and Height Properties

<img width="967" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/4d2c9bc6-506a-4823-ad2f-0db7d95d1c58">
<img width="1214" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/6a2af6da-7794-40e4-9037-f944d1455bce">

### x-dave-gray/blogapp/src/index.css:

```bs
body {
  min-height: 100vh;
  font-family: "Open Sans", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: flex;
  background-color: #efefef;
}

#root {
  flex-grow: 1;
  display: flex;
  justify-content: center;
  align-items: center;
}

.App {
  width: 100%;
  max-width: 800px;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
  border: 1px solid #333;
  box-shadow: 0px 0px 15px gray;
}
```

```css
@import url("https://fonts.googleapis.com/css2?family=Open+Sans&display=swap");

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  font-size: 16px;
}

body {
  min-height: 100vh;
  font-family: "Open Sans", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: flex;
  background-color: #efefef;
}

#root {
  flex-grow: 1;
  display: flex;
  justify-content: center;
  align-items: center;
}

.App {
  width: 100%;
  max-width: 800px;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
  border: 1px solid #333;
  box-shadow: 0px 0px 15px gray;
}

.Header,
.Footer {
  width: 100%;
  background-color: #66d8f5;
  padding: 1rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.Header h1 {
  font-size: 1.5rem;
}

.Header svg {
  font-size: 2rem;
}

.Footer {
  padding: 0.75rem;
  display: grid;
  place-content: center;
}

.Nav {
  width: 100%;
  background-color: #333;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: flex-start;
}

.searchForm {
  width: 80%;
  padding: 1rem 0 0 0.75rem;
}

.searchForm input[type="text"] {
  font-family: "Open Sans", sans-serif;
  width: 100%;
  min-height: 48px;
  font-size: 1rem;
  padding: 0.25rem;
  border-radius: 0.25rem;
  outline: none;
}

.searchForm label {
  position: absolute;
  left: -99999px;
}

.Nav ul {
  color: #fff;
  list-style-type: none;
  display: flex;
  flex-wrap: nowrap;
  align-items: center;
}

.Nav li {
  padding: 1rem;
}

.Nav li:hover,
.Nav li:focus {
  padding: 1rem;
}

.Nav li a {
  color: #fff;
  text-decoration: none;
}

.Nav li:hover,
.Nav li:focus,
.Nav li:hover a,
.Nav li:focus a {
  background-color: #eee;
  color: #333;
}

.Nav li:hover a,
.Nav li:focus a {
  cursor: pointer;
}

.Home,
.NewPost,
.PostPage,
.About,
.Missing {
  width: 100%;
  flex-grow: 1;
  padding: 1rem;
  overflow-y: auto;
  background-color: #fff;
}

.post {
  margin-top: 1rem;
  padding-bottom: 1rem;
  border-bottom: 1px solid lightgray;
}

.Home .post a {
  text-decoration: none;
}

.Home .post a,
.Home .post a:visited {
  color: #000;
}

.post:first-child {
  margin-top: 0;
}

.post:last-child {
  border-bottom: none;
}

.postDate {
  font-size: 0.75rem;
  margin-top: 0.25rem;
}

.postBody {
  margin: 1rem 0;
}

.newPostForm {
  display: flex;
  flex-direction: column;
}

.newPostForm label {
  margin-top: 1rem;
}

.newPostForm input[type="text"],
.newPostForm textarea {
  font-family: "Open Sans", sans-serif;
  width: 100%;
  min-height: 48px;
  font-size: 1rem;
  padding: 0.25rem;
  border-radius: 0.25rem;
  margin-right: 0.25rem;
  outline: none;
}

.newPostForm textarea {
  height: 100px;
}

.newPostForm button {
  margin-top: 1rem;
  height: 48px;
  min-width: 48px;
  border-radius: 10px;
  padding: 0.5rem;
  font-size: 1rem;
  cursor: pointer;
}

.Missing h2,
.PostPage h2,
.Missing p,
.PostPage p {
  margin-bottom: 1rem;
}

.PostPage button {
  height: 48px;
  min-width: 48px;
  border-radius: 0.25rem;
  padding: 0.5rem;
  font-size: 1rem;
  background-color: red;
  color: #fff;
  cursor: pointer;
}

.statusMsg {
  margin-top: 2rem;
}

@media only screen and (min-width: 610px) {
  html {
    font-size: 22px;
  }

  .Header h1 {
    font-size: 2rem;
  }

  .Nav {
    flex-direction: row;
    flex-wrap: nowrap;
    justify-content: space-between;
    align-items: center;
  }

  .Nav ul {
    text-align: right;
  }

  .Nav li:hover,
  .Nav li:focus,
  .Nav li:hover a,
  .Nav li:focus a {
    background-color: #eee;
    color: #333;
  }

  .searchForm {
    width: 50%;
    padding: 0.5rem 0;
  }

  .searchForm input[type="text"] {
    margin-left: 0.5rem;
  }

  .newPostForm textarea {
    height: 300px;
  }
}

@media only screen and (min-width: 992px) {
  .Header svg {
    font-size: 3rem;
  }
}
```

# #End  </details>

+BLOG APP WITH JSON SERVER & AXIOS

<details>
  <summary>47. Blog App - Setup data/db.json file for JSON Server and Axios</summary>

# Setup data/db.json file for JSON Server and Axios

<img width="967" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/c6033862-3116-47c4-a67d-393c6f61208d">
<img width="1107" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/3a6f5086-0e8a-4d98-9d69-b5d6d1265432">
<img width="1106" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/74aab502-53fa-47a0-b7da-5519b7f369a9">

# Install Axios:

```bs
npm i axios -S
```

# Install and start JSON Server:

```bs
npm i json-server
json-server -p 3500 --watch data/db.json
```

```bs
npx json-server -p 3500 -w data/db.json
```

### x-dave-gray/blogapp/data/db.json:

```json
{
  "posts": [
    {
      "id": 1,
      "title": "My First Post",
      "datetime": "July 01, 2021 11:17:36 AM",
      "body": "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis consequatur expedita, assumenda similique non optio! Modi nesciunt excepturi corrupti atque blanditiis quo nobis, non optio quae possimus illum exercitationem ipsa!"
    },
    {
      "id": 2,
      "title": "My 2nd Post",
      "datetime": "July 01, 2021 11:17:36 AM",
      "body": "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis consequatur expedita, assumenda similique non optio! Modi nesciunt excepturi corrupti atque blanditiis quo nobis, non optio quae possimus illum exercitationem ipsa!"
    },
    {
      "id": 3,
      "title": "My 3rd Post",
      "datetime": "July 01, 2021 11:17:36 AM",
      "body": "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis consequatur expedita, assumenda similique non optio! Modi nesciunt excepturi corrupti atque blanditiis quo nobis, non optio quae possimus illum exercitationem ipsa!"
    },
    {
      "id": 4,
      "title": "My Fourth Post",
      "datetime": "July 01, 2021 11:17:36 AM",
      "body": "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis consequatur expedita, assumenda similique non optio! Modi nesciunt excepturi corrupti atque blanditiis quo nobis, non optio quae possimus illum exercitationem ipsa!"
    }
  ]
}
```

### x-dave-gray/blogapp/src/App.js:

```js
import { useState, useEffect } from "react";
import { Route, Routes, useNavigate } from "react-router-dom";
import { format } from "date-fns";
import Header from "./Header";
import Nav from "./Nav";
import Footer from "./Footer";
import Home from "./Home";
import NewPost from "./NewPost";
import PostPage from "./PostPage";
import About from "./About";
import Missing from "./Missing";

function App() {
  const [posts, setPosts] = useState([]);
  const [search, setSearch] = useState("");
  const [searchResults, setSearchResults] = useState([]);
  const [postTitle, setPostTitle] = useState("");
  const [postBody, setPostBody] = useState("");
  const navigate = useNavigate();

  useEffect(() => {
    const filteredResults = posts.filter(
      (post) =>
        post.body.toLowerCase().includes(search.toLowerCase()) ||
        post.title.toLowerCase().includes(search.toLowerCase())
    );

    setSearchResults(filteredResults.reverse());
  }, [posts, search]);

  const handleSubmit = (e) => {
    e.preventDefault();
    const id = posts.length ? posts[posts.length - 1].id + 1 : 1;
    const datetime = format(new Date(), "MMMM dd, yyyy pp");
    //const datetime = format(new Date(), "yyyy-MM-dd HH:mm:ss");
    const newPost = { id, title: postTitle, datetime, body: postBody };
    const allPosts = [...posts, newPost];
    setPosts(allPosts);
    setPostTitle("");
    setPostBody("");
    navigate("/");
  };

  const handleDelete = (id) => {
    const postList = posts.filter((post) => post.id !== id);
    setPosts(postList);
    navigate("/");
  };

  return (
    <div className="App">
      <Header title="React JS Blog" />
      <Nav search={search} setSearch={setSearch} />
      <Routes>
        <Route exact path="/" element={<Home posts={searchResults} />} />
        <Route
          exact
          path="/post"
          element={
            <NewPost
              handleSubmit={handleSubmit}
              postTitle={postTitle}
              setPostTitle={setPostTitle}
              postBody={postBody}
              setPostBody={setPostBody}
            />
          }
        />
        <Route
          path="/post/:id"
          element={<PostPage posts={posts} handleDelete={handleDelete} />}
        />
        <Route path="/about" element={<About />} />
        <Route path="*" element={<Missing />} />
      </Routes>
      <Footer />
    </div>
  );
}

export default App;
```

# #End  </details>

<details>
  <summary>48. Blog App - Setting Base URL for Axios</summary>

# Setting Base URL for Axios

<img width="967" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/2f8f2a8b-171f-479a-8756-0f1717bf72bd">

### x-dave-gray/blogapp/src/api/posts.js:

```js
import axios from "axios";

export default axios.create({ baseURL: "http://localhost:3500" });
```

# #End  </details>

<details>
  <summary>49. Blog App - Fetch Data with Axios</summary>

# Fetch Data with Axios

<img width="967" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/e3737711-757f-4c4d-bb8a-6a49e8ee4ab7">
<img width="1106" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/e792aa73-1d65-4fa9-93b1-343c2453db67">

### x-dave-gray/blogapp/src/App.js:

```bs
useEffect(() => {
    const fetchPosts = async () => {
      try {
        const response = await api.get("/posts");
        setPosts(response.data);
        // if (response && response.data) {
        //   setPosts(response.data);
        // }
      } catch (err) {
        if (err.response) {
          // Got Data Error response
          console.log(err.response.data.message);
          console.log(err.response.data);
          console.log(err.response.status);
          console.log(err.response.headers);
        } else {
          //Got No Data Error response, if (err.code === 404)
          console.log(`Error: ${err.message}`);
        }
      }
    };

    fetchPosts();
  }, []);
```

```js
import { useState, useEffect } from "react";
import { Route, Routes, useNavigate } from "react-router-dom";
import { format } from "date-fns";
import Header from "./Header";
import Nav from "./Nav";
import Footer from "./Footer";
import Home from "./Home";
import NewPost from "./NewPost";
import PostPage from "./PostPage";
import About from "./About";
import Missing from "./Missing";
import api from "./api/posts";

function App() {
  const [posts, setPosts] = useState([]);
  const [search, setSearch] = useState("");
  const [searchResults, setSearchResults] = useState([]);
  const [postTitle, setPostTitle] = useState("");
  const [postBody, setPostBody] = useState("");
  const navigate = useNavigate();

  useEffect(() => {
    const fetchPosts = async () => {
      try {
        const response = await api.get("/posts");
        setPosts(response.data);
        // if (response && response.data) {
        //   setPosts(response.data);
        // }
      } catch (err) {
        if (err.response) {
          // Got Data Error response
          console.log(err.response.data.message);
          console.log(err.response.data);
          console.log(err.response.status);
          console.log(err.response.headers);
        } else {
          //Got No Data Error response, if (err.code === 404)
          console.log(`Error: ${err.message}`);
        }
      }
    };

    fetchPosts();
  }, []);

  useEffect(() => {
    const filteredResults = posts.filter(
      (post) =>
        post.body.toLowerCase().includes(search.toLowerCase()) ||
        post.title.toLowerCase().includes(search.toLowerCase())
    );

    setSearchResults(filteredResults.reverse());
  }, [posts, search]);

  const handleSubmit = (e) => {
    e.preventDefault();
    const id = posts.length ? posts[posts.length - 1].id + 1 : 1;
    const datetime = format(new Date(), "MMMM dd, yyyy pp");
    //const datetime = format(new Date(), "yyyy-MM-dd HH:mm:ss");
    const newPost = { id, title: postTitle, datetime, body: postBody };
    const allPosts = [...posts, newPost];
    setPosts(allPosts);
    setPostTitle("");
    setPostBody("");
    navigate("/");
  };

  const handleDelete = (id) => {
    const postList = posts.filter((post) => post.id !== id);
    setPosts(postList);
    navigate("/");
  };

  return (
    <div className="App">
      <Header title="React JS Blog" />
      <Nav search={search} setSearch={setSearch} />
      <Routes>
        <Route exact path="/" element={<Home posts={searchResults} />} />
        <Route
          exact
          path="/post"
          element={
            <NewPost
              handleSubmit={handleSubmit}
              postTitle={postTitle}
              setPostTitle={setPostTitle}
              postBody={postBody}
              setPostBody={setPostBody}
            />
          }
        />
        <Route
          path="/post/:id"
          element={<PostPage posts={posts} handleDelete={handleDelete} />}
        />
        <Route path="/about" element={<About />} />
        <Route path="*" element={<Missing />} />
      </Routes>
      <Footer />
    </div>
  );
}

export default App;
```

# #End  </details>

<details>
  <summary>50. Blog App - Post/Create Data with Axios</summary>

# Post/Create Data with Axios

<img width="969" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/24f42308-5bd1-4146-9e8f-be910a5eec60">
<img width="1106" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/43c47a2b-d019-40f5-bfe5-fff6f5941466">
<img width="1106" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/2818fb71-2202-4957-8767-c99fbfd9ea2d">
<img width="1105" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/69c26b00-3093-47b3-9e5b-c7d1671ddf9d">

### x-dave-gray/blogapp/src/App.js:

```bs
const handleSubmit = async (e) => {
    e.preventDefault();
    const id = posts.length ? posts[posts.length - 1].id + 1 : 1;
    const datetime = format(new Date(), "MMMM dd, yyyy pp");
    //const datetime = format(new Date(), "yyyy-MM-dd HH:mm:ss");
    const newPost = { id, title: postTitle, datetime, body: postBody };
    try {
      const response = await api.post("/posts", newPost);
      const allPosts = [...posts, response.data];
      setPosts(allPosts);
      setPostTitle("");
      setPostBody("");
      navigate("/");
    } catch (err) {
      console.log(`Error: ${err.message}`);
    }
  };
```

```js
import { useState, useEffect } from "react";
import { Route, Routes, useNavigate } from "react-router-dom";
import { format } from "date-fns";
import Header from "./Header";
import Nav from "./Nav";
import Footer from "./Footer";
import Home from "./Home";
import NewPost from "./NewPost";
import PostPage from "./PostPage";
import About from "./About";
import Missing from "./Missing";
import api from "./api/posts";

function App() {
  const [posts, setPosts] = useState([]);
  const [search, setSearch] = useState("");
  const [searchResults, setSearchResults] = useState([]);
  const [postTitle, setPostTitle] = useState("");
  const [postBody, setPostBody] = useState("");
  const navigate = useNavigate();

  useEffect(() => {
    const fetchPosts = async () => {
      try {
        const response = await api.get("/posts");
        setPosts(response.data);
        // if (response && response.data) {
        //   setPosts(response.data);
        // }
      } catch (err) {
        if (err.response) {
          // Got Data Error response
          console.log(err.response.data.message);
          console.log(err.response.data);
          console.log(err.response.status);
          console.log(err.response.headers);
        } else {
          //Got No Data Error response, if (err.code === 404)
          console.log(`Error: ${err.message}`);
        }
      }
    };

    fetchPosts();
  }, []);

  useEffect(() => {
    const filteredResults = posts.filter(
      (post) =>
        post.body.toLowerCase().includes(search.toLowerCase()) ||
        post.title.toLowerCase().includes(search.toLowerCase())
    );

    setSearchResults(filteredResults.reverse());
  }, [posts, search]);

  const handleSubmit = async (e) => {
    e.preventDefault();
    const id = posts.length ? posts[posts.length - 1].id + 1 : 1;
    const datetime = format(new Date(), "MMMM dd, yyyy pp");
    //const datetime = format(new Date(), "yyyy-MM-dd HH:mm:ss");
    const newPost = { id, title: postTitle, datetime, body: postBody };
    try {
      const response = await api.post("/posts", newPost);
      const allPosts = [...posts, response.data];
      setPosts(allPosts);
      setPostTitle("");
      setPostBody("");
      navigate("/");
    } catch (err) {
      console.log(`Error: ${err.message}`);
    }
  };

  const handleDelete = (id) => {
    const postList = posts.filter((post) => post.id !== id);
    setPosts(postList);
    navigate("/");
  };

  return (
    <div className="App">
      <Header title="React JS Blog" />
      <Nav search={search} setSearch={setSearch} />
      <Routes>
        <Route exact path="/" element={<Home posts={searchResults} />} />
        <Route
          exact
          path="/post"
          element={
            <NewPost
              handleSubmit={handleSubmit}
              postTitle={postTitle}
              setPostTitle={setPostTitle}
              postBody={postBody}
              setPostBody={setPostBody}
            />
          }
        />
        <Route
          path="/post/:id"
          element={<PostPage posts={posts} handleDelete={handleDelete} />}
        />
        <Route path="/about" element={<About />} />
        <Route path="*" element={<Missing />} />
      </Routes>
      <Footer />
    </div>
  );
}

export default App;
```

# #End  </details>

<details>
  <summary>51. Blog App - Delete Data with Axios</summary>

# Delete Data with Axios

<img width="970" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/40cd3dbd-40cb-4225-a03a-71e005a9738f">
<img width="1107" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/d53176fd-40be-47c9-ad68-6815c751fc6e">
<img width="1107" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/17d0785b-c4e8-47af-92a1-1895d32b82a1">
<img width="1107" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/ab8feb90-693d-40e7-ad71-5d9103946b13">
<img width="1107" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/5c7cbfb9-9962-4e53-8984-96b61540f803">

### x-dave-gray/blogapp/src/App.js:

```bs
const handleDelete = async (id) => {
    try {
      await api.delete(`/posts/${id}`);
      const postList = posts.filter((post) => post.id !== id);
      setPosts(postList);
      navigate("/");
    } catch (err) {
      console.log(`Error: ${err.message}`);
    }
  };
```

```js
import { useState, useEffect } from "react";
import { Route, Routes, useNavigate } from "react-router-dom";
import { format } from "date-fns";
import Header from "./Header";
import Nav from "./Nav";
import Footer from "./Footer";
import Home from "./Home";
import NewPost from "./NewPost";
import PostPage from "./PostPage";
import About from "./About";
import Missing from "./Missing";
import api from "./api/posts";

function App() {
  const [posts, setPosts] = useState([]);
  const [search, setSearch] = useState("");
  const [searchResults, setSearchResults] = useState([]);
  const [postTitle, setPostTitle] = useState("");
  const [postBody, setPostBody] = useState("");
  const navigate = useNavigate();

  useEffect(() => {
    const fetchPosts = async () => {
      try {
        const response = await api.get("/posts");
        setPosts(response.data);
        // if (response && response.data) {
        //   setPosts(response.data);
        // }
      } catch (err) {
        if (err.response) {
          // Got Data Error response
          console.log(err.response.data.message);
          console.log(err.response.data);
          console.log(err.response.status);
          console.log(err.response.headers);
        } else {
          //Got No Data Error response, if (err.code === 404)
          console.log(`Error: ${err.message}`);
        }
      }
    };

    fetchPosts();
  }, []);

  useEffect(() => {
    const filteredResults = posts.filter(
      (post) =>
        post.body.toLowerCase().includes(search.toLowerCase()) ||
        post.title.toLowerCase().includes(search.toLowerCase())
    );

    setSearchResults(filteredResults.reverse());
  }, [posts, search]);

  const handleSubmit = async (e) => {
    e.preventDefault();
    const id = posts.length ? posts[posts.length - 1].id + 1 : 1;
    const datetime = format(new Date(), "MMMM dd, yyyy pp");
    //const datetime = format(new Date(), "yyyy-MM-dd HH:mm:ss");
    const newPost = { id, title: postTitle, datetime, body: postBody };
    try {
      const response = await api.post("/posts", newPost);
      const allPosts = [...posts, response.data];
      setPosts(allPosts);
      setPostTitle("");
      setPostBody("");
      navigate("/");
    } catch (err) {
      console.log(`Error: ${err.message}`);
    }
  };

  const handleDelete = async (id) => {
    try {
      await api.delete(`/posts/${id}`);
      const postList = posts.filter((post) => post.id !== id);
      setPosts(postList);
      navigate("/");
    } catch (err) {
      console.log(`Error: ${err.message}`);
    }
  };

  return (
    <div className="App">
      <Header title="React JS Blog" />
      <Nav search={search} setSearch={setSearch} />
      <Routes>
        <Route exact path="/" element={<Home posts={searchResults} />} />
        <Route
          exact
          path="/post"
          element={
            <NewPost
              handleSubmit={handleSubmit}
              postTitle={postTitle}
              setPostTitle={setPostTitle}
              postBody={postBody}
              setPostBody={setPostBody}
            />
          }
        />
        <Route
          path="/post/:id"
          element={<PostPage posts={posts} handleDelete={handleDelete} />}
        />
        <Route path="/about" element={<About />} />
        <Route path="*" element={<Missing />} />
      </Routes>
      <Footer />
    </div>
  );
}

export default App;
```

# #End  </details>

<details>
  <summary>52. Blog App - Update/Edit Post with Axios</summary>

# Update/Edit Post with Axios

<img width="971" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/c66b0892-3d93-43f0-905d-09705d462412">
<img width="1105" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/f37240e0-43ea-4724-8b3f-a7b06fc73734">
<img width="1105" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/f5e7a2f6-b464-4fe4-a829-1add12b9f01f">
<img width="1105" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/e8b02b87-da55-4fb9-a39c-4921878d81c0">
<img width="1105" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/39dd736b-3aa9-46cf-a641-7d8cf16237cc">
<img width="1105" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/8c3060e3-8e52-4fa4-b0b7-b9de2c957539">

### x-dave-gray/blogapp/src/App.js:

```js
import { useState, useEffect } from "react";
import { Route, Routes, useNavigate } from "react-router-dom";
import { format } from "date-fns";
import Header from "./Header";
import Nav from "./Nav";
import Footer from "./Footer";
import Home from "./Home";
import NewPost from "./NewPost";
import PostPage from "./PostPage";
import About from "./About";
import Missing from "./Missing";
import api from "./api/posts";
import EditPost from "./EditPost";

function App() {
  const [posts, setPosts] = useState([]);
  const [search, setSearch] = useState("");
  const [searchResults, setSearchResults] = useState([]);
  const [postTitle, setPostTitle] = useState("");
  const [postBody, setPostBody] = useState("");
  const [editTitle, setEditTitle] = useState("");
  const [editBody, setEditBody] = useState("");
  const navigate = useNavigate();

  useEffect(() => {
    const fetchPosts = async () => {
      try {
        const response = await api.get("/posts");
        setPosts(response.data);
        // if (response && response.data) {
        //   setPosts(response.data);
        // }
      } catch (err) {
        if (err.response) {
          // Got Data Error response
          console.log(err.response.data.message);
          console.log(err.response.data);
          console.log(err.response.status);
          console.log(err.response.headers);
        } else {
          //Got No Data Error response, if (err.code === 404)
          console.log(`Error: ${err.message}`);
        }
      }
    };

    fetchPosts();
  }, []);

  useEffect(() => {
    const filteredResults = posts.filter(
      (post) =>
        post.body.toLowerCase().includes(search.toLowerCase()) ||
        post.title.toLowerCase().includes(search.toLowerCase())
    );

    setSearchResults(filteredResults.reverse());
  }, [posts, search]);

  const handleSubmit = async (e) => {
    e.preventDefault();
    const id = posts.length ? posts[posts.length - 1].id + 1 : 1;
    const datetime = format(new Date(), "MMMM dd, yyyy pp");
    //const datetime = format(new Date(), "yyyy-MM-dd HH:mm:ss");
    const newPost = { id, title: postTitle, datetime, body: postBody };
    try {
      const response = await api.post("/posts", newPost);
      const allPosts = [...posts, response.data];
      setPosts(allPosts);
      setPostTitle("");
      setPostBody("");
      navigate("/");
    } catch (err) {
      console.log(`Error: ${err.message}`);
    }
  };

  const handleEdit = async (id) => {
    const datetime = format(new Date(), "MMMM dd, yyyy pp");
    const updatedPost = { id, title: editTitle, datetime, body: editBody };
    try {
      const response = await api.put(`/posts/${id}`, updatedPost);
      setPosts(
        posts.map((post) => (post.id === id ? { ...response.data } : post))
      );
      setEditTitle("");
      setEditBody("");
      navigate("/");
    } catch (err) {
      console.log(`Error: ${err.message}`);
    }
  };

  const handleDelete = async (id) => {
    try {
      await api.delete(`/posts/${id}`);
      const postList = posts.filter((post) => post.id !== id);
      setPosts(postList);
      navigate("/");
    } catch (err) {
      console.log(`Error: ${err.message}`);
    }
  };

  return (
    <div className="App">
      <Header title="React JS Blog" />
      <Nav search={search} setSearch={setSearch} />
      <Routes>
        <Route exact path="/" element={<Home posts={searchResults} />} />
        <Route
          exact
          path="/post"
          element={
            <NewPost
              handleSubmit={handleSubmit}
              postTitle={postTitle}
              setPostTitle={setPostTitle}
              postBody={postBody}
              setPostBody={setPostBody}
            />
          }
        />
        <Route
          path="/edit/:id"
          element={
            <EditPost
              posts={posts}
              handleEdit={handleEdit}
              editTitle={editTitle}
              setEditTitle={setEditTitle}
              editBody={editBody}
              setEditBody={setEditBody}
            />
          }
        />
        <Route
          path="/post/:id"
          element={<PostPage posts={posts} handleDelete={handleDelete} />}
        />
        <Route path="/about" element={<About />} />
        <Route path="*" element={<Missing />} />
      </Routes>
      <Footer />
    </div>
  );
}

export default App;
```

### x-dave-gray/blogapp/src/EditPost.js:

```js
import React, { useEffect } from "react";
import { useParams, Link } from "react-router-dom";

const EditPost = ({
  posts,
  handleEdit,
  editBody,
  setEditBody,
  editTitle,
  setEditTitle,
}) => {
  const { id } = useParams();
  const post = posts.find((post) => post.id.toString() === id);

  useEffect(() => {
    if (post) {
      setEditTitle(post.title);
      setEditBody(post.body);
    }
  }, [post, setEditTitle, setEditBody]);

  return (
    <main className="NewPost">
      {editTitle ? (
        <>
          <h2>EditPost</h2>
          <form className="newPostForm" onSubmit={(e) => e.preventDefault()}>
            <label htmlFor="postTitle">Title:</label>
            <input
              type="text"
              id="postTitle"
              value={editTitle}
              onChange={(e) => setEditTitle(e.target.value)}
              required
            />
            <label htmlFor="postBody">Post:</label>
            <textarea
              id="postBody"
              value={editBody}
              onChange={(e) => setEditBody(e.target.value)}
              // cols="10"
              // rows="30"
              required
            />
            <button type="submit" onClick={() => handleEdit(post.id)}>
              Submit
            </button>
          </form>
        </>
      ) : (
        <>
          <h2>Post Not Found</h2>
          <p>Well, that's disappointing.</p>
          <p>
            <Link to="/">Visit our Homepage</Link>
          </p>
        </>
      )}
    </main>
  );
};

export default EditPost;
```

### x-dave-gray/blogapp/src/PostPage.js:

```js
import React from "react";
import { useParams, Link } from "react-router-dom";

const PostPage = ({ posts, handleDelete }) => {
  const { id } = useParams();
  const post = posts.find((post) => post.id.toString() === id);

  return (
    <main className="PostPage">
      <article className="post">
        {post ? (
          <>
            <h2>{post.title}</h2>
            <p className="postDate">{post.datetime}</p>
            <p className="postBody">{post.body}</p>
            <Link to={`/edit/${post.id}`}>
              <button className="editButton">Edit Post</button>
            </Link>
            <button
              className="deleteButton"
              onClick={() => handleDelete(post.id)}
            >
              Delete Post
            </button>
          </>
        ) : (
          <>
            <h2>Post Not Found</h2>
            <p>Well, that's disappointing.</p>
            <p>
              <Link to="/">Visit our Home Page</Link>
            </p>
          </>
        )}
      </article>
    </main>
  );
};

export default PostPage;
```

### x-dave-gray/blogapp/src/index.css:

```css
@import url("https://fonts.googleapis.com/css2?family=Open+Sans&display=swap");

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  font-size: 16px;
}

body {
  min-height: 100vh;
  font-family: "Open Sans", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: flex;
  background-color: #efefef;
}

#root {
  flex-grow: 1;
  display: flex;
  justify-content: center;
  align-items: center;
}

.App {
  width: 100%;
  max-width: 800px;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
  border: 1px solid #333;
  box-shadow: 0px 0px 15px gray;
}

.Header,
.Footer {
  width: 100%;
  background-color: #66d8f5;
  padding: 1rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.Header h1 {
  font-size: 1.5rem;
}

.Header svg {
  font-size: 2rem;
}

.Footer {
  padding: 0.75rem;
  display: grid;
  place-content: center;
}

.Nav {
  width: 100%;
  background-color: #333;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: flex-start;
}

.searchForm {
  width: 80%;
  padding: 1rem 0 0 0.75rem;
}

.searchForm input[type="text"] {
  font-family: "Open Sans", sans-serif;
  width: 100%;
  min-height: 48px;
  font-size: 1rem;
  padding: 0.25rem;
  border-radius: 0.25rem;
  outline: none;
}

.searchForm label {
  position: absolute;
  left: -99999px;
}

.Nav ul {
  color: #fff;
  list-style-type: none;
  display: flex;
  flex-wrap: nowrap;
  align-items: center;
}

.Nav li {
  padding: 1rem;
}

.Nav li:hover,
.Nav li:focus {
  padding: 1rem;
}

.Nav li a {
  color: #fff;
  text-decoration: none;
}

.Nav li:hover,
.Nav li:focus,
.Nav li:hover a,
.Nav li:focus a {
  background-color: #eee;
  color: #333;
}

.Nav li:hover a,
.Nav li:focus a {
  cursor: pointer;
}

.Home,
.NewPost,
.PostPage,
.About,
.Missing {
  width: 100%;
  flex-grow: 1;
  padding: 1rem;
  overflow-y: auto;
  background-color: #fff;
}

.post {
  margin-top: 1rem;
  padding-bottom: 1rem;
  border-bottom: 1px solid lightgray;
}

.Home .post a {
  text-decoration: none;
}

.Home .post a,
.Home .post a:visited {
  color: #000;
}

.post:first-child {
  margin-top: 0;
}

.post:last-child {
  border-bottom: none;
}

.postDate {
  font-size: 0.75rem;
  margin-top: 0.25rem;
}

.postBody {
  margin: 1rem 0;
}

.newPostForm {
  display: flex;
  flex-direction: column;
}

.newPostForm label {
  margin-top: 1rem;
}

.newPostForm input[type="text"],
.newPostForm textarea {
  font-family: "Open Sans", sans-serif;
  width: 100%;
  min-height: 48px;
  font-size: 1rem;
  padding: 0.25rem;
  border-radius: 0.25rem;
  margin-right: 0.25rem;
  outline: none;
}

.newPostForm textarea {
  height: 100px;
}

.newPostForm button {
  margin-top: 1rem;
  height: 48px;
  min-width: 48px;
  border-radius: 10px;
  padding: 0.5rem;
  font-size: 1rem;
  cursor: pointer;
}

.Missing p,
.PostPage p,
.NewPost p {
  margin-top: 1rem;
}

.PostPage button {
  height: 48px;
  min-width: 48px;
  border-radius: 0.25rem;
  padding: 0.5rem;
  margin-right: 0.5rem;
  font-size: 1rem;
  color: #fff;
  cursor: pointer;
}

.deleteButton {
  background-color: red;
}

.editButton {
  background-color: #333;
}

.statusMsg {
  margin-top: 2rem;
}

@media only screen and (min-width: 610px) {
  html {
    font-size: 22px;
  }

  .Header h1 {
    font-size: 2rem;
  }

  .Nav {
    flex-direction: row;
    flex-wrap: nowrap;
    justify-content: space-between;
    align-items: center;
  }

  .Nav ul {
    text-align: right;
  }

  .Nav li:hover,
  .Nav li:focus,
  .Nav li:hover a,
  .Nav li:focus a {
    background-color: #eee;
    color: #333;
  }

  .searchForm {
    width: 50%;
    padding: 0.5rem 0;
  }

  .searchForm input[type="text"] {
    margin-left: 0.5rem;
  }

  .newPostForm textarea {
    height: 300px;
  }
}

@media only screen and (min-width: 992px) {
  .Header svg {
    font-size: 3rem;
  }
}
```

# #End  </details>

+BLOG APP WITH CUSTOM HOOKS

<details>
  <summary>53. Blog App - Create useWindowSize Custom Hook</summary>

# Create useWindowSize Custom Hook

<img width="969" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/5725f4a5-e949-4df9-9f71-2cfbe3d9063f">
<img width="969" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/b04c3380-2f74-4846-b48e-15b4e61fbbe4">
<img width="1272" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/855bb9b4-8f10-4d10-8bd8-6f868d437cf7">
<img width="1272" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/3be88ba0-0211-45a8-9e82-59eeef2285a5">
<img width="1272" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/5160161b-d1ca-45a6-b2d2-5fdb25719caf">

# Install react-icons:

```bs
npm i react-icons -S
```

### x-dave-gray/blogapp/src/hooks/useWindowSize.js:

```js
import React, { useState, useEffect } from "react";

const useWindowSize = () => {
  const [windowSize, setWindowSize] = useState({
    width: undefined,
    height: undefined,
  });

  useEffect(() => {
    const handleResize = () => {
      setWindowSize({
        width: window.innerWidth,
        height: window.innerHeight,
      });
    };

    handleResize();

    window.addEventListener("resize", handleResize);

    const cleanUp = () => {
      //console.log("runs if a useEffect dep changes");
      window.removeEventListener("resize", handleResize);
    };
    return cleanUp;

    // () => window.removeEventListener("resize", handleResize);
  }, []);
  return windowSize;
};

export default useWindowSize;
```

### x-dave-gray/blogapp/src/App.js:

```js
import { useState, useEffect } from "react";
import { Route, Routes, useNavigate } from "react-router-dom";
import { format } from "date-fns";
import Header from "./Header";
import Nav from "./Nav";
import Footer from "./Footer";
import Home from "./Home";
import NewPost from "./NewPost";
import PostPage from "./PostPage";
import About from "./About";
import Missing from "./Missing";
import api from "./api/posts";
import EditPost from "./EditPost";
import useWindowSize from "./hooks/useWindowSize";

function App() {
  const [posts, setPosts] = useState([]);
  const [search, setSearch] = useState("");
  const [searchResults, setSearchResults] = useState([]);
  const [postTitle, setPostTitle] = useState("");
  const [postBody, setPostBody] = useState("");
  const [editTitle, setEditTitle] = useState("");
  const [editBody, setEditBody] = useState("");
  const navigate = useNavigate();
  const { width } = useWindowSize();

  useEffect(() => {
    const fetchPosts = async () => {
      try {
        const response = await api.get("/posts");
        setPosts(response.data);
      } catch (err) {
        if (err.response) {
          // Got Data Error but Not in the 200 response range
          console.log(err.response.data.message);
          console.log(err.response.data);
          console.log(err.response.status);
          console.log(err.response.headers);
        } else {
          //No Data Error, if (err.code === 404)
          console.log(`Error: ${err.message}`);
        }
      }
    };
    fetchPosts();
  }, []);

  useEffect(() => {
    const filteredResults = posts.filter(
      (post) =>
        post.body.toLowerCase().includes(search.toLowerCase()) ||
        post.title.toLowerCase().includes(search.toLowerCase())
    );

    setSearchResults(filteredResults.reverse());
  }, [posts, search]);

  const handleSubmit = async (e) => {
    e.preventDefault();
    const id = posts.length ? posts[posts.length - 1].id + 1 : 1;
    const datetime = format(new Date(), "MMMM dd, yyyy pp");
    //const datetime = format(new Date(), "yyyy-MM-dd HH:mm:ss");
    const newPost = { id, title: postTitle, datetime, body: postBody };
    try {
      const response = await api.post("/posts", newPost);
      const allPosts = [...posts, response.data];
      setPosts(allPosts);
      setPostTitle("");
      setPostBody("");
      navigate("/");
    } catch (err) {
      console.log(`Error: ${err.message}`);
    }
  };

  const handleEdit = async (id) => {
    const datetime = format(new Date(), "MMMM dd, yyyy pp");
    const updatedPost = { id, title: editTitle, datetime, body: editBody };
    try {
      const response = await api.put(`/posts/${id}`, updatedPost);
      setPosts(
        posts.map((post) => (post.id === id ? { ...response.data } : post))
      );
      setEditTitle("");
      setEditBody("");
      navigate("/");
    } catch (err) {
      console.log(`Error: ${err.message}`);
    }
  };

  const handleDelete = async (id) => {
    try {
      await api.delete(`/posts/${id}`);
      const postList = posts.filter((post) => post.id !== id);
      setPosts(postList);
      navigate("/");
    } catch (err) {
      console.log(`Error: ${err.message}`);
    }
  };

  return (
    <div className="App">
      <Header title="React JS Blog" width={width} />
      <Nav search={search} setSearch={setSearch} />
      <Routes>
        <Route exact path="/" element={<Home posts={searchResults} />} />
        <Route
          exact
          path="/post"
          element={
            <NewPost
              handleSubmit={handleSubmit}
              postTitle={postTitle}
              setPostTitle={setPostTitle}
              postBody={postBody}
              setPostBody={setPostBody}
            />
          }
        />
        <Route
          path="/edit/:id"
          element={
            <EditPost
              posts={posts}
              handleEdit={handleEdit}
              editTitle={editTitle}
              setEditTitle={setEditTitle}
              editBody={editBody}
              setEditBody={setEditBody}
            />
          }
        />
        <Route
          path="/post/:id"
          element={<PostPage posts={posts} handleDelete={handleDelete} />}
        />
        <Route path="/about" element={<About />} />
        <Route path="*" element={<Missing />} />
      </Routes>
      <Footer />
    </div>
  );
}

export default App;
```

### x-dave-gray/blogapp/src/Header.js:

```js
import React from "react";
import { FaLaptop, FaTabletAlt, FaMobileAlt } from "react-icons/fa";

const Header = ({ title, width }) => {
  return (
    <header className="Header">
      <h1>{title}</h1>
      {width < 768 ? (
        <FaMobileAlt />
      ) : width < 992 ? (
        <FaTabletAlt />
      ) : (
        <FaLaptop />
      )}
    </header>
  );
};

export default Header;
```

# #End  </details>

<details>
  <summary>54. Blog App - Create useAxiosFetch Custom Hook</summary>

# Create useAxiosFetch Custom Hook

<img width="969" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/20f4babd-182e-4bad-a2d3-f1dc519faa6f">
<img width="969" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/32345a40-5557-48dd-b869-85c244328676">
<img width="1271" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/8c9e7af0-c9f7-4bf3-a885-5da907bc8554">
<img width="1271" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/55efd625-b297-45a9-ade1-50b7dab951c5">

### x-dave-gray/blogapp/src/hooks/useAxiosFetch.js:

```js
import React, { useState, useEffect } from "react";
import axios from "axios";

const useAxiosFetch = (dataUrl) => {
  const [data, setData] = useState([]);
  const [fetchError, setFetchError] = useState(null);
  const [isLoading, setIsLoading] = useState(false);

  useEffect(() => {
    let isMounted = true;
    const source = axios.CancelToken.source();

    const fetchData = async (url) => {
      setIsLoading(true);
      try {
        const response = await axios.get(url, { cancelToken: source.token });
        if (isMounted) {
          setData(response.data);
          setFetchError(null);
        }
      } catch (err) {
        if (isMounted) {
          setFetchError(err.message);
          setData([]);
        }
      } finally {
        isMounted && setTimeout(() => setIsLoading(false), 1000);
      }
    };

    fetchData(dataUrl);

    const cleanUp = () => {
      //console.log("clean up function");
      isMounted = false;
      source.cancel();
    };

    return cleanUp;
  }, [dataUrl]);

  return { data, fetchError, isLoading };
};

export default useAxiosFetch;
```

### x-dave-gray/blogapp/src/App.js:

```js
import { useState, useEffect } from "react";
import { Route, Routes, useNavigate } from "react-router-dom";
import { format } from "date-fns";
import Header from "./Header";
import Nav from "./Nav";
import Footer from "./Footer";
import Home from "./Home";
import NewPost from "./NewPost";
import PostPage from "./PostPage";
import About from "./About";
import Missing from "./Missing";
import api from "./api/posts";
import EditPost from "./EditPost";
import useWindowSize from "./hooks/useWindowSize";
import useAxiosFetch from "./hooks/useAxiosFetch";

function App() {
  const [posts, setPosts] = useState([]);
  const [search, setSearch] = useState("");
  const [searchResults, setSearchResults] = useState([]);
  const [postTitle, setPostTitle] = useState("");
  const [postBody, setPostBody] = useState("");
  const [editTitle, setEditTitle] = useState("");
  const [editBody, setEditBody] = useState("");
  const navigate = useNavigate();
  const { width } = useWindowSize();
  const { data, fetchError, isLoading } = useAxiosFetch(
    "http://localhost:3500/posts"
  );

  useEffect(() => {
    setPosts(data);
  }, [data]);

  // useEffect(() => {
  //   const fetchPosts = async () => {
  //     try {
  //       const response = await api.get("/posts");
  //       setPosts(response.data);
  //     } catch (err) {
  //       if (err.response) {
  //         // Got Data Error but Not in the 200 response range
  //         console.log(err.response.data.message);
  //         console.log(err.response.data);
  //         console.log(err.response.status);
  //         console.log(err.response.headers);
  //       } else {
  //         //No Data Error, if (err.code === 404)
  //         console.log(`Error: ${err.message}`);
  //       }
  //     }
  //   };
  //   fetchPosts();
  // }, []);

  useEffect(() => {
    const filteredResults = posts.filter(
      (post) =>
        post.body.toLowerCase().includes(search.toLowerCase()) ||
        post.title.toLowerCase().includes(search.toLowerCase())
    );

    setSearchResults(filteredResults.reverse());
  }, [posts, search]);

  const handleSubmit = async (e) => {
    e.preventDefault();
    const id = posts.length ? posts[posts.length - 1].id + 1 : 1;
    const datetime = format(new Date(), "MMMM dd, yyyy pp");
    //const datetime = format(new Date(), "yyyy-MM-dd HH:mm:ss");
    const newPost = { id, title: postTitle, datetime, body: postBody };
    try {
      const response = await api.post("/posts", newPost);
      const allPosts = [...posts, response.data];
      setPosts(allPosts);
      setPostTitle("");
      setPostBody("");
      navigate("/");
    } catch (err) {
      console.log(`Error: ${err.message}`);
    }
  };

  const handleEdit = async (id) => {
    const datetime = format(new Date(), "MMMM dd, yyyy pp");
    const updatedPost = { id, title: editTitle, datetime, body: editBody };
    try {
      const response = await api.put(`/posts/${id}`, updatedPost);
      setPosts(
        posts.map((post) => (post.id === id ? { ...response.data } : post))
      );
      setEditTitle("");
      setEditBody("");
      navigate("/");
    } catch (err) {
      console.log(`Error: ${err.message}`);
    }
  };

  const handleDelete = async (id) => {
    try {
      await api.delete(`/posts/${id}`);
      const postList = posts.filter((post) => post.id !== id);
      setPosts(postList);
      navigate("/");
    } catch (err) {
      console.log(`Error: ${err.message}`);
    }
  };

  return (
    <div className="App">
      <Header title="React JS Blog" width={width} />
      <Nav search={search} setSearch={setSearch} />
      <Routes>
        <Route
          exact
          path="/"
          element={
            <Home
              posts={searchResults}
              fetchError={fetchError}
              isLoading={isLoading}
            />
          }
        />
        <Route
          exact
          path="/post"
          element={
            <NewPost
              handleSubmit={handleSubmit}
              postTitle={postTitle}
              setPostTitle={setPostTitle}
              postBody={postBody}
              setPostBody={setPostBody}
            />
          }
        />
        <Route
          path="/edit/:id"
          element={
            <EditPost
              posts={posts}
              handleEdit={handleEdit}
              editTitle={editTitle}
              setEditTitle={setEditTitle}
              editBody={editBody}
              setEditBody={setEditBody}
            />
          }
        />
        <Route
          path="/post/:id"
          element={<PostPage posts={posts} handleDelete={handleDelete} />}
        />
        <Route path="/about" element={<About />} />
        <Route path="*" element={<Missing />} />
      </Routes>
      <Footer />
    </div>
  );
}

export default App;
```

### x-dave-gray/blogapp/src/Home.js:

```js
import React from "react";
import Feed from "./Feed";

const Home = ({ posts, fetchError, isLoading }) => {
  return (
    <main className="Home">
      {isLoading && <p className="statusMsg">Loading posts...</p>}
      {!isLoading && fetchError && (
        <p className="statusMsg" style={{ color: "red" }}>
          {fetchError}
        </p>
      )}
      {!isLoading &&
        !fetchError &&
        (posts.length ? (
          <Feed posts={posts} />
        ) : (
          <p className="statusMsg">No Posts to display.</p>
        ))}
    </main>
  );
};

export default Home;
```

# #End  </details>

+BLOG APP WITH CONTEXT API

<details>
  <summary>55. Blog App - Create Context API</summary>

#  Create Context API

<img width="969" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/dab789fa-a85a-4cd2-b38e-055f17e78768">
<img width="1271" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/ef13f9e6-cded-4cb1-ac25-1d2082b7d37d">

### x-dave-gray/blogapp/src/context/DataContext.js:

```js
import React, { createContext, useState, useEffect } from "react";

const DataContext = createContext({});

export const DataProvider = ({ children }) => {
  return <DataContext.Provider value={{}}>{children}</DataContext.Provider>;
};

export default DataContext;
```

### x-dave-gray/blogapp/src/App.js:

```js
import { useState, useEffect } from "react";
import { Route, Routes, useNavigate } from "react-router-dom";
import { format } from "date-fns";
import Header from "./Header";
import Nav from "./Nav";
import Footer from "./Footer";
import Home from "./Home";
import NewPost from "./NewPost";
import PostPage from "./PostPage";
import About from "./About";
import Missing from "./Missing";
import api from "./api/posts";
import EditPost from "./EditPost";
import useWindowSize from "./hooks/useWindowSize";
import useAxiosFetch from "./hooks/useAxiosFetch";
import { DataProvider } from "./context/DataContext";

function App() {
  const [posts, setPosts] = useState([]);
  const [search, setSearch] = useState("");
  const [searchResults, setSearchResults] = useState([]);
  const [postTitle, setPostTitle] = useState("");
  const [postBody, setPostBody] = useState("");
  const [editTitle, setEditTitle] = useState("");
  const [editBody, setEditBody] = useState("");
  const navigate = useNavigate();
  const { width } = useWindowSize();
  const { data, fetchError, isLoading } = useAxiosFetch(
    "http://localhost:3500/posts"
  );

  useEffect(() => {
    setPosts(data);
  }, [data]);

  useEffect(() => {
    const filteredResults = posts.filter(
      (post) =>
        post.body.toLowerCase().includes(search.toLowerCase()) ||
        post.title.toLowerCase().includes(search.toLowerCase())
    );

    setSearchResults(filteredResults.reverse());
  }, [posts, search]);

  const handleSubmit = async (e) => {
    e.preventDefault();
    const id = posts.length ? posts[posts.length - 1].id + 1 : 1;
    const datetime = format(new Date(), "MMMM dd, yyyy pp");
    //const datetime = format(new Date(), "yyyy-MM-dd HH:mm:ss");
    const newPost = { id, title: postTitle, datetime, body: postBody };
    try {
      const response = await api.post("/posts", newPost);
      const allPosts = [...posts, response.data];
      setPosts(allPosts);
      setPostTitle("");
      setPostBody("");
      navigate("/");
    } catch (err) {
      console.log(`Error: ${err.message}`);
    }
  };

  const handleEdit = async (id) => {
    const datetime = format(new Date(), "MMMM dd, yyyy pp");
    const updatedPost = { id, title: editTitle, datetime, body: editBody };
    try {
      const response = await api.put(`/posts/${id}`, updatedPost);
      setPosts(
        posts.map((post) => (post.id === id ? { ...response.data } : post))
      );
      setEditTitle("");
      setEditBody("");
      navigate("/");
    } catch (err) {
      console.log(`Error: ${err.message}`);
    }
  };

  const handleDelete = async (id) => {
    try {
      await api.delete(`/posts/${id}`);
      const postList = posts.filter((post) => post.id !== id);
      setPosts(postList);
      navigate("/");
    } catch (err) {
      console.log(`Error: ${err.message}`);
    }
  };

  return (
    <div className="App">
      <DataProvider>
        <Header title="React JS Blog" width={width} />
        <Nav search={search} setSearch={setSearch} />
        <Routes>
          <Route
            exact
            path="/"
            element={
              <Home
                posts={searchResults}
                fetchError={fetchError}
                isLoading={isLoading}
              />
            }
          />
          <Route
            exact
            path="/post"
            element={
              <NewPost
                handleSubmit={handleSubmit}
                postTitle={postTitle}
                setPostTitle={setPostTitle}
                postBody={postBody}
                setPostBody={setPostBody}
              />
            }
          />
          <Route
            path="/edit/:id"
            element={
              <EditPost
                posts={posts}
                handleEdit={handleEdit}
                editTitle={editTitle}
                setEditTitle={setEditTitle}
                editBody={editBody}
                setEditBody={setEditBody}
              />
            }
          />
          <Route
            path="/post/:id"
            element={<PostPage posts={posts} handleDelete={handleDelete} />}
          />
          <Route path="/about" element={<About />} />
          <Route path="*" element={<Missing />} />
        </Routes>
        <Footer />
      </DataProvider>
    </div>
  );
}

export default App;
```

# #End  </details>

<details>
  <summary>56. Blog App - Refactor Header with Context API</summary>

# Refactor Header with Context API

<img width="968" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/214639db-2fea-4eee-9b5f-05069da59280">
<img width="968" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/4fee8db9-3c10-4cca-a3c7-f3aaa9b3350e">
<img width="1250" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/c4f0bb70-bfbe-480a-8f9a-67ab28467f52">

### x-dave-gray/blogapp/src/context/DataContext.js:

```js
import React, { createContext, useState, useEffect } from "react";
import useWindowSize from "../hooks/useWindowSize";

const DataContext = createContext({});

export const DataProvider = ({ children }) => {
  const { width } = useWindowSize();

  return (
    <DataContext.Provider value={{ width }}>{children}</DataContext.Provider>
  );
};

export default DataContext;
```

### x-dave-gray/blogapp/src/App.js:

```js
import { useState, useEffect } from "react";
import { Route, Routes, useNavigate } from "react-router-dom";
import { format } from "date-fns";
import Header from "./Header";
import Nav from "./Nav";
import Footer from "./Footer";
import Home from "./Home";
import NewPost from "./NewPost";
import PostPage from "./PostPage";
import About from "./About";
import Missing from "./Missing";
import api from "./api/posts";
import EditPost from "./EditPost";
import useAxiosFetch from "./hooks/useAxiosFetch";

import { DataProvider } from "./context/DataContext";

function App() {
  const [posts, setPosts] = useState([]);
  const [search, setSearch] = useState("");
  const [searchResults, setSearchResults] = useState([]);
  const [postTitle, setPostTitle] = useState("");
  const [postBody, setPostBody] = useState("");
  const [editTitle, setEditTitle] = useState("");
  const [editBody, setEditBody] = useState("");
  const navigate = useNavigate();

  const { data, fetchError, isLoading } = useAxiosFetch(
    "http://localhost:3500/posts"
  );

  useEffect(() => {
    setPosts(data);
  }, [data]);

  useEffect(() => {
    const filteredResults = posts.filter(
      (post) =>
        post.body.toLowerCase().includes(search.toLowerCase()) ||
        post.title.toLowerCase().includes(search.toLowerCase())
    );

    setSearchResults(filteredResults.reverse());
  }, [posts, search]);

  const handleSubmit = async (e) => {
    e.preventDefault();
    const id = posts.length ? posts[posts.length - 1].id + 1 : 1;
    const datetime = format(new Date(), "MMMM dd, yyyy pp");
    //const datetime = format(new Date(), "yyyy-MM-dd HH:mm:ss");
    const newPost = { id, title: postTitle, datetime, body: postBody };
    try {
      const response = await api.post("/posts", newPost);
      const allPosts = [...posts, response.data];
      setPosts(allPosts);
      setPostTitle("");
      setPostBody("");
      navigate("/");
    } catch (err) {
      console.log(`Error: ${err.message}`);
    }
  };

  const handleEdit = async (id) => {
    const datetime = format(new Date(), "MMMM dd, yyyy pp");
    const updatedPost = { id, title: editTitle, datetime, body: editBody };
    try {
      const response = await api.put(`/posts/${id}`, updatedPost);
      setPosts(
        posts.map((post) => (post.id === id ? { ...response.data } : post))
      );
      setEditTitle("");
      setEditBody("");
      navigate("/");
    } catch (err) {
      console.log(`Error: ${err.message}`);
    }
  };

  const handleDelete = async (id) => {
    try {
      await api.delete(`/posts/${id}`);
      const postList = posts.filter((post) => post.id !== id);
      setPosts(postList);
      navigate("/");
    } catch (err) {
      console.log(`Error: ${err.message}`);
    }
  };

  return (
    <div className="App">
      <DataProvider>
        <Header title="React JS Blog" />
        <Nav search={search} setSearch={setSearch} />
        <Routes>
          <Route
            exact
            path="/"
            element={
              <Home
                posts={searchResults}
                fetchError={fetchError}
                isLoading={isLoading}
              />
            }
          />
          <Route
            exact
            path="/post"
            element={
              <NewPost
                handleSubmit={handleSubmit}
                postTitle={postTitle}
                setPostTitle={setPostTitle}
                postBody={postBody}
                setPostBody={setPostBody}
              />
            }
          />
          <Route
            path="/edit/:id"
            element={
              <EditPost
                posts={posts}
                handleEdit={handleEdit}
                editTitle={editTitle}
                setEditTitle={setEditTitle}
                editBody={editBody}
                setEditBody={setEditBody}
              />
            }
          />
          <Route
            path="/post/:id"
            element={<PostPage posts={posts} handleDelete={handleDelete} />}
          />
          <Route path="/about" element={<About />} />
          <Route path="*" element={<Missing />} />
        </Routes>
        <Footer />
      </DataProvider>
    </div>
  );
}

export default App;
```

### x-dave-gray/blogapp/src/Header.js:

```js
import React, { useContext } from "react";
import { FaLaptop, FaTabletAlt, FaMobileAlt } from "react-icons/fa";
import DataContext from "./context/DataContext";

const Header = ({ title }) => {
  const { width } = useContext(DataContext);

  return (
    <header className="Header">
      <h1>{title}</h1>
      {width < 768 ? (
        <FaMobileAlt />
      ) : width < 992 ? (
        <FaTabletAlt />
      ) : (
        <FaLaptop />
      )}
    </header>
  );
};

export default Header;
```

# #End  </details>

<details>
  <summary>57. Blog App - Refactor Nav and Home with Context API</summary>

# Refactor Nav and Home with Context API

<img width="967" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/66acee86-e8f0-4702-a333-fcc049923188">
<img width="967" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/740808b3-b398-453e-ac0d-76d44178ef79">
<img width="967" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/a7496d22-4ef5-4bb3-b7d7-63584276793d">
<img width="1249" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/2561a649-8010-452f-a6fc-2b375d24cebf">

### x-dave-gray/blogapp/src/context/DataContext.js:

```js
import React, { createContext, useState, useEffect } from "react";
import { useNavigate } from "react-router-dom";
import { format } from "date-fns";
import api from "../api/posts";
import useAxiosFetch from "../hooks/useAxiosFetch";
import useWindowSize from "../hooks/useWindowSize";

const DataContext = createContext({});

export const DataProvider = ({ children }) => {
  const { width } = useWindowSize();
  const [posts, setPosts] = useState([]);
  const [search, setSearch] = useState("");
  const [searchResults, setSearchResults] = useState([]);
  const [postTitle, setPostTitle] = useState("");
  const [postBody, setPostBody] = useState("");
  const [editTitle, setEditTitle] = useState("");
  const [editBody, setEditBody] = useState("");
  const navigate = useNavigate();

  const { data, fetchError, isLoading } = useAxiosFetch(
    "http://localhost:3500/posts"
  );

  useEffect(() => {
    setPosts(data);
  }, [data]);

  useEffect(() => {
    const filteredResults = posts.filter(
      (post) =>
        post.body.toLowerCase().includes(search.toLowerCase()) ||
        post.title.toLowerCase().includes(search.toLowerCase())
    );

    setSearchResults(filteredResults.reverse());
  }, [posts, search]);

  const handleSubmit = async (e) => {
    e.preventDefault();
    const id = posts.length ? posts[posts.length - 1].id + 1 : 1;
    const datetime = format(new Date(), "MMMM dd, yyyy pp");
    //const datetime = format(new Date(), "yyyy-MM-dd HH:mm:ss");
    const newPost = { id, title: postTitle, datetime, body: postBody };
    try {
      const response = await api.post("/posts", newPost);
      const allPosts = [...posts, response.data];
      setPosts(allPosts);
      setPostTitle("");
      setPostBody("");
      navigate("/");
    } catch (err) {
      console.log(`Error: ${err.message}`);
    }
  };

  const handleEdit = async (id) => {
    const datetime = format(new Date(), "MMMM dd, yyyy pp");
    const updatedPost = { id, title: editTitle, datetime, body: editBody };
    try {
      const response = await api.put(`/posts/${id}`, updatedPost);
      setPosts(
        posts.map((post) => (post.id === id ? { ...response.data } : post))
      );
      setEditTitle("");
      setEditBody("");
      navigate("/");
    } catch (err) {
      console.log(`Error: ${err.message}`);
    }
  };

  const handleDelete = async (id) => {
    try {
      await api.delete(`/posts/${id}`);
      const postList = posts.filter((post) => post.id !== id);
      setPosts(postList);
      navigate("/");
    } catch (err) {
      console.log(`Error: ${err.message}`);
    }
  };

  return (
    <DataContext.Provider
      value={{
        width,
        search,
        setSearch,
        searchResults,
        fetchError,
        isLoading,
      }}
    >
      {children}
    </DataContext.Provider>
  );
};

export default DataContext;
```

### x-dave-gray/blogapp/src/App.js:

```js
import React from "react";
import { Route, Routes } from "react-router-dom";
import Header from "./Header";
import Nav from "./Nav";
import Footer from "./Footer";
import Home from "./Home";
import NewPost from "./NewPost";
import PostPage from "./PostPage";
import About from "./About";
import Missing from "./Missing";
import EditPost from "./EditPost";

import { DataProvider } from "./context/DataContext";

function App() {
  const {
    handleSubmit,
    postTitle,
    setPostTitle,
    postBody,
    setPostBody,
    posts,
    handleEdit,
    editTitle,
    setEditTitle,
    editBody,
    setEditBody,
    handleDelete,
  } = {};
  return (
    <div className="App">
      <DataProvider>
        <Header title="React JS Blog" />
        <Nav />
        <Routes>
          <Route exact path="/" element={<Home />} />
          <Route
            exact
            path="/post"
            element={
              <NewPost
                handleSubmit={handleSubmit}
                postTitle={postTitle}
                setPostTitle={setPostTitle}
                postBody={postBody}
                setPostBody={setPostBody}
              />
            }
          />
          <Route
            path="/edit/:id"
            element={
              <EditPost
                posts={posts}
                handleEdit={handleEdit}
                editTitle={editTitle}
                setEditTitle={setEditTitle}
                editBody={editBody}
                setEditBody={setEditBody}
              />
            }
          />
          <Route
            path="/post/:id"
            element={<PostPage posts={posts} handleDelete={handleDelete} />}
          />
          <Route path="/about" element={<About />} />
          <Route path="*" element={<Missing />} />
        </Routes>
        <Footer />
      </DataProvider>
    </div>
  );
}

export default App;
```

### x-dave-gray/blogapp/src/Nav.js:

```js
import React, { useContext } from "react";
import { Link } from "react-router-dom";
import DataContext from "./context/DataContext";

const Nav = () => {
  const { search, setSearch } = useContext(DataContext);

  return (
    <nav className="Nav">
      <form className="searchForm" onSubmit={(e) => e.preventDefault()}>
        <label htmlFor="search">Search Posts</label>
        <input
          id="search"
          type="text"
          placeholder="Search Posts"
          value={search}
          onChange={(e) => setSearch(e.target.value)}
        />
      </form>
      <ul>
        <li>
          <Link to="/">Home</Link>
        </li>
        <li>
          <Link to="/post">Post</Link>
        </li>
        <li>
          <Link to="/about">About</Link>
        </li>
      </ul>
    </nav>
  );
};

export default Nav;
```

### x-dave-gray/blogapp/src/Home.js:

```js
import React, { useContext } from "react";
import DataContext from "./context/DataContext";
import Feed from "./Feed";

const Home = () => {
  const { searchResults, fetchError, isLoading } = useContext(DataContext);
  return (
    <main className="Home">
      {isLoading && <p className="statusMsg">Loading posts...</p>}
      {!isLoading && fetchError && (
        <p className="statusMsg" style={{ color: "red" }}>
          {fetchError}
        </p>
      )}
      {!isLoading &&
        !fetchError &&
        (searchResults?.length ? (
          <Feed posts={searchResults} />
        ) : (
          <p className="statusMsg">No Posts to display.</p>
        ))}
    </main>
  );
};

export default Home;
```

# #End  </details>

<details>
  <summary>58. Blog App - Refactor NewPost with Context API</summary>

# Blog App - Refactor NewPost with Context API

<img width="969" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/590f94f6-9ab9-4573-89f9-df6fe7b56399">
<img width="969" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/626f728c-b737-4481-92dd-5c2d27c7c7e2">
<img width="1250" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/28c8a081-fdf7-4573-8bc3-c28e95c31f83">

### x-dave-gray/blogapp/src/context/DataContext.js:

```js
import React, { createContext, useState, useEffect } from "react";
import { useNavigate } from "react-router-dom";
import { format } from "date-fns";
import api from "../api/posts";
import useAxiosFetch from "../hooks/useAxiosFetch";
import useWindowSize from "../hooks/useWindowSize";

const DataContext = createContext({});

export const DataProvider = ({ children }) => {
  const { width } = useWindowSize();
  const [posts, setPosts] = useState([]);
  const [search, setSearch] = useState("");
  const [searchResults, setSearchResults] = useState([]);
  const [postTitle, setPostTitle] = useState("");
  const [postBody, setPostBody] = useState("");
  const [editTitle, setEditTitle] = useState("");
  const [editBody, setEditBody] = useState("");
  const navigate = useNavigate();

  const { data, fetchError, isLoading } = useAxiosFetch(
    "http://localhost:3500/posts"
  );

  useEffect(() => {
    setPosts(data);
  }, [data]);

  useEffect(() => {
    const filteredResults = posts.filter(
      (post) =>
        post.body.toLowerCase().includes(search.toLowerCase()) ||
        post.title.toLowerCase().includes(search.toLowerCase())
    );

    setSearchResults(filteredResults.reverse());
  }, [posts, search]);

  const handleSubmit = async (e) => {
    e.preventDefault();
    const id = posts.length ? posts[posts.length - 1].id + 1 : 1;
    const datetime = format(new Date(), "MMMM dd, yyyy pp");
    //const datetime = format(new Date(), "yyyy-MM-dd HH:mm:ss");
    const newPost = { id, title: postTitle, datetime, body: postBody };
    try {
      const response = await api.post("/posts", newPost);
      const allPosts = [...posts, response.data];
      setPosts(allPosts);
      setPostTitle("");
      setPostBody("");
      navigate("/");
    } catch (err) {
      console.log(`Error: ${err.message}`);
    }
  };

  const handleEdit = async (id) => {
    const datetime = format(new Date(), "MMMM dd, yyyy pp");
    const updatedPost = { id, title: editTitle, datetime, body: editBody };
    try {
      const response = await api.put(`/posts/${id}`, updatedPost);
      setPosts(
        posts.map((post) => (post.id === id ? { ...response.data } : post))
      );
      setEditTitle("");
      setEditBody("");
      navigate("/");
    } catch (err) {
      console.log(`Error: ${err.message}`);
    }
  };

  const handleDelete = async (id) => {
    try {
      await api.delete(`/posts/${id}`);
      const postList = posts.filter((post) => post.id !== id);
      setPosts(postList);
      navigate("/");
    } catch (err) {
      console.log(`Error: ${err.message}`);
    }
  };

  return (
    <DataContext.Provider
      value={{
        width,
        search,
        setSearch,
        searchResults,
        fetchError,
        isLoading,
        handleSubmit,
        postTitle,
        setPostTitle,
        postBody,
        setPostBody,
      }}
    >
      {children}
    </DataContext.Provider>
  );
};

export default DataContext;
```

### x-dave-gray/blogapp/src/App.js:

```js
import React from "react";
import { Route, Routes } from "react-router-dom";
import Header from "./Header";
import Nav from "./Nav";
import Footer from "./Footer";
import Home from "./Home";
import NewPost from "./NewPost";
import PostPage from "./PostPage";
import About from "./About";
import Missing from "./Missing";
import EditPost from "./EditPost";

import { DataProvider } from "./context/DataContext";

function App() {
  const {
    posts,
    handleEdit,
    editTitle,
    setEditTitle,
    editBody,
    setEditBody,
    handleDelete,
  } = {};
  return (
    <div className="App">
      <DataProvider>
        <Header title="React JS Blog" />
        <Nav />
        <Routes>
          <Route exact path="/" element={<Home />} />
          <Route exact path="/post" element={<NewPost />} />
          <Route
            path="/edit/:id"
            element={
              <EditPost
                posts={posts}
                handleEdit={handleEdit}
                editTitle={editTitle}
                setEditTitle={setEditTitle}
                editBody={editBody}
                setEditBody={setEditBody}
              />
            }
          />
          <Route
            path="/post/:id"
            element={<PostPage posts={posts} handleDelete={handleDelete} />}
          />
          <Route path="/about" element={<About />} />
          <Route path="*" element={<Missing />} />
        </Routes>
        <Footer />
      </DataProvider>
    </div>
  );
}

export default App;
```

### x-dave-gray/blogapp/src/NewPost.js:

```js
import React, { useContext } from "react";
import DataContext from "./context/DataContext";

const NewPost = () => {
  const { handleSubmit, postTitle, setPostTitle, postBody, setPostBody } =
    useContext(DataContext);

  return (
    <main className="NewPost">
      <h2>NewPost</h2>
      <form className="newPostForm" onSubmit={handleSubmit}>
        <label htmlFor="postTitle">Title:</label>
        <input
          type="text"
          id="postTitle"
          value={postTitle}
          onChange={(e) => setPostTitle(e.target.value)}
          required
        />
        <label htmlFor="postBody">Post:</label>
        <textarea
          id="postBody"
          value={postBody}
          onChange={(e) => setPostBody(e.target.value)}
          // cols="10"
          // rows="30"
          required
        />
        <button type="submit">Submit</button>
      </form>
    </main>
  );
};

export default NewPost;
```

# #End  </details>

<details>
  <summary>59. Blog App - Refactor PostPage and EditPost with Context API</summary>

# Refactor PostPage and EditPost with Context API

<img width="965" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/722a1c50-bcdd-44d8-94ac-b51b859296be">
<img width="965" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/ccece9ac-ce22-480f-bc5a-88e4306924da">
<img width="965" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/5a0c1c0e-8088-4055-ae84-5863543e4d23">
<img width="1248" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/498fdbd3-cfb0-44f1-aff8-4ddc08432f0c">
<img width="1248" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/ba221715-f4f7-4cea-99e0-679ca528ce9d">
<img width="1248" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/9f1834ff-eb1d-4f42-b61d-74df2c08dd08">
<img width="1248" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/276b6d71-1994-4007-ada0-cc8a7e2c2b33">

### x-dave-gray/blogapp/src/context/DataContext.js:

```js
import React, { createContext, useState, useEffect } from "react";
import { useNavigate } from "react-router-dom";
import { format } from "date-fns";
import api from "../api/posts";
import useAxiosFetch from "../hooks/useAxiosFetch";
import useWindowSize from "../hooks/useWindowSize";

const DataContext = createContext({});

export const DataProvider = ({ children }) => {
  const { width } = useWindowSize();
  const [posts, setPosts] = useState([]);
  const [search, setSearch] = useState("");
  const [searchResults, setSearchResults] = useState([]);
  const [postTitle, setPostTitle] = useState("");
  const [postBody, setPostBody] = useState("");
  const [editTitle, setEditTitle] = useState("");
  const [editBody, setEditBody] = useState("");
  const navigate = useNavigate();

  const { data, fetchError, isLoading } = useAxiosFetch(
    "http://localhost:3500/posts"
  );

  useEffect(() => {
    setPosts(data);
  }, [data]);

  useEffect(() => {
    const filteredResults = posts.filter(
      (post) =>
        post.body.toLowerCase().includes(search.toLowerCase()) ||
        post.title.toLowerCase().includes(search.toLowerCase())
    );

    setSearchResults(filteredResults.reverse());
  }, [posts, search]);

  const handleSubmit = async (e) => {
    e.preventDefault();
    const id = posts.length ? posts[posts.length - 1].id + 1 : 1;
    const datetime = format(new Date(), "MMMM dd, yyyy pp");
    //const datetime = format(new Date(), "yyyy-MM-dd HH:mm:ss");
    const newPost = { id, title: postTitle, datetime, body: postBody };
    try {
      const response = await api.post("/posts", newPost);
      const allPosts = [...posts, response.data];
      setPosts(allPosts);
      setPostTitle("");
      setPostBody("");
      navigate("/");
    } catch (err) {
      console.log(`Error: ${err.message}`);
    }
  };

  const handleEdit = async (id) => {
    const datetime = format(new Date(), "MMMM dd, yyyy pp");
    const updatedPost = { id, title: editTitle, datetime, body: editBody };
    try {
      const response = await api.put(`/posts/${id}`, updatedPost);
      setPosts(
        posts.map((post) => (post.id === id ? { ...response.data } : post))
      );
      setEditTitle("");
      setEditBody("");
      navigate("/");
    } catch (err) {
      console.log(`Error: ${err.message}`);
    }
  };

  const handleDelete = async (id) => {
    try {
      await api.delete(`/posts/${id}`);
      const postList = posts.filter((post) => post.id !== id);
      setPosts(postList);
      navigate("/");
    } catch (err) {
      console.log(`Error: ${err.message}`);
    }
  };

  return (
    <DataContext.Provider
      value={{
        width,
        search,
        setSearch,
        searchResults,
        fetchError,
        isLoading,
        handleSubmit,
        postTitle,
        setPostTitle,
        postBody,
        setPostBody,
        posts,
        handleEdit,
        editBody,
        setEditBody,
        editTitle,
        setEditTitle,
        handleDelete,
      }}
    >
      {children}
    </DataContext.Provider>
  );
};

export default DataContext;
```

### x-dave-gray/blogapp/src/App.js:

```js
import React from "react";
import { Route, Routes } from "react-router-dom";
import Header from "./Header";
import Nav from "./Nav";
import Footer from "./Footer";
import Home from "./Home";
import NewPost from "./NewPost";
import PostPage from "./PostPage";
import About from "./About";
import Missing from "./Missing";
import EditPost from "./EditPost";

import { DataProvider } from "./context/DataContext";

function App() {
  return (
    <div className="App">
      <DataProvider>
        <Header title="React JS Blog" />
        <Nav />
        <Routes>
          <Route exact path="/" element={<Home />} />
          <Route exact path="/post" element={<NewPost />} />
          <Route path="/edit/:id" element={<EditPost />} />
          <Route path="/post/:id" element={<PostPage />} />
          <Route path="/about" element={<About />} />
          <Route path="*" element={<Missing />} />
        </Routes>
        <Footer />
      </DataProvider>
    </div>
  );
}

export default App;
```

### x-dave-gray/blogapp/src/PostPage.js:

```js
import React, { useContext } from "react";
import DataContext from "./context/DataContext";
import { useParams, Link } from "react-router-dom";

const PostPage = () => {
  const { posts, handleDelete } = useContext(DataContext);
  const { id } = useParams();
  const post = posts.find((post) => post.id.toString() === id);

  return (
    <main className="PostPage">
      <article className="post">
        {post ? (
          <>
            <h2>{post.title}</h2>
            <p className="postDate">{post.datetime}</p>
            <p className="postBody">{post.body}</p>
            <Link to={`/edit/${post.id}`}>
              <button className="editButton">Edit Post</button>
            </Link>
            <button
              className="deleteButton"
              onClick={() => handleDelete(post.id)}
            >
              Delete Post
            </button>
          </>
        ) : (
          <>
            <h2>Post Not Found</h2>
            <p>Well, that's disappointing.</p>
            <p>
              <Link to="/">Visit our Home Page</Link>
            </p>
          </>
        )}
      </article>
    </main>
  );
};

export default PostPage;
```

### x-dave-gray/blogapp/src/EditPost.js:

```js
import React, { useEffect, useContext } from "react";
import DataContext from "./context/DataContext";
import { useParams, Link } from "react-router-dom";

const EditPost = () => {
  const { posts, handleEdit, editBody, setEditBody, editTitle, setEditTitle } =
    useContext(DataContext);
  const { id } = useParams();
  const post = posts.find((post) => post.id.toString() === id);

  useEffect(() => {
    if (post) {
      setEditTitle(post.title);
      setEditBody(post.body);
    }
  }, [post, setEditTitle, setEditBody]);

  return (
    <main className="NewPost">
      {post ? (
        <>
          <h2>EditPost</h2>
          <form className="newPostForm" onSubmit={(e) => e.preventDefault()}>
            <label htmlFor="postTitle">Title:</label>
            <input
              type="text"
              id="postTitle"
              value={editTitle}
              onChange={(e) => setEditTitle(e.target.value)}
              required
            />
            <label htmlFor="postBody">Post:</label>
            <textarea
              id="postBody"
              value={editBody}
              onChange={(e) => setEditBody(e.target.value)}
              // cols="10"
              // rows="30"
              required
            />
            <button type="submit" onClick={() => handleEdit(post.id)}>
              Submit
            </button>
          </form>
        </>
      ) : (
        <>
          <h2>Post Not Found</h2>
          <p>Well, that's disappointing.</p>
          <p>
            <Link to="/">Visit our Homepage</Link>
          </p>
        </>
      )}
    </main>
  );
};

export default EditPost;
```

# #End  </details>

<details>
  <summary>60. Blog App - Isolating Header and Footer Component State from Shared Context API</summary>

# Isolating Header and Footer Component State from Shared Context API

<img width="970" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/bd5e60d4-a09c-4ec9-8025-5a26983c2408">
<img width="970" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/e3cb586f-c66d-4ac3-a205-69b58355a628">
<img width="970" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/375e30db-9404-42a7-8602-fcb6d0e9592c">
<img width="1249" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/04252edc-fa61-4b55-b1cc-38f0d485a46c">

### x-dave-gray/blogapp/src/App.js:

```js
import React from "react";
import { Route, Routes } from "react-router-dom";
import Header from "./Header";
import Nav from "./Nav";
import Footer from "./Footer";
import Home from "./Home";
import NewPost from "./NewPost";
import PostPage from "./PostPage";
import About from "./About";
import Missing from "./Missing";
import EditPost from "./EditPost";

import { DataProvider } from "./context/DataContext";

function App() {
  return (
    <div className="App">
      <Header title="React JS Blog" />
      <DataProvider>
        <Nav />
        <Routes>
          <Route exact path="/" element={<Home />} />
          <Route exact path="/post" element={<NewPost />} />
          <Route path="/edit/:id" element={<EditPost />} />
          <Route path="/post/:id" element={<PostPage />} />
          <Route path="/about" element={<About />} />
          <Route path="*" element={<Missing />} />
        </Routes>
      </DataProvider>
      <Footer />
    </div>
  );
}

export default App;
```

### x-dave-gray/blogapp/src/context/DataContext.js:

```js
import React, { createContext, useState, useEffect } from "react";
import { useNavigate } from "react-router-dom";
import { format } from "date-fns";
import api from "../api/posts";
import useAxiosFetch from "../hooks/useAxiosFetch";

const DataContext = createContext({});

export const DataProvider = ({ children }) => {
  const [posts, setPosts] = useState([]);
  const [search, setSearch] = useState("");
  const [searchResults, setSearchResults] = useState([]);
  const [postTitle, setPostTitle] = useState("");
  const [postBody, setPostBody] = useState("");
  const [editTitle, setEditTitle] = useState("");
  const [editBody, setEditBody] = useState("");
  const navigate = useNavigate();

  const { data, fetchError, isLoading } = useAxiosFetch(
    "http://localhost:3500/posts"
  );

  useEffect(() => {
    setPosts(data);
  }, [data]);

  useEffect(() => {
    const filteredResults = posts.filter(
      (post) =>
        post.body.toLowerCase().includes(search.toLowerCase()) ||
        post.title.toLowerCase().includes(search.toLowerCase())
    );

    setSearchResults(filteredResults.reverse());
  }, [posts, search]);

  const handleSubmit = async (e) => {
    e.preventDefault();
    const id = posts.length ? posts[posts.length - 1].id + 1 : 1;
    const datetime = format(new Date(), "MMMM dd, yyyy pp");
    //const datetime = format(new Date(), "yyyy-MM-dd HH:mm:ss");
    const newPost = { id, title: postTitle, datetime, body: postBody };
    try {
      const response = await api.post("/posts", newPost);
      const allPosts = [...posts, response.data];
      setPosts(allPosts);
      setPostTitle("");
      setPostBody("");
      navigate("/");
    } catch (err) {
      console.log(`Error: ${err.message}`);
    }
  };

  const handleEdit = async (id) => {
    const datetime = format(new Date(), "MMMM dd, yyyy pp");
    const updatedPost = { id, title: editTitle, datetime, body: editBody };
    try {
      const response = await api.put(`/posts/${id}`, updatedPost);
      setPosts(
        posts.map((post) => (post.id === id ? { ...response.data } : post))
      );
      setEditTitle("");
      setEditBody("");
      navigate("/");
    } catch (err) {
      console.log(`Error: ${err.message}`);
    }
  };

  const handleDelete = async (id) => {
    try {
      await api.delete(`/posts/${id}`);
      const postList = posts.filter((post) => post.id !== id);
      setPosts(postList);
      navigate("/");
    } catch (err) {
      console.log(`Error: ${err.message}`);
    }
  };

  return (
    <DataContext.Provider
      value={{
        search,
        setSearch,
        searchResults,
        fetchError,
        isLoading,
        handleSubmit,
        postTitle,
        setPostTitle,
        postBody,
        setPostBody,
        posts,
        handleEdit,
        editBody,
        setEditBody,
        editTitle,
        setEditTitle,
        handleDelete,
      }}
    >
      {children}
    </DataContext.Provider>
  );
};

export default DataContext;
```

### x-dave-gray/blogapp/src/Header.js:

```js
import React from "react";
import { FaLaptop, FaTabletAlt, FaMobileAlt } from "react-icons/fa";
import useWindowSize from "./hooks/useWindowSize";
// import DataContext from "./context/DataContext";

const Header = ({ title }) => {
  // const { width } = useContext(DataContext);
  const { width } = useWindowSize();

  return (
    <header className="Header">
      <h1>{title}</h1>
      {width < 768 ? (
        <FaMobileAlt />
      ) : width < 992 ? (
        <FaTabletAlt />
      ) : (
        <FaLaptop />
      )}
    </header>
  );
};

export default Header;
```

### x-dave-gray/blogapp/src/Footer.js:

```js
import React from "react";

const Footer = () => {
  const today = new Date();

  return (
    <footer className="Footer">
      <p>Copyright &copy; {today.getFullYear()}</p>
    </footer>
  );
};

export default Footer;
```

# #End  </details>

+BLOG APP WITH EASY PEASY REDUX

<details>
  <summary>61. Blog App - Using Easy Peasy v5 for State Management</summary>

# Using Easy Peasy v5 for State Management

<img width="968" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/74393f20-f162-463d-b863-13228f0612ce">
<img width="968" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/62c8b5d9-ceef-43de-9716-4f2327409d51">
<img width="968" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/3313233f-d1ca-4567-8171-cc9ad54e1b4f">
<img width="968" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/58893951-edfd-417f-98a9-136522fad77c">

# Install Easy Peasy

```bs
npm install easy-peasy
```

# Create your store

### x-dave-gray/blogapp/src/store.js:

```js
import { createStore, action } from "easy-peasy";

export const store = createStore({
  todos: ["Create store", "Wrap application", "Use store"],

  addTodo: action((state, payload) => {
    state.todos.push(payload);
  }),
});
```

# Wrap your application

### x-dave-gray/blogapp/src/App.js:

```js
import { StoreProvider } from "easy-peasy";
import { store } from "./store";
import TodoList from "./TodoList";

function App() {
  return (
    <StoreProvider store={store}>
      <TodoList />
    </StoreProvider>
  );
}

export default App;
```

# Use the store state in your components

### x-dave-gray/blogapp/src/TodoList.js:

```js
import { useStoreState, useStoreActions } from "easy-peasy";
import AddTodo from "./AddTodo";

function TodoList() {
  const todos = useStoreState((state) => state.todos);
  const addTodo = useStoreActions((actions) => actions.addTodo);

  return (
    <div>
      {todos.map((todo, idx) => (
        <div key={idx}>
          <h2>{todo}</h2>
        </div>
      ))}
      <AddTodo onAdd={addTodo} />
    </div>
  );
}

export default TodoList;
```

### x-dave-gray/blogapp/src/AddTodo.js:

```js
import React, { useState } from "react";

const AddTodo = ({ onAdd }) => {
  const [todo, setTodo] = useState("");

  return (
    <div>
      <input
        onChange={(e) => {
          setTodo(e.target.value);
        }}
        type="text"
      />
      <button onClick={() => onAdd(todo)}>Add Item</button>

      <div>{todo}</div>
    </div>
  );
};

export default AddTodo;
```

# #End  </details>

<details>
  <summary>62. Blog App - Create Easy Peasy store </summary>

# Create Easy Peasy store

<img width="968" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/ef7a4b22-04a2-4c95-a449-907a065f73cc">

# Remove unused packages

```bs
npm uninstall @testing-library/jest-dom @testing-library/react @testing-library/user-event web-vitals
```

# Install Easy Peasy v5 Redux

```bs
npm install easy-peasy
```

# Start npx server:

```bs
npx json-server -p 3500 -w data/db.json
```

### x-dave-gray/blogapp/src/store.js:

```js
import { createStore, action, thunk, computed } from "easy-peasy";
import api from "./api/posts";

export default createStore({
  posts: [],
  setPosts: action((state, payload) => {
    state.posts = payload;
  }),
  postTitle: "",
  setPostTitle: action((state, payload) => {
    state.postTitle = payload;
  }),
  postBody: "",
  setPostBody: action((state, payload) => {
    state.postBody = payload;
  }),
  editTitle: "",
  setEditTitle: action((state, payload) => {
    state.editTitle = payload;
  }),
  editBody: "",
  setEditBody: action((state, payload) => {
    state.editBody = payload;
  }),
  search: "",
  setSearch: action((state, payload) => {
    state.search = payload;
  }),
  searchResults: [],
  setSearchResults: action((state, payload) => {
    state.searchResults = payload;
  }),
  postCount: computed((state) => state.posts.length),
  getPostById: computed((state) => {
    return (id) => state.posts.find((post) => post.id.toString() === id);
  }),
  savePost: thunk(async (actions, newPost, helpers) => {
    const { posts } = helpers.getState();
    try {
      const response = await api.post("/posts", newPost);
      actions.setPosts([...posts, response.data]);
      actions.setPostTitle("");
      actions.setPostBody("");
    } catch (err) {
      console.log(`Error: ${err.message}`);
    }
  }),
  deletePost: thunk(async (actions, id, helpers) => {
    const { posts } = helpers.getState();
    try {
      await api.delete(`/posts/${id}`);
      actions.setPosts(posts.filter((post) => post.id !== id));
    } catch (err) {
      console.log(`Error: ${err.message}`);
    }
  }),
  editPost: thunk(async (actions, updatedPost, helpers) => {
    const { posts } = helpers.getState();
    const { id } = updatedPost;
    try {
      const response = await api.put(`/posts/${id}`, updatedPost);
      actions.setPosts(
        posts.map((post) => (post.id === id ? { ...response.data } : post))
      );
      actions.setEditTitle("");
      actions.setEditBody("");
    } catch (err) {
      console.log(`Error: ${err.message}`);
    }
  }),
});
```

# #End  </details>

<details>
  <summary>63.  Blog App - Refactoring Index.js and App.js </summary>

# Refactoring Index.js and App.js

<img width="968" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/14ec7db0-6a12-4a6d-b46e-97daf70d8753">
<img width="968" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/53552fe8-d4d9-41af-a35c-1bf378b2e697">

### x-dave-gray/blogapp/src/index.js:

```js
import React from "react";
import ReactDOM from "react-dom/client";
import "./index.css";
import App from "./App";
import { BrowserRouter as Router, Routes, Route } from "react-router-dom";
import { StoreProvider } from "easy-peasy";
import store from "./store";

const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(
  <React.StrictMode>
    <StoreProvider store={store}>
      <Router>
        <Routes>
          <Route path="/*" element={<App />} />
        </Routes>
      </Router>
    </StoreProvider>
  </React.StrictMode>
);
```

### x-dave-gray/blogapp/src/App.js:

```js
import Header from "./Header";
import Nav from "./Nav";
import Footer from "./Footer";
import Home from "./Home";
import NewPost from "./NewPost";
import PostPage from "./PostPage";
import EditPost from "./EditPost";
import About from "./About";
import Missing from "./Missing";
import { Route, Routes } from "react-router-dom";
import { useEffect } from "react";
import useAxiosFetch from "./hooks/useAxiosFetch";
import { useStoreActions } from "easy-peasy";

function App() {
  const setPosts = useStoreActions((actions) => actions.setPosts);

  const { data, fetchError, isLoading } = useAxiosFetch(
    "http://localhost:3500/posts"
  );

  useEffect(() => {
    setPosts(data);
  }, [data, setPosts]);

  return (
    <div className="App">
      <Header title="React JS Blog" />
      <Nav />
      <Routes>
        <Route
          exact
          path="/"
          element={<Home isLoading={isLoading} fetchError={fetchError} />}
        />
        <Route exact path="/post" element={<NewPost />} />
        <Route path="/edit/:id" element={<EditPost />} />
        <Route path="/post/:id" element={<PostPage />} />
        <Route path="/about" element={<About />} />
        <Route path="*" element={<Missing />} />
      </Routes>
      <Footer />
    </div>
  );
}

export default App;
```

# #End  </details>

<details>
  <summary>64. Blog App - Refactoring Nav.js</summary>

# Refactoring Nav.js

<img width="968" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/acaf99a4-38ba-4de9-83a0-a1c5499fa8d4">

### x-dave-gray/blogapp/src/Nav.js:

```js
import { Link } from "react-router-dom";
import { useEffect } from "react";
import { useStoreState, useStoreActions } from "easy-peasy";

const Nav = () => {
  const posts = useStoreState((state) => state.posts);
  const search = useStoreState((state) => state.search);
  const setSearch = useStoreActions((actions) => actions.setSearch);
  const setSearchResults = useStoreActions(
    (actions) => actions.setSearchResults
  );

  useEffect(() => {
    const filteredResults = posts.filter(
      (post) =>
        post.body.toLowerCase().includes(search.toLowerCase()) ||
        post.title.toLowerCase().includes(search.toLowerCase())
    );

    setSearchResults(filteredResults.reverse());
  }, [posts, search, setSearchResults]);

  return (
    <nav className="Nav">
      <form className="searchForm" onSubmit={(e) => e.preventDefault()}>
        <label htmlFor="search">Search Posts</label>
        <input
          id="search"
          type="text"
          placeholder="Search Posts"
          value={search}
          onChange={(e) => setSearch(e.target.value)}
        />
      </form>
      <ul>
        <li>
          <Link to="/">Home</Link>
        </li>
        <li>
          <Link to="/post">Post</Link>
        </li>
        <li>
          <Link to="/about">About</Link>
        </li>
      </ul>
    </nav>
  );
};

export default Nav;
```

# #End  </details>

<details>
  <summary>65. Blog App - Refactoring Home.js</summary>

# Refactoring Home.js

<img width="967" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/9a2e02b6-cca1-4b3e-82f1-a134de518399">
<img width="1251" alt="image" src="https://github.com/omeatai/My-Tutorials/assets/32337103/bdcf0183-77db-4d21-a7f8-36711fd3bb43">

### x-dave-gray/blogapp/src/Home.js:

```js
import Feed from "./Feed";
import { useStoreState } from "easy-peasy";

const Home = ({ isLoading, fetchError }) => {
  const searchResults = useStoreState((state) => state.searchResults);

  return (
    <main className="Home">
      {isLoading && <p className="statusMsg">Loading posts...</p>}
      {!isLoading && fetchError && (
        <p className="statusMsg" style={{ color: "red" }}>
          {fetchError}
        </p>
      )}
      {!isLoading &&
        !fetchError &&
        (searchResults.length ? (
          <Feed posts={searchResults} />
        ) : (
          <p className="statusMsg">No posts to display.</p>
        ))}
    </main>
  );
};

export default Home;
```

# #End  </details>

<details>
  <summary>66. Blog App - Refactoring PostPage.js</summary>

# Refactoring PostPage.js

### x-dave-gray/blogapp/src/PostPage.js:

```js
import { useParams, Link, useNavigate } from "react-router-dom";
import { useStoreState, useStoreActions } from "easy-peasy";

const PostPage = () => {
  const { id } = useParams();
  const navigate = useNavigate();
  const deletePost = useStoreActions((actions) => actions.deletePost);
  const getPostById = useStoreState((state) => state.getPostById);
  const post = getPostById(id);

  const handleDelete = (id) => {
    deletePost(id);
    navigate("/");
  };

  return (
    <main className="PostPage">
      <article className="post">
        {post && (
          <>
            <h2>{post.title}</h2>
            <p className="postDate">{post.datetime}</p>
            <p className="postBody">{post.body}</p>
            <Link to={`/edit/${post.id}`}>
              <button className="editButton">Edit Post</button>
            </Link>
            <button
              className="deleteButton"
              onClick={() => handleDelete(post.id)}
            >
              Delete Post
            </button>
          </>
        )}
        {!post && (
          <>
            <h2>Post Not Found</h2>
            <p>Well, that's disappointing.</p>
            <p>
              <Link to="/">Visit Our Homepage</Link>
            </p>
          </>
        )}
      </article>
    </main>
  );
};

export default PostPage;
```

# #End  </details>

<details>
  <summary>67. Blog App - Refactoring NewPost.js</summary>

# Refactoring NewPost.js

NewPost.js:

```js
import { useNavigate } from "react-router-dom";
import { format } from "date-fns";
import { useStoreState, useStoreActions } from "easy-peasy";

const NewPost = () => {
  const navigate = useNavigate();

  const posts = useStoreState((state) => state.posts);
  const postTitle = useStoreState((state) => state.postTitle);
  const postBody = useStoreState((state) => state.postBody);

  const savePost = useStoreActions((actions) => actions.savePost);
  const setPostTitle = useStoreActions((actions) => actions.setPostTitle);
  const setPostBody = useStoreActions((actions) => actions.setPostBody);

  const handleSubmit = (e) => {
    e.preventDefault();
    const id = posts.length ? posts[posts.length - 1].id + 1 : 1;
    const datetime = format(new Date(), "MMMM dd, yyyy pp");
    const newPost = { id, title: postTitle, datetime, body: postBody };
    savePost(newPost);
    navigate("/");
  };

  return (
    <main className="NewPost">
      <h2>New Post</h2>
      <form className="newPostForm" onSubmit={handleSubmit}>
        <label htmlFor="postTitle">Title:</label>
        <input
          id="postTitle"
          type="text"
          required
          value={postTitle}
          onChange={(e) => setPostTitle(e.target.value)}
        />
        <label htmlFor="postBody">Post:</label>
        <textarea
          id="postBody"
          required
          value={postBody}
          onChange={(e) => setPostBody(e.target.value)}
        />
        <button type="submit">Submit</button>
      </form>
    </main>
  );
};

export default NewPost;
```

# #End  </details>

<details>
  <summary>178. Blog App - Refactoring EditPost.js</summary>

EditPost.js:

```js
import { useEffect } from "react";
import { useParams, Link, useNavigate } from "react-router-dom";
import { format } from "date-fns";
import { useStoreState, useStoreActions } from "easy-peasy";

const EditPost = () => {
  const navigate = useNavigate();
  const { id } = useParams();

  const editTitle = useStoreState((state) => state.editTitle);
  const editBody = useStoreState((state) => state.editBody);

  const editPost = useStoreActions((actions) => actions.editPost);
  const setEditTitle = useStoreActions((actions) => actions.setEditTitle);
  const setEditBody = useStoreActions((actions) => actions.setEditBody);

  const getPostById = useStoreState((state) => state.getPostById);
  const post = getPostById(id);

  useEffect(() => {
    if (post) {
      setEditTitle(post.title);
      setEditBody(post.body);
    }
  }, [post, setEditTitle, setEditBody]);

  const handleEdit = (id) => {
    const datetime = format(new Date(), "MMMM dd, yyyy pp");
    const updatedPost = { id, title: editTitle, datetime, body: editBody };
    editPost(updatedPost);
    navigate(`/post/${id}`);
  };

  return (
    <main className="NewPost">
      {editTitle && (
        <>
          <h2>Edit Post</h2>
          <form className="newPostForm" onSubmit={(e) => e.preventDefault()}>
            <label htmlFor="postTitle">Title:</label>
            <input
              id="postTitle"
              type="text"
              required
              value={editTitle}
              onChange={(e) => setEditTitle(e.target.value)}
            />
            <label htmlFor="postBody">Post:</label>
            <textarea
              id="postBody"
              required
              value={editBody}
              onChange={(e) => setEditBody(e.target.value)}
            />
            <button type="button" onClick={() => handleEdit(post.id)}>
              Submit
            </button>
          </form>
        </>
      )}
      {!editTitle && (
        <>
          <h2>Post Not Found</h2>
          <p>Well, that's disappointing.</p>
          <p>
            <Link to="/">Visit Our Homepage</Link>
          </p>
        </>
      )}
    </main>
  );
};

export default EditPost;
```

# #End  </details>

<details>
  <summary>179. Blog App - Refactoring Footer.js</summary>

Footer.js:

```js
import { useStoreState } from "easy-peasy";

const Footer = () => {
  const postCount = useStoreState((state) => state.postCount);
  return (
    <footer className="Footer">
      <p>{postCount} Blog Posts</p>
    </footer>
  );
};

export default Footer;
```

# #End  </details>

+DEPLOY

<details>
  <summary>180. Deploy React App to Netlify and Github Pages</summary>

Uninstall unused modules:

```bs
npm uninstall @testing-library/jest-dom @testing-library/react @testing-library/user-event web-vitals
```

Install JSON Server to Production:

```bs
npm i json-server -S
```

```bs
json-server -p 3500 -w data/db.json
```

Setup up GIT & GitHub:

```bs
echo "# deploy_react_blog_netlify" >> README.md
git init
git add README.md OR git add .
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/omeatai/deploy_react_blog_netlify.git
OR
git remote set-url origin https://github.com/omeatai/deploy_react_blog_netlify.git
git push -u origin main
```

For Github-Pages:

```bs
npm i gh-pages -D
```

```bs
"homepage": "https://omeatai.github.io/deploy_react_blog_gh",

"predeploy": "npm run build",
"deploy": "gh-pages -d build",

"devDependencies": {
  "gh-pages": "^4.0.0"
}
```

```json
{
  "name": "blog",
  "version": "0.1.0",
  "homepage": "https://omeatai.github.io/deploy_react_blog_gh",
  "private": true,
  "dependencies": {
    "axios": "^1.2.1",
    "date-fns": "^2.29.3",
    "easy-peasy": "^5.2.0",
    "json-server": "^0.17.1",
    "react": "^18.2.0",
    "react-dom": "^18.2.0",
    "react-icons": "^4.7.1",
    "react-router-dom": "^6.5.0",
    "react-scripts": "5.0.1"
  },
  "scripts": {
    "predeploy": "npm run build",
    "deploy": "gh-pages -d build",
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test",
    "eject": "react-scripts eject"
  },
  "eslintConfig": {
    "extends": ["react-app", "react-app/jest"]
  },
  "browserslist": {
    "production": [">0.2%", "not dead", "not op_mini all"],
    "development": [
      "last 1 chrome version",
      "last 1 firefox version",
      "last 1 safari version"
    ]
  },
  "devDependencies": {
    "gh-pages": "^4.0.0"
  }
}
```

```bs
echo "# deploy_react_blog_gh" >> README.md
git init
git add README.md OR git add .
git commit -m "first commit"
git branch -M main
git remote set-url origin https://github.com/omeatai/deploy_react_blog_gh.git
OR
git remote add origin https://github.com/omeatai/deploy_react_blog_gh.git
git push -u origin main
```

Deploy App on GitHub Pages:

```bs
npm run deploy
```

```bs
Go to https://omeatai.github.io/deploy_react_blog_gh to view site.
```

# #End  </details>

+REACT-HOOKS

<details>
  <summary>181. Using PrevState to update React State Hooks </summary>

Counter.js:

```js
import React, { useState } from "react";

const Counter = () => {
  const [count, setCount] = useState(0);
  const [values, setValues] = useState([]);
  const [names, setNames] = useState({
    firstName: "John",
    lastName: "Mcgrill",
  });

  const add = () => setCount((prevState) => prevState + 1);
  const subtract = () => setCount((prevState) => prevState - 1);
  const updateValue = (newVal) =>
    setValues((prevState) => [...prevState, newVal]);
  const updateName = (first, last) =>
    setNames((prevState) => ({
      ...prevState,
      firstName: first,
      lastName: last,
    }));

  return (
    <div className="Counter">
      <h1>Counter</h1>
      <h1>{count}</h1>
      <div className="row">
        <button onClick={add}>+</button>
        <button onClick={subtract}>-</button>
      </div>
      <div className="row">
        <button onClick={() => setCount(0)}>Reset</button>
      </div>
      <div>
        <h2>{values}</h2>
        <button onClick={() => updateValue(count)}>Update Value</button>
      </div>
      <div>
        <h2>
          {names.firstName} {names.lastName}
        </h2>
        <button onClick={() => updateName("Bob", "Ashley")}>Update Name</button>
      </div>
    </div>
  );
};

export default Counter;
```

# #End  </details>

<details>
  <summary>182. useCallback Hook</summary>
useCallback provides a memoized function.<br>
useCallback is usually used when a function is used within a dependency array.<br>
The 'sum' function makes the dependencies of useEffect Hook change on every render.
Move it inside the useEffect callback.
Alternatively, wrap the definition of 'sum' in its own useCallback() Hook.<br>

Example 1:

```js
import { useState, useEffect, useCallback } from "react";

const Input = () => {
  const [userInput, setUserInput] = useState("");
  const [result, setResult] = useState(0);
  const [num1] = useState(4);
  const [num2] = useState(5);

  const sum = useCallback(() => num1 + num2, [num1, num2]);

  useEffect(() => {
    console.log(`New sum. Value: ${sum()}`);
    setResult(sum());
  }, [sum]);

  return (
    <main className="Input">
      <input
        type="text"
        placeholder="input"
        value={userInput}
        onChange={(e) => setUserInput(e.target.value)}
      />
      <h1>Output: {userInput || "--"}</h1>
      <h2>{result}</h2>
    </main>
  );
};

export default Input;
```

Example 2:

```js
import { useState, useEffect, useCallback } from "react";

const Input = () => {
  const [userInput, setUserInput] = useState("");
  const [result, setResult] = useState(0);
  const [num1] = useState(4);
  const [num2] = useState(5);

  const buildArray = useCallback(() => [num1, num2], [num1, num2]);

  useEffect(() => {
    console.log(`New sum. Value: ${buildArray()}`);
    setResult(buildArray());
  }, [buildArray]);

  return (
    <main className="Input">
      <input
        type="text"
        placeholder="input"
        value={userInput}
        onChange={(e) => setUserInput(e.target.value)}
      />
      <h1>Output: {userInput || "--"}</h1>
      <h2>{result}</h2>
    </main>
  );
};

export default Input;
```

UseCallback.js:

```js
import { useState, useEffect, useCallback } from "react";

const App = () => {
  const [userInput, setUserInput] = useState("");
  const [result, setResult] = useState(0);
  const [num1] = useState(4);
  const [num2] = useState(5);

  //const sum = useCallback(() => num1 + num2, [num1, num2]);
  const buildArray = useCallback(() => [num1, num2], [num1, num2]);

  useEffect(() => {
    console.log(`New array: ${buildArray()}`);
    setResult(buildArray());
  }, [buildArray]);

  return (
    <main className="App">
      <input
        type="text"
        placeholder="input"
        value={userInput}
        onChange={(e) => setUserInput(e.target.value)}
      />
      <h1>Output: {userInput || "--"}</h1>
      <p>Result: {JSON.stringify(result)}</p>
    </main>
  );
};

export default App;
```

Input.css:

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  font-size: 22px;
}

body {
  background-color: #000;
  color: #fff;
  min-height: 100vh;
  font-family: "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Fira Sans",
    "Droid Sans", "Helvetica Neue", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.App {
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
  padding: 1rem;
}

h1 {
  margin-bottom: 1rem;
}

button {
  min-width: 50px;
  padding: 1em;
  margin: 0.25em;
  border-radius: 0.5em;
}

input {
  font-size: 1rem;
  padding: 0.25rem;
  border-radius: 0.5em;
  margin-bottom: 1rem;
  outline: none;
}
```

# #End  </details>

<details>
  <summary>183. useMemo Hook</summary>

useMemo provides a memorized result.

UseMemo.js:

```js
import { useCallback } from "react";
import { useState, useEffect, useMemo } from "react";

const UseMemo = () => {
  const [userNumber, setUserNumber] = useState("");
  const [randomInput, setRandomInput] = useState("");

  const fib = useCallback((n) => {
    return n <= 1 ? n : fib(n - 1) + fib(n - 2);
  }, []);

  const getArray = () => {
    for (let i = 0; i < 1000000000; i++) {
      //do something expensive
    }
    return ["Dave", "Gray"];
  };

  const fibNumber = useMemo(() => fib(userNumber), [fib, userNumber]);

  const myArray = useMemo(() => getArray(), []);

  useEffect(() => {
    console.log("new number");
    console.log("my Array");
  }, [fibNumber, fib, myArray]);

  return (
    <main className="App">
      <label>Fibonacci Sequence: </label>
      <input
        type="number"
        value={userNumber}
        placeholder="Position"
        onChange={(e) => setUserNumber(e.target.value)}
      />
      <p>Number: {fibNumber || "--"}</p>
      <br />
      <br />
      <label>Random Input: </label>
      <input
        type="text"
        value={randomInput}
        placeholder="Random Input"
        onChange={(e) => setRandomInput(e.target.value)}
      />
      <p>{randomInput}</p>
    </main>
  );
};

export default UseMemo;
```

```js
import { useState, useEffect, useMemo, useCallback } from "react";

const getArray = () => {
  for (let i = 0; i < 1000000000; i++) {
    //do something expensive
  }
  return ["Dave", "Gray"];
};

const UseMemo = () => {
  const [userNumber, setUserNumber] = useState("");
  const [randomInput, setRandomInput] = useState("");

  const fib = useCallback((n) => {
    return n <= 1 ? n : fib(n - 1) + fib(n - 2);
  }, []);

  const fibNumber = useMemo(() => fib(userNumber), [userNumber, fib]);

  const myArray = useMemo(() => getArray(), []);

  useEffect(() => {
    console.log("New array");
  }, [myArray]);

  return (
    <main className="App">
      <label>Fibonacci Sequence:</label>
      <input
        type="number"
        value={userNumber}
        placeholder="Position"
        onChange={(e) => setUserNumber(e.target.value)}
      />
      <p>Number: {fibNumber || "--"}</p>
      <br />
      <br />
      <label>Random Input:</label>
      <input
        type="text"
        value={randomInput}
        placeholder="Random Input"
        onChange={(e) => setRandomInput(e.target.value)}
      />
      <p>{randomInput}</p>
    </main>
  );
};

export default UseMemo;
```

Index.css:

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  font-size: 22px;
}

body {
  background-color: #000;
  color: #fff;
  min-height: 100vh;
  font-family: "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Fira Sans",
    "Droid Sans", "Helvetica Neue", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.App {
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
  padding: 1rem;
}

h1 {
  margin-bottom: 1rem;
}

button {
  min-width: 50px;
  padding: 1em;
  margin: 0.25em;
  border-radius: 0.5em;
}

input {
  font-size: 1rem;
  padding: 0.25rem;
  border-radius: 0.5em;
  margin-bottom: 1rem;
  outline: none;
}
```

# #End  </details>

<details>
  <summary>184. useRef Hook</summary>

UseRef.js:

```js
import { useState, useRef } from "react";

const UseRef = () => {
  const [randomInput, setRandomInput] = useState("");
  const [seconds, setSeconds] = useState(0);

  const renders = useRef(0);
  const inputRef = useRef();
  const timerId = useRef();

  const handleChange = (e) => {
    setRandomInput(e.target.value);
    renders.current++;
  };

  const startTimer = () => {
    timerId.current = setInterval(() => {
      renders.current++;
      setSeconds((prev) => prev + 1);
    }, 1000);
    inputRef.current.focus();
  };

  const stopTimer = () => {
    clearInterval(timerId.current);
    timerId.current = 0;
    inputRef.current.focus();
  };

  const resetTimer = () => {
    stopTimer();
    if (seconds) {
      renders.current++;
      setSeconds(0);
    }
    inputRef.current.focus();
  };

  return (
    <main className="App">
      <input
        ref={inputRef}
        type="text"
        value={randomInput}
        placeholder="Random Input"
        onChange={handleChange}
      />
      <p>Renders: {renders.current}</p>
      <br />
      <br />
      <section>
        <button onClick={startTimer}>Start</button>
        <button onClick={stopTimer}>Stop</button>
        <button onClick={resetTimer}>Reset</button>
      </section>
      <br />
      <br />
      <p>Seconds: {seconds}</p>
      <br />
      <br />
      <p>{randomInput}</p>
    </main>
  );
};

export default UseRef;
```

```js
import { useState, useRef } from "react";

function UseRef() {
  const [randomInput, setRandomInput] = useState("");
  const [seconds, setSeconds] = useState(0);

  const renders = useRef(0);
  const inputRef = useRef();
  const timerId = useRef();

  const handleChange = (e) => {
    setRandomInput(e.target.value);
    renders.current++;
  };

  const startTimer = () => {
    timerId.current = setInterval(() => {
      renders.current++;
      setSeconds((prev) => prev + 1);
    }, 1000);
    inputRef.current.focus();
  };

  const stopTimer = () => {
    clearInterval(timerId.current);
    timerId.current = 0;
    inputRef.current.focus();
  };

  const resetTimer = () => {
    stopTimer();
    if (seconds) {
      renders.current++;
      setSeconds(0);
    }
    inputRef.current.focus();
  };

  return (
    <main className="App">
      <input
        ref={inputRef}
        type="text"
        value={randomInput}
        placeholder="Random Input"
        onChange={handleChange}
      />
      <p>Renders: {renders.current}</p>
      <br />
      <br />
      <section>
        <button onClick={startTimer}>Start</button>
        <button onClick={stopTimer}>Stop</button>
        <button onClick={resetTimer}>Reset</button>
      </section>
      <br />
      <br />
      <p>Seconds: {seconds}</p>
      <br />
      <br />
      <p>{randomInput}</p>
    </main>
  );
}

export default UseRef;
```

Index.css:

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  font-size: 36px;
}

body {
  background-color: #000;
  color: #fff;
  min-height: 100vh;
  font-family: "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Fira Sans",
    "Droid Sans", "Helvetica Neue", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.App {
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
  padding: 1rem;
}

h1 {
  margin-bottom: 1rem;
}

section {
  display: flex;
  justify-content: center;
  align-items: center;
}

button {
  font-size: 1rem;
  width: 150px;
  padding: 1em;
  margin: 0.25em;
  border-radius: 0.5em;
  display: grid;
  place-content: center;
}

input {
  font-size: 1rem;
  padding: 0.25rem;
  border-radius: 0.5em;
  margin-bottom: 1rem;
  outline: none;
}
```

# #End  </details>

<details>
  <summary>185. useReducer Hook</summary>

UseReducer.js:

```js
import { useReducer } from "react";

const ACTION = {
  INCREMENT: "increment",
  DECREMENT: "decrement",
  NEW_USER_INPUT: "newUserInput",
  TG_COLOR: "tgColor",
};

const reducer = (state, action) => {
  switch (action.type) {
    case ACTION.INCREMENT:
      return { ...state, count: state.count + 1 };
    case ACTION.DECREMENT:
      return { ...state, count: state.count - 1 };
    case ACTION.NEW_USER_INPUT:
      return { ...state, userInput: action.payload };
    case ACTION.TG_COLOR:
      return { ...state, color: !state.color };
    default:
      throw new Error();
  }
};

const UseReducer = () => {
  const [state, dispatch] = useReducer(reducer, {
    count: 0,
    userInput: "",
    color: false,
  });

  return (
    <main className="App" style={{ color: state.color ? "#FFF" : "#FFF952" }}>
      <input
        type="text"
        value={state.userInput}
        onChange={(e) =>
          dispatch({ type: ACTION.NEW_USER_INPUT, payload: e.target.value })
        }
      />
      <br />
      <br />
      <p>{state.count}</p>
      <section>
        <button onClick={() => dispatch({ type: ACTION.DECREMENT })}>-</button>
        <button onClick={() => dispatch({ type: ACTION.INCREMENT })}>+</button>
        <button onClick={() => dispatch({ type: ACTION.TG_COLOR })}>
          Color
        </button>
      </section>
      <br />
      <br />
      <p>{state.userInput}</p>
    </main>
  );
};

export default UseReducer;
```

Index.css:

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  font-size: 36px;
}

body {
  background-color: #000;
  color: #fff;
  min-height: 100vh;
  font-family: "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Fira Sans",
    "Droid Sans", "Helvetica Neue", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.App {
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
  padding: 1rem;
}

h1 {
  margin-bottom: 1rem;
}

section {
  display: flex;
  justify-content: center;
  align-items: center;
}

button {
  font-size: 1rem;
  min-width: 100px;
  padding: 0.25rem;
  margin: 0.25em;
  border-radius: 0.5em;
  display: grid;
  place-content: center;
}

input {
  font-size: 1rem;
  padding: 0.25rem;
  border-radius: 0.5em;
  margin-bottom: 1rem;
  outline: none;
}
```

# #End  </details>

<details>
  <summary>186. useLayoutEffect Hook</summary>

useLayoutEffect is Synchorous, which means it will delay running the DOM to the browser until it has concluded its operation; unlike useEffect, which is Asynchronous and will allow changes to the DOM while processing its operation.
useLayoutEffect denies the user from observing changes to state on the browser unlike useEffect which makes the changes noticable on the browser.

UseLayoutEffect.js:

```js
import { useState, useRef, useEffect, useLayoutEffect } from "react";

function UseLayoutEffect() {
  const [number, setNumber] = useState(0);
  const [sectionStyle, setSectionStyle] = useState({});
  const sectionRef = useRef();

  /*
  useEffect is asynchronous.
  You see the number change in the DOM before the padding changes.

  useLayoutEffect is synchronous.
  You see the number change only after the padding has changed.
  */

  // change to useLayoutEffect to see the difference
  useLayoutEffect(() => {
    const random = Math.floor(Math.random() * 500);

    /* loop is just to make the changes in this example slow enough to be observable */
    for (let i = 0; i <= 100000000; i++) {
      if (i === 100000000) setSectionStyle({ paddingTop: `${random}px` });
    }
  }, [number]);

  return (
    <main className="App">
      <section ref={sectionRef} style={sectionStyle}>
        <p>{number}</p>
        <div>
          <button onClick={() => setNumber((prev) => prev - 1)}>-</button>
          <button onClick={() => setNumber((prev) => prev + 1)}>+</button>
        </div>
      </section>
    </main>
  );
}

export default UseLayoutEffect;
```

Index.css:

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  font-size: 48px;
}

body {
  background-color: #000;
  color: #fff;
  min-height: 100vh;
  font-family: "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Fira Sans",
    "Droid Sans", "Helvetica Neue", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

#root {
  min-height: inherit;
}

.App {
  min-height: inherit;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
  padding: 1rem;
}

h1 {
  margin-bottom: 1rem;
}

button {
  min-width: 75px;
  padding: 1em;
  margin: 0.25em;
  border-radius: 0.5em;
  font-size: 0.5rem;
}

input {
  font-size: 1rem;
  padding: 0.25rem;
  border-radius: 0.5em;
  margin-bottom: 1rem;
  outline: none;
}

p {
  text-align: center;
}
```

# #End  </details>

<details>
  <summary>187. useImperativeHandle Hook</summary>

useImperativeHandle enables the Child state to be changed by the Parent. It calls a function from the Parent component that is defined in the Child component.

UseImperativeHandle.js:

```js
import { useRef } from "react";
import Modal from "./Modal";

function UseImperativeHandle() {
  const modalRef = useRef();

  const handleOpenModal = () => {
    modalRef.current.openModal();
  };

  console.log("parent rendered");

  return (
    <main className="App">
      <p>Parent Component</p>
      <Modal ref={modalRef} />
      <button onClick={handleOpenModal}>Open</button>
    </main>
  );
}

export default UseImperativeHandle;
```

Modal.js:

```js
import { forwardRef, useImperativeHandle, useState } from "react";

const Modal = (props, ref) => {
  const [modalState, setModalState] = useState(false);

  useImperativeHandle(ref, () => ({
    openModal: () => setModalState(true),
  }));

  console.log("child rendered");

  if (!modalState) return null;

  return (
    <div className="modal">
      <p>This is my modal!</p>
      <button onClick={() => setModalState(false)}>Close</button>
    </div>
  );
};

export default forwardRef(Modal);
```

Index.css:

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  font-size: 48px;
}

body {
  background-color: #000;
  color: #fff;
  min-height: 100vh;
  font-family: "Roboto", "Oxygen", "Ubuntu", "Cantarell", "Fira Sans",
    "Droid Sans", "Helvetica Neue", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

#root {
  min-height: inherit;
}

.App {
  min-height: inherit;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 1rem;
}

h1 {
  margin-bottom: 1rem;
}

button {
  min-width: 75px;
  padding: 1em;
  margin: 0.25em;
  border-radius: 0.5em;
  font-size: 0.5rem;
}

input {
  font-size: 1rem;
  padding: 0.25rem;
  border-radius: 0.5em;
  margin-bottom: 1rem;
  outline: none;
}

p {
  text-align: center;
}

.modal {
  z-index: 1;
  position: absolute;
  top: 50;
  left: 50;
  display: grid;
  place-content: center;
  min-height: 400px;
  min-width: 400px;
  border-radius: 1.5rem;
  background-color: papayawhip;
  color: #000;
  box-shadow: 0 0 40px #fff;
  margin: 1rem;
  padding: 0.25rem;
}
```

# #End  </details>

<details>
  <summary>188. useTransition vs useDeferredValue</summary>

App.js:

```js
import Example1 from "./Example1";
import Example2 from "./Example2";

const App = () => {
  return <Example1 />;
};

export default App;
```

Example1.js:

```js
import { useState, useTransition, useDeferredValue } from "react";

const Example1 = () => {
  const [count, setCount] = useState(0);
  const [items, setItems] = useState([]);
  const [isPending, startTransition] = useTransition();
  const deferredCount = useDeferredValue(count);

  const handleClick = () => {
    // urgent update
    setCount(count + 1);
    // transition update
    startTransition(() => {
      const myArr = Array(20000)
        .fill(1)
        .map((el, i) => count + 20000 - i);
      setItems(myArr);
    });
  };

  const content = (
    <div className="App">
      <button onClick={handleClick}>{count}</button>
      {isPending ? <p>Loading...</p> : null}
      <p>Deferred: {deferredCount}</p>
      <ul>
        {items.map((item) => (
          <li key={item}>{item}</li>
        ))}
      </ul>
    </div>
  );

  return content;
};
export default Example1;
```

Example2.js:

```js
import { useDeferredValue, useState, useTransition, useEffect } from "react";

const bigArray = [...Array(20000).keys()];

const Example2 = () => {
  const [inputValue, setInputValue] = useState("");
  const [list, setList] = useState(bigArray);
  const [isPending, startTransition] = useTransition();
  const deferredInput = useDeferredValue(inputValue);

  const handleInput = (e) => {
    setInputValue(e.target.value);
  };

  useEffect(() => {
    startTransition(() => {
      console.log(deferredInput);
      const filtered = bigArray.filter((item) =>
        item.toString().includes(deferredInput)
      );
      setList(filtered);
    });
  }, [deferredInput]);

  const content = (
    <section style={isPending ? { opacity: 0.4 } : null}>
      <p>Searching for: {deferredInput || "All"}</p>
      {isPending ? <p>Loading...</p> : null}
      <ul>
        {list.map((item) => (
          <li key={item}>{item}</li>
        ))}
      </ul>
    </section>
  );

  return (
    <div className="App">
      <input type="text" val={inputValue} onChange={handleInput} />
      {content}
    </div>
  );
};
export default Example2;
```

Index.css:

```css
body {
  background-color: #333;
  color: whitesmoke;
  font-size: 2rem;
  padding: 2rem;
}

input,
button {
  font: inherit;
  padding: 1rem;
}

button {
  display: block;
  margin-bottom: 1rem;
}
```

# #End  </details>

+AUTHENTICATION

<details>
  <summary>189. React Form - Create Register Component with Custom Validation</summary>

App.js:

```js
import Register from "./Register";

function App() {
  return (
    <div className="App">
      <Register />
    </div>
  );
}

export default App;
```

Set Up Font-Awesome with React:

-Add SVG Core

```bs
npm i --save @fortawesome/fontawesome-svg-core
```

-Add Icon Packages

```bs
npm i --save @fortawesome/free-solid-svg-icons
```

-Add the React Component

```bs
npm i --save @fortawesome/react-fontawesome@latest
```

Register.js:

```js
import { useRef, useState, useEffect } from "react";
import {
  faCheck,
  faTimes,
  faInfoCircle,
} from "@fortawesome/free-solid-svg-icons";
import { FontAwesomeIcon } from "@fortawesome/react-fontawesome";

const USER_REGEX = /^[A-z][A-z0-9-_]{3,23}$/;
const PWD_REGEX = /^(?=.*[a-z])(?=.*[A-Z])(?=.*[0-9])(?=.*[!@#$%]).{8,24}$/;

const Register = () => {
  const userRef = useRef();
  const errRef = useRef();

  const [user, setUser] = useState("");
  const [validName, setValidName] = useState(false);
  const [userFocus, setUserFocus] = useState(false);

  const [pwd, setPwd] = useState("");
  const [validPwd, setValidPwd] = useState(false);
  const [pwdFocus, setPwdFocus] = useState(false);

  const [matchPwd, setMatchPwd] = useState("");
  const [validMatch, setValidMatch] = useState(false);
  const [matchFocus, setMatchFocus] = useState(false);

  const [errMsg, setErrMsg] = useState("");
  const [success, setSuccess] = useState(false);

  useEffect(() => {
    userRef.current.focus();
  }, []);

  useEffect(() => {
    const result = USER_REGEX.test(user);
    console.log(result);
    console.log(user);
    setValidName(result);
    //setValidName(USER_REGEX.test(user));
  }, [user]);

  useEffect(() => {
    const result = PWD_REGEX.test(pwd);
    console.log(result);
    console.log(pwd);
    setValidPwd(result);
    //setValidPwd(PWD_REGEX.test(pwd));
    const match = pwd === matchPwd;
    setValidMatch(match);
    //setValidMatch(pwd === matchPwd);
  }, [pwd, matchPwd]);

  useEffect(() => {
    setErrMsg("");
  }, [user, pwd, matchPwd]);

  return (
    <section>
      <p
        ref={errRef}
        className={errMsg ? "errmsg" : "offscreen"}
        aria-live="assertive"
      >
        {errMsg}
      </p>
      <h1>Register</h1>
      <form>
        {/* Username */}
        <label htmlFor="username">
          Username:
          <FontAwesomeIcon
            icon={faCheck}
            className={validName ? "valid" : "hide"}
          />
          <FontAwesomeIcon
            icon={faTimes}
            className={validName || !user ? "hide" : "invalid"}
          />
        </label>
        <input
          type="text"
          id="username"
          ref={userRef}
          autoComplete="off"
          onChange={(e) => setUser(e.target.value)}
          value={user}
          required
          aria-invalid={validName ? "false" : "true"}
          aria-describedby="uidnote"
          onFocus={() => setUserFocus(true)}
          onBlur={() => setUserFocus(false)}
        />
        <p
          id="uidnote"
          className={
            userFocus && user && !validName ? "instructions" : "offscreen"
          }
        >
          <FontAwesomeIcon icon={faInfoCircle} />
          4 to 24 characters.
          <br />
          Must begin with a letter.
          <br />
          Letters, numbers, underscores, hyphens allowed.
        </p>

        {/* Password */}
        <label htmlFor="password">
          Password:
          <FontAwesomeIcon
            icon={faCheck}
            className={validPwd ? "valid" : "hide"}
          />
          <FontAwesomeIcon
            icon={faTimes}
            className={validPwd || !pwd ? "hide" : "invalid"}
          />
        </label>
        <input
          type="password"
          id="password"
          onChange={(e) => setPwd(e.target.value)}
          value={pwd}
          required
          aria-invalid={validPwd ? "false" : "true"}
          aria-describedby="pwdnote"
          onFocus={() => setPwdFocus(true)}
          onBlur={() => setPwdFocus(false)}
        />
        <p
          id="pwdnote"
          className={pwdFocus && !validPwd ? "instructions" : "offscreen"}
        >
          <FontAwesomeIcon icon={faInfoCircle} />
          8 to 24 characters.
          <br />
          Must include uppercase and lowercase letters, a number and a special character.
          <br />
          Allowed special characters: <span aria-label="exclamation mark">
            !
          </span> <span aria-label="at symbol">@</span> <span aria-label="hashtag">
            #
          </span> <span aria-label="dollar sign">$</span> <span aria-label="percent">%</span>
        </p>

        {/* Confirm Password */}
        <label htmlFor="confirm_pwd">
          Confirm Password:
          <FontAwesomeIcon
            icon={faCheck}
            className={validMatch && matchPwd ? "valid" : "hide"}
          />
          <FontAwesomeIcon
            icon={faTimes}
            className={validMatch || !matchPwd ? "hide" : "invalid"}
          />
        </label>
        <input
          type="password"
          id="confirm_pwd"
          onChange={(e) => setMatchPwd(e.target.value)}
          value={matchPwd}
          required
          aria-invalid={validMatch ? "false" : "true"}
          aria-describedby="confirmnote"
          onFocus={() => setMatchFocus(true)}
          onBlur={() => setMatchFocus(false)}
        />
        <p
          id="confirmnote"
          className={matchFocus && !validMatch ? "instructions" : "offscreen"}
        >
          <FontAwesomeIcon icon={faInfoCircle} />
          Must match the first password input field.
        </p>

        <button
          disabled={!validName || !validPwd || !validMatch ? true : false}
        >
          Sign Up
        </button>
      </form>
      <p>
        Already registered?
        <br />
        <span className="line">
          {/*put router link here*/}
          <a href="#">Sign In</a>
        </span>
      </p>
    </section>
  );
};

export default Register;
```

Index.css:

```css
@import url("https://fonts.googleapis.com/css2?family=Nunito&display=swap");

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  font-family: "Nunito", sans-serif;
  font-size: 22px;
  color: #fff;
}

body {
  min-height: 100vh;
  background-color: dodgerblue;
}

.App {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  padding: 1rem 0.5rem;
}

section {
  width: 100%;
  max-width: 420px;
  min-height: 400px;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  padding: 1rem;
  background-color: rgba(0, 0, 0, 0.4);
}

form {
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  flex-grow: 1;
  padding-bottom: 1rem;
}

a,
a:visited {
  color: #fff;
}

input[type="text"],
input[type="password"],
button,
textarea {
  font-family: "Nunito", sans-serif;
  font-size: 22px;
  padding: 0.25rem;
  border-radius: 0.5rem;
}

label,
button {
  margin-top: 1rem;
}

button {
  padding: 0.5rem;
}

.instructions {
  font-size: 0.75rem;
  border-radius: 0.5rem;
  background: #000;
  color: #fff;
  padding: 0.25rem;
  position: relative;
  bottom: -10px;
}

.instructions > svg {
  margin-right: 0.25rem;
}

.offscreen {
  position: absolute;
  left: -9999px;
}

.hide {
  display: none;
}

.valid {
  color: limegreen;
  margin-left: 0.25rem;
}

.invalid {
  color: red;
  margin-left: 0.25rem;
}

.errmsg {
  background-color: lightpink;
  color: firebrick;
  font-weight: bold;
  padding: 0.5rem;
  margin-bottom: 0.5rem;
}

.line {
  display: inline-block;
}
```

![proj10](https://user-images.githubusercontent.com/32337103/214263079-855d21db-1aa5-4db5-bddb-32e8c87cbd40.png)

# #End  </details>

<details>
  <summary>190. React Form - Handle Submit with Axios to Register Inputs</summary>

Install Axios:

```bs
npm install axios -S
```

api/axios.js:

```js
import axios from "axios";

export default axios.create({
  baseURL: "http://localhost:3500",
});
```

App.js:

```js
import Register from "./Register";

function App() {
  return (
    <div className="App">
      <Register />
    </div>
  );
}

export default App;
```

Register.js:

```js
import React, { useRef, useState, useEffect } from "react";
import {
  faCheck,
  faTimes,
  faInfoCircle,
} from "@fortawesome/free-solid-svg-icons";
import { FontAwesomeIcon } from "@fortawesome/react-fontawesome";
import axios from "./api/axios";

const USER_REGEX = /^[A-z][A-z0-9-_]{3,23}$/;
const PWD_REGEX = /^(?=.*[a-z])(?=.*[A-Z])(?=.*[0-9])(?=.*[!@#$%]).{8,24}$/;
const REGISTER_URL = "/register";

const Register = () => {
  const userRef = useRef();
  const errRef = useRef();

  const [user, setUser] = useState("");
  const [validName, setValidName] = useState(false);
  const [userFocus, setUserFocus] = useState(false);

  const [pwd, setPwd] = useState("");
  const [validPwd, setValidPwd] = useState(false);
  const [pwdFocus, setPwdFocus] = useState(false);

  const [matchPwd, setMatchPwd] = useState("");
  const [validMatch, setValidMatch] = useState(false);
  const [matchFocus, setMatchFocus] = useState(false);

  const [errMsg, setErrMsg] = useState("");
  const [success, setSuccess] = useState(false);

  useEffect(() => {
    userRef.current.focus();
  }, []);

  useEffect(() => {
    const result = USER_REGEX.test(user);
    //console.log(result);
    //console.log(user);
    setValidName(result);
    //setValidName(USER_REGEX.test(user));
  }, [user]);

  useEffect(() => {
    const result = PWD_REGEX.test(pwd);
    //console.log(result);
    //console.log(pwd);
    setValidPwd(result);
    //setValidPwd(PWD_REGEX.test(pwd));
    const match = pwd === matchPwd;
    setValidMatch(match);
    //setValidMatch(pwd === matchPwd);
  }, [pwd, matchPwd]);

  useEffect(() => {
    setErrMsg("");
  }, [user, pwd, matchPwd]);

  const handleSubmit = async (e) => {
    e.preventDefault();
    // if button enabled with JS hack
    const v1 = USER_REGEX.test(user);
    const v2 = PWD_REGEX.test(pwd);
    if (!v1 || !v2) {
      setErrMsg("Invalid Entry");
      return;
    }
    //console.log(user, pwd);
    //setSuccess(true);
    try {
      const response = await axios.post(
        REGISTER_URL,
        JSON.stringify({ user, pwd }),
        {
          headers: { "Content-Type": "application/json" },
          withCredentials: true,
        }
      );
      console.log(response?.data);
      console.log(response?.accessToken);
      console.log(JSON.stringify(response));
      setSuccess(true);
      //clear state and controlled inputs
      //need value attrib on inputs for this
      setUser("");
      setPwd("");
      setMatchPwd("");
    } catch (err) {
      if (!err?.response) {
        setErrMsg("No Server Response");
      } else if (err.response?.status === 409) {
        setErrMsg("Username Taken");
      } else {
        setErrMsg("Registration Failed");
      }
      errRef.current.focus();
    }
  };

  return (
    <React.Fragment>
      {/* {success ? () : ()} */}
      {success ? (
        <section>
          <h1>Success!</h1>
          <p>
            <a href="#">Sign In</a>
          </p>
        </section>
      ) : (
        <section>
          <p
            ref={errRef}
            className={errMsg ? "errmsg" : "offscreen"}
            aria-live="assertive"
          >
            {errMsg}
          </p>
          <h1>Register</h1>
          <form onSubmit={handleSubmit}>
            {/* Username */}
            <label htmlFor="username">
              Username:
              <FontAwesomeIcon
                icon={faCheck}
                className={validName ? "valid" : "hide"}
              />
              <FontAwesomeIcon
                icon={faTimes}
                className={validName || !user ? "hide" : "invalid"}
              />
            </label>
            <input
              type="text"
              id="username"
              ref={userRef}
              autoComplete="off"
              onChange={(e) => setUser(e.target.value)}
              value={user}
              required
              aria-invalid={validName ? "false" : "true"}
              aria-describedby="uidnote"
              onFocus={() => setUserFocus(true)}
              onBlur={() => setUserFocus(false)}
            />
            <p
              id="uidnote"
              className={
                userFocus && user && !validName ? "instructions" : "offscreen"
              }
            >
              <FontAwesomeIcon icon={faInfoCircle} />
              4 to 24 characters.
              <br />
              Must begin with a letter.
              <br />
              Letters, numbers, underscores, hyphens allowed.
            </p>

            {/* Password */}
            <label htmlFor="password">
              Password:
              <FontAwesomeIcon
                icon={faCheck}
                className={validPwd ? "valid" : "hide"}
              />
              <FontAwesomeIcon
                icon={faTimes}
                className={validPwd || !pwd ? "hide" : "invalid"}
              />
            </label>
            <input
              type="password"
              id="password"
              onChange={(e) => setPwd(e.target.value)}
              value={pwd}
              required
              aria-invalid={validPwd ? "false" : "true"}
              aria-describedby="pwdnote"
              onFocus={() => setPwdFocus(true)}
              onBlur={() => setPwdFocus(false)}
            />
            <p
              id="pwdnote"
              className={pwdFocus && !validPwd ? "instructions" : "offscreen"}
            >
              <FontAwesomeIcon icon={faInfoCircle} />
              8 to 24 characters.
              <br />
              Must include uppercase and lowercase letters, a number and a special
              character.
              <br />
              Allowed special characters: <span aria-label="exclamation mark">
                !
              </span> <span aria-label="at symbol">@</span> <span aria-label="hashtag">
                #
              </span> <span aria-label="dollar sign">$</span> <span aria-label="percent">%</span>
            </p>

            {/* Confirm Password */}
            <label htmlFor="confirm_pwd">
              Confirm Password:
              <FontAwesomeIcon
                icon={faCheck}
                className={validMatch && matchPwd ? "valid" : "hide"}
              />
              <FontAwesomeIcon
                icon={faTimes}
                className={validMatch || !matchPwd ? "hide" : "invalid"}
              />
            </label>
            <input
              type="password"
              id="confirm_pwd"
              onChange={(e) => setMatchPwd(e.target.value)}
              value={matchPwd}
              required
              aria-invalid={validMatch ? "false" : "true"}
              aria-describedby="confirmnote"
              onFocus={() => setMatchFocus(true)}
              onBlur={() => setMatchFocus(false)}
            />
            <p
              id="confirmnote"
              className={
                matchFocus && !validMatch ? "instructions" : "offscreen"
              }
            >
              <FontAwesomeIcon icon={faInfoCircle} />
              Must match the first password input field.
            </p>

            <button
              disabled={!validName || !validPwd || !validMatch ? true : false}
            >
              Sign Up
            </button>
          </form>
          <p>
            Already registered?
            <br />
            <span className="line">
              {/*put router link here*/}
              <a href="#">Sign In</a>
            </span>
          </p>
        </section>
      )}
    </React.Fragment>
  );
};

export default Register;
```

Add React Frontend to Node backend Server -

allowedOrigins.js:

```js
const allowedOrigins = [
  "https://www.yoursite.com",
  "http://127.0.0.1:5500",
  "http://localhost:3500",
  "http://localhost:3000",
];

module.exports = allowedOrigins;
```

Run Node.js Server:

```bs
npm run dev
```

index.css:

```css
@import url("https://fonts.googleapis.com/css2?family=Nunito&display=swap");

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  font-family: "Nunito", sans-serif;
  font-size: 22px;
  color: #fff;
}

body {
  min-height: 100vh;
  background-color: dodgerblue;
}

.App {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  padding: 1rem 0.5rem;
}

section {
  width: 100%;
  max-width: 420px;
  min-height: 400px;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  padding: 1rem;
  background-color: rgba(0, 0, 0, 0.4);
}

form {
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  flex-grow: 1;
  padding-bottom: 1rem;
}

a,
a:visited {
  color: #fff;
}

input[type="text"],
input[type="password"],
button,
textarea {
  font-family: "Nunito", sans-serif;
  font-size: 22px;
  padding: 0.25rem;
  border-radius: 0.5rem;
}

label,
button {
  margin-top: 1rem;
}

button {
  padding: 0.5rem;
}

.instructions {
  font-size: 0.75rem;
  border-radius: 0.5rem;
  background: #000;
  color: #fff;
  padding: 0.25rem;
  position: relative;
  bottom: -10px;
}

.instructions > svg {
  margin-right: 0.25rem;
}

.offscreen {
  position: absolute;
  left: -9999px;
}

.hide {
  display: none;
}

.valid {
  color: limegreen;
  margin-left: 0.25rem;
}

.invalid {
  color: red;
  margin-left: 0.25rem;
}

.errmsg {
  background-color: lightpink;
  color: firebrick;
  font-weight: bold;
  padding: 0.5rem;
  margin-bottom: 0.5rem;
}

.line {
  display: inline-block;
}
```

# #End  </details>

<details>
  <summary>191. React Form - Create User Login Component </summary>

App.js:

```js
import Register from "./Register";
import Login from "./Login";

function App() {
  return (
    <main className="App">
      <Login />
    </main>
  );
}

export default App;
```

Login.js:

```js
import { useRef, useState, useEffect, useContext } from "react";

const Login = () => {
  const userRef = useRef();
  const errRef = useRef();

  const [user, setUser] = useState("");
  const [pwd, setPwd] = useState("");
  const [errMsg, setErrMsg] = useState("");
  const [success, setSuccess] = useState(false);

  useEffect(() => {
    userRef.current.focus();
  }, []);

  useEffect(() => {
    setErrMsg("");
  }, [user, pwd]);

  const handleSubmit = () => {};

  return (
    <section>
      <p
        ref={errRef}
        className={errMsg ? "errmsg" : "offscreen"}
        aria-live="assertive"
      >
        {errMsg}
      </p>
      <h1>Sign In</h1>
      <form onSubmit={handleSubmit}>
        <label htmlFor="username">Username:</label>
        <input
          type="text"
          id="username"
          ref={userRef}
          autoComplete="off"
          onChange={(e) => setUser(e.target.value)}
          value={user}
          required
        />

        <label htmlFor="password">Password:</label>
        <input
          type="password"
          id="password"
          onChange={(e) => setPwd(e.target.value)}
          value={pwd}
          required
        />
        <button>Sign In</button>
      </form>
      <p>
        Need an Account?
        <br />
        <span className="line">
          {/*put router link here*/}
          <a href="#">Sign Up</a>
        </span>
      </p>
    </section>
  );
};

export default Login;
```

index.css:

```css
@import url("https://fonts.googleapis.com/css2?family=Nunito&display=swap");

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  font-family: "Nunito", sans-serif;
  font-size: 22px;
  color: #fff;
}

body {
  min-height: 100vh;
  background-color: dodgerblue;
}

.App {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  padding: 1rem 0.5rem;
}

section {
  width: 100%;
  max-width: 420px;
  min-height: 400px;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  padding: 1rem;
  background-color: rgba(0, 0, 0, 0.4);
}

form {
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  flex-grow: 1;
  padding-bottom: 1rem;
}

a,
a:visited {
  color: #fff;
}

input[type="text"],
input[type="password"],
button,
textarea {
  font-family: "Nunito", sans-serif;
  font-size: 22px;
  padding: 0.25rem;
  border-radius: 0.5rem;
}

label,
button {
  margin-top: 1rem;
}

button {
  padding: 0.5rem;
}

.instructions {
  font-size: 0.75rem;
  border-radius: 0.5rem;
  background: #000;
  color: #fff;
  padding: 0.25rem;
  position: relative;
  bottom: -10px;
}

.instructions > svg {
  margin-right: 0.25rem;
}

.offscreen {
  position: absolute;
  left: -9999px;
}

.hide {
  display: none;
}

.valid {
  color: limegreen;
  margin-left: 0.25rem;
}

.invalid {
  color: red;
  margin-left: 0.25rem;
}

.errmsg {
  background-color: lightpink;
  color: firebrick;
  font-weight: bold;
  padding: 0.5rem;
  margin-bottom: 0.5rem;
}

.line {
  display: inline-block;
}
```

![proj9](https://user-images.githubusercontent.com/32337103/214262692-28afe700-aaea-434a-82ed-f78539b4aa2a.png)

# #End  </details>

<details>
  <summary>192. React Form - Handle Submit to Login Input </summary>

Login.js:

```js
import { useRef, useState, useEffect, useContext } from "react";

const Login = () => {
  const userRef = useRef();
  const errRef = useRef();

  const [user, setUser] = useState("");
  const [pwd, setPwd] = useState("");
  const [errMsg, setErrMsg] = useState("");
  const [success, setSuccess] = useState(false);

  useEffect(() => {
    userRef.current.focus();
  }, []);

  useEffect(() => {
    setErrMsg("");
  }, [user, pwd]);

  const handleSubmit = async (e) => {
    e.preventDefault();
    console.log(user, pwd);
    setUser("");
    setPwd("");
    setSuccess(true);
  };

  return (
    <>
      {success ? (
        <section>
          <h1>You are logged in!</h1>
          <br />
          <p>
            <a href="#">Go to Home</a>
          </p>
        </section>
      ) : (
        <section>
          <p
            ref={errRef}
            className={errMsg ? "errmsg" : "offscreen"}
            aria-live="assertive"
          >
            {errMsg}
          </p>
          <h1>Sign In</h1>
          <form onSubmit={handleSubmit}>
            <label htmlFor="username">Username:</label>
            <input
              type="text"
              id="username"
              ref={userRef}
              autoComplete="off"
              onChange={(e) => setUser(e.target.value)}
              value={user}
              required
            />

            <label htmlFor="password">Password:</label>
            <input
              type="password"
              id="password"
              onChange={(e) => setPwd(e.target.value)}
              value={pwd}
              required
            />
            <button>Sign In</button>
          </form>
          <p>
            Need an Account?
            <br />
            <span className="line">
              {/*put router link here*/}
              <a href="#">Sign Up</a>
            </span>
          </p>
        </section>
      )}
    </>
  );
};

export default Login;
```

![proj11](https://user-images.githubusercontent.com/32337103/214399867-a19292f2-4945-4e12-b3e4-578c9c0a2021.png)

![proj12](https://user-images.githubusercontent.com/32337103/214399914-7a0ef78f-452c-4b87-9b58-3f2d21dc5277.png)

# #End  </details>

<details>
  <summary>193. React Form -  Using Context API to create Auth Provider</summary>

context/AuthProvider.js:

```js
import { createContext, useState } from "react";

const AuthContext = createContext({});

export const AuthProvider = ({ children }) => {
  const [auth, setAuth] = useState({});

  return (
    <AuthContext.Provider value={{ auth, setAuth }}>
      {children}
    </AuthContext.Provider>
  );
};

export default AuthContext;
```

index.js:

```js
import React from "react";
import ReactDOM from "react-dom";
import "./index.css";
import App from "./App";
import { AuthProvider } from "./context/AuthProvider";

ReactDOM.render(
  <React.StrictMode>
    <AuthProvider>
      <App />
    </AuthProvider>
  </React.StrictMode>,
  document.getElementById("root")
);
```

Login.js:

```bs
import AuthContext from "./context/AuthProvider";

const Login = () => {
  const { setAuth } = useContext(AuthContext);

```

```js
import { useRef, useState, useEffect, useContext } from "react";
import AuthContext from "./context/AuthProvider";

const Login = () => {
  const { setAuth } = useContext(AuthContext);
  const userRef = useRef();
  const errRef = useRef();

  const [user, setUser] = useState("");
  const [pwd, setPwd] = useState("");
  const [errMsg, setErrMsg] = useState("");
  const [success, setSuccess] = useState(false);

  useEffect(() => {
    userRef.current.focus();
  }, []);

  useEffect(() => {
    setErrMsg("");
  }, [user, pwd]);

  const handleSubmit = async (e) => {
    e.preventDefault();
    console.log(user, pwd);
    setUser("");
    setPwd("");
    setSuccess(true);
  };

  return (
    <>
      {success ? (
        <section>
          <h1>You are logged in!</h1>
          <br />
          <p>
            <a href="#">Go to Home</a>
          </p>
        </section>
      ) : (
        <section>
          <p
            ref={errRef}
            className={errMsg ? "errmsg" : "offscreen"}
            aria-live="assertive"
          >
            {errMsg}
          </p>
          <h1>Sign In</h1>
          <form onSubmit={handleSubmit}>
            <label htmlFor="username">Username:</label>
            <input
              type="text"
              id="username"
              ref={userRef}
              autoComplete="off"
              onChange={(e) => setUser(e.target.value)}
              value={user}
              required
            />

            <label htmlFor="password">Password:</label>
            <input
              type="password"
              id="password"
              onChange={(e) => setPwd(e.target.value)}
              value={pwd}
              required
            />
            <button>Sign In</button>
          </form>
          <p>
            Need an Account?
            <br />
            <span className="line">
              {/*put router link here*/}
              <a href="#">Sign Up</a>
            </span>
          </p>
        </section>
      )}
    </>
  );
};

export default Login;
```

# #End  </details>

<details>
  <summary>194. React Form - Using Axios to handle Login Submit to NodeJS Server</summary>

```bs
npm i axios
```

api/axios.js:

```js
import axios from "axios";

export default axios.create({
  baseURL: "http://localhost:3500",
});
```

Login.js:

```bs
import axios from './api/axios';
const LOGIN_URL = '/auth';
```

```js
import { useRef, useState, useEffect, useContext } from "react";
import AuthContext from "./context/AuthProvider";

import axios from "./api/axios";
const LOGIN_URL = "/auth";

const Login = () => {
  const { setAuth } = useContext(AuthContext);
  const userRef = useRef();
  const errRef = useRef();

  const [user, setUser] = useState("");
  const [pwd, setPwd] = useState("");
  const [errMsg, setErrMsg] = useState("");
  const [success, setSuccess] = useState(false);

  useEffect(() => {
    userRef.current.focus();
  }, []);

  useEffect(() => {
    setErrMsg("");
  }, [user, pwd]);

  const handleSubmit = async (e) => {
    e.preventDefault();

    try {
      const response = await axios.post(
        LOGIN_URL,
        JSON.stringify({ user, pwd }),
        {
          headers: { "Content-Type": "application/json" },
          withCredentials: true,
        }
      );
      console.log(JSON.stringify(response?.data));
      //console.log(JSON.stringify(response));
      const accessToken = response?.data?.accessToken;
      const roles = response?.data?.roles;
      setAuth({ user, pwd, roles, accessToken });
      setUser("");
      setPwd("");
      setSuccess(true);
    } catch (err) {
      if (!err?.response) {
        setErrMsg("No Server Response");
      } else if (err.response?.status === 400) {
        setErrMsg("Missing Username or Password");
      } else if (err.response?.status === 401) {
        setErrMsg("Unauthorized");
      } else {
        setErrMsg("Login Failed");
      }
      errRef.current.focus();
    }
  };

  return (
    <>
      {success ? (
        <section>
          <h1>You are logged in!</h1>
          <br />
          <p>
            <a href="#">Go to Home</a>
          </p>
        </section>
      ) : (
        <section>
          <p
            ref={errRef}
            className={errMsg ? "errmsg" : "offscreen"}
            aria-live="assertive"
          >
            {errMsg}
          </p>
          <h1>Sign In</h1>
          <form onSubmit={handleSubmit}>
            <label htmlFor="username">Username:</label>
            <input
              type="text"
              id="username"
              ref={userRef}
              autoComplete="off"
              onChange={(e) => setUser(e.target.value)}
              value={user}
              required
            />

            <label htmlFor="password">Password:</label>
            <input
              type="password"
              id="password"
              onChange={(e) => setPwd(e.target.value)}
              value={pwd}
              required
            />
            <button>Sign In</button>
          </form>
          <p>
            Need an Account?
            <br />
            <span className="line">
              {/*put router link here*/}
              <a href="#">Sign Up</a>
            </span>
          </p>
        </section>
      )}
    </>
  );
};

export default Login;
```

# #End  </details>

<details>
  <summary>195. React Form - Setup Node Server and Test</summary>

Frontend -

index.js:

```js
import React from "react";
import { createRoot } from "react-dom/client";
// import ReactDOM from "react-dom";
import "./index.css";
import App from "./App";
import { AuthProvider } from "./context/AuthProvider";

const root = createRoot(document.getElementById("root"));

root.render(
  <React.StrictMode>
    <AuthProvider>
      <App />
    </AuthProvider>
  </React.StrictMode>
);
```

Backend -

config/allowedOrigins.js:

```js
const allowedOrigins = [
  "https://www.yoursite.com",
  "http://127.0.0.1:5500",
  "http://localhost:3500",
  "http://localhost:3000", // include React URL for CORS to allow
];

module.exports = allowedOrigins;
```

controllers/authController.js:

```bs
// Get rid of nulls with Boolean
if (match) {
    const roles = Object.values(foundUser.roles).filter(Boolean);

// Send authorization roles and access token to user
res.json({ roles, accessToken });
```

```js
const User = require("../model/User");
const bcrypt = require("bcrypt");
const jwt = require("jsonwebtoken");

const handleLogin = async (req, res) => {
  const { user, pwd } = req.body;
  if (!user || !pwd)
    return res
      .status(400)
      .json({ message: "Username and password are required." });

  const foundUser = await User.findOne({ username: user }).exec();
  if (!foundUser) return res.sendStatus(401); //Unauthorized
  // evaluate password
  const match = await bcrypt.compare(pwd, foundUser.password);
  if (match) {
    const roles = Object.values(foundUser.roles).filter(Boolean);
    // create JWTs
    const accessToken = jwt.sign(
      {
        UserInfo: {
          username: foundUser.username,
          roles: roles,
        },
      },
      process.env.ACCESS_TOKEN_SECRET,
      { expiresIn: "10s" }
    );
    const refreshToken = jwt.sign(
      { username: foundUser.username },
      process.env.REFRESH_TOKEN_SECRET,
      { expiresIn: "1d" }
    );
    // Saving refreshToken with current user
    foundUser.refreshToken = refreshToken;
    const result = await foundUser.save();
    console.log(result);
    console.log(roles);

    // Creates Secure Cookie with refresh token
    res.cookie("jwt", refreshToken, {
      httpOnly: true,
      secure: false,
      sameSite: "None",
      maxAge: 24 * 60 * 60 * 1000,
    });

    // Send authorization roles and access token to user
    res.json({ roles, accessToken });
  } else {
    res.sendStatus(401);
  }
};

module.exports = { handleLogin };
```

```bs
npm run dev
```

```bs
[nodemon] restarting due to changes...
[nodemon] starting `node server.js`
(node:21485) [MONGOOSE] DeprecationWarning: Mongoose: the `strictQuery` option will be switched back to `false` by default in Mongoose 7. Use `mongoose.set('strictQuery', false);` if you want to prepare for this change. Or use `mongoose.set('strictQuery', true);` to suppress this warning.
(Use `node --trace-deprecation ...` to show where the warning was created)
Connected to MongoDB
Server running on port 3500
```

In MongoDB:

```bs
UN: dave1
PW: Aa$12345
[User: 2001]

UN: jane1
PW: Aa$12345
[User: 2001, Editor: 1984]

UN: walt1
PW: Aa$12345
[User: 2001, Editor: 1984, Admin: 5150]
```

Login with:

```bs
UN: ifeanyi
PW: password123
```

![proj13](https://user-images.githubusercontent.com/32337103/214529888-3afbb369-825f-45a0-bd99-9d9c73f748da.png)

```bs
POST http://localhost:3500/auth 401 (Unauthorized)
```

Login with:

```bs
UN: dave1
PW: Aa$12345
```

![proj14](https://user-images.githubusercontent.com/32337103/214537760-328830f7-f34d-4678-8d44-68dd912c0cb5.png)

![proj15](https://user-images.githubusercontent.com/32337103/214537792-0acb226d-05d2-47bb-b4d4-8128019f1ed0.png)

```bs
{"roles":[2001],"accessToken":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJVc2VySW5mbyI6eyJ1c2VybmFtZSI6ImRhdmUxIiwicm9sZXMiOlsyMDAxXX0sImlhdCI6MTY3NDY0MTYxNCwiZXhwIjoxNjc0NjQxNjI0fQ.JmsQ6tBQRBSMagaN2YRaa56ngDvqKg7M-0_bNLU9RuI"}
```

Login with:

```bs
UN: jane1
PW: Aa$12345
```

![proj15](https://user-images.githubusercontent.com/32337103/214537792-0acb226d-05d2-47bb-b4d4-8128019f1ed0.png)

```bs
{"roles":[2001,1984],"accessToken":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJVc2VySW5mbyI6eyJ1c2VybmFtZSI6ImphbmUxIiwicm9sZXMiOlsyMDAxLDE5ODRdfSwiaWF0IjoxNjc0NjQyNDI1LCJleHAiOjE2NzQ2NDI0MzV9.4WsQjSuFI7jjpbCBmAciO9J9X-0-QjaYL6JgCv2jR98"}
```

# #End  </details>

<details>
  <summary>196. React Form (Role-Based Authorization) - Setup Routes and Components</summary>

Install react-router-dom@6:

```bs
npm i react-router-dom@6
```

hooks/useAuth.js:

```js
import { useContext } from "react";
import AuthContext from "../context/AuthProvider";

const useAuth = () => {
  return useContext(AuthContext);
};

export default useAuth;
```

index.js:

```js
import React from "react";
import { createRoot } from "react-dom/client";
import "./index.css";
import App from "./App";
import { AuthProvider } from "./context/AuthProvider";
import { BrowserRouter, Routes, Route } from "react-router-dom";

const root = createRoot(document.getElementById("root"));

root.render(
  <React.StrictMode>
    <BrowserRouter>
      <AuthProvider>
        <Routes>
          <Route path="/*" element={<App />} />
        </Routes>
      </AuthProvider>
    </BrowserRouter>
  </React.StrictMode>
);
```

App.js:

```js
import Register from "./components/Register";
import Login from "./components/Login";
import Home from "./components/Home";
import Layout from "./components/Layout";
import Editor from "./components/Editor";
import Admin from "./components/Admin";
import Missing from "./components/Missing";
import Unauthorized from "./components/Unauthorized";
import Lounge from "./components/Lounge";
import LinkPage from "./components/LinkPage";
// import RequireAuth from "./components/RequireAuth";
import { Routes, Route } from "react-router-dom";

function App() {
  return (
    <Routes>
      <Route path="/" element={<Layout />}>
        {/* public routes */}
        <Route path="login" element={<Login />} />
        <Route path="register" element={<Register />} />
        <Route path="linkpage" element={<LinkPage />} />
        <Route path="unauthorized" element={<Unauthorized />} />

        {/* we want to protect these routes */}
        <Route path="/" element={<Home />} />
        <Route path="editor" element={<Editor />} />
        <Route path="admin" element={<Admin />} />
        <Route path="lounge" element={<Lounge />} />

        {/* catch all */}
        <Route path="*" element={<Missing />} />
      </Route>
    </Routes>
  );
}

export default App;
```

components/Layout.js:

```js
import { Outlet } from "react-router-dom";

const Layout = () => {
  return (
    <main className="App">
      <Outlet />
    </main>
  );
};

export default Layout;
```

components/Login.js:

```js
import { useRef, useState, useEffect } from "react";
import useAuth from "../hooks/useAuth";
import { Link, useNavigate, useLocation } from "react-router-dom";

import axios from "../api/axios";
const LOGIN_URL = "/auth";

const Login = () => {
  const { setAuth } = useAuth();

  const navigate = useNavigate();
  const location = useLocation();
  const from = location.state?.from?.pathname || "/";

  const userRef = useRef();
  const errRef = useRef();

  const [user, setUser] = useState("");
  const [pwd, setPwd] = useState("");
  const [errMsg, setErrMsg] = useState("");

  useEffect(() => {
    userRef.current.focus();
  }, []);

  useEffect(() => {
    setErrMsg("");
  }, [user, pwd]);

  const handleSubmit = async (e) => {
    e.preventDefault();

    try {
      const response = await axios.post(
        LOGIN_URL,
        JSON.stringify({ user, pwd }),
        {
          headers: { "Content-Type": "application/json" },
          withCredentials: true,
        }
      );
      console.log(JSON.stringify(response?.data));
      //console.log(JSON.stringify(response));
      const accessToken = response?.data?.accessToken;
      const roles = response?.data?.roles;
      setAuth({ user, pwd, roles, accessToken });
      setUser("");
      setPwd("");
      navigate(from, { replace: true });
    } catch (err) {
      if (!err?.response) {
        setErrMsg("No Server Response");
      } else if (err.response?.status === 400) {
        setErrMsg("Missing Username or Password");
      } else if (err.response?.status === 401) {
        setErrMsg("Unauthorized");
      } else {
        setErrMsg("Login Failed");
      }
      errRef.current.focus();
    }
  };

  return (
    <section>
      <p
        ref={errRef}
        className={errMsg ? "errmsg" : "offscreen"}
        aria-live="assertive"
      >
        {errMsg}
      </p>
      <h1>Sign In</h1>
      <form onSubmit={handleSubmit}>
        <label htmlFor="username">Username:</label>
        <input
          type="text"
          id="username"
          ref={userRef}
          autoComplete="off"
          onChange={(e) => setUser(e.target.value)}
          value={user}
          required
        />

        <label htmlFor="password">Password:</label>
        <input
          type="password"
          id="password"
          onChange={(e) => setPwd(e.target.value)}
          value={pwd}
          required
        />
        <button>Sign In</button>
      </form>
      <p>
        Need an Account?
        <br />
        <span className="line">
          <Link to="/register">Sign Up</Link>
        </span>
      </p>
    </section>
  );
};

export default Login;
```

components/Register.js:

```js
import { useRef, useState, useEffect } from "react";
import {
  faCheck,
  faTimes,
  faInfoCircle,
} from "@fortawesome/free-solid-svg-icons";
import { FontAwesomeIcon } from "@fortawesome/react-fontawesome";
import axios from "../api/axios";
import { Link } from "react-router-dom";

const USER_REGEX = /^[A-z][A-z0-9-_]{3,23}$/;
const PWD_REGEX = /^(?=.*[a-z])(?=.*[A-Z])(?=.*[0-9])(?=.*[!@#$%]).{8,24}$/;
const REGISTER_URL = "/register";

const Register = () => {
  const userRef = useRef();
  const errRef = useRef();

  const [user, setUser] = useState("");
  const [validName, setValidName] = useState(false);
  const [userFocus, setUserFocus] = useState(false);

  const [pwd, setPwd] = useState("");
  const [validPwd, setValidPwd] = useState(false);
  const [pwdFocus, setPwdFocus] = useState(false);

  const [matchPwd, setMatchPwd] = useState("");
  const [validMatch, setValidMatch] = useState(false);
  const [matchFocus, setMatchFocus] = useState(false);

  const [errMsg, setErrMsg] = useState("");
  const [success, setSuccess] = useState(false);

  useEffect(() => {
    userRef.current.focus();
  }, []);

  useEffect(() => {
    setValidName(USER_REGEX.test(user));
  }, [user]);

  useEffect(() => {
    setValidPwd(PWD_REGEX.test(pwd));
    setValidMatch(pwd === matchPwd);
  }, [pwd, matchPwd]);

  useEffect(() => {
    setErrMsg("");
  }, [user, pwd, matchPwd]);

  const handleSubmit = async (e) => {
    e.preventDefault();
    // if button enabled with JS hack
    const v1 = USER_REGEX.test(user);
    const v2 = PWD_REGEX.test(pwd);
    if (!v1 || !v2) {
      setErrMsg("Invalid Entry");
      return;
    }
    try {
      const response = await axios.post(
        REGISTER_URL,
        JSON.stringify({ user, pwd }),
        {
          headers: { "Content-Type": "application/json" },
          withCredentials: true,
        }
      );
      // TODO: remove console.logs before deployment
      console.log(JSON.stringify(response?.data));
      //console.log(JSON.stringify(response))
      setSuccess(true);
      //clear state and controlled inputs
      setUser("");
      setPwd("");
      setMatchPwd("");
    } catch (err) {
      if (!err?.response) {
        setErrMsg("No Server Response");
      } else if (err.response?.status === 409) {
        setErrMsg("Username Taken");
      } else {
        setErrMsg("Registration Failed");
      }
      errRef.current.focus();
    }
  };

  return (
    <>
      {success ? (
        <section>
          <h1>Success!</h1>
          <p>
            <a href="#">Sign In</a>
          </p>
        </section>
      ) : (
        <section>
          <p
            ref={errRef}
            className={errMsg ? "errmsg" : "offscreen"}
            aria-live="assertive"
          >
            {errMsg}
          </p>
          <h1>Register</h1>
          <form onSubmit={handleSubmit}>
            <label htmlFor="username">
              Username:
              <FontAwesomeIcon
                icon={faCheck}
                className={validName ? "valid" : "hide"}
              />
              <FontAwesomeIcon
                icon={faTimes}
                className={validName || !user ? "hide" : "invalid"}
              />
            </label>
            <input
              type="text"
              id="username"
              ref={userRef}
              autoComplete="off"
              onChange={(e) => setUser(e.target.value)}
              value={user}
              required
              aria-invalid={validName ? "false" : "true"}
              aria-describedby="uidnote"
              onFocus={() => setUserFocus(true)}
              onBlur={() => setUserFocus(false)}
            />
            <p
              id="uidnote"
              className={
                userFocus && user && !validName ? "instructions" : "offscreen"
              }
            >
              <FontAwesomeIcon icon={faInfoCircle} />
              4 to 24 characters.
              <br />
              Must begin with a letter.
              <br />
              Letters, numbers, underscores, hyphens allowed.
            </p>

            <label htmlFor="password">
              Password:
              <FontAwesomeIcon
                icon={faCheck}
                className={validPwd ? "valid" : "hide"}
              />
              <FontAwesomeIcon
                icon={faTimes}
                className={validPwd || !pwd ? "hide" : "invalid"}
              />
            </label>
            <input
              type="password"
              id="password"
              onChange={(e) => setPwd(e.target.value)}
              value={pwd}
              required
              aria-invalid={validPwd ? "false" : "true"}
              aria-describedby="pwdnote"
              onFocus={() => setPwdFocus(true)}
              onBlur={() => setPwdFocus(false)}
            />
            <p
              id="pwdnote"
              className={pwdFocus && !validPwd ? "instructions" : "offscreen"}
            >
              <FontAwesomeIcon icon={faInfoCircle} />
              8 to 24 characters.
              <br />
              Must include uppercase and lowercase letters, a number and a special
              character.
              <br />
              Allowed special characters: <span aria-label="exclamation mark">
                !
              </span> <span aria-label="at symbol">@</span> <span aria-label="hashtag">
                #
              </span> <span aria-label="dollar sign">$</span> <span aria-label="percent">%</span>
            </p>

            <label htmlFor="confirm_pwd">
              Confirm Password:
              <FontAwesomeIcon
                icon={faCheck}
                className={validMatch && matchPwd ? "valid" : "hide"}
              />
              <FontAwesomeIcon
                icon={faTimes}
                className={validMatch || !matchPwd ? "hide" : "invalid"}
              />
            </label>
            <input
              type="password"
              id="confirm_pwd"
              onChange={(e) => setMatchPwd(e.target.value)}
              value={matchPwd}
              required
              aria-invalid={validMatch ? "false" : "true"}
              aria-describedby="confirmnote"
              onFocus={() => setMatchFocus(true)}
              onBlur={() => setMatchFocus(false)}
            />
            <p
              id="confirmnote"
              className={
                matchFocus && !validMatch ? "instructions" : "offscreen"
              }
            >
              <FontAwesomeIcon icon={faInfoCircle} />
              Must match the first password input field.
            </p>

            <button
              disabled={!validName || !validPwd || !validMatch ? true : false}
            >
              Sign Up
            </button>
          </form>
          <p>
            Already registered?
            <br />
            <span className="line">
              <Link to="/">Sign In</Link>
            </span>
          </p>
        </section>
      )}
    </>
  );
};

export default Register;
```

components/LinkPage.js:

```js
import { Link } from "react-router-dom";

const LinkPage = () => {
  return (
    <section>
      <h1>Links</h1>
      <br />
      <h2>Public</h2>
      <Link to="/login">Login</Link>
      <Link to="/register">Register</Link>
      <br />
      <h2>Private</h2>
      <Link to="/">Home</Link>
      <Link to="/editor">Editors Page</Link>
      <Link to="/admin">Admin Page</Link>
    </section>
  );
};

export default LinkPage;
```

components/Unauthorized.js:

```js
import { useNavigate } from "react-router-dom";

const Unauthorized = () => {
  const navigate = useNavigate();

  const goBack = () => navigate(-1);

  return (
    <section>
      <h1>Unauthorized</h1>
      <br />
      <p>You do not have access to the requested page.</p>
      <div className="flexGrow">
        <button onClick={goBack}>Go Back</button>
      </div>
    </section>
  );
};

export default Unauthorized;
```

components/Home.js:

```js
import { useNavigate, Link } from "react-router-dom";
import { useContext } from "react";
import AuthContext from "../context/AuthProvider";

const Home = () => {
  const { setAuth } = useContext(AuthContext);
  const navigate = useNavigate();

  const logout = async () => {
    // if used in more components, this should be in context
    // axios to /logout endpoint
    setAuth({});
    navigate("/linkpage");
  };

  return (
    <section>
      <h1>Home</h1>
      <br />
      <p>You are logged in!</p>
      <br />
      <Link to="/editor">Go to the Editor page</Link>
      <br />
      <Link to="/admin">Go to the Admin page</Link>
      <br />
      <Link to="/lounge">Go to the Lounge</Link>
      <br />
      <Link to="/linkpage">Go to the link page</Link>
      <div className="flexGrow">
        <button onClick={logout}>Sign Out</button>
      </div>
    </section>
  );
};

export default Home;
```

components/Editor.js:

```js
import { Link } from "react-router-dom";

const Editor = () => {
  return (
    <section>
      <h1>Editors Page</h1>
      <br />
      <p>You must have been assigned an Editor role.</p>
      <div className="flexGrow">
        <Link to="/">Home</Link>
      </div>
    </section>
  );
};

export default Editor;
```

components/Admin.js:

```js
import { Link } from "react-router-dom";

const Admin = () => {
  return (
    <section>
      <h1>Admins Page</h1>
      <br />
      <p>You must have been assigned an Admin role.</p>
      <div className="flexGrow">
        <Link to="/">Home</Link>
      </div>
    </section>
  );
};

export default Admin;
```

components/Lounge.js:

```js
import { Link } from "react-router-dom";

const Lounge = () => {
  return (
    <section>
      <h1>The Lounge</h1>
      <br />
      <p>Admins and Editors can hang out here.</p>
      <div className="flexGrow">
        <Link to="/">Home</Link>
      </div>
    </section>
  );
};

export default Lounge;
```

components/Missing.js:

```js
import { Link } from "react-router-dom";

const Missing = () => {
  return (
    <article style={{ padding: "100px" }}>
      <h1>Oops!</h1>
      <p>Page Not Found</p>
      <div className="flexGrow">
        <Link to="/">Visit Our Homepage</Link>
      </div>
    </article>
  );
};

export default Missing;
```

![proj16](https://user-images.githubusercontent.com/32337103/214806232-32cd280c-2ac7-427c-861d-07758efedf48.png)

![proj17](https://user-images.githubusercontent.com/32337103/214806829-94eefea4-fd5f-4bc4-a35f-857507493ac9.png)

![proj18](https://user-images.githubusercontent.com/32337103/214806878-f4d0c92d-b629-4580-8e2a-673c7ddbd62b.png)

![proj19](https://user-images.githubusercontent.com/32337103/214806915-95c660e2-7b50-4e35-8a60-89a69e9382e7.png)

![proj20](https://user-images.githubusercontent.com/32337103/214806954-c3ff9aaa-2cc1-4555-bc92-aa1308008b36.png)

# #End  </details>

<details>
  <summary>197. React Form (Role-Based Authorization) - Require Auth Component 1 </summary>

hooks/useAuth.js:

```js
import { useContext } from "react";
import AuthContext from "../context/AuthProvider";

const useAuth = () => {
  return useContext(AuthContext);
};

export default useAuth;
```

components/Login.js:

```js
import { useRef, useState, useEffect } from "react";
import useAuth from "../hooks/useAuth";
import { Link, useNavigate, useLocation } from "react-router-dom";

import axios from "../api/axios";
const LOGIN_URL = "/auth";

const Login = () => {
  const { setAuth } = useAuth();

  const navigate = useNavigate();
  const location = useLocation();
  const from = location.state?.from?.pathname || "/";

  const userRef = useRef();
  const errRef = useRef();

  const [user, setUser] = useState("");
  const [pwd, setPwd] = useState("");
  const [errMsg, setErrMsg] = useState("");

  useEffect(() => {
    userRef.current.focus();
  }, []);

  useEffect(() => {
    setErrMsg("");
  }, [user, pwd]);

  const handleSubmit = async (e) => {
    e.preventDefault();

    try {
      const response = await axios.post(
        LOGIN_URL,
        JSON.stringify({ user, pwd }),
        {
          headers: { "Content-Type": "application/json" },
          withCredentials: true,
        }
      );
      console.log(JSON.stringify(response?.data));
      //console.log(JSON.stringify(response));
      const accessToken = response?.data?.accessToken;
      const roles = response?.data?.roles;
      setAuth({ user, pwd, roles, accessToken });
      setUser("");
      setPwd("");
      navigate(from, { replace: true });
    } catch (err) {
      if (!err?.response) {
        setErrMsg("No Server Response");
      } else if (err.response?.status === 400) {
        setErrMsg("Missing Username or Password");
      } else if (err.response?.status === 401) {
        setErrMsg("Unauthorized");
      } else {
        setErrMsg("Login Failed");
      }
      errRef.current.focus();
    }
  };

  return (
    <section>
      <p
        ref={errRef}
        className={errMsg ? "errmsg" : "offscreen"}
        aria-live="assertive"
      >
        {errMsg}
      </p>
      <h1>Sign In</h1>
      <form onSubmit={handleSubmit}>
        <label htmlFor="username">Username:</label>
        <input
          type="text"
          id="username"
          ref={userRef}
          autoComplete="off"
          onChange={(e) => setUser(e.target.value)}
          value={user}
          required
        />

        <label htmlFor="password">Password:</label>
        <input
          type="password"
          id="password"
          onChange={(e) => setPwd(e.target.value)}
          value={pwd}
          required
        />
        <button>Sign In</button>
      </form>
      <p>
        Need an Account?
        <br />
        <span className="line">
          <Link to="/register">Sign Up</Link>
        </span>
      </p>
    </section>
  );
};

export default Login;
```

components/RequireAuth.js:

```js
import { useLocation, Navigate, Outlet } from "react-router-dom";
import useAuth from "../hooks/useAuth";

const RequireAuth = ({ allowedRoles }) => {
  const { auth } = useAuth();
  const location = useLocation();

  return auth?.user ? (
    <Outlet />
  ) : (
    <Navigate to="/login" state={{ from: location }} replace />
  );

  // return auth?.roles?.find((role) => allowedRoles?.includes(role)) ? (
  //   <Outlet />
  // ) : auth?.user ? (
  //   <Navigate to="/unauthorized" state={{ from: location }} replace />
  // ) : (
  //   <Navigate to="/login" state={{ from: location }} replace />
  // );
};

export default RequireAuth;
```

App.js:

```js
import Register from "./components/Register";
import Login from "./components/Login";
import Home from "./components/Home";
import Layout from "./components/Layout";
import Editor from "./components/Editor";
import Admin from "./components/Admin";
import Missing from "./components/Missing";
import Unauthorized from "./components/Unauthorized";
import Lounge from "./components/Lounge";
import LinkPage from "./components/LinkPage";
import RequireAuth from "./components/RequireAuth";
import { Routes, Route } from "react-router-dom";

function App() {
  return (
    <Routes>
      <Route path="/" element={<Layout />}>
        {/* public routes */}
        <Route path="login" element={<Login />} />
        <Route path="register" element={<Register />} />
        <Route path="linkpage" element={<LinkPage />} />
        <Route path="unauthorized" element={<Unauthorized />} />

        {/* we want to protect these routes */}
        <Route element={<RequireAuth />}>
          <Route path="/" element={<Home />} />
          <Route path="editor" element={<Editor />} />
          <Route path="admin" element={<Admin />} />
          <Route path="lounge" element={<Lounge />} />
        </Route>

        {/* catch all */}
        <Route path="*" element={<Missing />} />
      </Route>
    </Routes>
  );
}

export default App;
```

# #End  </details>

<details>
  <summary>198. React Form (Role-Based Authorization) - Require Auth Component 2 with Route Auth </summary>

components/RequireAuth.js:

```js
import { useLocation, Navigate, Outlet } from "react-router-dom";
import useAuth from "../hooks/useAuth";

const RequireAuth = ({ allowedRoles }) => {
  const { auth } = useAuth();
  const location = useLocation();

  return auth?.roles?.find((role) => allowedRoles?.includes(role)) ? (
    <Outlet />
  ) : auth?.user ? (
    <Navigate to="/unauthorized" state={{ from: location }} replace />
  ) : (
    <Navigate to="/login" state={{ from: location }} replace />
  );
};

export default RequireAuth;
```

App.js:

```js
import Register from "./components/Register";
import Login from "./components/Login";
import Home from "./components/Home";
import Layout from "./components/Layout";
import Editor from "./components/Editor";
import Admin from "./components/Admin";
import Missing from "./components/Missing";
import Unauthorized from "./components/Unauthorized";
import Lounge from "./components/Lounge";
import LinkPage from "./components/LinkPage";
import RequireAuth from "./components/RequireAuth";
import { Routes, Route } from "react-router-dom";

const ROLES = {
  User: 2001,
  Editor: 1984,
  Admin: 5150,
};

function App() {
  return (
    <Routes>
      <Route path="/" element={<Layout />}>
        {/* public routes */}
        <Route path="login" element={<Login />} />
        <Route path="register" element={<Register />} />
        <Route path="linkpage" element={<LinkPage />} />
        <Route path="unauthorized" element={<Unauthorized />} />

        {/* we want to protect these routes */}
        <Route element={<RequireAuth allowedRoles={[ROLES.User]} />}>
          <Route path="/" element={<Home />} />
        </Route>

        <Route element={<RequireAuth allowedRoles={[ROLES.Editor]} />}>
          <Route path="editor" element={<Editor />} />
        </Route>

        <Route element={<RequireAuth allowedRoles={[ROLES.Admin]} />}>
          <Route path="admin" element={<Admin />} />
        </Route>

        <Route
          element={<RequireAuth allowedRoles={[ROLES.Editor, ROLES.Admin]} />}
        >
          <Route path="lounge" element={<Lounge />} />
        </Route>

        {/* catch all */}
        <Route path="*" element={<Missing />} />
      </Route>
    </Routes>
  );
}

export default App;
```

components/Login.js:

```js
import { useRef, useState, useEffect } from "react";
import useAuth from "../hooks/useAuth";
import { Link, useNavigate, useLocation } from "react-router-dom";

import axios from "../api/axios";
const LOGIN_URL = "/auth";

const Login = () => {
  const { setAuth } = useAuth();

  const navigate = useNavigate();
  const location = useLocation();
  const from = location.state?.from?.pathname || "/";

  const userRef = useRef();
  const errRef = useRef();

  const [user, setUser] = useState("");
  const [pwd, setPwd] = useState("");
  const [errMsg, setErrMsg] = useState("");

  useEffect(() => {
    userRef.current.focus();
  }, []);

  useEffect(() => {
    setErrMsg("");
  }, [user, pwd]);

  const handleSubmit = async (e) => {
    e.preventDefault();

    try {
      const response = await axios.post(
        LOGIN_URL,
        JSON.stringify({ user, pwd }),
        {
          headers: { "Content-Type": "application/json" },
          withCredentials: true,
        }
      );
      console.log(JSON.stringify(response?.data));
      //console.log(JSON.stringify(response));
      const accessToken = response?.data?.accessToken;
      const roles = response?.data?.roles;
      setAuth({ user, pwd, roles, accessToken });
      setUser("");
      setPwd("");
      navigate(from, { replace: true });
    } catch (err) {
      if (!err?.response) {
        setErrMsg("No Server Response");
      } else if (err.response?.status === 400) {
        setErrMsg("Missing Username or Password");
      } else if (err.response?.status === 401) {
        setErrMsg("Unauthorized");
      } else {
        setErrMsg("Login Failed");
      }
      errRef.current.focus();
    }
  };

  return (
    <section>
      <p
        ref={errRef}
        className={errMsg ? "errmsg" : "offscreen"}
        aria-live="assertive"
      >
        {errMsg}
      </p>
      <h1>Sign In</h1>
      <form onSubmit={handleSubmit}>
        <label htmlFor="username">Username:</label>
        <input
          type="text"
          id="username"
          ref={userRef}
          autoComplete="off"
          onChange={(e) => setUser(e.target.value)}
          value={user}
          required
        />

        <label htmlFor="password">Password:</label>
        <input
          type="password"
          id="password"
          onChange={(e) => setPwd(e.target.value)}
          value={pwd}
          required
        />
        <button>Sign In</button>
      </form>
      <p>
        Need an Account?
        <br />
        <span className="line">
          <Link to="/register">Sign Up</Link>
        </span>
      </p>
    </section>
  );
};

export default Login;
```

components/Unauthorized.js:

```js
import { useNavigate } from "react-router-dom";

const Unauthorized = () => {
  const navigate = useNavigate();

  const goBack = () => navigate(-1);

  return (
    <section>
      <h1>Unauthorized</h1>
      <br />
      <p>You do not have access to the requested page.</p>
      <div className="flexGrow">
        <button onClick={goBack}>Go Back</button>
      </div>
    </section>
  );
};

export default Unauthorized;
```

# #End  </details>

<details>
  <summary>199. React Form (Role-Based Authorization) - Testing Protected Routes </summary>

Users -

```bs
UN: dave1
PW: Aa$12345
ROLE: 2001 (User)

UN: jane1
PW: Aa$12345
ROLE: 2001 (User), 1984 (Editor)

UN: walt1
PW: Aa$12345
ROLE: 2001 (User), 1984 (Editor), 5150 (Admin)
```

Login with mike:

```bs
UN: mike
PW: Aa$12345
ROLE: None
```

Note: Cannot Access any Routes! Unauthorized!

![proj21](https://user-images.githubusercontent.com/32337103/214816284-a28a9c3a-1e7d-4786-b3e5-6f22d20e6b64.png)

Login with dave1:

```bs
UN: dave1
PW: Aa$12345
ROLE: 2001 (User)
```

Note: Can only Access Home Route. Unauthorized access to Editor, Admin and Lounge Pages!

![proj22](https://user-images.githubusercontent.com/32337103/214819972-8abd55a1-0088-447c-8901-70bbcbc51b61.png)

![proj001](https://user-images.githubusercontent.com/32337103/214820079-df6cd3ee-68ae-4e00-91d2-f204eddd801b.png)

Login with jane1:

```bs
UN: jane1
PW: Aa$12345
ROLE: 2001 (User), 1984 (Editor)
```

Note: Can Access Home, Editor and Lounge Routes, But Unauthorized access to Admin Route!

![proj22](https://user-images.githubusercontent.com/32337103/214819972-8abd55a1-0088-447c-8901-70bbcbc51b61.png)

![proj002](https://user-images.githubusercontent.com/32337103/214821717-74eb4e61-6926-46bc-8be1-a170144c0bf6.png)

![proj003](https://user-images.githubusercontent.com/32337103/214821803-820cfb1e-53d5-4c45-b801-da93ad3e00b1.png)

![proj001](https://user-images.githubusercontent.com/32337103/214820079-df6cd3ee-68ae-4e00-91d2-f204eddd801b.png)

Login with walt1:

```bs
UN: walt1
PW: Aa$12345
ROLE: 2001 (User), 1984 (Editor), 5150 (Admin)
```

Note: Can Access all routes - Home, Editor, Lounge and Admin Routes!

![proj22](https://user-images.githubusercontent.com/32337103/214819972-8abd55a1-0088-447c-8901-70bbcbc51b61.png)

![proj002](https://user-images.githubusercontent.com/32337103/214821717-74eb4e61-6926-46bc-8be1-a170144c0bf6.png)

![proj003](https://user-images.githubusercontent.com/32337103/214821803-820cfb1e-53d5-4c45-b801-da93ad3e00b1.png)

![proj004](https://user-images.githubusercontent.com/32337103/214823396-7b64ec32-7270-4c4c-9f6a-6f4f3ecb3fe0.png)

# #End  </details>

<details>
  <summary>200. React Form - Authentication with JWT Access, Refresh Tokens, Cookies and Axios</summary>

```bs
npm update
```

components/Users.js:

```js
import { useState, useEffect, useRef } from "react";
import useAxiosPrivate from "../hooks/useAxiosPrivate";
import { useNavigate, useLocation } from "react-router-dom";

const Users = () => {
  const [users, setUsers] = useState();
  const axiosPrivate = useAxiosPrivate();
  const navigate = useNavigate();
  const location = useLocation();
  const effectRun = useRef(false);

  useEffect(() => {
    let isMounted = true;
    const controller = new AbortController();

    const getUsers = async () => {
      try {
        const response = await axiosPrivate.get("/users", {
          signal: controller.signal,
        });
        console.log(response.data);
        isMounted && setUsers(response.data);
      } catch (err) {
        console.error(err);
        navigate("/login", { state: { from: location }, replace: true });
      }
    };

    // Check if useEffect has run the first time
    if (effectRun.current) {
      getUsers();
    }

    return () => {
      isMounted = false;
      controller.abort();
      effectRun.current = true; // update the value of effectRun to true
    };
  }, []);

  return (
    <article>
      <h2>Users List</h2>
      {users?.length ? (
        <ul>
          {users.map((user, i) => (
            <li key={i}>{user?.username}</li>
          ))}
        </ul>
      ) : (
        <p>No users to display</p>
      )}
    </article>
  );
};

export default Users;
```

component/Admin.js:

```js
import { Link } from "react-router-dom";
import Users from "./Users";

const Admin = () => {
  return (
    <section>
      <h1>Admins Page</h1>
      <br />
      <Users />
      <br />
      <div className="flexGrow">
        <Link to="/">Home</Link>
      </div>
    </section>
  );
};

export default Admin;
```

hooks/useRefreshToken.js:

```js
import axios from "../api/axios";
import useAuth from "./useAuth";

const useRefreshToken = () => {
  const { setAuth } = useAuth();

  const refresh = async () => {
    const response = await axios.get("/refresh", {
      withCredentials: true,
    });
    setAuth((prev) => {
      console.log(JSON.stringify(prev));
      console.log(response.data.accessToken);
      return { ...prev, accessToken: response.data.accessToken };
    });
    return response.data.accessToken;
  };
  return refresh;
};

export default useRefreshToken;
```

api/axios.js:

```js
import axios from "axios";
const BASE_URL = "http://localhost:3500";

export default axios.create({
  baseURL: BASE_URL,
});

export const axiosPrivate = axios.create({
  baseURL: BASE_URL,
  headers: { "Content-Type": "application/json" },
  withCredentials: true,
});
```

hooks/useAxiosPrivate.js:

```js
import { axiosPrivate } from "../api/axios";
import { useEffect } from "react";
import useRefreshToken from "./useRefreshToken";
import useAuth from "./useAuth";

const useAxiosPrivate = () => {
  const refresh = useRefreshToken();
  const { auth } = useAuth();

  useEffect(() => {
    const requestIntercept = axiosPrivate.interceptors.request.use(
      (config) => {
        if (!config.headers["Authorization"]) {
          config.headers["Authorization"] = `Bearer ${auth?.accessToken}`;
        }
        return config;
      },
      (error) => Promise.reject(error)
    );

    const responseIntercept = axiosPrivate.interceptors.response.use(
      (response) => response,
      async (error) => {
        const prevRequest = error?.config;
        if (error?.response?.status === 403 && !prevRequest?.sent) {
          prevRequest.sent = true;
          const newAccessToken = await refresh();
          prevRequest.headers["Authorization"] = `Bearer ${newAccessToken}`;
          return axiosPrivate(prevRequest);
        }
        return Promise.reject(error);
      }
    );

    return () => {
      axiosPrivate.interceptors.request.eject(requestIntercept);
      axiosPrivate.interceptors.response.eject(responseIntercept);
    };
  }, [auth, refresh]);

  return axiosPrivate;
};

export default useAxiosPrivate;
```

hooks/useAuth.js:

```js
import { useContext, useDebugValue } from "react";
import AuthContext from "../context/AuthProvider";

const useAuth = () => {
  const { auth } = useContext(AuthContext);
  useDebugValue(auth, (auth) => (auth?.user ? "Logged In" : "Logged Out"));
  return useContext(AuthContext);
};

export default useAuth;
```

# #End  </details>

<details>
  <summary>201. React Form - Persistent User Login Authentication with JWT Tokens</summary>

components/PersistLogin.js:

```js
import { Outlet } from "react-router-dom";
import { useState, useEffect } from "react";
import useRefreshToken from "../hooks/useRefreshToken";
import useAuth from "../hooks/useAuth";

const PersistLogin = () => {
  const [isLoading, setIsLoading] = useState(true);
  const refresh = useRefreshToken();
  const { auth, persist } = useAuth();

  useEffect(() => {
    let isMounted = true;

    const verifyRefreshToken = async () => {
      try {
        await refresh();
      } catch (err) {
        console.error(err);
      } finally {
        isMounted && setIsLoading(false);
      }
    };

    // Avoids unwanted call to verifyRefreshToken
    !auth?.accessToken && persist ? verifyRefreshToken() : setIsLoading(false);

    return () => (isMounted = false);
  }, []);

  useEffect(() => {
    console.log(`isLoading: ${isLoading}`);
    console.log(`aT: ${JSON.stringify(auth?.accessToken)}`);
  }, [isLoading, auth]);

  return (
    <>{!persist ? <Outlet /> : isLoading ? <p>Loading...</p> : <Outlet />}</>
  );
};

export default PersistLogin;
```

hooks/useRefreshToken.js:

```js
import axios from "../api/axios";
import useAuth from "./useAuth";

const useRefreshToken = () => {
  const { setAuth } = useAuth();

  const refresh = async () => {
    const response = await axios.get("/refresh", {
      withCredentials: true,
    });
    setAuth((prev) => {
      console.log(JSON.stringify(prev));
      console.log(response.data.accessToken);
      return {
        ...prev,
        roles: response.data.roles,
        accessToken: response.data.accessToken,
      };
    });
    return response.data.accessToken;
  };
  return refresh;
};

export default useRefreshToken;
```

App.js:

```js
import Register from "./components/Register";
import Login from "./components/Login";
import Home from "./components/Home";
import Layout from "./components/Layout";
import Editor from "./components/Editor";
import Admin from "./components/Admin";
import Missing from "./components/Missing";
import Unauthorized from "./components/Unauthorized";
import Lounge from "./components/Lounge";
import LinkPage from "./components/LinkPage";
import RequireAuth from "./components/RequireAuth";
import PersistLogin from "./components/PersistLogin";
import { Routes, Route } from "react-router-dom";

const ROLES = {
  User: 2001,
  Editor: 1984,
  Admin: 5150,
};

function App() {
  return (
    <Routes>
      <Route path="/" element={<Layout />}>
        {/* public routes */}
        <Route path="login" element={<Login />} />
        <Route path="register" element={<Register />} />
        <Route path="linkpage" element={<LinkPage />} />
        <Route path="unauthorized" element={<Unauthorized />} />

        {/* we want to protect these routes */}
        <Route element={<PersistLogin />}>
          <Route element={<RequireAuth allowedRoles={[ROLES.User]} />}>
            <Route path="/" element={<Home />} />
          </Route>

          <Route element={<RequireAuth allowedRoles={[ROLES.Editor]} />}>
            <Route path="editor" element={<Editor />} />
          </Route>

          <Route element={<RequireAuth allowedRoles={[ROLES.Admin]} />}>
            <Route path="admin" element={<Admin />} />
          </Route>

          <Route
            element={<RequireAuth allowedRoles={[ROLES.Editor, ROLES.Admin]} />}
          >
            <Route path="lounge" element={<Lounge />} />
          </Route>
        </Route>

        {/* catch all */}
        <Route path="*" element={<Missing />} />
      </Route>
    </Routes>
  );
}

export default App;
```

# #End  </details>

<details>
  <summary>202. sample</summary>

```bs

```

```js

```

```js

```

```js

```

```js

```

# #End  </details>

