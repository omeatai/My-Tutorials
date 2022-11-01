# React-Tutorial-2
Learn React by Ifeanyi Omeata

## Tutorial

---

### [1-REACT CRASH COURSE - NET NINJA](#)

+INTRODUCTION

<details>
  <summary>1. Check Node Version</summary>

```bash
node -v
```

</details>

<details>
  <summary>2. Create React App</summary>

```bash
npx create-react-app dojo-blog
```

</details>

<details>
  <summary>3. Setup Files</summary>

Index.js:

```Javascript
import React from 'react';
import ReactDOM from 'react-dom/client';
import './index.css';
import App from './App';

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);

```

App.js:

```Javascript
import logo from './logo.svg';
import './App.css';

function App() {
  return (
    <div className="App">
      <header className="App-header">
        <img src={logo} className="App-logo" alt="logo" />
        <p>
          Edit <code>src/App.js</code> and save to reload.
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

Index.html:

```HTML
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <link rel="icon" href="%PUBLIC_URL%/favicon.ico" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <meta name="theme-color" content="#000000" />
    <meta
      name="description"
      content="Web site created using create-react-app"
    />
    <link rel="apple-touch-icon" href="%PUBLIC_URL%/logo192.png" />
    <!--
      manifest.json provides metadata used when your web app is installed on a
      user's mobile device or desktop. See https://developers.google.com/web/fundamentals/web-app-manifest/
    -->
    <link rel="manifest" href="%PUBLIC_URL%/manifest.json" />
    <!--
      Notice the use of %PUBLIC_URL% in the tags above.
      It will be replaced with the URL of the `public` folder during the build.
      Only files inside the `public` folder can be referenced from the HTML.

      Unlike "/favicon.ico" or "favicon.ico", "%PUBLIC_URL%/favicon.ico" will
      work correctly both with client-side routing and a non-root public URL.
      Learn how to configure a non-root public URL by running `npm run build`.
    -->
    <title>React App</title>
  </head>
  <body>
    <noscript>You need to enable JavaScript to run this app.</noscript>
    <div id="root"></div>
    <!--
      This HTML file is a template.
      If you open it directly in the browser, you will see an empty page.

      You can add webfonts, meta tags, or analytics to this file.
      The build step will place the bundled scripts into the <body> tag.

      To begin the development, run `npm start` or `yarn start`.
      To create a production bundle, use `npm run build` or `yarn build`.
    -->
  </body>
</html>

```

</details>

<details>
  <summary>4. Start Local Server</summary>

```bash
npm run start
```

```Javascript
// Compiled successfully!

// You can now view dojo-blog in the browser.

//   Local:            http://localhost:3000
//   On Your Network:  http://192.168.178.68:3000

// Note that the development build is not optimized.
// To create a production build, use npm run build.

// webpack compiled successfully

```

</details>

<details>
  <summary>5. Install all dependencies from Package.json</summary>

```bash
npm install
```

</details>

<details>
  <summary>6. sample</summary>

```Javascript

```

```Javascript

```

```Javascript

```

```Javascript

```

</details>

<details>
  <summary>7. sample</summary>

```Javascript

```

```Javascript

```

```Javascript

```

```Javascript

```

</details>

<details>
  <summary>8. sample</summary>

```Javascript

```

```Javascript

```

```Javascript

```

```Javascript

```

</details>

<details>
  <summary>9. sample</summary>

```Javascript

```

```Javascript

```

```Javascript

```

```Javascript

```

</details>

<details>
  <summary>10. sample</summary>

```Javascript

```

```Javascript

```

```Javascript

```

```Javascript

```

</details>

