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
  <summary>6. App Component</summary>

App.js:

```Javascript
import './App.css';

function App() {
  const title = 'Welcome to the new blog';
  const likes = 50;
  const person = { name: 'yoshi' , age: 30 };
  const link = 'http://www.google.com';

  return (
    <div className="App">
      <header className="App-header">
        <h1>App Component</h1>
        <h2>{ title}</h2>
        <p>Liked { likes } times</p>
        <p>{ person.name }</p>
        <p>{ 10 }</p>
        <p>{ "hello, ninjas" }</p>
        <p>{ [1,2,3,4,5] }</p>
        <p>{Math.random() * 10 }</p>

        <a href={link}>Google Site</a>
      </header>
    </div>
  );
}

export default App;
```

</details>

<details>
  <summary>7. Importing Multiple Components</summary>

App.js:

```Javascript
import './App.css';
import Navbar from './components/Navbar';
import Home from './components/Home';

function App() {

  return (
    <div className="App">
      <Navbar />
      <header className="content">
        <Home />
      </header>
    </div>
  );
}

export default App;
```

Navbar.js:

```Javascript
const Navbar = () => {
    return (
        <nav className="navbar">
            <h1>The Dojo Blog</h1>
            <div className="links">
                <a href="/">Home</a>
                <a href="/create" style={{
                    color: "white",
                    backgroundColor: "#f1356d",
                    borderRadius: "8px",
                    padding: "5px",
                    textDecoration: "none"
                }}>New Blog</a>
            </div>
        </nav>
    );
}

export default Navbar;
```

Home.js:

```Javascript
const Home = ()=> {
    return (
        <div className="home">
            <h2>This is the Homepage</h2>
        </div>
    );
}

export default Home;
```

</details>

<details>
  <summary>8. Global Styling from Index</summary>

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
import Navbar from './components/Navbar';
import Home from './components/Home';

function App() {

  return (
    <div className="App">
      <Navbar />
      <header className="content">
        <Home />
      </header>
    </div>
  );
}

export default App;
```

Index.css:

```CSS
@import url('https://fonts.googleapis.com/css2?family=Quicksand:wght@300;400;500;600;700&display=swap');

/* base styles */
* {
  margin: 0;
  font-family: "Quicksand";
  color: #333;
}
.navbar {
  padding: 20px;
  display: flex;
  align-items: center;
  max-width: 600px;
  margin: 0 auto;
  border-bottom: 1px solid #f2f2f2;
}
.navbar h1 {
  color: #f1356d;
}
.navbar .links {
  margin-left: auto;
}
.navbar a {
  margin-left: 16px;
  text-decoration: none;
  padding: 6px;
}
.navbar a:hover {
  color: #f1356d;
}
.content {
  max-width: 600px;
  margin: 40px auto;
  padding: 20px;
}

```

</details>

<details>
  <summary>9. Click Events</summary>

Home.js:

```Javascript
const Home = ()=> {

    const handleClick = (e) => {
        console.log('hello, ninjas', e.target);
    }

    return (
        <div className="home">
            <h2>This is the Homepage</h2>
            <button onClick={handleClick}>Click me</button>
        </div>
    );
}

export default Home;
```

```Javascript
// hello, ninjas <button>Click me Again</button>
```

```Javascript
const Home = ()=> {

    const handleClick = (e) => {
        console.log('hello, ninjas', e.target);
    }

    const handleClickAgain = (e, name) => {
        console.log('hello ' + name);
        console.log(e.target);
    }

    return (
        <div className="home">
            <h2>This is the Homepage</h2>
            <button onClick={handleClick}>Click me</button>
            <button onClick={(e)=>handleClickAgain(e, 'Ben')}>Click me Again</button>
        </div>
    );
}

export default Home;
```

```Javascript
// hello Ben
// <button>Click me Again</button>
```

</details>

<details>
  <summary>10. Using State</summary>

Home.js:

```Javascript
import {useState} from 'react';

const Home = () => {

    const [name, setName] = useState('Andrew');

    const handleClick = (e) => {
        setName(e.target.value);
    }

    return (
        <div className="home">
            <h2>This is the Homepage</h2>
            <p>{name}</p>
            <button value='Mike' onClick={handleClick}>Click me</button>
        </div>
    );
}

export default Home;
```

```Javascript
import {useState} from 'react';

const Home = () => {

    const [name, setName] = useState('Andrew');
    const [age, setAge] = useState(25);

    const handleClick = (e) => {
        setName('Mike');
        setAge(30);
    }

    return (
        <div className="home">
            <h2>This is the Homepage</h2>
            <p>{ name } is { age } years old</p>
            <button onClick={handleClick}>Click me</button>
        </div>
    );
}

export default Home;
```

</details>

<details>
  <summary>11. Outputting Lists</summary>

Home.js:

```Javascript
import {useState} from 'react';

const Home = () => {

    const [blogs, setBlogs] = useState([
        {title: 'My new website', body: 'lorem ipsum...', author: 'mario', id: 1},
        {title: 'Welcome party!', body: 'lorem ipsum...', author: 'yoshi', id: 2},
        {title: 'Web dev top tips', body: 'lorem ipsum...', author: 'mario', id: 3}
    ]);

    return (
        <div className="home">
            {blogs.map((blog) => (
                <div className="blog-preview" key={blog.id}>
                    <h2>{ blog.title }</h2>
                    <p>Written by { blog.author }</p>
                </div>
            ))}
        </div>
    );
}

export default Home;
```

Index.css:

```css

/* blog previews / list */
.blog-preview {
  padding: 10px 16px;
  margin: 20px 0;
  border-bottom: 1px solid #fafafa;
}
.blog-preview:hover {
  box-shadow: 1px 3px 5px rgba(0,0,0,0.1);
}
.blog-preview h2 {
  font-size: 20px;
  color: #f1356d;
  margin-bottom: 8px;
}
```

</details>

<details>
  <summary>12. Reusable Components and Props</summary>

Home.js:

```Javascript
import {useState} from 'react';
import BlogList from './BlogList';

const Home = () => {

    const [blogs, setBlogs] = useState([
        {title: 'My new website', body: 'lorem ipsum...', author: 'mario', id: 1},
        {title: 'Welcome party!', body: 'lorem ipsum...', author: 'yoshi', id: 2},
        {title: 'Web dev top tips', body: 'lorem ipsum...', author: 'mario', id: 3}
    ]);

    return (
        <BlogList blogs={blogs} title="All Blogs!" />
    );
}

export default Home;
```

BlogList.js:

```Javascript
import React from 'react';

const BlogList = ({blogs, title}) => {
    // const blogs = props.blogs;
    // const title = props.title;

    return (
        <div className="home">
            <h2>{ title }</h2>
            {blogs.map((blog) => (
                <div className="blog-preview" key={blog.id}>
                    <h2>{ blog.title }</h2>
                    <p>Written by { blog.author }</p>
                </div>
            ))}
        </div>
     );
}

export default BlogList;
```

</details>

<details>
  <summary>13. Filtering Props</summary>

Home.js:

```Javascript
import {useState} from 'react';
import BlogList from './BlogList';

const Home = () => {

    const [blogs, setBlogs] = useState([
        {title: 'My new website', body: 'lorem ipsum...', author: 'mario', id: 1},
        {title: 'Welcome party!', body: 'lorem ipsum...', author: 'yoshi', id: 2},
        {title: 'Web dev top tips', body: 'lorem ipsum...', author: 'mario', id: 3}
    ]);

    return (
        <BlogList blogs={blogs.filter((blog) => blog.author === 'mario')} title="All Blogs!" />
    );
}

export default Home;
```

</details>

<details>
  <summary>14. Handle Delete Blog</summary>

Home.js:

```Javascript
import {useState} from 'react';
import BlogList from './BlogList';

const Home = () => {

    const [blogs, setBlogs] = useState([
        {title: 'My new website', body: 'lorem ipsum...', author: 'mario', id: 1},
        {title: 'Welcome party!', body: 'lorem ipsum...', author: 'yoshi', id: 2},
        {title: 'Web dev top tips', body: 'lorem ipsum...', author: 'mario', id: 3}
    ]);

    const handleDelete = (id)=> {
        const newBlogs = blogs.filter(blog => blog.id !== id);
        setBlogs(newBlogs);
    }

    return (
        <div className="home">
            <BlogList blogs={blogs} title="All Blogs!" handleDelete={handleDelete}/>
        </div>
    );
}

export default Home;
```

BlogList.js:

```Javascript
import React from 'react';

const BlogList = ({blogs, title, handleDelete}) => {

    return (
        <div className="blog-list">
            <h2>{ title }</h2>
            {blogs.map((blog) => (
                <div className="blog-preview" key={blog.id}>
                    <h2>{ blog.title }</h2>
                    <p>Written by { blog.author }</p>
                    <button onClick={()=>handleDelete(blog.id)}>Delete Blog</button>
                </div>
            ))}
        </div>
     );
}

export default BlogList;
```

</details>

<details>
  <summary>15. sample</summary>

```Javascript

```

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
  <summary>16. sample</summary>

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
  <summary>17. sample</summary>

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
  <summary>18. sample</summary>

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
  <summary>19. sample</summary>

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
  <summary>20. sample</summary>

```Javascript

```

```Javascript

```

```Javascript

```

```Javascript

```

</details>

