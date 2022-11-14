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

+JSON-SERVER

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

+BUILDING REST API FOR BLOG

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
  <summary>29. Set Loading Delay Message</summary>

Home.js:

```javascript
import { useEffect, useState } from "react";
import BlogList from "./BlogList";

const Home = () => {
    const [blogs, setBlogs] = useState(null);
    const [isPending, setIsPending] = useState(true);

    useEffect(() => {
        setTimeout(() => {
        fetch('http://localhost:8000/blogs')
        .then(res => {
            return res.json();
        })
        .then(data => {
            setIsPending(false);
            setBlogs(data);
        })
        }, 1000);
    }, [])

    return (
        <div className="home">
        { isPending && <div>Loading...</div> }
        {blogs && <BlogList blogs={blogs} title="All Blogs!" />}
        </div>
    );
}

export default Home;
```

</details>

<details>
  <summary>30. Catching Fetch Errors</summary>

Home.js:

```javascript
import { useEffect, useState } from "react";
import BlogList from "./BlogList";

const Home = () => {
    const [blogs, setBlogs] = useState(null);
    const [isPending, setIsPending] = useState(true);
    const [error, setError] = useState(null);

    useEffect(() => {
        setTimeout(() => {
        fetch('http://localhost:8000/blogs')
        .then(res => {
            if (!res.ok) { // error coming back from server
            throw Error('could not fetch the data for that resource');
            }
            return res.json();
        })
        .then(data => {
            setIsPending(false);
            setBlogs(data);
            setError(null);
        })
        .catch(err => {
            // auto catches network / connection error
            setIsPending(false);
            setError(err.message);
            setBlogs(null);
        })
        }, 1000);
    }, [])

    return (
        <div className="home">
        { error && <div>{ error }</div> }
        { isPending && <div>Loading...</div> }
        {blogs && <BlogList blogs={blogs} title="All Blogs!" />}
        </div>
    );
}

export default Home;
```

</details>

<details>
  <summary>31. Creating Custom Hooks</summary>

Home.js:

```Javascript
import BlogList from "./BlogList";
import useFetch from "./useFetch";

const Home = () => {
    const { error, isPending, data: blogs } = useFetch('http://localhost:8000/blogs');

    return (
        <div className="home">
        { error && <div>{ error }</div> }
        { isPending && <div>Loading...</div> }
        {blogs && <BlogList blogs={blogs} title="All Blogs!" />}
        </div>
    );
}

export default Home;

```

useFetch.js:

```javascript
import { useState, useEffect } from 'react';

const useFetch = (url) => {
    const [data, setData] = useState(null);
    const [isPending, setIsPending] = useState(true);
    const [error, setError] = useState(null);

    useEffect(() => {
        setTimeout(() => {
        fetch(url)
        .then(res => {
            if (!res.ok) { // error coming back from server
            throw Error('could not fetch the data for that resource');
            }
            return res.json();
        })
        .then(data => {
            setIsPending(false);
            setData(data);
            setError(null);
        })
        .catch(err => {
            // auto catches network / connection error
            setIsPending(false);
            setError(err.message);
            setData(null);
        })
        }, 1000);
    }, [url])

    return { data, isPending, error };
}

export default useFetch;

```

</details>


<details>
  <summary>32. Using React Router for Routes</summary>

Install React Router:

```bash
npm install react-router-dom@5
```

Import BrowserRouter:

App.js:

```Javascript
import Navbar from './components/Navbar';
import Home from './components/Home';
import { BrowserRouter as Router, Route, Switch } from 'react-router-dom';

function App() {
  return (
    <Router>
      <div className="App">
        <Navbar />
        <div className="content">
          <Switch>
            <Route path="/">
              <Home />
            </Route>
          </Switch>
        </div>
      </div>
    </Router>
  );
}

export default App;
```

</details>


<details>
  <summary>33. Create Route for Create Page</summary>

App.js:

```Javascript
import Navbar from './components/Navbar';
import Home from './components/Home';
import { BrowserRouter as Router, Route, Switch } from 'react-router-dom';
import Create from './components/Create';

function App() {
  return (
    <Router>
      <div className="App">
        <Navbar />
        <div className="content">
          <Switch>
            <Route exact path="/">
              <Home />
            </Route>
            <Route path="/create">
              <Create />
            </Route>
          </Switch>
        </div>
      </div>
    </Router>
  );
}

export default App;
```

Create.js:

```Javascript
const Create = () => {
        return (
        <div className="create">
            <h2>Add a New Blog</h2>
        </div>
        );
    }

export default Create;
```

</details>


<details>
  <summary>34. Using Route Links</summary>

Navbar.js:

```Javascript
import { Link } from "react-router-dom";

const Navbar = () => {
    return (
        <nav className="navbar">
          <h1>The Dojo Blog</h1>
          <div className="links">
            <Link to="/">Home</Link>
            <Link to="/create" style={{
              color: 'white',
              backgroundColor: '#f1356d',
              borderRadius: '8px'
            }}>New Blog</Link>
          </div>
        </nav>
    );
}

export default Navbar;
```

</details>


<details>
  <summary>35. UseEffect Cleanup using Abort Controller</summary>

useEffect.js:

```Javascript
import { useState, useEffect } from 'react';

const useFetch = (url) => {
    const [data, setData] = useState(null);
    const [isPending, setIsPending] = useState(true);
    const [error, setError] = useState(null);

    useEffect(() => {
        const abortCont = new AbortController();

        setTimeout(() => {
            fetch(url, { signal: abortCont.signal })
                .then(res => {
                    if (!res.ok) { // error coming back from server
                        throw Error('could not fetch the data for that resource');
                    }
                    return res.json();
                })
                .then(data => {
                    setIsPending(false);
                    setData(data);
                    setError(null);
                })
                .catch(err => {
                    if (err.name === 'AbortError') {
                        console.log('fetch aborted')
                    } else {
                        // auto catches network / connection error
                        setIsPending(false);
                        setError(err.message);
                        setData(null);
                    }
                })
        }, 1000);

        // abort the fetch
        return () => abortCont.abort();
    }, [url])

    return { data, isPending, error };
}

export default useFetch;
```

Index.js:

```Javascript
import React from 'react';
import ReactDOM from 'react-dom/client';
import './index.css';
import App from './App';

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
  //<React.StrictMode>
    <App />
  //</React.StrictMode>
);

```

</details>


<details>
  <summary>36. Using Route Parameters for Blog Details Page</summary>

BlogDetails.js:

```Javascript
import { useParams } from "react-router-dom";

const BlogDetails = () => {
  const { id } = useParams();

  return (
    <div className="blog-details">
      <h2>Blog details - { id }</h2>
    </div>
  );
}

export default BlogDetails;

```

App.js:

```Javascript
import Navbar from './components/Navbar';
import Home from './components/Home';
import { BrowserRouter as Router, Route, Switch } from 'react-router-dom';
import Create from './components/Create';
import BlogDetails from './components/BlogDetails';

function App() {
  return (
    <Router>
      <div className="App">
        <Navbar />
        <div className="content">
          <Switch>
            <Route exact path="/">
              <Home />
            </Route>
            <Route path="/create">
              <Create />
            </Route>
            <Route path="/blogs/:id">
              <BlogDetails />
            </Route>
          </Switch>
        </div>
      </div>
    </Router>
  );
}

export default App;

```

BlogList.js:

```Javascript
import { Link } from 'react-router-dom';

const BlogList = ({ blogs }) => {
    return (
        <div className="blog-list">
        {blogs.map(blog => (
            <div className="blog-preview" key={blog.id} >
            <Link to={`/blogs/${blog.id}`}>
                <h2>{ blog.title }</h2>
                <p>Written by { blog.author }</p>
            </Link>
            </div>
        ))}
        </div>
    );
}

export default BlogList;
```

Index.css:

```CSS
.blog-preview a{
  text-decoration: none;
}
```

</details>


<details>
  <summary>37. Reusing Custom Hooks for BlogDetails Page</summary>

BlogDetails.js:

```Javascript
import { useParams } from "react-router-dom";
import useFetch from "./useFetch";

const BlogDetails = () => {
    const { id } = useParams();
    const { data: blog, error, isPending } = useFetch('http://localhost:8000/blogs/' + id);

    return (
        <div className="blog-details">
        { isPending && <div>Loading...</div> }
        { error && <div>{ error }</div> }
        { blog && (
            <article>
            <h2>{ blog.title }</h2>
            <p>Written by { blog.author }</p>
            <div>{ blog.body }</div>
            </article>
        )}
        </div>
    );
}

export default BlogDetails;
```

index.css:

```CSS
/* blog details page */
.blog-details h2 {
  font-size: 20px;
  color: #f1356d;
  margin-bottom: 10px;
}
.blog-details div {
  margin: 20px 0;
}

.blog-details button {
  background: #f1356d;
  color: #fff;
  border: 0;
  padding: 8px;
  border-radius: 8px;
  cursor: pointer;
}

```

</details>


<details>
  <summary>38. Using Controlled Form Inputs for Create Page</summary>

Create.js:

```Javascript
import { useState } from "react";

const Create = () => {
    const [title, setTitle] = useState('');
    const [body, setBody] = useState('');
    const [author, setAuthor] = useState('mario');

    return (
            <div className="create">
              <h2>Add a New Blog</h2>
              <form>
                  <label>Blog title:</label>
                  <input
                  type="text"
                  required
                  value={title}
                  onChange={(e) => setTitle(e.target.value)}
                  />
                  <label>Blog body:</label>
                  <textarea
                  required
                  value={body}
                  onChange={(e) => setBody(e.target.value)}
                  ></textarea>
                  <label>Blog author:</label>
                  <select
                  value={author}
                  onChange={(e) => setAuthor(e.target.value)}
                  >
                  <option value="mario">mario</option>
                  <option value="yoshi">yoshi</option>
                  </select>
                  <button>Add Blog</button>
              </form>
            </div>
    );
}

export default Create;
```

index.css:

```css
/* create new blog form */
.create {
  max-width: 400px;
  margin: 0 auto;
  text-align: center;
}
.create label {
  text-align: left;
  display: block;
}
.create h2 {
  font-size: 20px;
  color: #f1356d;
  margin-bottom: 30px;
}
.create input, .create textarea, .create select {
  width: 100%;
  padding: 6px 10px;
  margin: 10px 0;
  border: 1px solid #ddd;
  box-sizing: border-box;
  display: block;
}
.create button {
  background: #f1356d;
  color: #fff;
  border: 0;
  padding: 8px;
  border-radius: 8px;
  cursor: pointer;
}
```

</details>


<details>
  <summary>39. Submitting Form Events</summary>

Create.js:

```Javascript
import { useState } from "react";

const Create = () => {
  const [title, setTitle] = useState('');
  const [body, setBody] = useState('');
  const [author, setAuthor] = useState('mario');

  const handleSubmit = (e) => {
    e.preventDefault();
    const blog = { title, body, author };

    console.log(blog);
  }

  return (
    <div className="create">
      <h2>Add a New Blog</h2>
      <form onSubmit={handleSubmit}>
        <label>Blog title:</label>
        <input
          type="text"
          required
          value={title}
          onChange={(e) => setTitle(e.target.value)}
        />
        <label>Blog body:</label>
        <textarea
          required
          value={body}
          onChange={(e) => setBody(e.target.value)}
        ></textarea>
        <label>Blog author:</label>
        <select
          value={author}
          onChange={(e) => setAuthor(e.target.value)}
        >
          <option value="mario">mario</option>
          <option value="yoshi">yoshi</option>
        </select>
        <button>Add Blog</button>
      </form>
    </div>
  );
}

export default Create;
```

</details>


<details>
  <summary>40. Creating Post Request for Create Page</summary>

Create.js:

```Javascript
import { useState } from "react";

const Create = () => {
    const [title, setTitle] = useState('');
    const [body, setBody] = useState('');
    const [author, setAuthor] = useState('mario');
    const [isPending, setIsPending] = useState(false);

    const handleSubmit = (e) => {
        e.preventDefault();
        const blog = { title, body, author };

        setIsPending(true);

        fetch('http://localhost:8000/blogs/', {
        method: 'POST',
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify(blog)
        }).then(() => {
        console.log('new blog added');
        setIsPending(false);
        })
    }

    return (
        <div className="create">
        <h2>Add a New Blog</h2>
        <form onSubmit={handleSubmit}>
            <label>Blog title:</label>
            <input
            type="text"
            required
            value={title}
            onChange={(e) => setTitle(e.target.value)}
            />
            <label>Blog body:</label>
            <textarea
            required
            value={body}
            onChange={(e) => setBody(e.target.value)}
            ></textarea>
            <label>Blog author:</label>
            <select
            value={author}
            onChange={(e) => setAuthor(e.target.value)}
            >
            <option value="mario">mario</option>
            <option value="yoshi">yoshi</option>
            </select>
            {!isPending ? <button>Add Blog</button> : <button disabled>Adding Blog...</button>}
        </form>
        </div>
    );
}

export default Create;
```

</details>

<details>
  <summary>41. Redirecting with useHistory()</summary>

Create.js:

```Javascript
import { useState } from "react";
import { useHistory } from "react-router-dom";

const Create = () => {
    const [title, setTitle] = useState('');
    const [body, setBody] = useState('');
    const [author, setAuthor] = useState('mario');
    const history = useHistory();

    const handleSubmit = (e) => {
        e.preventDefault();
        const blog = { title, body, author };

        fetch('http://localhost:8000/blogs/', {
        method: 'POST',
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify(blog)
        }).then(() => {
        // history.go(-1);
        history.push('/');
        })
    }

    return (
        <div className="create">
        <h2>Add a New Blog</h2>
        <form onSubmit={handleSubmit}>
            <label>Blog title:</label>
            <input
            type="text"
            required
            value={title}
            onChange={(e) => setTitle(e.target.value)}
            />
            <label>Blog body:</label>
            <textarea
            required
            value={body}
            onChange={(e) => setBody(e.target.value)}
            ></textarea>
            <label>Blog author:</label>
            <select
            value={author}
            onChange={(e) => setAuthor(e.target.value)}
            >
            <option value="mario">mario</option>
            <option value="yoshi">yoshi</option>
            </select>
            <button>Add Blog</button>
        </form>
        </div>
    );
}

export default Create;
```

</details>

<details>
  <summary>42. Deleting Blogs</summary>

BlogDetails.js:

```Javascript
import { useHistory, useParams } from "react-router-dom";
import useFetch from "./useFetch";

const BlogDetails = () => {
    const { id } = useParams();
    const { data: blog, error, isPending } = useFetch('http://localhost:8000/blogs/' + id);
    const history = useHistory();

    const handleClick = () => {
        fetch('http://localhost:8000/blogs/' + blog.id, {
        method: 'DELETE'
        }).then(() => {
        history.push('/');
        })
    }

    return (
        <div className="blog-details">
        { isPending && <div>Loading...</div> }
        { error && <div>{ error }</div> }
        { blog && (
            <article>
            <h2>{ blog.title }</h2>
            <p>Written by { blog.author }</p>
            <div>{ blog.body }</div>
            <button onClick={handleClick}>delete</button>
            </article>
        )}
        </div>
    );
}

export default BlogDetails;
```

Index.css:

```css
.blog-details button {
  background: #f1356d;
  color: #fff;
  border: 0;
  padding: 8px;
  border-radius: 8px;
  cursor: pointer;
}
```

</details>

<details>
  <summary>43. Redirect to 404 Page</summary>

NotFound.js:

```Javascript
import { Link } from "react-router-dom"

const NotFound = () => {
    return (
        <div className="not-found">
        <h2>Sorry</h2>
        <p>That page cannot be found</p>
        <Link to="/">Back to the homepage...</Link>
        </div>
    );
}

export default NotFound;

```

App.js:

```Javascript
import Navbar from './components/Navbar';
import Home from './components/Home';
import { BrowserRouter as Router, Route, Switch } from 'react-router-dom';
import Create from './components/Create';
import BlogDetails from './components/BlogDetails';
import NotFound from './components/NotFound';

function App() {
  return (
    <Router>
      <div className="App">
        <Navbar />
        <div className="content">
          <Switch>
            <Route exact path="/">
              <Home />
            </Route>
            <Route path="/create">
              <Create />
            </Route>
            <Route path="/blogs/:id">
              <BlogDetails />
            </Route>
            <Route path="*">
              <NotFound />
            </Route>
          </Switch>
        </div>
      </div>
    </Router>
  );
}

export default App;
```

</details>


### [2-REACTJS COURSE - PEDROTECH](#)

+INTRODUCTION

<details>
  <summary>44. Initialize React App</summary>

NPM Version:

```bash
npm -v
```

Node Version:

```bash
node -v
```

Install React App:

```bash
npx create-react-app .
npx create-react-app reactjs-course

npx create-react-app reactjs-course --template typescript
npx create-react-app reactjs-course --template redux
npx create-react-app reactjs-course --template redux-typescript
```

Run React App:

```bash
npm start
```

</details>

<details>
  <summary>45. Setup Files</summary>

Index.js:

```Javascript
import React from 'react';
import ReactDOM from 'react-dom/client';
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
import './App.css';

function App() {
  return (
    <div className="App">
      <h1>Home</h1>
    </div>
  );
}

export default App;

```

</details>

<details>
  <summary>46. JSX and Components</summary>

App.js:

```Javascript
import './App.css';

function App() {
  return (
    <div className="App">
      <User />
      <User />
      <User />
    </div>
  );
};

const User = () => {
  return (
    <div>
      <h1>Pedro</h1>
      <h2>21</h2>
      <h2>pedro@pedro.com</h2>
    </div>
  );
};

export default App;

```

</details>

<details>
  <summary>47. Props</summary>

App.js:

```Javascript
import "./App.css";

function App() {
  return (
    <div className="App">
      <Job salary={90000} position="Senior SDE" company="Amazon" />
      <Job salary={12000} position="Junior SDE" company="Google" />
      <Job salary={10000} position="Project Manager" company="Netflix" />
    </div>
  );
}

const Job = (props) => {
  return (
    <div>
      <h1> {props.salary}</h1>
      <h1> {props.position}</h1>
      <h1> {props.company}</h1>
    </div>
  );
};

export default App;
```

</details>

<details>
  <summary>48. CSS Module Stylesheets</summary>

App.js:

```Javascript
import styles from "./App.module.css";

function App() {
  return (
    <div className={styles.App}>
    <h1 className={styles.name}> Pedro </h1>
    </div>
  );
}

export default App;
```

App.module.css:

```css
.App {
  text-align: center;
}

.name {
  color: red;
}

.App-logo {
  height: 40vmin;
  pointer-events: none;
}

@media (prefers-reduced-motion: no-preference) {
  .App-logo {
    animation: App-logo-spin infinite 20s linear;
  }
}

.App-header {
  background-color: #282c34;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  font-size: calc(10px + 2vmin);
  color: white;
}

.App-link {
  color: #61dafb;
}

@keyframes App-logo-spin {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

```

</details>

<details>
  <summary>49. Ternary Operator</summary>

```Javascript
const age = 15;

if(age >= 18) {
  console.log("IS OVER AGE");
  } else {
  console.log("IS UNDER AGE");
}

age >= 18 ? console.log("IS OVER AGE") : console.log("IS UNDER AGE");
```

App.js:

```Javascript
import "./App.css";

function App() {
  const age = 19;

  return (
    <div className="App">
      {age >= 18 ? <h1> OVER AGE</h1> : <h1> UNDER AGE</h1>}
    </div>
  );
}
export default App;
```

</details>

<details>
  <summary>50. Inline Styling</summary>

App.js:

```Javascript
import "./App.css";

function App() {
  const age = 19;

  return (
    <div className="App">
      {age >= 18 ? <h1> OVER AGE</h1> : <h1> UNDER AGE</h1>}
      <h1 style={{color: "red", backgroundColor: "black"}}> THIS HAS COLOR </h1>
    </div>
  );
}
export default App;
```

with Ternary Operator:

```Javascript
import "./App.css";

function App() {
  const age = 19;
  const isGreen = true;

  return (
    <div className="App">
      {age >= 18 ? <h1> OVER AGE</h1> : <h1> UNDER AGE</h1>}
      <h1 style={{color: isGreen ? "green" : "red", backgroundColor: "black"}}> THIS HAS COLOR </h1>
    </div>
  );
}

export default App;
```

</details>

<details>
  <summary>51. Conditional Rendering</summary>

```Javascript
import "./App.css";

function App() {
  const age = 19;
  const isActive = true;

  return (
    <div className="App">
      {age >= 18 ? <h1> OVER AGE</h1> : <h1> UNDER AGE</h1>}
      {isActive &&  <button>Continue Registration</button>}
    </div>
  );
}

export default App;
```

</details>

<details>
  <summary>52. Lists in React</summary>

App.js:

```Javascript
import "./App.css";

function App() {
  const planets = [
    { name: "Mars", isGasPlanet: false },
    { name: "Earth", isGasPlanet: false },
    { name: "Jupiter", isGasPlanet: true },
    { name: "Venus", isGasPlanet: false },
    { name: "Neptune", isGasPlanet: true },
    { name: "Uranus", isGasPlanet: true },
  ];

  return (
    <div className="App">
      <h2>Not Gas Planets:</h2>
      {planets.map(
        (planet, key, arr) => !planet.isGasPlanet && <h1 key={key}> {planet.name} </h1>
      )}
    </div>
  );
}

export default App;
```

</details>

<details>
  <summary>53. Importing Components</summary>

App.js:

```Javascript
import "./App.css";
import { User } from "./User";

function App() {
    const users = [
      { name: "Pedro", age: 21 },
      { name: "Jake", age: 25 },
      { name: "Jessica" , age: 45 },
    ];

    return (
      <div className="App">
        {users.map((user, key, arr) => {
          return <User name={user.name} age={user.age} />;
        })}
      </div>
    );
}

export default App;
```

User.js:

```Javascript
export const User = (props) => {
    return (
        <div>
            <h2>{props.name} - {props.age}</h2>
        </div>
    );
};

//export default User;
```

</details>

<details>
  <summary>54. **Digital Clock**</summary>

App.js:

```Javascript
import "./App.css";
import {useState} from 'react';

function App() {
    const [age, setAge] = useState(0);
    const [time, setTime] = useState('00:00:00 AM');

    setInterval(() => {
      const date = new Date();
      setTime(date.toLocaleTimeString("en-us"));
    }, 1000);

    return (
      <div className="App">
        <h1>Age: {age}</h1>
        <h1 style={{color: "grey"}}>Time: {time}</h1>
        <button onClick={() => setAge(age => age + 1)}>Increase</button>
        <button onClick={() => setAge(age => age - 1)}>Decrease</button>
      </div>
    );
}

export default App;
```


```Javascript
import "./App.css";
import { useState, useEffect} from 'react';

function App() {

    const [time, setTime] = useState('00:00:00 AM');
    const [isON, setIsON] = useState(true);

    useEffect(() => {
      if(isON) {
        const interval = setInterval(myTimer, 1000);
        return () => clearInterval(interval);
      }
    }, [isON])

    function myTimer() {
        const date = new Date();
        setTime(date.toLocaleTimeString('en-US'));
    }

    const handleStop = () => {
      console.log('Stopping...');
      setIsON(false);
    }

    const handleStart = () => {
      console.log('Starting...');
      setIsON(true);
    }

    const myStyle = {
      padding: '10px 20px',
      marginRight: '10px',
    }

    return (
      <div className="App">
        <h1>My Digital Clock</h1>
        <h2 style={{fontSize: "3rem", color: "gray"}}>{time}</h2>
        <button onClick={handleStart} style={myStyle }>Start</button>
        <button onClick={handleStop} style={myStyle }>Stop</button>
      </div>
    );
}

export default App;
```

</details>

<details>
  <summary>55. **Deploy React App to Github Pages**</summary>

Create a new repository on the command line:

```bash
echo "# my-project" >> README.md
git init
git add .
# git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/machadop1487/my-project.git
git push -u origin main
```

Push an existing repository from the command line:

```bash
git remote add origin https://github.com/machadop1487/my-project.git
git branch -M main
git push -u origin main
```

Use Access Token to connect to Github -
Generate a personal access token. This can be done in the application settings of your GitHub account.

```bash
git remote -v
git remote remove origin
git remote add origin https://<your-username>:<token>@github.com/<username>/<repo-name>.git
```

Install dependencies:

```bash
npm install gh-pages --save-dev

yarn add -D gh-pages
```

Set homepage in package.json:

```bash
"homepage": "http://<username>.github.io/<repo-name>/"
"homepage": "http://machadop1487.github.io/my-project/"
```

```json
{
  "homepage": "http://omeatai.github.io/Digital-Clock-Project/",
  "name": "digital-clock-project",
  "version": "0.1.0",
  "private": true,
}
```

Add Scripts to package.json:

```bash
"predeploy": "npm run build",
"deploy": "gh-pages -d build",
```

```json
{
  "homepage": "http://omeatai.github.io/Digital-Clock-Project/",
  "name": "digital-clock-project",
  "version": "0.1.0",
  "private": true,
  "dependencies": {
    "@testing-library/jest-dom": "^5.16.5",
    "@testing-library/react": "^13.4.0",
    "@testing-library/user-event": "^13.5.0",
    "react": "^18.2.0",
    "react-dom": "^18.2.0",
    "react-scripts": "5.0.1",
    "web-vitals": "^2.1.4"
  },
  "scripts": {
    "start": "react-scripts start",
    "predeploy": "npm run build",
    "deploy": "gh-pages -d build",
    "build": "react-scripts build",
    "test": "react-scripts test",
    "eject": "react-scripts eject"
  },
}
```

Make Commit:

```bash
git add .
git commit -m "Deploy to Github Pages"
git push -u origin main

# git push origin main
# git push
```

Deploy github pages branch:

```bash
npm run deploy
```

```bash
Settings -> Pages -> Source -> Branch (gh-pages) -> /(root) folder
```

```bash
Click on the publish link to see the app.
```

</details>

<details>
  <summary>56. Using State Hooks</summary>

App.js:

```Javascript
import "./App.css";
import { useState } from "react";

function App() {
  const [count, setCount] = useState(0);

  const increase = () => {
    setCount(count + 1);
  };
  const decrease = () => {
    setCount(count - 1);
  };
  const setToZero = () => {
    setCount(0);
  };

  return (
    <div className="App">
      <button onClick={increase}>Increase</button>
      <button onClick={decrease}>Decrease</button>
      <button onClick={setToZero}>Set to Zero</button>

      {count}
    </div>
  );
}

export default App;
```

</details>

<details>
  <summary>57. TodoList - Handle Delete</summary>

App.js:

```Javascript
import "./App.css";
import { useState } from "react";
import { Task } from "./Task";

function App() {
  const [todoList, setTodoList] = useState([]);
  const [newTask, setNewTask] = useState("");

  const handleChange = (event) => {
    setNewTask(event.target.value);
  };

  const addTask = () => {
    const task = {
      id: todoList.length === 0 ? 1 : todoList[todoList.length - 1].id + 1,
      taskName: newTask,
      completed: false,
    };
    setTodoList(task.taskName !== "" ? [...todoList, task] : todoList);
  };

  const deleteTask = (id) => {
    setTodoList(todoList.filter((task) => task.id !== id));
  };

  const completeTask = (id) => {
    setTodoList(
      todoList.map((task) => {
        if (task.id === id) {
          return { ...task, completed: true };
        } else {
          return task;
        }
      })
    );
  };

  return (
    <div className="App">
      <div className="addTask">
        <input onChange={handleChange} />
        <button onClick={addTask}> Add Task</button>
      </div>
      <div className="list">
        {todoList.map((task) => {
          return (
            <Task
              taskName={task.taskName}
              id={task.id}
              completed={task.completed}
              deleteTask={deleteTask}
              completeTask={completeTask}
            />
          );
        })}
      </div>
    </div>
  );
}

export default App;
```

Task.js:

```Javascript
export const Task = (props) => {
    return (
      <div
        className="task"
        style={{ backgroundColor: props.completed ? "green" : "white" }}
      >
        <h1>{props.taskName}</h1>
        <button onClick={() => props.completeTask(props.id)}> Complete </button>
        <button onClick={() => props.deleteTask(props.id)}> X </button>
      </div>
    );
  };
```

App.css:

```css
.App {
  display: flex;
  align-items: center;
  flex-direction: column;
  width: 100vw;
  font-family: Arial, Helvetica, sans-serif;
}

body {
  margin: 0;
  padding: 0;
}

.addTask {
  height: 30vh;
  background-color: dodgerblue;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.list {
  height: auto;
  width: 100%;
  display: flex;
  align-items: center;
  padding-top: 50px;
  flex-direction: column;
}

.task {
  width: 500px;
  height: 50px;
  display: flex;
  margin: 15px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.task button {
  width: auto;
  height: 20px;
  margin-left: 5px;
  text-align: center;
}
```

Sample code:

```Javascript
import "./App.css";
import { useState } from "react";

function App() {
  const [todoList, setTodoList] = useState([]);
  const [newTask, setNewTask] = useState("");

  const handleChange = (e) => {
    setNewTask(e.target.value);
  };

  const addTask = () => {
    if(newTask !== "") {
      setTodoList([...todoList, newTask]);
      setNewTask("");
      console.log(todoList);
    }
  };

  const handleDelete = (e) => {
    const index = e.target.id;
    console.log(e.target.id)
    const newTodoList = todoList.filter((task, i) => i !== parseInt(index));
    setTodoList(newTodoList);
  };

  return (
    <div className="App">
      <div className="addTask">
        <input onChange={handleChange} value={newTask}/>
        <button onClick={addTask}>Add Task</button>
      </div>
      <div className="list"></div>
      <div>{newTask}</div>
      <div>{todoList.map((todo, id)=>{
        return <div key={id}>{todo} <button id={id} onClick={handleDelete} style={{backgroundColor: "red"}}>X</button></div>
      })}</div>
    </div>
  );
}

export default App;

```

</details>

<details>
  <summary>58. React Component Lifecycle</summary>

```bash
- mounting
- updating
- unmounting
```

App.js:

```Javascript
import "./App.css";
import { useState } from "react";
import { Text } from "./Text";

function App() {
  const [showText, setShowText] = useState(false);

  return (
    <div className="App">
      <button
        onClick={() => {
          setShowText(!showText);
        }}
      >
        Show Text
      </button>

      {showText && <Text />}
    </div>
  );
}

export default App;
```

Text.js:

```Javascript
import React from "react";
import { useState, useEffect } from "react";

export const Text = () => {
    const [text, setText] = useState("");

    useEffect(() => {
        console.log("COMPONENT MOUNTED");

        return () => {
        console.log("COMPONENT UNMOUNTED");
        };
    }, []);

    return (
        <div>
        <input
            onChange={(event) => {
            setText(event.target.value);
            }}
        />

        <h1> {text}</h1>
        </div>
    );
};
```

</details>

<details>
  <summary>59. Fetching Data from API</summary>

App.js:

```Javascript
import "./App.css";
import { useEffect, useState } from "react";

function App() {

  const [fact, setFact] = useState("");

  useEffect(() => {
    handleNewFact();
  }, []);

  const handleNewFact = () => {
    fetch("https://catfact.ninja/fact")
      .then((res) => res.json())
      .then((data) => {
        console.log(data);
        setFact(data.fact);
      });
  };

  return (
    <div className="App">
      <button onClick={handleNewFact}>Generate Cat Fact</button>
      <p>{fact}</p>
    </div>
  );
}

export default App;
```

</details>

<details>
  <summary>60. Using Axios to Fetch API</summary>

Install Axios:

```bash
npm install axios
```

With https://catfact.ninja/fact API:

```Javascript
import "./App.css";
import { useEffect, useState } from "react";
import Axios from "axios";

function App() {
  const [fact, setFact] = useState("");

  useEffect(() => {
    handleNewFact();
  }, []);

  const handleNewFact = () => {
    Axios.get("https://catfact.ninja/fact")
      .then((res) => {
        setFact(res.data.fact);
        console.log(res.data.fact);
      })
      .catch((err) => {
        console.log(err);
      });
  };

  return (
    <div className="App">
      <button onClick={handleNewFact}>Generate Cat Fact</button>
      <p>{fact}</p>
    </div>
  );
}

export default App;
```

With https://api.agify.io?name= API:

```Javascript
import "./App.css";
import { useState } from "react";
import Axios from "axios";

function App() {
  const [person, setPerson] = useState({name: "", age: ""});
  const [show, setShow] = useState(false);

  const fetchData = () => {
    if(person?.name){
      Axios.get(`https://api.agify.io?name=${person?.name}`)
      .then((res) => {
        setPerson(res.data);
        console.log(res.data);
        setShow(true);
      })
      .catch((err) => {
        console.log(err);
      });
    }

  };

  const handleChange = (e) => {
    setPerson({ ...person, name: e.target.value });
    setShow(false);
  };

  return (
    <div className="App">
      <br/>
      <input onChange={handleChange} type="text" placeholder="Charles..." value={person?.name} />
      <br/>
      <button onClick={fetchData}>Generate Age</button>
      <p>{person?.name || "Charles"} is {show ? person?.age : "___"} years old.</p>
    </div>
  );
}

export default App;
```

```Javascript

```

</details>

<details>
  <summary>61. sample</summary>



```Javascript

```

```Javascript

```

```Javascript

```

</details>

<details>
  <summary>62. sample</summary>



```Javascript

```

```Javascript

```

```Javascript

```

</details>

<details>
  <summary>63. sample</summary>



```Javascript

```

```Javascript

```

```Javascript

```

</details>

<details>
  <summary>64. sample</summary>



```Javascript

```

```Javascript

```

```Javascript

```

</details>

<details>
  <summary>65. sample</summary>



```Javascript

```

```Javascript

```

```Javascript

```

</details>

<details>
  <summary>66. sample</summary>



```Javascript

```

```Javascript

```

```Javascript

```

</details>

<details>
  <summary>67. sample</summary>



```Javascript

```

```Javascript

```

```Javascript

```

</details>

<details>
  <summary>68. sample</summary>



```Javascript

```

```Javascript

```

```Javascript

```

</details>

<details>
  <summary>69. sample</summary>



```Javascript

```

```Javascript

```

```Javascript

```

</details>

<details>
  <summary>70. sample</summary>



```Javascript

```

```Javascript

```

```Javascript

```

</details>


