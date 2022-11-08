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
  <summary>15. UseEffect Dependency</summary>

Home.js:

```Javascript
import { useEffect, useState } from "react";
import BlogList from "./BlogList";

const Home = () => {
    const [blogs, setBlogs] = useState([
        { title: "My new website", body: "lorem ipsum...", author: "mario", id: 1 },
        { title: "Welcome party!", body: "lorem ipsum...", author: "yoshi", id: 2 },
        { title: "Web dev top tips", body: "lorem ipsum...", author: "mario", id: 3},
    ]);

    const [name, setName] = useState('mario');

    const handleDelete = (id) => {
        const newBlogs = blogs.filter((blog) => blog.id !== id);
        setBlogs(newBlogs);
    };

    useEffect(() => {
        console.log("use effect ran");
        console.log(name);
    },[name]);

    return (
        <div className="home">
            <BlogList blogs={blogs} title="All Blogs!" handleDelete={handleDelete} />
            <button onClick={() => setName('luigi')}>change name</button>
            <p>{ name }</p>
        </div>
    );
};

export default Home;
```

</details>

<details>
  <summary>16. JSON Server - Setup Files</summary>

index.html:

```html
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="styles.css">
  <title>JSON Server</title>
</head>
<body>

  <nav>
    <h1>All Blogs</h1>
    <a href="/create.html">Add a new blog</a>
  </nav>

  <div class="blogs">
    <!-- inject blogs here from js -->
  </div>

  <script src="js/index.js"></script>
</body>
</html>
```

create.html:

```html
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="styles.css">
  <title>JSON Server</title>
</head>
<body>

  <h1>Create a New Blog</h1>

  <form>
    <input type="text" name="title" required placeholder="Blog title">
    <textarea name="body" required placeholder="Blog body"></textarea>
    <button>Create</button>
  </form>

  <script src="js/create.js"></script>
</body>
</html>
```

details.html:

```html
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="styles.css">
  <title>JSON Server</title>
</head>
<body>

  <div class="details">
    <!-- inject blog details here -->
  </div>

  <script src="js/details.js"></script>
</body>
</html>
```

styles.css:

```css
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&display=swap');

/* base styles */
body {
  background: #eee;
  font-family: 'Roboto';
  color: #444;
  max-width: 960px;
  margin: 100px auto;
  padding: 10px;
}
nav {
  display: flex;
  justify-content: space-between;
}
nav h1 {
  margin: 0;
}
nav a {
  color: white;
  text-decoration: none;
  background: #36cca2;
  padding: 10px;
  border-radius: 10px;
}
form {
  max-width: 500px;
}
input, textarea {
  display: block;
  margin: 16px 0;
  padding: 6px 10px;
  width: 100%;
  border: 1px solid #ddd;
  font-family: 'Roboto';
}
textarea {
  min-height:200px;
}
```

js/index.js

```Javascript
// javascript for index.html
```

js/create.js:

```Javascript
// javascript for create.html
```

js/details.js:

```Javascript
// javascript for details.html
```

</details>

<details>
  <summary>17. JSON Server - Install Server</summary>

```bash
# Install JSON Server Globally
npm install -g json-server

# #Install JSON Server Locally
npm install json-server

# Check JSON Server version
json-server --version

# Run JSON server
json-server --watch db.json
json-server --watch db.json --port 3004
```

</details>

<details>
  <summary>18. JSON Server - Create a Database</summary>

data/db.json:

```Json
{
  "posts": [
    {
      "id": 1,
      "likes": 30,
      "title": "Welcome to the new blog",
      "body": "Lorem ninja ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat."
    },
    {
      "id": 2,
      "likes": 15,
      "title": "How to be a Net Ninja",
      "body": "Lorem ninja ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat."
    },
    {
      "title": "New Vue course coming soon!",
      "body": "Lorem ninja ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat.",
      "likes": 20,
      "id": 3
    },
    {
      "title": "Mario Kart Live review",
      "body": "Lorem ninja ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat.",
      "likes": 69,
      "id": 4
    }
  ],
  "polls": [
    {
      "id": 1,
      "question": "Do you prefer Vue or React?",
      "answerA": "Vue",
      "answerB": "React"
    }
  ]
}

```

</details>

<details>
  <summary>19. JSON Server - Run Server/Watch Database</summary>

```bash
# Run JSON server
json-server --watch data/db.json
json-server --watch data/db.json --port 3004
```

```javascript
// \{^_^}/ hi!

//   Loading data/db.json
//   Done

//   Resources
//   http://localhost:3000/posts
//   http://localhost:3000/polls

//   Home
//   http://localhost:3000

//   Type s + enter at any time to create a snapshot of the database
//   Watching...
```

</details>

<details>
  <summary>20. JSON Server - Fetch All Data</summary>

Index.html:

```html
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="styles.css">
  <title>JSON Server</title>
</head>
<body>

  <nav>
    <h1>All Blogs</h1>
    <a href="/create.html">Add a new blog</a>
  </nav>

  <div class="blogs">
    <!-- inject blogs here from js -->
  </div>

  <script src="js/index.js"></script>
</body>
</html>
```

js/index.js:

```javascript
// javascript for index.html
const container = document.querySelector('.blogs');
const pathname = window.location.pathname;
const filename = pathname.slice(pathname.lastIndexOf('/') + 1);
const dirname = pathname.slice(0, pathname.lastIndexOf('/'));

const renderPosts = async () => {
  let uri = 'http://localhost:3000/posts';

  const res = await fetch(uri);
  const posts = await res.json();

  let template = '';
  posts.forEach(post => {
    template += `
      <div class="post">
        <h2>${post.title}</h2>
        <p><small>${post.likes} likes</small></p>
        <p>${post.body.slice(0, 200)}...</p>
        <a href="${dirname}/details.html?id=${post.id}">Read more</a>
      </div>
    `
  });

  container.innerHTML = template;
}

window.addEventListener('DOMContentLoaded', () => renderPosts());
```

styles.css:

```css
/* post list */
.post {
  padding: 16px;
  background: white;
  border-radius: 10px;
  margin: 20px 0;
}
.post h2 {
  margin: 0;
}
.post p {
  margin-top: 0;
}
.post a {
  color: #36cca2;
}

```

</details>

<details>
  <summary>21. JSON Server - Fetch Single Post </summary>

details.html:

```html
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="styles.css">
  <title>JSON Server</title>
</head>
<body>

  <div class="details">
    <!-- inject blog details here -->
  </div>

  <script src="js/details.js"></script>
</body>
</html>
```

js/details.js:

```javascript
// javascript for details.html
const id = new URLSearchParams(window.location.search).get('id');
const container = document.querySelector('.details');
const pathname = window.location.pathname;
const filename = pathname.slice(pathname.lastIndexOf('/') + 1);
const dirname = pathname.slice(0, pathname.lastIndexOf('/'));

const renderDetails = async () => {
  const res = await fetch('http://localhost:3000/posts/' + id);
  if (!res.ok) {
    window.location.replace(`${dirname}/index.html`);
  }
  const post = await res.json();

  const template = `
    <h1>${post.title}</h1>
    <p>${post.body}</p>
  `

  container.innerHTML = template;
}

window.addEventListener('DOMContentLoaded', renderDetails);

```

</details>

<details>
  <summary>22. JSON Server - Window location</summary>

```javascript
// window.location.href returns the href (URL) of the current page
// window.location.hostname returns the domain name of the web host
// window.location.pathname returns the path and filename of the current page
// window.location.protocol returns the web protocol used (http: or https:)
// window.location.assign() loads a new document
```

```Javascript
const pathname = window.location.pathname;
const filename = pathname.slice(pathname.lastIndexOf('/') + 1);
const dirname = pathname.slice(0, pathname.lastIndexOf('/'));
```

</details>

<details>
  <summary>23. JSON Server - Sorting Posts</summary>

```Javascript
let uri = 'http://localhost:3000/posts?_sort=likes&_order=desc';
```

Index.js:

```Javascript
// javascript for index.html
const container = document.querySelector('.blogs');
const pathname = window.location.pathname;
const filename = pathname.slice(pathname.lastIndexOf('/') + 1);
const dirname = pathname.slice(0, pathname.lastIndexOf('/'));

const renderPosts = async () => {
  let uri = 'http://localhost:3000/posts?_sort=likes&_order=desc';

  const res = await fetch(uri);
  const posts = await res.json();

  let template = '';
  posts.forEach(post => {
    template += `
      <div class="post">
        <h2>${post.title}</h2>
        <p><small>${post.likes} likes</small></p>
        <p>${post.body.slice(0, 200)}...</p>
        <a href="${dirname}/details.html?id=${post.id}">Read more</a>
      </div>
    `
  });

  container.innerHTML = template;
}

window.addEventListener('DOMContentLoaded', () => renderPosts());
```

</details>

<details>
  <summary>24. JSON Server - Add Posts to JSON DB</summary>

create.html:

```html
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="styles.css">
  <title>JSON Server</title>
</head>
<body>

  <h1>Create a New Blog</h1>

  <form>
    <input type="text" name="title" required placeholder="Blog title">
    <textarea name="body" required placeholder="Blog body"></textarea>
    <button>Create</button>
  </form>

  <script src="js/create.js"></script>
</body>
</html>
```

create.js:

```javascript
// javascript for create.html

const form = document.querySelector('form');

const pathname = window.location.pathname;
const filename = pathname.slice(pathname.lastIndexOf('/') + 1);
const dirname = pathname.slice(0, pathname.lastIndexOf('/'));

const createPost = async (e) => {
  e.preventDefault();

  const doc = {
    title: form.title.value,
    body: form.body.value,
    likes: 0,
  }

  await fetch('http://localhost:3000/posts', {
    method: 'POST',
    body: JSON.stringify(doc),
    headers: { 'Content-Type': 'application/json' }
  })

  window.location.replace(`${dirname}/index.html`);
}

form.addEventListener('submit', createPost);

```

</details>

<details>
  <summary>25. JSON Server - Delete Post from DB</summary>

details.html:

```html
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="styles.css">
  <title>JSON Server</title>
</head>
<body>

  <div class="details">
    <!-- inject blog details here -->
  </div>
  <button class="delete">delete</button>

  <script src="js/details.js"></script>
</body>
</html>
```

details.js:

```javascript
// javascript for details.html
const id = new URLSearchParams(window.location.search).get('id');
const container = document.querySelector('.details');
const deleteBtn = document.querySelector('.delete');

const pathname = window.location.pathname;
const filename = pathname.slice(pathname.lastIndexOf('/') + 1);
const dirname = pathname.slice(0, pathname.lastIndexOf('/'));

const renderDetails = async () => {
  const res = await fetch('http://localhost:3000/posts/' + id);
  if (!res.ok) {
    window.location.replace(`${dirname}/index.html`);
  }
  const post = await res.json();

  const template = `
    <h1>${post.title}</h1>
    <p>${post.body}</p>
  `

  container.innerHTML = template;
}

deleteBtn.addEventListener('click', async () => {
  const res = await fetch('http://localhost:3000/posts/' + id, {
    method: 'DELETE'
  });
  window.location.replace(`${dirname}/index.html`);
})

window.addEventListener('DOMContentLoaded', renderDetails);

```

</details>

<details>
  <summary>26. JSON Server - Search for Posts Keywords</summary>

index.html:

```html
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="styles.css">
  <title>JSON Server</title>
</head>
<body>

  <nav>
    <h1>All Blogs</h1>
    <a href="/Cloud/Json-Server/create.html">Add a new blog</a>
  </nav>

  <form class="search">
    <input type="text" placeholder="search term" name="term">
  </form>

  <div class="blogs">
    <!-- inject blogs here from js -->
  </div>

  <script src="js/index.js"></script>
</body>
</html>

```

js/index.js:

```Javascript
// javascript for index.html
const container = document.querySelector('.blogs');
const searchForm = document.querySelector('.search');

const pathname = window.location.pathname;
const filename = pathname.slice(pathname.lastIndexOf('/') + 1);
const dirname = pathname.slice(0, pathname.lastIndexOf('/'));

const renderPosts = async (term) => {
  let uri = 'http://localhost:3000/posts?_sort=likes&_order=desc';
  if (term) {
    uri += `&q=${term}`
  }

  const res = await fetch(uri);
  const posts = await res.json();

  let template = '';
  posts.forEach(post => {
    template += `
      <div class="post">
        <h2>${post.title}</h2>
        <p><small>${post.likes} likes</small></p>
        <p>${post.body.slice(0, 200)}...</p>
        <a href="${dirname}/details.html?id=${post.id}">Read more</a>
      </div>
    `
  });

  container.innerHTML = template;
}

// search
searchForm.addEventListener('submit', async (e) => {
  e.preventDefault();
  renderPosts(searchForm.term.value.trim());
})

window.addEventListener('DOMContentLoaded', () => renderPosts());
```

</details>

<details>
  <summary>27. Using JSON Server for REST API</summary>

data/db.json:

```json
{
  "blogs": [
    {
      "title": "My First Blog",
      "body": "Why do we use it?\nIt is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English.",
      "author": "mario",
      "id": 1
    },
    {
      "title": "Opening Party!",
      "body": "Why do we use it?\nIt is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English.",
      "author": "yoshi",
      "id": 2
    }
  ]
}

```

Run JSON Server:

```bash
json-server --watch data/db.json --port 8000
```

API Endpoints:

```bash
/blogs        GET     Fetch all blogs
/blogs/{id}   GET     Fetch a single blog
/blogs        POST    Add a new blog
/blogs/{id}   DELETE  Delete a blog
```

</details>

<details>
  <summary>28. Fetch All Blogs with UseEffect</summary>

Home.js:

```javascript
import { useEffect, useState } from "react";
import BlogList from "./BlogList";

const Home = () => {
    const [blogs, setBlogs] = useState(null)

    useEffect(() => {
        fetch('http://localhost:8000/blogs')
        .then(res => {
            return res.json();
        })
        .then(data => {
            setBlogs(data);
        })
    }, [])

    return (
        <div className="home">
        {blogs && <BlogList blogs={blogs} title="All Blogs!" />}
        </div>
    );
}

export default Home;

```

BlogList.js:

```javascript
import React from 'react';

const BlogList = ({blogs, title}) => {

    return (
        <div className="blog-list">
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
  <summary>29. sample</summary>



```Javascript

```

```Javascript

```

```Javascript

```

</details>

<details>
  <summary>30. sample</summary>



```Javascript

```

```Javascript

```

```Javascript

```

</details>

