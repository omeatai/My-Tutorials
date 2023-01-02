# React-Tutorial

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
  box-shadow: 1px 3px 5px rgba(0, 0, 0, 0.1);
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
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="styles.css" />
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
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="styles.css" />
    <title>JSON Server</title>
  </head>
  <body>
    <h1>Create a New Blog</h1>

    <form>
      <input type="text" name="title" required placeholder="Blog title" />
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
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="styles.css" />
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
@import url("https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&display=swap");

/* base styles */
body {
  background: #eee;
  font-family: "Roboto";
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
input,
textarea {
  display: block;
  margin: 16px 0;
  padding: 6px 10px;
  width: 100%;
  border: 1px solid #ddd;
  font-family: "Roboto";
}
textarea {
  min-height: 200px;
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
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="styles.css" />
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
const container = document.querySelector(".blogs");
const pathname = window.location.pathname;
const filename = pathname.slice(pathname.lastIndexOf("/") + 1);
const dirname = pathname.slice(0, pathname.lastIndexOf("/"));

const renderPosts = async () => {
  let uri = "http://localhost:3000/posts";

  const res = await fetch(uri);
  const posts = await res.json();

  let template = "";
  posts.forEach((post) => {
    template += `
      <div class="post">
        <h2>${post.title}</h2>
        <p><small>${post.likes} likes</small></p>
        <p>${post.body.slice(0, 200)}...</p>
        <a href="${dirname}/details.html?id=${post.id}">Read more</a>
      </div>
    `;
  });

  container.innerHTML = template;
};

window.addEventListener("DOMContentLoaded", () => renderPosts());
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
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="styles.css" />
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
const id = new URLSearchParams(window.location.search).get("id");
const container = document.querySelector(".details");
const pathname = window.location.pathname;
const filename = pathname.slice(pathname.lastIndexOf("/") + 1);
const dirname = pathname.slice(0, pathname.lastIndexOf("/"));

const renderDetails = async () => {
  const res = await fetch("http://localhost:3000/posts/" + id);
  if (!res.ok) {
    window.location.replace(`${dirname}/index.html`);
  }
  const post = await res.json();

  const template = `
    <h1>${post.title}</h1>
    <p>${post.body}</p>
  `;

  container.innerHTML = template;
};

window.addEventListener("DOMContentLoaded", renderDetails);
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
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="styles.css" />
    <title>JSON Server</title>
  </head>
  <body>
    <h1>Create a New Blog</h1>

    <form>
      <input type="text" name="title" required placeholder="Blog title" />
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

const form = document.querySelector("form");

const pathname = window.location.pathname;
const filename = pathname.slice(pathname.lastIndexOf("/") + 1);
const dirname = pathname.slice(0, pathname.lastIndexOf("/"));

const createPost = async (e) => {
  e.preventDefault();

  const doc = {
    title: form.title.value,
    body: form.body.value,
    likes: 0,
  };

  await fetch("http://localhost:3000/posts", {
    method: "POST",
    body: JSON.stringify(doc),
    headers: { "Content-Type": "application/json" },
  });

  window.location.replace(`${dirname}/index.html`);
};

form.addEventListener("submit", createPost);
```

</details>

<details>
  <summary>25. JSON Server - Delete Post from DB</summary>

details.html:

```html
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="styles.css" />
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
const id = new URLSearchParams(window.location.search).get("id");
const container = document.querySelector(".details");
const deleteBtn = document.querySelector(".delete");

const pathname = window.location.pathname;
const filename = pathname.slice(pathname.lastIndexOf("/") + 1);
const dirname = pathname.slice(0, pathname.lastIndexOf("/"));

const renderDetails = async () => {
  const res = await fetch("http://localhost:3000/posts/" + id);
  if (!res.ok) {
    window.location.replace(`${dirname}/index.html`);
  }
  const post = await res.json();

  const template = `
    <h1>${post.title}</h1>
    <p>${post.body}</p>
  `;

  container.innerHTML = template;
};

deleteBtn.addEventListener("click", async () => {
  const res = await fetch("http://localhost:3000/posts/" + id, {
    method: "DELETE",
  });
  window.location.replace(`${dirname}/index.html`);
});

window.addEventListener("DOMContentLoaded", renderDetails);
```

</details>

<details>
  <summary>26. JSON Server - Search for Posts Keywords</summary>

index.html:

```html
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="styles.css" />
    <title>JSON Server</title>
  </head>
  <body>
    <nav>
      <h1>All Blogs</h1>
      <a href="/Cloud/Json-Server/create.html">Add a new blog</a>
    </nav>

    <form class="search">
      <input type="text" placeholder="search term" name="term" />
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
  const [blogs, setBlogs] = useState(null);

  useEffect(() => {
    fetch("http://localhost:8000/blogs")
      .then((res) => {
        return res.json();
      })
      .then((data) => {
        setBlogs(data);
      });
  }, []);

  return (
    <div className="home">
      {blogs && <BlogList blogs={blogs} title="All Blogs!" />}
    </div>
  );
};

export default Home;
```

BlogList.js:

```javascript
import React from "react";

const BlogList = ({ blogs, title }) => {
  return (
    <div className="blog-list">
      <h2>{title}</h2>
      {blogs.map((blog) => (
        <div className="blog-preview" key={blog.id}>
          <h2>{blog.title}</h2>
          <p>Written by {blog.author}</p>
        </div>
      ))}
    </div>
  );
};

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
      fetch("http://localhost:8000/blogs")
        .then((res) => {
          return res.json();
        })
        .then((data) => {
          setIsPending(false);
          setBlogs(data);
        });
    }, 1000);
  }, []);

  return (
    <div className="home">
      {isPending && <div>Loading...</div>}
      {blogs && <BlogList blogs={blogs} title="All Blogs!" />}
    </div>
  );
};

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
      fetch("http://localhost:8000/blogs")
        .then((res) => {
          if (!res.ok) {
            // error coming back from server
            throw Error("could not fetch the data for that resource");
          }
          return res.json();
        })
        .then((data) => {
          setIsPending(false);
          setBlogs(data);
          setError(null);
        })
        .catch((err) => {
          // auto catches network / connection error
          setIsPending(false);
          setError(err.message);
          setBlogs(null);
        });
    }, 1000);
  }, []);

  return (
    <div className="home">
      {error && <div>{error}</div>}
      {isPending && <div>Loading...</div>}
      {blogs && <BlogList blogs={blogs} title="All Blogs!" />}
    </div>
  );
};

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
import { useState, useEffect } from "react";

const useFetch = (url) => {
  const [data, setData] = useState(null);
  const [isPending, setIsPending] = useState(true);
  const [error, setError] = useState(null);

  useEffect(() => {
    setTimeout(() => {
      fetch(url)
        .then((res) => {
          if (!res.ok) {
            // error coming back from server
            throw Error("could not fetch the data for that resource");
          }
          return res.json();
        })
        .then((data) => {
          setIsPending(false);
          setData(data);
          setError(null);
        })
        .catch((err) => {
          // auto catches network / connection error
          setIsPending(false);
          setError(err.message);
          setData(null);
        });
    }, 1000);
  }, [url]);

  return { data, isPending, error };
};

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
.create input,
.create textarea,
.create select {
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
  "private": true
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
  }
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

+REACT-FETCH

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

+REACT-AXIOS

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

With https://excuser.herokuapp.com/v1/excuse/ API:

```Javascript
import "./App.css";
import Axios from "axios";
import { useState } from "react";

function App() {
  const [generatedExcuse, setGeneratedExcuse] = useState("");

  const fetchExcuse = (excuse) => {
    Axios.get(`https://excuser.herokuapp.com/v1/excuse/${excuse}/`).then(
      (res) => {
        setGeneratedExcuse(res.data[0].excuse);
      }
    );
  };

  return (
    <div className="App">
      <h1> Generate An Excuse </h1>
      <button onClick={() => fetchExcuse("party")}> Party</button>
      <button onClick={() => fetchExcuse("family")}> Family</button>
      <button onClick={() => fetchExcuse("office")}> Office </button>

      <p> {generatedExcuse} </p>
    </div>
  );
}

export default App;
```

</details>

+REACT-ROUTER

<details>
  <summary>61. React Router Dom</summary>

Install React Router Dom:

```bash
npm install react-router-dom
```

App.js:

```Javascript
import "./App.css";
import { BrowserRouter as Router, Routes, Route } from "react-router-dom";
import { Home } from "./pages/Home";
import { Menu } from "./pages/Menu";
import { Contact } from "./pages/Contact";
import { Navbar } from "./Navbar";

function App() {
  return (
    <div className="App">
      <Router>
        <Navbar />
        <Routes>
          <Route path="/" element={<Home />} />
          <Route path="/menu" element={<Menu />} />
          <Route path="/contact" element={<Contact />} />
          <Route path="*" element={<h1> PAGE NOT FOUND</h1>} />
        </Routes>
      </Router>
    </div>
  );
}

export default App;
```

Navbar.js:

```Javascript
import { Link } from "react-router-dom";

export const Navbar = () => {
  return (
    <div>
      <Link to="/"> Home </Link>
      <Link to="/menu"> Menu </Link>
      <Link to="/contact"> Contact </Link>
    </div>
  );
};
```

Home.js:

```Javascript
export const Home = () => {
    return <h1> THIS IS THE HOME PAGE</h1>;
  };
```

Menu.js:

```Javascript
export const Menu = () => {
    return <h1> THIS IS THE MENU PAGE</h1>;
  };
```

Contact.js:

```Javascript
export const Contact = () => {
    return <h1> THIS IS THE CONTACT PAGE</h1>;
  };
```

</details>

<details>
  <summary>62. React Router Dom Version 6</summary>

Install React Router Dom Version 6:

```bash
npm install react-router-dom@6

yarn add react-router-dom@6
```

App.js:

```Javascript
import "./App.css";
import { BrowserRouter as Router, Routes, Route, Link } from "react-router-dom";
import Home from "./pages/Home";
import About from "./pages/About";
import Profile from "./pages/Profile";
import ErrorPage from "./pages/ErrorPage";

function App() {
  return (
    <Router>
      <nav>
        <Link to="/"> Home </Link>
        <Link to="/about"> About </Link>
        <Link to="/profile"> Profile </Link>
      </nav>
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/about" element={<About />} />
        <Route path="/profile/" element={<Profile />} />
        <Route path="/profile/:username" element={<Profile />} />
        <Route path="*" element={<ErrorPage />} />
      </Routes>
      <div> Foooter </div>
    </Router>
  );
}

export default App;
```

Home.js:

```Javascript
import React from "react";

function Home() {
  return <div> THIS IS THE HOME PAGE</div>;
}

export default Home;
```

About.js:

```Javascript
import React from "react";

function About() {
  return <div>THIS IS THE ABOUT PAGE</div>;
}

export default About;
```

Profile.js:

```Javascript
import React from "react";
import { useNavigate, useParams } from "react-router-dom";

function Profile() {
  let navigate = useNavigate();
  let { username } = useParams();
  return (
    <div>
      THIS IS THE PROFILE PAGE FOR {username || "Admin"}!
      <button
        onClick={() => {
          navigate("/about");
        }}
      >
        {" "}
        Change to about page
      </button>
    </div>
  );
}

export default Profile;
```

</details>

+CONTEXT-API

<details>
  <summary>63. useContext Hook (Context API)</summary>

App.js:

```Javascript
import "./App.css";
import { BrowserRouter as Router, Routes, Route } from "react-router-dom";
import { Home } from "./pages/Home";
import { Profile } from "./pages/Profile";
import { Contact } from "./pages/Contact";
import { Navbar } from "./Navbar";
import {useState, createContext } from "react";

export const AppContext = createContext();

function App() {
  const [username, setUsername] = useState("Pedro");

  return (
    <div className="App">
      <AppContext.Provider value={{username, setUsername}}>
      <Router>
        <Navbar />
        <Routes>
          <Route path="/" element={<Home username={username}/>} />
          <Route path="/profile" element={<Profile username={username} setUsername={setUsername}/>} />
          <Route path="/contact" element={<Contact username={username} />} />
          <Route path="*" element={<h1> PAGE NOT FOUND</h1>} />
        </Routes>
      </Router>
      </AppContext.Provider>
    </div>
  );
}

export default App;

```

Home.js:

```Javascript
import { useContext } from 'react';
import { AppContext } from '../App';

export const Home = () => {
  const { username } = useContext(AppContext);
  return <h1> THIS IS THE HOME PAGE for {username}.</h1>;
};
```

Profile.js:

```Javascript
import { ChangeProfile } from "./changeProfile";
import { useContext } from 'react';
import { AppContext } from '../App';

export const Profile = (props) => {
  const { username } = useContext(AppContext);

  return (
    <div>
      PROFILE, user is: {username}
      <ChangeProfile />
    </div>
  );
};
```

ChangeProfile.js:

```Javascript
import { useState } from "react";
import { useContext } from 'react';
import { AppContext } from '../App';

export const ChangeProfile = (props) => {
    const [newUsername, setNewUsername] = useState("");
    const { setUsername } = useContext(AppContext);

    return (
        <div>
            <input
                onChange={(event) => {
                    setNewUsername(event.target.value);
                }}
            />
            <button onClick={()=>{setUsername(newUsername)}}> Change Username</button>
        </div>
    );
};

```

</details>

+REACT-QUERY

<details>
  <summary>64. React Query Library</summary>

Install React Query:

```bash
npm install @tanstack/react-query
```

Install Axios:

```bash
npm install axios
```

App.js:

```Javascript
import "./App.css";
import { BrowserRouter as Router, Routes, Route } from "react-router-dom";
import { Home } from "./pages/Home";
import { Profile } from "./pages/Profile";
import { Contact } from "./pages/Contact";
import { Navbar } from "./Navbar";
import {useState, createContext } from "react";
import { QueryClient, QueryClientProvider } from "@tanstack/react-query";

export const AppContext = createContext();

function App() {
  const [username, setUsername] = useState("Pedro");
  const [newUsername, setNewUsername] = useState("");
  const client = new QueryClient({
    defaultOptions: {
      queries: {
        refetchOnWindowFocus: true,
      },
    },
  });

  return (
    <div className="App">
      <QueryClientProvider client={client}>
      <AppContext.Provider value={{username, setUsername, newUsername, setNewUsername}}>
      <Router>
        <Navbar />
        <Routes>
          <Route path="/" element={<Home username={username}/>} />
          <Route path="/profile" element={<Profile username={username} setUsername={setUsername}/>} />
          <Route path="/contact" element={<Contact username={username} />} />
          <Route path="*" element={<h1> PAGE NOT FOUND</h1>} />
        </Routes>
      </Router>
      </AppContext.Provider>
      </QueryClientProvider>
    </div>
  );
}

export default App;

```

Home.js:

```Javascript
import { useContext } from 'react';
import { AppContext } from '../App';
import { useQuery } from '@tanstack/react-query';
import Axios from 'axios';

export const Home = () => {
  const { username } = useContext(AppContext);
  const { data: catData, isLoading, isError, error, refetch } = useQuery(["cat"], () => {
    return Axios.get("https://catfact.ninja/fact").then((res) => res.data);
      //.catch((err) => console.log(`There was an error: ${err}`));
  });

  return (
    <section className="home">
      <h1> THIS IS THE HOME PAGE for {username}.</h1>
      <h2>Quote:</h2>
      <p>{ isLoading && "Loading..."}{ isError ? error.message : catData?.fact }</p>
      <button onClick={() => refetch()}>Update Data</button>
    </section>
    );
};
```

</details>

+YUP/REACT-HOOK-FORM

<details>
  <summary>65. React-Hook-Form & Yup</summary>

Install React-Hook-Form and Yup:

```bash
npm install react-hook-form yup
```

Install @hookform/resolvers:

```bash
npm install @hookform/resolvers
```

App.js:

```Javascript
import "./App.css";
import { Form } from "./pages/Form";

function App() {
  return (
    <div className="App">
      <Form />
    </div>
  );
}

export default App;

```

Form.js:

```Javascript
import { useForm } from "react-hook-form";
import { yupResolver } from "@hookform/resolvers/yup";
import * as yup from "yup";

export const Form = () => {
    const schema = yup.object().shape({
        fullName: yup.string().required("Your Full Name is Required!"),
        email: yup.string().email().required(),
        age: yup.number().positive().integer().min(18).required(),
        password: yup.string().min(4).max(20).required(),
        confirmPassword: yup
            .string()
            .oneOf([yup.ref("password"), null], "Passwords Don't Match")
            .required(),
    });

    const {register, handleSubmit, formState: { errors }, } = useForm({
        resolver: yupResolver(schema),
    });

    const onSubmit = (data) => {
        console.log(data);
    };

    return (
        <form onSubmit={handleSubmit(onSubmit)}>
            <input type="text" placeholder="Full Name..." {...register("fullName")} />
            <p>{errors.fullName?.message}</p>
            <input type="text" placeholder="Email..." {...register("email")} />
            <p>{errors.email?.message}</p>
            <input type="number" placeholder="Age..." {...register("age")} />
            <p>{errors.age?.message}</p>
            <input
                type="password"
                placeholder="Password..."
                {...register("password")}
            />
            <p>{errors.password?.message}</p>
            <input
                type="password"
                placeholder="Confirm Password..."
                {...register("confirmPassword")}
            />
            <p>{errors.confirmPassword?.message}</p>
            <input type="submit" />
        </form>
    );
};

```

</details>

+CUSTOM-HOOKS

<details>
  <summary>66. Custom Hooks</summary>

App.js:

```Javascript
import "./App.css";
import { useToggle } from "./useToggle";

function App() {
  const [isVisible, toggle] = useToggle();
  const [isVisible2, toggle2] = useToggle();

  return (
    <div className="App">
      <button onClick={toggle}>{isVisible ? "Hide" : "Show"}</button>
      {isVisible && <h1> Hidden text</h1>}

      <button onClick={toggle2}>{isVisible2 ? "Hide" : "Show"}</button>
      {isVisible2 && <h1> Hidden text</h1>}
    </div>
  );
}

export default App;
```

useToggle.js:

```Javascript
import { useState } from "react";

export const useToggle = (initialVal = false) => {
    const [state, setState] = useState(initialVal);

    const toggle= () => {
        setState((prev) => !prev);
    };
    return [state, toggle];
};

```

</details>

<details>
  <summary>67. Cat.js Custom Hook Example</summary>

App.js:

```Javascript
import "./App.css";
import { Cat } from "./pages/Cat";
import { QueryClient, QueryClientProvider } from "@tanstack/react-query";

function App() {
  const client = new QueryClient({
    defaultOptions: {
      queries: {
        refetchOnWindowFocus: true,
      },
    },
  });

  return (
    <div className="App">
      <QueryClientProvider client={client}>
        <Cat />
      </QueryClientProvider>
    </div>
  );
}
export default App;
```

Cat.js:

```Javascript
import useGetCat from "../useGetCat";

export const Cat = () => {
    const { data: catData, refetchData: refresh, isCatLoading } = useGetCat();

    if(isCatLoading) {
        return <h1>Loading...</h1>
    }

    return (
        <div>
            <h1> {isCatLoading ? "Loading..." : catData?.fact}</h1>
            <button onClick={refresh}>Refresh</button>
        </div>

    );
};
```

useGetCat.js:

```Javascript
import { useQuery } from "@tanstack/react-query";
import Axios from "axios";

const useGetCat = () => {
    const { data, refetch, isLoading: isCatLoading } = useQuery(["cat"] , async () => {
        return Axios.get("https://catfact.ninja/fact").then((res) => res.data);
    });

    const refetchData = () => {
        console.log("DATA REFRESHED");
        refetch();
    };

    return { data, refetchData, isCatLoading };
};

export default useGetCat;
```

</details>

<details>
  <summary>68. Counter Custom Hook Example</summary>

COUNTER Example:

App.js:

```Javascript
import "./App.css";
import { Counter } from "./pages/Counter";
import { QueryClient, QueryClientProvider } from "@tanstack/react-query";

function App() {
  const client = new QueryClient({
    defaultOptions: {
      queries: {
        refetchOnWindowFocus: true,
      },
    },
  });

  return (
    <div className="App">
      <QueryClientProvider client={client}>
        <Counter />
      </QueryClientProvider>
    </div>
  );
}
export default App;
```

Counter.js:

```Javascript
import { useCounter } from './useCounter';

export const Counter = () => {
    const {state: count, increment, decrement, reset} = useCounter();

    return (
        <div>
            <h1>{count}</h1>
            <button onClick={increment}>Increment</button>
            <button onClick={reset}>Reset</button>
            <button onClick={decrement}>Decrement</button>
        </div>
    );
}
```

useCounter.js:

```Javascript
import { useState } from 'react';

export const useCounter = (initialCount = 0) => {

    const [state, setState] = useState(initialCount);

    const increment = () => {
        setState(state + 1);
    };

    const decrement = () => {
        setState(state - 1);
    };

    const reset = () => {
        setState(0);
    };

    return {state, increment, decrement, reset};

}
```

</details>

+TYPESCRIPT

<details>
  <summary>69. React Type Safety (PropTypes)</summary>

Install PropTypes:

```bash
npm install prop-types
```

App.js:

```Javascript
import "./App.css";
import { Person } from "./pages/Person";

function App() {
  return (
    <div className="App">
      <Person
        name="Pedro"
        email="pedro@gmail.com"
        age={21}
        isMarried={true}
        friends={["jessica", "jake", "jerry", "jasmine"]}
      />
    </div>
  );
}

export default App;
```

Person.js:

```Javascript
import PropTypes from "prop-types";

export const Person = (props) => {
    return (
        <div>
            <h1>Name: {props.name}</h1>
            <h1>Email: {props.email}</h1>
            <h1>Age: {props.age}</h1>
            <h1>This person {props.isMarried ? "is" : "is not"} MARRIED</h1>
            <h1>Friends:</h1>
            <ol>
            {props.friends.map((friend, index) => (
                <li key={index}>{`${friend.charAt(0).toUpperCase()}${friend.slice(1)}`}</li>
            ))}
            </ol>
        </div>
    );
};

Person.propTypes = {
    name: PropTypes.string.isRequired,
    email: PropTypes.string.isRequired,
    age: PropTypes.number.isRequired,
    isMarried: PropTypes.bool.isRequired,
    friends: PropTypes.arrayOf(PropTypes.string).isRequired,
};

export default Person;

```

</details>

<details>
  <summary>70. React Type Safety (TypeScript)</summary>

Install TypeScript App:

```bash
npx create-react-app . --template typescript
```

App.tsx:

```typescript
import { Person, Country } from "./Person";

function App() {
  return (
    <div className="App">
      <Person
        name="Pedro"
        email="pedro@gmail.com"
        age={21}
        isMarried={true}
        friends={["jessica", "jake", "jerry", "jasmine"]}
        country={Country.Nigeria}
      />
    </div>
  );
}

export default App;
```

Person.tsx:

```typescript
import { useState } from "react";

interface Props {
  name: string;
  email: string;
  age: number;
  isMarried: boolean;
  friends: string[];
  country: string;
}

export enum Country {
  Brazil = "Brazil",
  Nigeria = "Nigeria",
  USA = "USA",
}

export const Person = (props: Props) => {
  const firstName: string = "Dave";
  const [name, setName] = useState<string>("Adam");
  const getAge = (name: string): number => {
    return props.age;
  };

  return (
    <div>
      <h1>Name: {props.name}</h1>
      <h1>Email: {props.email}</h1>
      <h1>Age: {props.age}</h1>
      <h1>This person {props.isMarried ? "is" : "is not"} MARRIED</h1>
      <h1>{firstName}</h1>
      <h1>{name}</h1>
      <h1>{typeof String(getAge(props.name))}</h1>
      <h1>Friends:</h1>
      <ol>
        {props.friends.map((friend: string, index: number) => (
          <li key={index}>{`${friend.charAt(0).toUpperCase()}${friend.slice(
            1
          )}`}</li>
        ))}
      </ol>
      <h1>Country: {props.country}</h1>
    </div>
  );
};

export default Person;
```

</details>

+REDUX-TOOLKIT

<details>
  <summary>71. Redux Toolkit</summary>

Install Redux Toolkit Packages:

```bash
npm install @reduxjs/toolkit react-redux
```

App.tsx:

```typescript
import { BrowserRouter as Router, Routes, Route, Link } from "react-router-dom";
import { Home } from "./pages/Home";
import { Contact } from "./pages/Contact";
import { Login } from "./pages/Login";
import { Provider } from "react-redux";
import { store } from "./store";

function App() {
  return (
    <div className="App">
      <Provider store={store}>
        <Router>
          <Link to="/">Home</Link>
          <Link to="/login">Login</Link>
          <Link to="/contact">Contact</Link>
          <Routes>
            <Route path="/" element={<Home />} />
            <Route path="/login" element={<Login />} />
            <Route path="/contact" element={<Contact />} />
          </Routes>
        </Router>
      </Provider>
    </div>
  );
}

export default App;
```

store.ts:

```typescript
import { configureStore, createSlice, PayloadAction } from "@reduxjs/toolkit";

interface UserStateValue {
  username: string;
}

interface UserState {
  value: UserStateValue;
}

const initialState = { value: { username: "" } } as UserState;
const userSlice = createSlice({
  name: "user",
  initialState,
  reducers: {
    login: (state: UserState, action: PayloadAction<UserStateValue>) => {
      state.value = action.payload;
    },
    logout: (state: UserState) => {
      state.value = initialState.value;
    },
  },
});

export const { login, logout } = userSlice.actions;

export const store = configureStore({
  reducer: {
    user: userSlice.reducer,
  },
});
```

Login.tsx:

```typescript
import React, { useState } from "react";
import { login, logout } from "../store";
import { useDispatch, useSelector } from "react-redux";

export const Login = () => {
  const [newUsername, setNewUsername] = useState<string>("");
  const dispatch = useDispatch();
  const username = useSelector((state: any) => state.user.value.username);

  return (
    <div>
      <h1>Login</h1>
      <h2>Username: {username}</h2>
      <input
        onChange={(e: React.ChangeEvent<HTMLInputElement>) =>
          setNewUsername(e.target.value)
        }
        type="text"
        placeholder="username"
      />
      <button onClick={() => dispatch(login({ username: newUsername }))}>
        Submit Login
      </button>
      <button onClick={() => dispatch(logout())}>Logout</button>
    </div>
  );
};
```

Home.tsx:

```typescript
import { useDispatch, useSelector } from "react-redux";

export const Home = () => {
  const username = useSelector((state: any) => state.user.value.username);

  return (
    <div>
      <h1>Home</h1>
      <h2>Username: {username}</h2>
    </div>
  );
};
```

Contact.tsx:

```typescript
export const Contact = () => {
  return <h1>Contact</h1>;
};
```

</details>

+FIREBASE SOCIAL MEDIA PROJECT

<details>
  <summary>72. Introduction</summary>

Create React Project:

```bash
npx create-react-app . --template typescript
```

Run Project:

```bash
npm start
```

index.tsx:

```typescript
import React from "react";
import ReactDOM from "react-dom/client";
import App from "./App";

const root = ReactDOM.createRoot(
  document.getElementById("root") as HTMLElement
);
root.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);
```

App.tsx:

```typescript
import React from "react";
import "./App.css";

function App() {
  return (
    <div className="App">
      <h1>React App</h1>
    </div>
  );
}

export default App;
```

</details>

<details>
  <summary>73. Setting up Components</summary>

Install React Router DOM

```bash
npm install react-router-dom
```

App.tsx:

```typescript
import React from "react";
import "./App.css";
import { Main } from "./pages/Main";
import { Login } from "./pages/Login";
import { Navbar } from "./components/Navbar";
import { BrowserRouter as Router, Routes, Route } from "react-router-dom";

function App() {
  return (
    <div className="App">
      <Router>
        <Navbar />
        <Routes>
          <Route path="/" element={<Main />} />
          <Route path="/login" element={<Login />} />
        </Routes>
      </Router>
    </div>
  );
}

export default App;
```

Navbar.tsx:

```typescript
import { Link } from "react-router-dom";

export const Navbar = () => {
  return (
    <nav>
      <Link to="/">Home</Link>
      <Link to="/login">Login</Link>
    </nav>
  );
};
```

Main.tsx:

```ts
export const Main = () => {
  return <h1>Home Page</h1>;
};
```

Login.tsx:

```ts
export const Login = () => {
  return <h1> Login Page</h1>;
};
```

</details>

<details>
  <summary>74. Integrate Firebase</summary>

Install Firebase:

```bash
npm install firebase
```

config.ts:

```ts
// Import the functions you need from the SDKs you need
import { initializeApp } from "firebase/app";
import { getAuth, GoogleAuthProvider } from "firebase/auth";
// TODO: Add SDKs for Firebase products that you want to use
// https://firebase.google.com/docs/web/setup#available-libraries

// Your web app's Firebase configuration
const firebaseConfig = {
  apiKey: "AIzaSyDdFw8SFSfGwmm3S5CBX5nFi7KMxd8GyyQ",
  authDomain: "pedro-app-8bd3b.firebaseapp.com",
  projectId: "pedro-app-8bd3b",
  storageBucket: "pedro-app-8bd3b.appspot.com",
  messagingSenderId: "679821378683",
  appId: "1:679821378683:web:54f00cc4f7433907150ede",
};

// Initialize Firebase
const app = initializeApp(firebaseConfig);

export const auth = getAuth(app);
export const provider = new GoogleAuthProvider();
```

</details>

<details>
  <summary>75. Login Google Authentication</summary>

```bs
npm install react-firebase-hooks
```

Login.tsx:

```tsx
import { auth, provider } from "../config/firebase";
import { signInWithPopup } from "firebase/auth";
import { useNavigate } from "react-router-dom";

export const Login = () => {
  const navigate = useNavigate();

  const signInWithGoogle = async () => {
    const result = await signInWithPopup(auth, provider);
    if (result) {
      navigate("/");
    }
  };

  return (
    <div>
      <h1> Login Page</h1>
      <p>Sign In With Google To Continue</p>
      <button onClick={signInWithGoogle}>Sign In With Google</button>
    </div>
  );
};
```

Navbar.tsx:

```tsx
import { Link } from "react-router-dom";
import { auth } from "../config/firebase";
import { useAuthState } from "react-firebase-hooks/auth";
import { signOut } from "firebase/auth";

export const Navbar = () => {
  const [user, loading, error] = useAuthState(auth);

  const signUserOut = async () => {
    await signOut(auth);
  };

  return (
    <nav className="navbar">
      <div className="links">
        <Link to="/">Home</Link>
        <Link to="/login">Login</Link>
      </div>
      <div className="user">
        {user ? (
          <>
            <p>{user?.displayName}</p>
            <img
              src={user?.photoURL || ""}
              alt="photoURL"
              width="20"
              height="20"
            />
            <button onClick={signUserOut}> Log Out</button>
          </>
        ) : null}
      </div>
    </nav>
  );
};
```

App.css:

```css
.App {
  text-align: center;
}

body {
  margin: 0;
  padding: 0;
  font-family: Arial, Helvetica, sans-serif;
}

.navbar {
  width: 100%;
  height: 80px;
  background-color: slateblue;
  display: flex;
  align-items: center;
  justify-content: flex-end;
}

.navbar .links {
  text-align: center;
  margin-right: 50px;
}

.links a {
  color: white;
  text-decoration: none;
  border-bottom: 3px solid white;
  padding-bottom: 2px;
  margin: 10px;
}

.navbar .user {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-right: 50px;
}

.user p {
  font-size: 15px;
  margin-right: 10px;
  color: white;
}

.user img {
  font-size: 15px;
  border-radius: 50%;
}
```

</details>

<details>
  <summary>76. Create Firebase Collection</summary>

```bs
Firebase -> Build -> Firestore Database -> Collection -> "Posts"
```

```bs
description -> "Hello, people." -> (string)
id -> "pedrotech01" -> (string)
title -> "the first post" -> (string)
username -> "PedroTech" -> (string)
```

</details>

<details>
  <summary>77. Controlling Login availability</summary>

Navbar.tsx:

```tsx
import { Link } from "react-router-dom";
import { auth } from "../config/firebase";
import { useAuthState } from "react-firebase-hooks/auth";
import { signOut } from "firebase/auth";

export const Navbar = () => {
  const [user, loading, error] = useAuthState(auth);

  const signUserOut = async () => {
    await signOut(auth);
  };

  return (
    <nav className="navbar">
      <div className="links">
        <Link to="/">Home</Link>
        {!user ? (
          <Link to="/login">Login</Link>
        ) : (
          <Link to="/createpost">Create Post</Link>
        )}
      </div>
      <div className="user">
        {user ? (
          <>
            <p>{user?.displayName}</p>
            <img src={user?.photoURL || ""} alt="" width="20" height="20" />
            <button onClick={signUserOut}> Log Out</button>
          </>
        ) : null}
      </div>
    </nav>
  );
};
```

</details>

<details>
  <summary>78. Create Post route and Component</summary>

App.tsx:

```tsx
import React from "react";
import "./App.css";
import { Main } from "./pages/Main";
import { Login } from "./pages/Login";
import { CreatePost } from "./pages/createpost/CreatePost";
import { Navbar } from "./components/Navbar";
import { BrowserRouter as Router, Routes, Route } from "react-router-dom";

function App() {
  return (
    <div className="App">
      <Router>
        <Navbar />
        <Routes>
          <Route path="/" element={<Main />} />
          <Route path="/login" element={<Login />} />
          <Route path="/createpost" element={<CreatePost />} />
        </Routes>
      </Router>
    </div>
  );
}

export default App;
```

CreatePost.tsx:

```tsx
export const CreatePost = () => {
  return <div>Create Post</div>;
};
```

</details>

<details>
  <summary>79. Create Post Form</summary>

```bs
npm install react-hook-form yup @hookform/resolvers
```

CreatePost.tsx:

```tsx
import { CreateForm } from "./CreateForm";

export const CreatePost = () => {
  return (
    <div>
      <h1>Create Post</h1>
      <CreateForm />
    </div>
  );
};
```

CreateForm.tsx:

```tsx
import { useForm } from "react-hook-form";
import * as yup from "yup";
import { yupResolver } from "@hookform/resolvers/yup";

export const CreateForm = () => {
  interface CreateFormData {
    title: string;
    description: string;
  }

  const schema = yup.object().shape({
    title: yup.string().required("You must add a Title."),
    description: yup.string().required("You must add a Description."),
  });

  const {
    register,
    handleSubmit,
    formState: { errors },
  } = useForm<CreateFormData>({
    resolver: yupResolver(schema),
  });

  const onCreatePost = (data: CreateFormData) => {
    console.log(data);
  };

  return (
    <form onSubmit={handleSubmit(onCreatePost)}>
      <input placeholder="Title..." {...register("title")} />
      <p style={{ color: "red" }}>{errors.title?.message}</p>
      <textarea placeholder="Description..." {...register("description")} />
      <p style={{ color: "red" }}>{errors.description?.message}</p>
      <input type="submit" />
    </form>
  );
};
```

</details>

<details>
  <summary>80. Send data to Firebase</summary>

config/firebase.ts:

```tsx
// Import the functions you need from the SDKs you need
import { initializeApp } from "firebase/app";
import { getAuth, GoogleAuthProvider } from "firebase/auth";
import { getFirestore } from "firebase/firestore";
// TODO: Add SDKs for Firebase products that you want to use
// https://firebase.google.com/docs/web/setup#available-libraries

// Your web app's Firebase configuration
const firebaseConfig = {
  apiKey: "AIzaSyDdFw8SFSfGwmm3S5CBX5nFi7KMxd8GyyQ",
  authDomain: "pedro-app-8bd3b.firebaseapp.com",
  projectId: "pedro-app-8bd3b",
  storageBucket: "pedro-app-8bd3b.appspot.com",
  messagingSenderId: "679821378683",
  appId: "1:679821378683:web:54f00cc4f7433907150ede",
};

// Initialize Firebase
const app = initializeApp(firebaseConfig);

export const auth = getAuth(app);
export const provider = new GoogleAuthProvider();
export const db = getFirestore(app);
```

CreateForm.tsx:

```tsx
import { useForm } from "react-hook-form";
import * as yup from "yup";
import { yupResolver } from "@hookform/resolvers/yup";
import { addDoc, collection } from "firebase/firestore";
import { auth, db } from "../../config/firebase";
import { useAuthState } from "react-firebase-hooks/auth";
import { useNavigate } from "react-router-dom";

export const CreateForm = () => {
  const [user] = useAuthState(auth);
  const navigate = useNavigate();

  interface CreateFormData {
    title: string;
    description: string;
  }

  const schema = yup.object().shape({
    title: yup.string().required("You must add a Title."),
    description: yup.string().required("You must add a Description."),
  });

  const {
    register,
    handleSubmit,
    formState: { errors },
  } = useForm<CreateFormData>({
    resolver: yupResolver(schema),
  });

  const postsRef = collection(db, "posts");

  const onCreatePost = async (data: CreateFormData) => {
    await addDoc(postsRef, {
      ...data,
      username: user?.displayName,
      userId: user?.uid,
    });

    navigate("/");
  };

  return (
    <form onSubmit={handleSubmit(onCreatePost)}>
      <input placeholder="Title..." {...register("title")} />
      <p style={{ color: "red" }}>{errors.title?.message}</p>
      <textarea placeholder="Description..." {...register("description")} />
      <p style={{ color: "red" }}>{errors.description?.message}</p>
      <input type="submit" />
    </form>
  );
};
```

</details>

<details>
  <summary>81. Set Firebase Rules (Permissions)</summary>

```bs
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read, write: if false;
    }
  }
}
```

```bs
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow write, delete, update: if request.auth != null && request.auth.uid == request.resource.data.userId;
      allow read: if request.auth != null;
    }
  }
}
```

</details>

<details>
  <summary>82. Adding Styling to Form</summary>

App.css:

```css
.App {
  text-align: center;
}

body {
  margin: 0;
  padding: 0;
  font-family: Arial, Helvetica, sans-serif;
}

.navbar {
  width: 100%;
  height: 80px;
  background-color: slateblue;
  display: flex;
  align-items: center;
  justify-content: flex-end;
}

.navbar .links {
  text-align: center;
  margin-right: 50px;
}

.links a {
  color: white;
  text-decoration: none;
  border-bottom: 3px solid white;
  padding-bottom: 2px;
  margin: 10px;
}

.navbar .user {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-right: 50px;
}

.user p {
  font-size: 15px;
  margin-right: 10px;
  color: white;
}

.user img {
  font-size: 15px;
  border-radius: 50%;
}

input,
textarea {
  font-family: "Nunito", sans-serif;
}

.create-post {
  width: 100%;
  height: auto;
  display: flex;
  justify-content: center;
}

form {
  margin-top: 50px;
  padding: 30px 20px;
  width: 320px;
  border-radius: 7px;
  background-color: white;
  backdrop-filter: blur(5px);
  background-color: rgba(43, 0, 255, 0.588);
  overflow: hidden;
}

input,
textarea {
  padding: 8px 10px;
  margin: 3px 8px 16px 8px;
  background-color: rgba(222, 239, 248, 0.877);
  border: 0px transparent;
  border-radius: 5px;
  color: rgb(97, 4, 184);
  font-size: 16px;
  z-index: 1;
}

.submitForm:hover {
  cursor: pointer;
}

.main {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
```

</details>

<details>
  <summary>83. Rendering Contents in Home Page</summary>

main/Main.tsx:

```tsx
import { getDocs, collection } from "firebase/firestore";
import { useEffect, useState } from "react";
import { db } from "../../config/firebase";
import { Post } from "./Post";

export interface Posts {
  id: string;
  userId: string;
  title: string;
  username: string;
  description: string;
}

export const Main = () => {
  const [postsList, setPostsList] = useState<Posts[] | null>(null);
  const postsRef = collection(db, "posts");

  const getPosts = async () => {
    const data = await getDocs(postsRef);
    setPostsList(
      data.docs.map((doc) => ({ ...doc.data(), id: doc.id })) as Posts[]
    );
  };

  useEffect(() => {
    getPosts();
  }, []);

  return (
    <div>
      {postsList?.map((post) => (
        <Post post={post} key={post.id} />
      ))}
    </div>
  );
};
```

main/Post.tsx:

```tsx
import {
  addDoc,
  getDocs,
  collection,
  query,
  where,
  deleteDoc,
  doc,
} from "firebase/firestore";
import { useEffect, useState } from "react";
import { useAuthState } from "react-firebase-hooks/auth";
import { db, auth } from "../../config/firebase";
import { Posts as IPost } from "./Main";

interface Props {
  post: IPost;
}

interface Like {
  likeId: string;
  userId: string;
}

export const Post = (props: Props) => {
  const { post } = props;
  const [user] = useAuthState(auth);

  const [likes, setLikes] = useState<Like[] | null>(null);

  const likesRef = collection(db, "likes");

  const likesDoc = query(likesRef, where("postId", "==", post.id));

  const getLikes = async () => {
    const data = await getDocs(likesDoc);
    setLikes(
      data.docs.map((doc) => ({ userId: doc.data().userId, likeId: doc.id }))
    );
  };
  const addLike = async () => {
    try {
      const newDoc = await addDoc(likesRef, {
        userId: user?.uid,
        postId: post.id,
      });
      if (user) {
        setLikes((prev) =>
          prev
            ? [...prev, { userId: user.uid, likeId: newDoc.id }]
            : [{ userId: user.uid, likeId: newDoc.id }]
        );
      }
    } catch (err) {
      console.log(err);
    }
  };

  const removeLike = async () => {
    try {
      const likeToDeleteQuery = query(
        likesRef,
        where("postId", "==", post.id),
        where("userId", "==", user?.uid)
      );

      const likeToDeleteData = await getDocs(likeToDeleteQuery);
      const likeId = likeToDeleteData.docs[0].id;
      const likeToDelete = doc(db, "likes", likeId);
      await deleteDoc(likeToDelete);
      if (user) {
        setLikes(
          (prev) => prev && prev.filter((like) => like.likeId !== likeId)
        );
      }
    } catch (err) {
      console.log(err);
    }
  };

  const hasUserLiked = likes?.find((like) => like.userId === user?.uid);

  useEffect(() => {
    getLikes();
  }, []);

  return (
    <div>
      <div className="title">
        <h1> {post.title}</h1>
      </div>
      <div className="body">
        <p> {post.description} </p>
      </div>

      <div className="footer">
        <p> @{post.username} </p>
        <button onClick={hasUserLiked ? removeLike : addLike}>
          {hasUserLiked ? <>&#128078;</> : <>&#128077;</>}{" "}
        </button>
        {likes && <p> Likes: {likes?.length} </p>}
      </div>
    </div>
  );
};
```

Firebase Auth:

```bs
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow write, delete, update: if request.auth != null && request.auth.uid == request.resource.data.userId;
      allow read, delete: if request.auth != null;
    }
  }
}
```

</details>

<details>
  <summary>84. Deploy Firebase</summary>

```bs
Firebase -> Build -> Hosting -> Get Started
```

```bs
npm install -g firebase-tools
```

```bs
npm run build
```

Git:

```bs
#Just follow next steps in console terminal ;)
git init	#Initialize git in folder
git add .	#add all files of folder to be pushed
git commit -m "First commit"	#add first commit
git remote add origin remote_repository_URL #replace with your remote repo url
git remote -v	#verify that your remote repository url is properly found
git branch -M main  #change main branch name to main
git push --force origin main	#force pushing your project into github repo

//make sure you're on the local branch, then:
git pull origin YourRemoteBranch
//which is the same as:
git fetch origin YourRemoteBranch
git merge origin/YourRemoteBranch

git push origin --delete feature/login
git push origin --delete master

# Push newly created local branch to remote
git push --set-upstream origin <branch name>
git push --force origin main //force pushing to remote github repo
git push -u origin new_branch

github@branch/c/remote/push  (new-branch)
git clone https://github.com/learn-git-fast/git-branch-examples.git
cd git*
git checkout -b new-branch

github@branch/c/remote/push (new-branch)
git branch -a
touch devolution.jpg
git add .
git commit -m "Are we not gender neutral people? We are Devo?"
git push --set-upstream origin new-branch

git pull --rebase origin main
# Resolve merge conflicts if needed
git push origin main
```

```bs
firebase login
```

```bs
firebase init
```

```bs
firebase deploy
```

</details>

### [3-FIREBASE 9 TUTORIAL - NET NINJA](#)

+INTRODUCTION

<details>
  <summary>85. Setting up Webpack</summary>

```bs
dist -> index.html
src -> index.js
```

Create package.json file:

```bs
npm init -y
```

Install webpack:

```bs
npm i webpack webpack-cli -D
npm i webpack webpack-cli webpack-dev-server html-webpack-plugin -D
```

watch.config.js:

```js
const path = require("path");

module.exports = {
  mode: "development",
  entry: "./src/index.js",
  output: {
    path: path.resolve(__dirname, "dist"),
    filename: "bundle.js",
  },
  watch: true,
};
```

```js
const path = require("path");

module.exports = {
  mode: "development",
  entry: "./src/index.js",
  output: {
    path: path.join(__dirname, "dist"),
    filename: "bundle.js",
    sourceMapFilename: "bundle.js.map",
  },
  devtool: "source-map",
  watch: true,
};
```

package.json:

```bs
"scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "build": "webpack"
},
```

```js
{
  "name": "firebase-netninja",
  "version": "1.0.0",
  "description": "",
  "main": "webpack.config.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "build": "webpack"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "devDependencies": {
    "webpack": "^5.75.0",
    "webpack-cli": "^5.0.0"
  }
}
```

Run Webpack:

```bs
npm run build
```

index.html:

```bs
<script src="bundle.js"></script>
```

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Firebase 9</title>
  </head>
  <body>
    <h1>Getting started with firebase 9</h1>
    <script src="bundle.js"></script>
  </body>
</html>
```

</details>

<details>
  <summary>86. Create Firebase Project</summary>

Install Firebase:

```bs
npm install firebase
```

index.js:

```js
import { initializeApp } from "firebase/app";

const firebaseConfig = {
  apiKey: "AIzaSyAkkJyg-3xzVITPx6FU3wDaRKR4OGpmzSs",
  authDomain: "fir-9-ninja-30222.firebaseapp.com",
  projectId: "fir-9-ninja-30222",
  storageBucket: "fir-9-ninja-30222.appspot.com",
  messagingSenderId: "700813053129",
  appId: "1:700813053129:web:165552244a3a57a0775118",
};

// Initialize Firebase
const app = initializeApp(firebaseConfig);
```

</details>

<details>
  <summary>87. Connect Firebase App</summary>

index.js:

```js
import { initializeApp } from "firebase/app";
import { getFirestore, collection, getDocs } from "firebase/firestore";

const firebaseConfig = {
  apiKey: "AIzaSyAkkJyg-3xzVITPx6FU3wDaRKR4OGpmzSs",
  authDomain: "fir-9-ninja-30222.firebaseapp.com",
  projectId: "fir-9-ninja-30222",
  storageBucket: "fir-9-ninja-30222.appspot.com",
  messagingSenderId: "700813053129",
  appId: "1:700813053129:web:165552244a3a57a0775118",
};

// Initialize Firebase App
initializeApp(firebaseConfig);

// init db services
const db = getFirestore();

// collection ref
const colRef = collection(db, "books");

// get collection data
getDocs(colRef)
  .then((snapshot) => {
    // console.log(snapshot.docs)
    let books = [];
    snapshot.docs.forEach((doc) => {
      books.push({ ...doc.data(), id: doc.id });
    });
    console.log(books);
  })
  .catch((err) => {
    console.log(err.message);
  });
```

```js
// author: "patrick bamford"
// id: "5t16O84fjMNOU73F1pC5"
// title: "the fall of snowden"

// author: "gary nerds"
// id: "OKNxNdBC2ncnpa16SjDB"
// title: "the cloud"
```

</details>

<details>
  <summary>88. Adding and Deleting Documents</summary>

index.html:

```js
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Firebase 9</title>
</head>
<body>
  <h1>Getting Started with Firebase 9</h1>

  <h2>Firebase Firestore</h2>

  <form class="add">
    <label for="title">Title:</label>
    <input type="text" name="title" required>
    <label for="author">Author:</label>
    <input type="text" name="author" required>

    <button>add a new book</button>
  </form>

  <form class="delete">
    <label for="id">Document id:</label>
    <input type="text" name="id" required>

    <button>delete a book</button>
  </form>

  <script src="bundle.js"></script>
</body>
</html>
```

index.js:

```js
import { initializeApp } from "firebase/app";
import {
  getFirestore,
  collection,
  getDocs,
  addDoc,
  deleteDoc,
  doc,
} from "firebase/firestore";

const firebaseConfig = {
  apiKey: "AIzaSyAkkJyg-3xzVITPx6FU3wDaRKR4OGpmzSs",
  authDomain: "fir-9-ninja-30222.firebaseapp.com",
  projectId: "fir-9-ninja-30222",
  storageBucket: "fir-9-ninja-30222.appspot.com",
  messagingSenderId: "700813053129",
  appId: "1:700813053129:web:165552244a3a57a0775118",
};

// Initialize Firebase App
initializeApp(firebaseConfig);

// init db services
const db = getFirestore();

// collection ref
const colRef = collection(db, "books");

// get collection data
getDocs(colRef)
  .then((snapshot) => {
    // console.log(snapshot.docs)
    let books = [];
    snapshot.docs.forEach((doc) => {
      books.push({ ...doc.data(), id: doc.id });
    });
    console.log(books);
  })
  .catch((err) => {
    console.log(err.message);
  });

// adding docs
const addBookForm = document.querySelector(".add");
addBookForm.addEventListener("submit", (e) => {
  e.preventDefault();

  addDoc(colRef, {
    title: addBookForm.title.value,
    author: addBookForm.author.value,
  }).then(() => {
    addBookForm.reset();
  });
});

// deleting docs
const deleteBookForm = document.querySelector(".delete");
deleteBookForm.addEventListener("submit", (e) => {
  e.preventDefault();

  const docRef = doc(db, "books", deleteBookForm.id.value);

  deleteDoc(docRef).then(() => {
    deleteBookForm.reset();
  });
});
```

</details>

<details>
  <summary>89. Real Time onSnapshot Listener </summary>

index.js:

```js
import { initializeApp } from "firebase/app";
import {
  getFirestore,
  collection,
  onSnapshot,
  addDoc,
  deleteDoc,
  doc,
} from "firebase/firestore";

const firebaseConfig = {
  apiKey: "AIzaSyAkkJyg-3xzVITPx6FU3wDaRKR4OGpmzSs",
  authDomain: "fir-9-ninja-30222.firebaseapp.com",
  projectId: "fir-9-ninja-30222",
  storageBucket: "fir-9-ninja-30222.appspot.com",
  messagingSenderId: "700813053129",
  appId: "1:700813053129:web:165552244a3a57a0775118",
};

// Initialize Firebase App
initializeApp(firebaseConfig);

// init db services
const db = getFirestore();

// collection ref
const colRef = collection(db, "books");

// realtime collection data
onSnapshot(colRef, (snapshot) => {
  let books = [];
  snapshot.docs.forEach((doc) => {
    books.push({ ...doc.data(), id: doc.id });
  });
  console.log(books);
});

// adding docs
const addBookForm = document.querySelector(".add");
addBookForm.addEventListener("submit", (e) => {
  e.preventDefault();

  addDoc(colRef, {
    title: addBookForm.title.value,
    author: addBookForm.author.value,
  }).then(() => {
    addBookForm.reset();
  });
});

// deleting docs
const deleteBookForm = document.querySelector(".delete");
deleteBookForm.addEventListener("submit", (e) => {
  e.preventDefault();

  const docRef = doc(db, "books", deleteBookForm.id.value);

  deleteDoc(docRef).then(() => {
    deleteBookForm.reset();
  });
});
```

</details>

<details>
  <summary>90. Firebase Where Queries</summary>

```js
import { initializeApp } from "firebase/app";
import {
  getFirestore,
  collection,
  onSnapshot,
  addDoc,
  deleteDoc,
  doc,
  query,
  where,
} from "firebase/firestore";

const firebaseConfig = {
  apiKey: "AIzaSyAkkJyg-3xzVITPx6FU3wDaRKR4OGpmzSs",
  authDomain: "fir-9-ninja-30222.firebaseapp.com",
  projectId: "fir-9-ninja-30222",
  storageBucket: "fir-9-ninja-30222.appspot.com",
  messagingSenderId: "700813053129",
  appId: "1:700813053129:web:165552244a3a57a0775118",
};

// Initialize Firebase App
initializeApp(firebaseConfig);

// init db services
const db = getFirestore();

// collection ref
const colRef = collection(db, "books");

// queries
const q = query(colRef, where("author", "==", "Ashley Stampley"));

// realtime collection data
onSnapshot(q, (snapshot) => {
  let books = [];
  snapshot.docs.forEach((doc) => {
    books.push({ ...doc.data(), id: doc.id });
  });
  console.log(books);
});

// adding docs
const addBookForm = document.querySelector(".add");
addBookForm.addEventListener("submit", (e) => {
  e.preventDefault();

  addDoc(colRef, {
    title: addBookForm.title.value,
    author: addBookForm.author.value,
  }).then(() => {
    addBookForm.reset();
  });
});

// deleting docs
const deleteBookForm = document.querySelector(".delete");
deleteBookForm.addEventListener("submit", (e) => {
  e.preventDefault();

  const docRef = doc(db, "books", deleteBookForm.id.value);

  deleteDoc(docRef).then(() => {
    deleteBookForm.reset();
  });
});
```

</details>

<details>
  <summary>91. Ordering by Property</summary>

```bs
// queries
const q = query(colRef, where("author", "==", "dave ramsey"), orderBy("title", "asc"))
```

```js
import { initializeApp } from "firebase/app";
import {
  getFirestore,
  collection,
  onSnapshot,
  addDoc,
  deleteDoc,
  doc,
  query,
  where,
  orderBy,
} from "firebase/firestore";

const firebaseConfig = {
  apiKey: "AIzaSyAkkJyg-3xzVITPx6FU3wDaRKR4OGpmzSs",
  authDomain: "fir-9-ninja-30222.firebaseapp.com",
  projectId: "fir-9-ninja-30222",
  storageBucket: "fir-9-ninja-30222.appspot.com",
  messagingSenderId: "700813053129",
  appId: "1:700813053129:web:165552244a3a57a0775118",
};

// Initialize Firebase App
initializeApp(firebaseConfig);

// init db services
const db = getFirestore();

// collection ref
const colRef = collection(db, "books");

// queries
const q = query(
  colRef,
  where("author", "==", "dave ramsey"),
  orderBy("title", "asc")
);

// realtime collection data
onSnapshot(q, (snapshot) => {
  let books = [];
  snapshot.docs.forEach((doc) => {
    books.push({ ...doc.data(), id: doc.id });
  });
  console.log(books);
});

// adding docs
const addBookForm = document.querySelector(".add");
addBookForm.addEventListener("submit", (e) => {
  e.preventDefault();

  addDoc(colRef, {
    title: addBookForm.title.value,
    author: addBookForm.author.value,
  }).then(() => {
    addBookForm.reset();
  });
});

// deleting docs
const deleteBookForm = document.querySelector(".delete");
deleteBookForm.addEventListener("submit", (e) => {
  e.preventDefault();

  const docRef = doc(db, "books", deleteBookForm.id.value);

  deleteDoc(docRef).then(() => {
    deleteBookForm.reset();
  });
});
```

</details>

<details>
  <summary>92. Ordering by Timestamps</summary>

```bs
// queries
const q = query(
  colRef,
  where("author", "==", "dave ramsey"),
  orderBy("createdAt")
);
```

```js
import { initializeApp } from "firebase/app";
import {
  getFirestore,
  collection,
  onSnapshot,
  addDoc,
  deleteDoc,
  doc,
  query,
  where,
  orderBy,
  serverTimestamp,
} from "firebase/firestore";

const firebaseConfig = {
  apiKey: "AIzaSyAkkJyg-3xzVITPx6FU3wDaRKR4OGpmzSs",
  authDomain: "fir-9-ninja-30222.firebaseapp.com",
  projectId: "fir-9-ninja-30222",
  storageBucket: "fir-9-ninja-30222.appspot.com",
  messagingSenderId: "700813053129",
  appId: "1:700813053129:web:165552244a3a57a0775118",
};

// Initialize Firebase App
initializeApp(firebaseConfig);

// init db services
const db = getFirestore();

// collection ref
const colRef = collection(db, "books");

// queries
const q = query(
  colRef,
  where("author", "==", "dave ramsey"),
  orderBy("createdAt")
);

// realtime collection data
onSnapshot(q, (snapshot) => {
  let books = [];
  snapshot.docs.forEach((doc) => {
    books.push({ ...doc.data(), id: doc.id });
  });
  console.log(books);
});

// adding docs
const addBookForm = document.querySelector(".add");
addBookForm.addEventListener("submit", (e) => {
  e.preventDefault();

  addDoc(colRef, {
    title: addBookForm.title.value,
    author: addBookForm.author.value,
    createdAt: serverTimestamp(),
  }).then(() => {
    addBookForm.reset();
  });
});

// deleting docs
const deleteBookForm = document.querySelector(".delete");
deleteBookForm.addEventListener("submit", (e) => {
  e.preventDefault();

  const docRef = doc(db, "books", deleteBookForm.id.value);

  deleteDoc(docRef).then(() => {
    deleteBookForm.reset();
  });
});
```

</details>

<details>
  <summary>93. Fetching a Single Document</summary>

```bs
// fetching a single document (& realtime)
const docRef = doc(db, "books", "M3bROLjs0pyabVoNvUaK");

// getDoc(docRef)
//   .then(doc => {
//     console.log(doc.data(), doc.id)
//   })

onSnapshot(docRef, (doc) => {
  console.log(doc.data(), doc.id);
});
```

```js
import { initializeApp } from "firebase/app";
import {
  getFirestore,
  collection,
  onSnapshot,
  addDoc,
  deleteDoc,
  doc,
  query,
  where,
  orderBy,
  serverTimestamp,
  getDoc,
} from "firebase/firestore";

const firebaseConfig = {
  apiKey: "AIzaSyAkkJyg-3xzVITPx6FU3wDaRKR4OGpmzSs",
  authDomain: "fir-9-ninja-30222.firebaseapp.com",
  projectId: "fir-9-ninja-30222",
  storageBucket: "fir-9-ninja-30222.appspot.com",
  messagingSenderId: "700813053129",
  appId: "1:700813053129:web:165552244a3a57a0775118",
};

// Initialize Firebase App
initializeApp(firebaseConfig);

// init db services
const db = getFirestore();

// collection ref
const colRef = collection(db, "books");

// queries
const q = query(
  colRef,
  where("author", "==", "dave ramsey"),
  orderBy("createdAt")
);

// realtime collection data
onSnapshot(q, (snapshot) => {
  let books = [];
  snapshot.docs.forEach((doc) => {
    books.push({ ...doc.data(), id: doc.id });
  });
  console.log(books);
});

// adding docs
const addBookForm = document.querySelector(".add");
addBookForm.addEventListener("submit", (e) => {
  e.preventDefault();

  addDoc(colRef, {
    title: addBookForm.title.value,
    author: addBookForm.author.value,
    createdAt: serverTimestamp(),
  }).then(() => {
    addBookForm.reset();
  });
});

// deleting docs
const deleteBookForm = document.querySelector(".delete");
deleteBookForm.addEventListener("submit", (e) => {
  e.preventDefault();

  const docRef = doc(db, "books", deleteBookForm.id.value);

  deleteDoc(docRef).then(() => {
    deleteBookForm.reset();
  });
});

// fetching a single document (& realtime)
const docRef = doc(db, "books", "M3bROLjs0pyabVoNvUaK");

// getDoc(docRef)
//   .then(doc => {
//     console.log(doc.data(), doc.id)
//   })

onSnapshot(docRef, (doc) => {
  console.log(doc.data(), doc.id);
});
```

</details>

<details>
  <summary>94. Updating Documents</summary>

index.html:

```html
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Firebase 9</title>
  </head>
  <body>
    <h1>Getting Started with Firebase 9</h1>

    <h2>Firebase Firestore</h2>

    <form class="add">
      <label for="title">Title:</label>
      <input type="text" name="title" required />
      <label for="author">Author:</label>
      <input type="text" name="author" required />

      <button>add a new book</button>
    </form>

    <form class="delete">
      <label for="id">Document id:</label>
      <input type="text" name="id" required />

      <button>delete a book</button>
    </form>

    <form class="update">
      <label for="id">Document id:</label>
      <input type="text" name="id" required />

      <button>update a book</button>
    </form>

    <script src="bundle.js"></script>
  </body>
</html>
```

index.js:

```bs
// updating a document
const updateForm = document.querySelector('.update')
updateForm.addEventListener('submit', (e) => {
  e.preventDefault()

  let docRef = doc(db, 'books', updateForm.id.value)

  updateDoc(docRef, {
    title: 'updated title'
  })
  .then(() => {
    updateForm.reset()
  })
})
```

```js
import { initializeApp } from "firebase/app";
import {
  getFirestore,
  collection,
  onSnapshot,
  addDoc,
  deleteDoc,
  doc,
  query,
  where,
  orderBy,
  serverTimestamp,
  getDoc,
  updateDoc,
} from "firebase/firestore";

const firebaseConfig = {
  apiKey: "AIzaSyAkkJyg-3xzVITPx6FU3wDaRKR4OGpmzSs",
  authDomain: "fir-9-ninja-30222.firebaseapp.com",
  projectId: "fir-9-ninja-30222",
  storageBucket: "fir-9-ninja-30222.appspot.com",
  messagingSenderId: "700813053129",
  appId: "1:700813053129:web:165552244a3a57a0775118",
};

// Initialize Firebase App
initializeApp(firebaseConfig);

// init db services
const db = getFirestore();

// collection ref
const colRef = collection(db, "books");

// queries
const q = query(
  colRef,
  where("author", "==", "dave ramsey"),
  orderBy("createdAt")
);

// realtime collection data
onSnapshot(q, (snapshot) => {
  let books = [];
  snapshot.docs.forEach((doc) => {
    books.push({ ...doc.data(), id: doc.id });
  });
  console.log(books);
});

// adding docs
const addBookForm = document.querySelector(".add");
addBookForm.addEventListener("submit", (e) => {
  e.preventDefault();

  addDoc(colRef, {
    title: addBookForm.title.value,
    author: addBookForm.author.value,
    createdAt: serverTimestamp(),
  }).then(() => {
    addBookForm.reset();
  });
});

// deleting docs
const deleteBookForm = document.querySelector(".delete");
deleteBookForm.addEventListener("submit", (e) => {
  e.preventDefault();

  const docRef = doc(db, "books", deleteBookForm.id.value);

  deleteDoc(docRef).then(() => {
    deleteBookForm.reset();
  });
});

// fetching a single document (& realtime)
const docRef = doc(db, "books", "M3bROLjs0pyabVoNvUaK");

// getDoc(docRef)
//   .then(doc => {
//     console.log(doc.data(), doc.id)
//   })

onSnapshot(docRef, (doc) => {
  console.log(doc.data(), doc.id);
});

// updating a document
const updateForm = document.querySelector(".update");
updateForm.addEventListener("submit", (e) => {
  e.preventDefault();

  let docRef = doc(db, "books", updateForm.id.value);

  updateDoc(docRef, {
    title: "updated title",
  }).then(() => {
    updateForm.reset();
  });
});
```

</details>

<details>
  <summary>95. Signing up Users</summary>

index.html:

```html
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Firebase 9</title>
  </head>
  <body>
    <h1>Getting Started with Firebase 9</h1>

    <h2>Firebase Firestore</h2>

    <form class="add">
      <label for="title">Title:</label>
      <input type="text" name="title" required />
      <label for="author">Author:</label>
      <input type="text" name="author" required />

      <button>add a new book</button>
    </form>

    <form class="delete">
      <label for="id">Document id:</label>
      <input type="text" name="id" required />

      <button>delete a book</button>
    </form>

    <form class="update">
      <label for="id">Document id:</label>
      <input type="text" name="id" required />

      <button>update a book</button>
    </form>

    <h2>Firebase Auth</h2>

    <form class="signup">
      <label for="email">email:</label>
      <input type="email" name="email" />
      <label for="password">password:</label>
      <input type="password" name="password" />
      <button>signup</button>
    </form>

    <script src="bundle.js"></script>
  </body>
</html>
```

index.js:

```bs
import {
  getAuth,
  createUserWithEmailAndPassword,
} from 'firebase/auth'
```

```bs
// init db services
const db = getFirestore()
const auth = getAuth()
```

```bs
// signing users up
const signupForm = document.querySelector('.signup')
signupForm.addEventListener('submit', (e) => {
  e.preventDefault()

  const email = signupForm.email.value
  const password = signupForm.password.value

  createUserWithEmailAndPassword(auth, email, password)
    .then(cred => {
      console.log('user created:', cred.user)
      signupForm.reset()
    })
    .catch(err => {
      console.log(err.message)
    })
})
```

```js
import { initializeApp } from "firebase/app";
import {
  getFirestore,
  collection,
  onSnapshot,
  addDoc,
  deleteDoc,
  doc,
  query,
  where,
  orderBy,
  serverTimestamp,
  getDoc,
  updateDoc,
} from "firebase/firestore";
import { getAuth, createUserWithEmailAndPassword } from "firebase/auth";

const firebaseConfig = {
  apiKey: "AIzaSyAkkJyg-3xzVITPx6FU3wDaRKR4OGpmzSs",
  authDomain: "fir-9-ninja-30222.firebaseapp.com",
  projectId: "fir-9-ninja-30222",
  storageBucket: "fir-9-ninja-30222.appspot.com",
  messagingSenderId: "700813053129",
  appId: "1:700813053129:web:165552244a3a57a0775118",
};

// Initialize Firebase App
initializeApp(firebaseConfig);

// init db services
const db = getFirestore();
const auth = getAuth();

// collection ref
const colRef = collection(db, "books");

// queries
const q = query(
  colRef,
  where("author", "==", "dave ramsey"),
  orderBy("createdAt")
);

// realtime collection data
onSnapshot(q, (snapshot) => {
  let books = [];
  snapshot.docs.forEach((doc) => {
    books.push({ ...doc.data(), id: doc.id });
  });
  console.log(books);
});

// adding docs
const addBookForm = document.querySelector(".add");
addBookForm.addEventListener("submit", (e) => {
  e.preventDefault();

  addDoc(colRef, {
    title: addBookForm.title.value,
    author: addBookForm.author.value,
    createdAt: serverTimestamp(),
  }).then(() => {
    addBookForm.reset();
  });
});

// deleting docs
const deleteBookForm = document.querySelector(".delete");
deleteBookForm.addEventListener("submit", (e) => {
  e.preventDefault();

  const docRef = doc(db, "books", deleteBookForm.id.value);

  deleteDoc(docRef).then(() => {
    deleteBookForm.reset();
  });
});

// fetching a single document (& realtime)
const docRef = doc(db, "books", "gGu4P9x0ZHK9SspA1d9j");

onSnapshot(docRef, (doc) => {
  console.log(doc.data(), doc.id);
});

// updating a document
const updateForm = document.querySelector(".update");
updateForm.addEventListener("submit", (e) => {
  e.preventDefault();

  let docRef = doc(db, "books", updateForm.id.value);

  updateDoc(docRef, {
    title: "updated title",
  }).then(() => {
    updateForm.reset();
  });
});

// signing users up
const signupForm = document.querySelector(".signup");
signupForm.addEventListener("submit", (e) => {
  e.preventDefault();

  const email = signupForm.email.value;
  const password = signupForm.password.value;

  createUserWithEmailAndPassword(auth, email, password)
    .then((cred) => {
      console.log("user created:", cred.user);
      signupForm.reset();
    })
    .catch((err) => {
      console.log(err.message);
    });
});
```

</details>

<details>
  <summary>96. Logging in and out </summary>

index.html:

```html
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Firebase 9</title>
  </head>
  <body>
    <h1>Getting Started with Firebase 9</h1>

    <h2>Firebase Firestore</h2>

    <form class="add">
      <label for="title">Title:</label>
      <input type="text" name="title" required />
      <label for="author">Author:</label>
      <input type="text" name="author" required />

      <button>add a new book</button>
    </form>

    <form class="delete">
      <label for="id">Document id:</label>
      <input type="text" name="id" required />

      <button>delete a book</button>
    </form>

    <form class="update">
      <label for="id">Document id:</label>
      <input type="text" name="id" required />

      <button>update a book</button>
    </form>

    <h2>Firebase Auth</h2>

    <form class="signup">
      <label for="email">email:</label>
      <input type="email" name="email" />
      <label for="password">password:</label>
      <input type="password" name="password" />
      <button>signup</button>
    </form>

    <form class="login">
      <label for="email">email:</label>
      <input type="email" name="email" />
      <label for="password">password:</label>
      <input type="password" name="password" />
      <button>login</button>
    </form>

    <button class="logout">logout</button>

    <script src="bundle.js"></script>
  </body>
</html>
```

index.js:

```bs
import {
  getAuth,
  createUserWithEmailAndPassword,
  signInWithEmailAndPassword, signOut
} from 'firebase/auth'
```

```bs
// logging in and out
const logoutButton = document.querySelector('.logout')
logoutButton.addEventListener('click', () => {
  signOut(auth)
    .then(() => {
      console.log('user signed out')
    })
    .catch(err => {
      console.log(err.message)
    })
})

const loginForm = document.querySelector('.login')
loginForm.addEventListener('submit', (e) => {
  e.preventDefault()

  const email = loginForm.email.value
  const password = loginForm.password.value

  signInWithEmailAndPassword(auth, email, password)
    .then(cred => {
      console.log('user logged in:', cred.user)
      loginForm.reset()
    })
    .catch(err => {
      console.log(err.message)
    })
})
```

```js
import { initializeApp } from "firebase/app";
import {
  getFirestore,
  collection,
  onSnapshot,
  addDoc,
  deleteDoc,
  doc,
  query,
  where,
  orderBy,
  serverTimestamp,
  updateDoc,
} from "firebase/firestore";
import {
  getAuth,
  createUserWithEmailAndPassword,
  signInWithEmailAndPassword,
  signOut,
} from "firebase/auth";

const firebaseConfig = {
  apiKey: "AIzaSyDmXgb_58lO7aK_ujN37pGlNxzWGEU0YpI",
  authDomain: "fb9-sandbox.firebaseapp.com",
  projectId: "fb9-sandbox",
  storageBucket: "fb9-sandbox.appspot.com",
  messagingSenderId: "867529587246",
  appId: "1:867529587246:web:dc754ab7840c737f47bdbf",
};

// init firebase
initializeApp(firebaseConfig);

// init services
const db = getFirestore();
const auth = getAuth();

// collection ref
const colRef = collection(db, "books");

// queries
const q = query(
  colRef,
  where("author", "==", "patrick rothfuss"),
  orderBy("createdAt")
);

// realtime collection data
onSnapshot(q, (snapshot) => {
  let books = [];
  snapshot.docs.forEach((doc) => {
    books.push({ ...doc.data(), id: doc.id });
  });
  console.log(books);
});

// adding docs
const addBookForm = document.querySelector(".add");
addBookForm.addEventListener("submit", (e) => {
  e.preventDefault();

  addDoc(colRef, {
    title: addBookForm.title.value,
    author: addBookForm.author.value,
    createdAt: serverTimestamp(),
  }).then(() => {
    addBookForm.reset();
  });
});

// deleting docs
const deleteBookForm = document.querySelector(".delete");
deleteBookForm.addEventListener("submit", (e) => {
  e.preventDefault();

  const docRef = doc(db, "books", deleteBookForm.id.value);

  deleteDoc(docRef).then(() => {
    deleteBookForm.reset();
  });
});

// fetching a single document (& realtime)
const docRef = doc(db, "books", "gGu4P9x0ZHK9SspA1d9j");

onSnapshot(docRef, (doc) => {
  console.log(doc.data(), doc.id);
});

// updating a document
const updateForm = document.querySelector(".update");
updateForm.addEventListener("submit", (e) => {
  e.preventDefault();

  let docRef = doc(db, "books", updateForm.id.value);

  updateDoc(docRef, {
    title: "updated title",
  }).then(() => {
    updateForm.reset();
  });
});

// signing users up
const signupForm = document.querySelector(".signup");
signupForm.addEventListener("submit", (e) => {
  e.preventDefault();

  const email = signupForm.email.value;
  const password = signupForm.password.value;

  createUserWithEmailAndPassword(auth, email, password)
    .then((cred) => {
      console.log("user created:", cred.user);
      signupForm.reset();
    })
    .catch((err) => {
      console.log(err.message);
    });
});

// logging in and out
const logoutButton = document.querySelector(".logout");
logoutButton.addEventListener("click", () => {
  signOut(auth)
    .then(() => {
      console.log("user signed out");
    })
    .catch((err) => {
      console.log(err.message);
    });
});

const loginForm = document.querySelector(".login");
loginForm.addEventListener("submit", (e) => {
  e.preventDefault();

  const email = loginForm.email.value;
  const password = loginForm.password.value;

  signInWithEmailAndPassword(auth, email, password)
    .then((cred) => {
      console.log("user logged in:", cred.user);
      loginForm.reset();
    })
    .catch((err) => {
      console.log(err.message);
    });
});
```

</details>

<details>
  <summary>97. Subscribing to Auth Changes</summary>

index.js:

```bs
import {
  getAuth,
  createUserWithEmailAndPassword,
  signInWithEmailAndPassword, signOut, onAuthStateChanged
} from 'firebase/auth'
```

```bs
// subscribing to auth changes
onAuthStateChanged(auth, (user) => {
  console.log('user status changed:', user)
})
```

```js
import { initializeApp } from "firebase/app";
import {
  getFirestore,
  collection,
  onSnapshot,
  addDoc,
  deleteDoc,
  doc,
  query,
  where,
  orderBy,
  serverTimestamp,
  getDoc,
  updateDoc,
} from "firebase/firestore";
import {
  getAuth,
  createUserWithEmailAndPassword,
  signInWithEmailAndPassword,
  signOut,
  onAuthStateChanged,
} from "firebase/auth";

const firebaseConfig = {
  apiKey: "AIzaSyAkkJyg-3xzVITPx6FU3wDaRKR4OGpmzSs",
  authDomain: "fir-9-ninja-30222.firebaseapp.com",
  projectId: "fir-9-ninja-30222",
  storageBucket: "fir-9-ninja-30222.appspot.com",
  messagingSenderId: "700813053129",
  appId: "1:700813053129:web:165552244a3a57a0775118",
};

// Initialize Firebase App
initializeApp(firebaseConfig);

// init db services
const db = getFirestore();
const auth = getAuth();

// collection ref
const colRef = collection(db, "books");

// queries
const q = query(
  colRef,
  where("author", "==", "dave ramsey"),
  orderBy("createdAt")
);

// realtime collection data
onSnapshot(q, (snapshot) => {
  let books = [];
  snapshot.docs.forEach((doc) => {
    books.push({ ...doc.data(), id: doc.id });
  });
  console.log(books);
});

// adding docs
const addBookForm = document.querySelector(".add");
addBookForm.addEventListener("submit", (e) => {
  e.preventDefault();

  addDoc(colRef, {
    title: addBookForm.title.value,
    author: addBookForm.author.value,
    createdAt: serverTimestamp(),
  }).then(() => {
    addBookForm.reset();
  });
});

// deleting docs
const deleteBookForm = document.querySelector(".delete");
deleteBookForm.addEventListener("submit", (e) => {
  e.preventDefault();

  const docRef = doc(db, "books", deleteBookForm.id.value);

  deleteDoc(docRef).then(() => {
    deleteBookForm.reset();
  });
});

// fetching a single document (& realtime)
const docRef = doc(db, "books", "gGu4P9x0ZHK9SspA1d9j");

onSnapshot(docRef, (doc) => {
  console.log(doc.data(), doc.id);
});

// updating a document
const updateForm = document.querySelector(".update");
updateForm.addEventListener("submit", (e) => {
  e.preventDefault();

  let docRef = doc(db, "books", updateForm.id.value);

  updateDoc(docRef, {
    title: "updated title",
  }).then(() => {
    updateForm.reset();
  });
});

// signing users up
const signupForm = document.querySelector(".signup");
signupForm.addEventListener("submit", (e) => {
  e.preventDefault();

  const email = signupForm.email.value;
  const password = signupForm.password.value;

  createUserWithEmailAndPassword(auth, email, password)
    .then((cred) => {
      console.log("user created:", cred.user);
      signupForm.reset();
    })
    .catch((err) => {
      console.log(err.message);
    });
});

// logging in and out
const logoutButton = document.querySelector(".logout");
logoutButton.addEventListener("click", () => {
  signOut(auth)
    .then(() => {
      console.log("user signed out");
    })
    .catch((err) => {
      console.log(err.message);
    });
});

const loginForm = document.querySelector(".login");
loginForm.addEventListener("submit", (e) => {
  e.preventDefault();

  const email = loginForm.email.value;
  const password = loginForm.password.value;

  signInWithEmailAndPassword(auth, email, password)
    .then((cred) => {
      console.log("user logged in:", cred.user);
      loginForm.reset();
    })
    .catch((err) => {
      console.log(err.message);
    });
});

// subscribing to auth changes
onAuthStateChanged(auth, (user) => {
  console.log("user status changed:", user);
});
```

</details>

<details>
  <summary>98. Unsubscribing from Changes</summary>

index.html:

```bs
  <button class="unsub">unsubscribe from db/auth changes</button>
```

```html
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Firebase 9</title>
  </head>
  <body>
    <h1>Getting Started with Firebase 9</h1>

    <h2>Firebase Firestore</h2>

    <form class="add">
      <label for="title">Title:</label>
      <input type="text" name="title" required />
      <label for="author">Author:</label>
      <input type="text" name="author" required />

      <button>add a new book</button>
    </form>

    <form class="delete">
      <label for="id">Document id:</label>
      <input type="text" name="id" required />

      <button>delete a book</button>
    </form>

    <form class="update">
      <label for="id">Document id:</label>
      <input type="text" name="id" required />

      <button>update a book</button>
    </form>

    <h2>Firebase Auth</h2>

    <form class="signup">
      <label for="email">email:</label>
      <input type="email" name="email" />
      <label for="password">password:</label>
      <input type="password" name="password" />
      <button>signup</button>
    </form>

    <form class="login">
      <label for="email">email:</label>
      <input type="email" name="email" />
      <label for="password">password:</label>
      <input type="password" name="password" />
      <button>login</button>
    </form>

    <button class="logout">logout</button>

    <h2>Unsubscribing</h2>
    <button class="unsub">unsubscribe from db/auth changes</button>

    <script src="bundle.js"></script>
  </body>
</html>
```

index.js:

```bs
// realtime collection data
const unsubCol = onSnapshot(q, (snapshot) => {
  let books = []
  snapshot.docs.forEach(doc => {
    books.push({ ...doc.data(), id: doc.id })
  })
  console.log(books)
})

// fetching a single document (& realtime)
const docRef = doc(db, 'books', 'gGu4P9x0ZHK9SspA1d9j')

const unsubDoc = onSnapshot(docRef, (doc) => {
  console.log(doc.data(), doc.id)
})

// subscribing to auth changes
const unsubAuth = onAuthStateChanged(auth, (user) => {
  console.log('user status changed:', user)
})

// unsubscribing from changes (auth & db)
const unsubButton = document.querySelector('.unsub')
unsubButton.addEventListener('click', () => {
  console.log('unsubscribing')
  unsubCol()
  unsubDoc()
  unsubAuth()
})
```

```js
import { initializeApp } from "firebase/app";
import {
  getFirestore,
  collection,
  onSnapshot,
  addDoc,
  deleteDoc,
  doc,
  query,
  where,
  orderBy,
  serverTimestamp,
  updateDoc,
} from "firebase/firestore";
import {
  getAuth,
  createUserWithEmailAndPassword,
  signInWithEmailAndPassword,
  signOut,
  onAuthStateChanged,
} from "firebase/auth";

const firebaseConfig = {
  apiKey: "AIzaSyDmXgb_58lO7aK_ujN37pGlNxzWGEU0YpI",
  authDomain: "fb9-sandbox.firebaseapp.com",
  projectId: "fb9-sandbox",
  storageBucket: "fb9-sandbox.appspot.com",
  messagingSenderId: "867529587246",
  appId: "1:867529587246:web:dc754ab7840c737f47bdbf",
};

// init firebase
initializeApp(firebaseConfig);

// init services
const db = getFirestore();
const auth = getAuth();

// collection ref
const colRef = collection(db, "books");

// queries
const q = query(
  colRef,
  where("author", "==", "patrick rothfuss"),
  orderBy("createdAt")
);

// realtime collection data
const unsubCol = onSnapshot(q, (snapshot) => {
  let books = [];
  snapshot.docs.forEach((doc) => {
    books.push({ ...doc.data(), id: doc.id });
  });
  console.log(books);
});

// adding docs
const addBookForm = document.querySelector(".add");
addBookForm.addEventListener("submit", (e) => {
  e.preventDefault();

  addDoc(colRef, {
    title: addBookForm.title.value,
    author: addBookForm.author.value,
    createdAt: serverTimestamp(),
  }).then(() => {
    addBookForm.reset();
  });
});

// deleting docs
const deleteBookForm = document.querySelector(".delete");
deleteBookForm.addEventListener("submit", (e) => {
  e.preventDefault();

  const docRef = doc(db, "books", deleteBookForm.id.value);

  deleteDoc(docRef).then(() => {
    deleteBookForm.reset();
  });
});

// fetching a single document (& realtime)
const docRef = doc(db, "books", "gGu4P9x0ZHK9SspA1d9j");

const unsubDoc = onSnapshot(docRef, (doc) => {
  console.log(doc.data(), doc.id);
});

// updating a document
const updateForm = document.querySelector(".update");
updateForm.addEventListener("submit", (e) => {
  e.preventDefault();

  let docRef = doc(db, "books", updateForm.id.value);

  updateDoc(docRef, {
    title: "updated title",
  }).then(() => {
    updateForm.reset();
  });
});

// signing users up
const signupForm = document.querySelector(".signup");
signupForm.addEventListener("submit", (e) => {
  e.preventDefault();

  const email = signupForm.email.value;
  const password = signupForm.password.value;

  createUserWithEmailAndPassword(auth, email, password)
    .then((cred) => {
      console.log("user created:", cred.user);
      signupForm.reset();
    })
    .catch((err) => {
      console.log(err.message);
    });
});

// logging in and out
const logoutButton = document.querySelector(".logout");
logoutButton.addEventListener("click", () => {
  signOut(auth)
    .then(() => {
      console.log("user signed out");
    })
    .catch((err) => {
      console.log(err.message);
    });
});

const loginForm = document.querySelector(".login");
loginForm.addEventListener("submit", (e) => {
  e.preventDefault();

  const email = loginForm.email.value;
  const password = loginForm.password.value;

  signInWithEmailAndPassword(auth, email, password)
    .then((cred) => {
      console.log("user logged in:", cred.user);
      loginForm.reset();
    })
    .catch((err) => {
      console.log(err.message);
    });
});

// subscribing to auth changes
const unsubAuth = onAuthStateChanged(auth, (user) => {
  console.log("user status changed:", user);
});

// unsubscribing from changes (auth & db)
const unsubButton = document.querySelector(".unsub");
unsubButton.addEventListener("click", () => {
  console.log("unsubscribing");
  unsubCol();
  unsubDoc();
  unsubAuth();
});
```

</details>

### [4-NEXTJS TUTORIAL - NET NINJA](#)

+INTRODUCTION

<details>
  <summary>99. Create Next App</summary>

```bs
npx create-next-app .

npx create-next-app@latest
# or
yarn create next-app
# or
pnpm create next-app

npx create-next-app@latest --typescript
# or
yarn create next-app --typescript
# or
pnpm create next-app --typescript
```

```bs
npm run dev
```

pages/index.js:

```js
import Head from "next/head";
import Image from "next/image";
import styles from "../styles/Home.module.css";

export default function Home() {
  return (
    <div className={styles.container}>
      <Head>
        <title>Create Next App</title>
        <meta name="description" content="Generated by create next app" />
        <link rel="icon" href="/favicon.ico" />
      </Head>

      <main className={styles.main}>
        <h1 className={styles.title}>
          Welcome to <a href="https://nextjs.org">Next.js!</a>
        </h1>

        <p className={styles.description}>
          Get started by editing{" "}
          <code className={styles.code}>pages/index.js</code>
        </p>

        <div className={styles.grid}>
          <a href="https://nextjs.org/docs" className={styles.card}>
            <h2>Documentation &rarr;</h2>
            <p>Find in-depth information about Next.js features and API.</p>
          </a>

          <a href="https://nextjs.org/learn" className={styles.card}>
            <h2>Learn &rarr;</h2>
            <p>Learn about Next.js in an interactive course with quizzes!</p>
          </a>

          <a
            href="https://github.com/vercel/next.js/tree/canary/examples"
            className={styles.card}
          >
            <h2>Examples &rarr;</h2>
            <p>Discover and deploy boilerplate example Next.js projects.</p>
          </a>

          <a
            href="https://vercel.com/new?utm_source=create-next-app&utm_medium=default-template&utm_campaign=create-next-app"
            target="_blank"
            rel="noopener noreferrer"
            className={styles.card}
          >
            <h2>Deploy &rarr;</h2>
            <p>
              Instantly deploy your Next.js site to a public URL with Vercel.
            </p>
          </a>
        </div>
      </main>

      <footer className={styles.footer}>
        <a
          href="https://vercel.com?utm_source=create-next-app&utm_medium=default-template&utm_campaign=create-next-app"
          target="_blank"
          rel="noopener noreferrer"
        >
          Powered by{" "}
          <span className={styles.logo}>
            <Image src="/vercel.svg" alt="Vercel Logo" width={72} height={16} />
          </span>
        </a>
      </footer>
    </div>
  );
}
```

pages/\_app.js:

```js
import "../styles/globals.css";

function MyApp({ Component, pageProps }) {
  return <Component {...pageProps} />;
}

export default MyApp;
```

pages/api/hello.js:

```js
// Next.js API route support: https://nextjs.org/docs/api-routes/introduction

export default function handler(req, res) {
  res.status(200).json({ name: "John Doe" });
}
```

</details>

<details>
  <summary>100. Automatically Generated Routes</summary>

pages/index.js:

```bs
Route: http://localhost:3000/
```

```js
export default function Home() {
  return (
    <div>
      <h1>Home</h1>
      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Est nostrum
        omnis, animi cum perferendis, similique commodi fugit eos sequi maiores
        minima inventore dolorem dolore vitae quam. Ea quasi nihil nesciunt.
      </p>
      <p>
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quia delectus
        iste veniam sequi dolores inventore, placeat aliquid. Nulla dolores
        tenetur hic est nobis non at eum ipsam similique. Reprehenderit,
        provident!
      </p>
    </div>
  );
}
```

pages/about.js:

```bs
Route: http://localhost:3000/about
```

```js
const About = () => {
  return (
    <div>
      <h1>Find out more About us</h1>
      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Laudantium
        consequatur ad necessitatibus. Autem, culpa! Vitae, accusamus doloremque
        alias praesentium a eos dolorem, voluptas maiores dicta, adipisci atque.
        Fugit, velit natus!
      </p>
      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Consequuntur
        assumenda incidunt totam sit cupiditate tenetur sunt! Nam distinctio
        corporis consectetur fugiat omnis, quam, laborum necessitatibus facere
        tempore nihil doloribus vero?
      </p>
    </div>
  );
};

export default About;
```

pages/ninjas/index.js:

```bs
Route: http://localhost:3000/ninjas
```

```js
const Ninjas = () => {
  return (
    <div>
      <h1>All Ninjas</h1>
    </div>
  );
};

export default Ninjas;
```

</details>

<details>
  <summary>101. Adding Components</summary>

index.js:

```js
import Head from "next/head";
import Navbar from "../components/Navbar";
import Footer from "../components/Footer";
import styles from "../styles/Home.module.css";

export default function Home() {
  return (
    <div>
      <Navbar />
      <h1>Homepage</h1>
      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Est nostrum
        omnis, animi cum perferendis, similique commodi fugit eos sequi maiores
        minima inventore dolorem dolore vitae quam. Ea quasi nihil nesciunt.
      </p>
      <p>
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quia delectus
        iste veniam sequi dolores inventore, placeat aliquid. Nulla dolores
        tenetur hic est nobis non at eum ipsam similique. Reprehenderit,
        provident!
      </p>
      <Footer />
    </div>
  );
}
```

components/Navbar.js:

```js
const Navbar = () => {
  return (
    <nav>
      <div className="logo">
        <h1>Ninja List</h1>
      </div>
      <a>Home</a>
      <a>About</a>
      <a>Ninja Listing</a>
    </nav>
  );
};

export default Navbar;
```

components/Footer.js:

```js
const Footer = () => {
  return <div>Copyright 2022 Ninja List</div>;
};
export default Footer;
```

</details>

<details>
  <summary>102. Using Links</summary>

pages/index.js:

```js
import Head from "next/head";
import Link from "next/link";
import { Navbar, Footer } from "../components";
import styles from "../styles/Home.module.css";

export default function Home() {
  return (
    <div>
      <Navbar />
      <h1>Homepage</h1>
      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Est nostrum
        omnis, animi cum perferendis, similique commodi fugit eos sequi maiores
        minima inventore dolorem dolore vitae quam. Ea quasi nihil nesciunt.
      </p>
      <p>
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quia delectus
        iste veniam sequi dolores inventore, placeat aliquid. Nulla dolores
        tenetur hic est nobis non at eum ipsam similique. Reprehenderit,
        provident!
      </p>
      <Link href="/ninjas">See Ninja Listing</Link>
      <Footer />
    </div>
  );
}
```

pages/about.js:

```js
import { Navbar, Footer } from "../components";

const About = () => {
  return (
    <div>
      <Navbar />
      <h1>Find out more About us</h1>
      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Laudantium
        consequatur ad necessitatibus. Autem, culpa! Vitae, accusamus doloremque
        alias praesentium a eos dolorem, voluptas maiores dicta, adipisci atque.
        Fugit, velit natus!
      </p>
      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Consequuntur
        assumenda incidunt totam sit cupiditate tenetur sunt! Nam distinctio
        corporis consectetur fugiat omnis, quam, laborum necessitatibus facere
        tempore nihil doloribus vero?
      </p>
      <Footer />
    </div>
  );
};

export default About;
```

pages/ninjas/index.js:

```js
import { Navbar, Footer } from "../../components";

const Ninjas = () => {
  return (
    <div>
      <Navbar />
      <h1>All Ninjas</h1>
      <Footer />
    </div>
  );
};

export default Ninjas;
```

components/index.js:

```js
export { Navbar } from "./Navbar";
export { Footer } from "./Footer";
```

components/Navbar.js:

```js
import Link from "next/link";

export const Navbar = () => {
  return (
    <nav>
      <div className="logo">
        <h1>Ninja List</h1>
      </div>
      <Link href="/">Home</Link>
      <Link href="/about">About</Link>
      <Link href="/ninjas">Ninja Listing</Link>
    </nav>
  );
};
```

components/Footer.js:

```js
export const Footer = () => {
  return <div>Copyright 2022 Ninja List</div>;
};
```

</details>

<details>
  <summary>103. Creating a Layout Component</summary>

pages/\_app.js:

```js
import "../styles/globals.css";
import Layout from "../components/Layout";

function MyApp({ Component, pageProps }) {
  //return <Component {...pageProps} />
  return (
    <Layout>
      <Component {...pageProps} />
    </Layout>
  );
}

export default MyApp;
```

components/layout.js:

```js
import { Navbar } from "./navbar";
import { Footer } from "./footer";

const Layout = ({ children }) => {
  return (
    <div className="content">
      <Navbar />
      {children}
      <Footer />
    </div>
  );
};

export default Layout;
```

pages/index.js:

```js
import Head from "next/head";
import Link from "next/link";
import styles from "../styles/Home.module.css";

export default function Home() {
  return (
    <div>
      <h1>Homepage</h1>
      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Est nostrum
        omnis, animi cum perferendis, similique commodi fugit eos sequi maiores
        minima inventore dolorem dolore vitae quam. Ea quasi nihil nesciunt.
      </p>
      <p>
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quia delectus
        iste veniam sequi dolores inventore, placeat aliquid. Nulla dolores
        tenetur hic est nobis non at eum ipsam similique. Reprehenderit,
        provident!
      </p>
      <Link href="/ninjas">See Ninja Listing</Link>
    </div>
  );
}
```

pages/about.js:

```js
const About = () => {
  return (
    <div>
      <h1>Find out more About us</h1>
      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Laudantium
        consequatur ad necessitatibus. Autem, culpa! Vitae, accusamus doloremque
        alias praesentium a eos dolorem, voluptas maiores dicta, adipisci atque.
        Fugit, velit natus!
      </p>
      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Consequuntur
        assumenda incidunt totam sit cupiditate tenetur sunt! Nam distinctio
        corporis consectetur fugiat omnis, quam, laborum necessitatibus facere
        tempore nihil doloribus vero?
      </p>
    </div>
  );
};

export default About;
```

pages/ninjas/index.js:

```js
const Ninjas = () => {
  return (
    <div>
      <h1>All Ninjas</h1>
    </div>
  );
};

export default Ninjas;
```

</details>

<details>
  <summary>104. Global Styling</summary>

styles/globals.css:

```css
@import url("https://fonts.googleapis.com/css2?family=Nunito:wght@300;400;600;700&display=swap");

body {
  background: #f2f2f2;
  color: #333;
  font-family: "Nunito";
}

a {
  color: #333;
  text-decoration: none;
}

.content {
  max-width: 960px;
  margin: 0 auto;
}

nav {
  margin: 10px auto 80px;
  padding: 10px 0;
  display: flex;
  justify-content: flex-end;
  align-items: flex-end;
  border-bottom: 1px solid #ddd;
}

nav a {
  margin-left: 12px;
}

nav .logo {
  margin-right: auto;
}

footer {
  display: block;
  text-align: center;
  padding: 30px 0;
  margin-top: 60px;
  color: #777;
  border-top: 1px solid #eaeaea;
}
```

components/Footer:

```js
export const Footer = () => {
  return <footer>Copyright 2022 Ninja List</footer>;
};
```

pages/\_app.js:

```js
import "../styles/globals.css";
import Layout from "../components/Layout";

function MyApp({ Component, pageProps }) {
  //return <Component {...pageProps} />
  return (
    <Layout>
      <Component {...pageProps} />
    </Layout>
  );
}

export default MyApp;
```

</details>

<details>
  <summary>105. Styling with CSS Modules</summary>

Home.module.css:

```css
.title {
  color: #333;
  padding-bottom: 20px;
  text-align: center;
}

.text {
  color: #777;
}

.btn {
  display: block;
  width: 150px;
  padding: 8px 0;
  margin: 20px auto;
  background: #4979ff;
  border-radius: 4px;
  color: white;
  text-align: center;
}
```

index.js:

```js
import Head from "next/head";
import Link from "next/link";
import styles from "../styles/Home.module.css";

export default function Home() {
  return (
    <div>
      <h1 className={styles.title}>Homepage</h1>
      <p className={styles.text}>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Est nostrum
        omnis, animi cum perferendis, similique commodi fugit eos sequi maiores
        minima inventore dolorem dolore vitae quam. Ea quasi nihil nesciunt.
      </p>
      <p className={styles.text}>
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quia delectus
        iste veniam sequi dolores inventore, placeat aliquid. Nulla dolores
        tenetur hic est nobis non at eum ipsam similique. Reprehenderit,
        provident!
      </p>
      <Link className={styles.btn} href="/ninjas">
        See Ninja Listing
      </Link>
    </div>
  );
}
```

</details>

<details>
  <summary>106. Custom 404 page</summary>

pages/404.js:

```js
import Link from "next/link";

const NotFound = () => {
  return (
    <div className="not-found">
      <h1>Oooops...</h1>
      <h2>That page cannot be found. </h2>
      <p>
        Go back to the <Link href="/">Homepage</Link>
      </p>
    </div>
  );
};

export default NotFound;
```

styles/globals.css:

```bs
.not-found {
  text-align: center;
}

.not-found a {
  color: #4979ff;
  text-decoration: underline;
}
```

```css
@import url("https://fonts.googleapis.com/css2?family=Nunito:wght@300;400;600;700&display=swap");

body {
  background: #f2f2f2;
  color: #333;
  font-family: "Nunito";
}

a {
  color: #333;
  text-decoration: none;
}

.content {
  max-width: 960px;
  margin: 0 auto;
}

nav {
  margin: 10px auto 80px;
  padding: 10px 0;
  display: flex;
  justify-content: flex-end;
  align-items: flex-end;
  border-bottom: 1px solid #ddd;
}

nav a {
  margin-left: 12px;
}

nav .logo {
  margin-right: auto;
}

footer {
  display: block;
  text-align: center;
  padding: 30px 0;
  margin-top: 60px;
  color: #777;
  border-top: 1px solid #eaeaea;
}

.not-found {
  text-align: center;
}

.not-found a {
  color: #4979ff;
  text-decoration: underline;
}
```

</details>

<details>
  <summary>107. Redirect Automatically</summary>

pages/404.js:

```js
import Link from "next/link";
import { useEffect } from "react";
import { useRouter } from "next/router";

const NotFound = () => {
  const router = useRouter();

  useEffect(() => {
    setTimeout(() => {
      // router.go(-1)
      router.push("/");
    }, 3000);
  }, []);

  return (
    <div className="not-found">
      <h1>Oooops...</h1>
      <h2>That page cannot be found. </h2>
      <p>
        Go back to the <Link href="/">Homepage</Link>
      </p>
    </div>
  );
};

export default NotFound;
```

</details>

<details>
  <summary>108. Adding Images</summary>

- Put images to Public Folder

components/Navbar.js:

```js
import Link from "next/link";
import Image from "next/image";

export const Navbar = () => {
  return (
    <nav>
      <div className="logo">
        <Image src="/undraw.svg" width={128} height={77} />
      </div>
      <Link href="/">Home</Link>
      <Link href="/about">About</Link>
      <Link href="/ninjas">Ninja Listing</Link>
    </nav>
  );
};
```

</details>

<details>
  <summary>109. Adding Custom Metadata</summary>

pages/index.js:

```js
import Head from "next/head";
import Link from "next/link";
import styles from "../styles/Home.module.css";

export default function Home() {
  return (
    <>
      <Head>
        <title>Ninja List | Home</title>
        <meta name="description" content="Ninja List Website" />
        <meta name="keywords" content="ninjas" />
      </Head>
      <div>
        <h1 className={styles.title}>Homepage</h1>
        <p className={styles.text}>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Est nostrum
          omnis, animi cum perferendis, similique commodi fugit eos sequi
          maiores minima inventore dolorem dolore vitae quam. Ea quasi nihil
          nesciunt.
        </p>
        <p className={styles.text}>
          Lorem ipsum, dolor sit amet consectetur adipisicing elit. Quia
          delectus iste veniam sequi dolores inventore, placeat aliquid. Nulla
          dolores tenetur hic est nobis non at eum ipsam similique.
          Reprehenderit, provident!
        </p>
        <Link className={styles.btn} href="/ninjas">
          See Ninja Listing
        </Link>
      </div>
    </>
  );
}
```

pages/about.js:

```js
import Head from "next/head";

const About = () => {
  return (
    <>
      <Head>
        <title>Ninja List | About</title>
        <meta name="description" content="Ninja List Website" />
        <meta name="keywords" content="About ninjas" />
      </Head>
      <div>
        <h1>Find out more About us</h1>
        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Laudantium
          consequatur ad necessitatibus. Autem, culpa! Vitae, accusamus
          doloremque alias praesentium a eos dolorem, voluptas maiores dicta,
          adipisci atque. Fugit, velit natus!
        </p>
        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Consequuntur
          assumenda incidunt totam sit cupiditate tenetur sunt! Nam distinctio
          corporis consectetur fugiat omnis, quam, laborum necessitatibus facere
          tempore nihil doloribus vero?
        </p>
      </div>
    </>
  );
};

export default About;
```

</details>

<details>
  <summary>110. {JSON} Placeholder</summary>

```bs
https://jsonplaceholder.typicode.com/
```

JSONPlaceholder comes with a set of 6 common resources:

```bs
/posts	    100 posts
/comments	    500 comments
/albums	    100 albums
/photos	    5000 photos
/todos	    200 todos
/users	    10 users
```

Routes

```bs

GET	      /posts
GET	      /posts/1
GET	      /posts/1/comments
GET	      /comments?postId=1
POST	      /posts
PUT	      /posts/1
PATCH	      /posts/1
DELETE	      /posts/1
```

Getting a resource 1:

```js
fetch("https://jsonplaceholder.typicode.com/todos/1")
  .then((response) => response.json())
  .then((json) => console.log(json));
```

Result:

```js
// {
//   "userId": 1,
//   "id": 1,
//   "title": "delectus aut autem",
//   "completed": false
// }
```

Getting a resource 2:

```js
fetch("https://jsonplaceholder.typicode.com/posts/1")
  .then((response) => response.json())
  .then((json) => console.log(json));
```

Result:

```js
// {
//   id: 1,
//   title: '...',
//   body: '...',
//   userId: 1
// }
```

Listing all resources:

```js
fetch("https://jsonplaceholder.typicode.com/posts")
  .then((response) => response.json())
  .then((json) => console.log(json));
```

Result:

```js
// [
//   { id: 1, title: '...' /* ... */ },
//   { id: 2, title: '...' /* ... */ },
//   { id: 3, title: '...' /* ... */ },
//   /* ... */
//   { id: 100, title: '...' /* ... */ },
// ];
```

Creating a resource:

```js
fetch("https://jsonplaceholder.typicode.com/posts", {
  method: "POST",
  body: JSON.stringify({
    title: "foo",
    body: "bar",
    userId: 1,
  }),
  headers: {
    "Content-type": "application/json; charset=UTF-8",
  },
})
  .then((response) => response.json())
  .then((json) => console.log(json));
```

Result:

```js
// {
//   id: 101,
//   title: 'foo',
//   body: 'bar',
//   userId: 1
// }
```

Updating a resource:

```js
fetch("https://jsonplaceholder.typicode.com/posts/1", {
  method: "PUT",
  body: JSON.stringify({
    id: 1,
    title: "foo",
    body: "bar",
    userId: 1,
  }),
  headers: {
    "Content-type": "application/json; charset=UTF-8",
  },
})
  .then((response) => response.json())
  .then((json) => console.log(json));
```

Result:

```js
// {
//   id: 1,
//   title: 'foo',
//   body: 'bar',
//   userId: 1
// }
```

Patching a resource:

```js
fetch("https://jsonplaceholder.typicode.com/posts/1", {
  method: "PATCH",
  body: JSON.stringify({
    title: "foo",
  }),
  headers: {
    "Content-type": "application/json; charset=UTF-8",
  },
})
  .then((response) => response.json())
  .then((json) => console.log(json));
```

```js
// {
//   id: 1,
//   title: 'foo',
//   body: '...',
//   userId: 1
// }
```

Deleting a resource:

```js
fetch("https://jsonplaceholder.typicode.com/posts/1", {
  method: "DELETE",
});
```

Filtering resources:

```js
// This will return all the posts that belong to the first user
fetch("https://jsonplaceholder.typicode.com/posts?userId=1")
  .then((response) => response.json())
  .then((json) => console.log(json));
```

Listing nested resources:

```js
// This is equivalent to /comments?postId=1
fetch("https://jsonplaceholder.typicode.com/posts/1/comments")
  .then((response) => response.json())
  .then((json) => console.log(json));
```

https://jsonplaceholder.typicode.com/users

```js
// [
//   {
//     id: 1,
//     name: "Leanne Graham",
//     username: "Bret",
//     email: "Sincere@april.biz",
//     address: {
//       street: "Kulas Light",
//       suite: "Apt. 556",
//       city: "Gwenborough",
//       zipcode: "92998-3874",
//       geo: {
//         lat: "-37.3159",
//         lng: "81.1496",
//       },
//     },
//     phone: "1-770-736-8031 x56442",
//     website: "hildegard.org",
//     company: {
//       name: "Romaguera-Crona",
//       catchPhrase: "Multi-layered client-server neural-net",
//       bs: "harness real-time e-markets",
//     },
//   },
//   {
//     id: 2,
//     name: "Ervin Howell",
//     username: "Antonette",
//     email: "Shanna@melissa.tv",
//     address: {
//       street: "Victor Plains",
//       suite: "Suite 879",
//       city: "Wisokyburgh",
//       zipcode: "90566-7771",
//       geo: {
//         lat: "-43.9509",
//         lng: "-34.4618",
//       },
//     },
//     phone: "010-692-6593 x09125",
//     website: "anastasia.net",
//     company: {
//       name: "Deckow-Crist",
//       catchPhrase: "Proactive didactic contingency",
//       bs: "synergize scalable supply-chains",
//     },
//   },
//   {
//     id: 3,
//     name: "Clementine Bauch",
//     username: "Samantha",
//     email: "Nathan@yesenia.net",
//     address: {
//       street: "Douglas Extension",
//       suite: "Suite 847",
//       city: "McKenziehaven",
//       zipcode: "59590-4157",
//       geo: {
//         lat: "-68.6102",
//         lng: "-47.0653",
//       },
//     },
//     phone: "1-463-123-4447",
//     website: "ramiro.info",
//     company: {
//       name: "Romaguera-Jacobson",
//       catchPhrase: "Face to face bifurcated interface",
//       bs: "e-enable strategic applications",
//     },
//   },
//   {
//     id: 4,
//     name: "Patricia Lebsack",
//     username: "Karianne",
//     email: "Julianne.OConner@kory.org",
//     address: {
//       street: "Hoeger Mall",
//       suite: "Apt. 692",
//       city: "South Elvis",
//       zipcode: "53919-4257",
//       geo: {
//         lat: "29.4572",
//         lng: "-164.2990",
//       },
//     },
//     phone: "493-170-9623 x156",
//     website: "kale.biz",
//     company: {
//       name: "Robel-Corkery",
//       catchPhrase: "Multi-tiered zero tolerance productivity",
//       bs: "transition cutting-edge web services",
//     },
//   },
//   {
//     id: 5,
//     name: "Chelsey Dietrich",
//     username: "Kamren",
//     email: "Lucio_Hettinger@annie.ca",
//     address: {
//       street: "Skiles Walks",
//       suite: "Suite 351",
//       city: "Roscoeview",
//       zipcode: "33263",
//       geo: {
//         lat: "-31.8129",
//         lng: "62.5342",
//       },
//     },
//     phone: "(254)954-1289",
//     website: "demarco.info",
//     company: {
//       name: "Keebler LLC",
//       catchPhrase: "User-centric fault-tolerant solution",
//       bs: "revolutionize end-to-end systems",
//     },
//   },
//   {
//     id: 6,
//     name: "Mrs. Dennis Schulist",
//     username: "Leopoldo_Corkery",
//     email: "Karley_Dach@jasper.info",
//     address: {
//       street: "Norberto Crossing",
//       suite: "Apt. 950",
//       city: "South Christy",
//       zipcode: "23505-1337",
//       geo: {
//         lat: "-71.4197",
//         lng: "71.7478",
//       },
//     },
//     phone: "1-477-935-8478 x6430",
//     website: "ola.org",
//     company: {
//       name: "Considine-Lockman",
//       catchPhrase: "Synchronised bottom-line interface",
//       bs: "e-enable innovative applications",
//     },
//   },
//   {
//     id: 7,
//     name: "Kurtis Weissnat",
//     username: "Elwyn.Skiles",
//     email: "Telly.Hoeger@billy.biz",
//     address: {
//       street: "Rex Trail",
//       suite: "Suite 280",
//       city: "Howemouth",
//       zipcode: "58804-1099",
//       geo: {
//         lat: "24.8918",
//         lng: "21.8984",
//       },
//     },
//     phone: "210.067.6132",
//     website: "elvis.io",
//     company: {
//       name: "Johns Group",
//       catchPhrase: "Configurable multimedia task-force",
//       bs: "generate enterprise e-tailers",
//     },
//   },
//   {
//     id: 8,
//     name: "Nicholas Runolfsdottir V",
//     username: "Maxime_Nienow",
//     email: "Sherwood@rosamond.me",
//     address: {
//       street: "Ellsworth Summit",
//       suite: "Suite 729",
//       city: "Aliyaview",
//       zipcode: "45169",
//       geo: {
//         lat: "-14.3990",
//         lng: "-120.7677",
//       },
//     },
//     phone: "586.493.6943 x140",
//     website: "jacynthe.com",
//     company: {
//       name: "Abernathy Group",
//       catchPhrase: "Implemented secondary concept",
//       bs: "e-enable extensible e-tailers",
//     },
//   },
//   {
//     id: 9,
//     name: "Glenna Reichert",
//     username: "Delphine",
//     email: "Chaim_McDermott@dana.io",
//     address: {
//       street: "Dayna Park",
//       suite: "Suite 449",
//       city: "Bartholomebury",
//       zipcode: "76495-3109",
//       geo: {
//         lat: "24.6463",
//         lng: "-168.8889",
//       },
//     },
//     phone: "(775)976-6794 x41206",
//     website: "conrad.com",
//     company: {
//       name: "Yost and Sons",
//       catchPhrase: "Switchable contextually-based project",
//       bs: "aggregate real-time technologies",
//     },
//   },
//   {
//     id: 10,
//     name: "Clementina DuBuque",
//     username: "Moriah.Stanton",
//     email: "Rey.Padberg@karina.biz",
//     address: {
//       street: "Kattie Turnpike",
//       suite: "Suite 198",
//       city: "Lebsackbury",
//       zipcode: "31428-2261",
//       geo: {
//         lat: "-38.2386",
//         lng: "57.2232",
//       },
//     },
//     phone: "024-648-3804",
//     website: "ambrose.net",
//     company: {
//       name: "Hoeger LLC",
//       catchPhrase: "Centralized empowering task-force",
//       bs: "target end-to-end models",
//     },
//   },
// ];
```

</details>

<details>
  <summary>111. Fetch Data</summary>

pages/index.js:

```js
import styles from "../../styles/Jobs.module.css";

export const getStaticProps = async () => {
  const res = await fetch("https://jsonplaceholder.typicode.com/users");
  const data = await res.json();

  return {
    props: { ninjas: data },
  };
};

const Ninjas = ({ ninjas }) => {
  console.log(ninjas);

  return (
    <div>
      <h1>All Ninjas</h1>
      {ninjas.map((ninja) => (
        <div key={ninja.id}>
          <a className={styles.single}>
            <h3>{ninja.name}</h3>
          </a>
        </div>
      ))}
    </div>
  );
};

export default Ninjas;
```

styles/Jobs.module.css:

```css
.single {
  padding: 2px 16px;
  background: #fff;
  display: block;
  margin: 20px 10px;
  border-left: 8px solid #fff;
}

.single:hover {
  border-left: 8px solid #4979ff;
}
```

</details>

<details>
  <summary>112. Dynamic Routes (Details Page)</summary>

pages/ninjas/[id].js:

```js
const Details = () => {
  return (
    <div>
      <h1>Details Page</h1>
    </div>
  );
};

export default Details;
```

pages/index.js:

```js
import Link from "next/link";
import styles from "../../styles/Jobs.module.css";

export const getStaticProps = async () => {
  const res = await fetch("https://jsonplaceholder.typicode.com/users");
  const data = await res.json();

  return {
    props: { ninjas: data },
  };
};

const Ninjas = ({ ninjas }) => {
  console.log(ninjas);

  return (
    <div>
      <h1>All Ninjas</h1>
      {ninjas.map((ninja) => (
        <div key={ninja.id}>
          <Link href={`/ninjas/${ninja.id}`} className={styles.single}>
            <h3>{ninja.name}</h3>
          </Link>
        </div>
      ))}
    </div>
  );
};

export default Ninjas;
```

</details>

<details>
  <summary>113. Dynamic Routes (getStaticPaths)</summary>

pages/ninjas/[id].js:

```js
export const getStaticPaths = async () => {
  const res = await fetch("https://jsonplaceholder.typicode.com/users");
  const data = await res.json();

  // map data to an array of path objects with params (id)
  const paths = data.map((ninja) => {
    return {
      params: { id: ninja.id.toString() },
    };
  });

  return {
    paths,
    fallback: false,
  };
};

const Details = () => {
  return (
    <div>
      <h1>Details Page</h1>
    </div>
  );
};

export default Details;
```

</details>

<details>
  <summary>114. Fetching a Single Item (Detial)</summary>

pages/ninjas/[id].js:

```js
export const getStaticPaths = async () => {
  const res = await fetch("https://jsonplaceholder.typicode.com/users");
  const data = await res.json();

  // map data to an array of path objects with params (id)
  const paths = data.map((ninja) => {
    return {
      params: { id: ninja.id.toString() },
    };
  });

  return {
    paths,
    fallback: false,
  };
};

export const getStaticProps = async (context) => {
  const id = context.params.id;
  const res = await fetch("https://jsonplaceholder.typicode.com/users/" + id);
  const data = await res.json();

  return {
    props: { ninja: data },
  };
};

const Details = ({ ninja }) => {
  return (
    <div>
      <h1>{ninja.name}</h1>
      <p>{ninja.email}</p>
      <p>{ninja.website}</p>
      <p>{ninja.address.city}</p>
    </div>
  );
};

export default Details;
```

</details>

<details>
  <summary>115. Deploy NextJS App in Vercel</summary>

Build NextJS app:

```bs
npm run build
```

Deploy to Github:

```bs
git remote add origin https://github.com/omeatai/practice-ninja-blog-app.git
git add .
git commit -m "initial commit"
git push --force origin main
```

Vercel:

```bs
Create new project -> Import Git Repository -> Deploy
```

</details>

### [5-REACT TUTORIAL - DAVE GRAY](#)

+INTRODUCTION

<details>
  <summary>116. Create React App</summary>

```bs
node -v
```

```bs
npx create-react-app .
```

Start App:

```bs
npm start
```

index.js:

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

App.js:

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

</details>

<details>
  <summary>117. handleChange Function</summary>

App.js:

```js
import logo from "./logo.svg";
import "./App.css";

function App() {
  const handleChange = () => {
    const names = ["Dave", "Sally", "Ben", "Andrew"];
    const indexPos = Math.floor(Math.random() * names.length);
    return names[indexPos];
  };
  return (
    <div className="App">
      <header className="App-header">
        <img src={logo} className="App-logo" alt="logo" />
        <p>Hello {handleChange()}!</p>
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

</details>

<details>
  <summary>118. Using React Components</summary>

App.js:

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

Header.js:

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

Content.js:

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

Footer.js:

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

</details>

<details>
  <summary>119. Styling Components</summary>

1. Styled Components - https://styled-components.com/

2. Inline Styling -

Header.js:

```js
import React from "react";

const Header = () => {
  return (
    <header style={{ backgroundColor: "mediumblue", color: "white" }}>
      <h1>Groceries List</h1>
    </header>
  );
};

export default Header;
```

3. External Styling -

index.css:

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
  align-items: center;
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

index.js:

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

</details>

<details>
  <summary>120. **DoubleClick Event**</summary>

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
<button onClick={click}>clic</button>;
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

</details>

<details>
  <summary>121. onClick Events</summary>

Content.js:

```js
import React from "react";

const Content = () => {
  const handleChange = () => {
    const names = ["Dave", "Sally", "Ben", "Andrew"];
    const indexPos = Math.floor(Math.random() * names.length);
    return names[indexPos];
  };

  const handleClick1 = () => {
    console.log("Click 1 button was clicked.");
  };

  const handleClick2 = (name) => {
    console.log(`Click 2 button with name "${name}" was clicked.`);
  };

  const handleClick3 = (obj) => {
    console.log(
      `Click 3 button with ${Object.keys(obj)} "${Object.values(
        obj
      )}" was clicked.`
    );
  };

  const handleClick4 = (e) => {
    console.log(e.target);
    console.log("Text: ", e.target.innerText);
    console.log("Value: ", e.target.value);
    console.log("Type: ", e.target.type);
  };

  return (
    <main>
      <p>Hello, {handleChange()}!</p>
      <button onClick={handleClick1}>Click 1</button>
      <button onClick={() => handleClick2("David")}>Click 2</button>
      <button onClick={() => handleClick3({ Age: "32" })}>Click 3</button>
      <button value={"Button Value"} onClick={(e) => handleClick4(e)}>
        Click 4
      </button>
    </main>
  );
};

export default Content;
```

```js
// Click 1 button was clicked.

// Click 2 button with name "David" was clicked.

// Click 3 button with Age "32" was clicked.

// <button value="Button Value">Click 4</button>
// Text:  Click 4
// Value:  Button Value
// Type:  submit
```

</details>

<details>
  <summary>122. useState Hooks</summary>

Content.js:

```js
import React, { useState } from "react";

const Content = () => {
  const [name, setName] = useState("Dave");
  const [count, setCount] = useState(0);

  const handleNameChange = () => {
    const names = ["Dave", "Sally", "Ben", "Andrew"];
    const indexPos = Math.floor(Math.random() * names.length);
    setName(names[indexPos]);
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

</details>

<details>
  <summary>123. handleCheck + LocalStorage</summary>

```bs
npm i react-icons -D
npm install react-icons --save
```

Content.js:

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
              onClick={() => handleCheck(item.id)}
            >
              {item.item}
            </label>
            <FaTrashAlt role="button" tabIndex="0" />
          </li>
        ))}
      </ul>
    </main>
  );
};

export default Content;
```

index.css:

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
  align-items: center;
  overflow-y: auto;
}

footer {
  width: 100%;
  padding: 0.25em;
  background-color: mediumblue;
  color: aliceblue;
  display: grid;
  place-content: center;
  text-align: center;
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

</details>

<details>
  <summary>124. handle Delete</summary>

Content.js:

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
                onClick={() => handleCheck(item.id)}
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
        <p style={{ marginTop: "2rem" }}>Your List is empty!</p>
      )}
    </main>
  );
};

export default Content;
```

</details>

<details>
  <summary>125. React Props</summary>

App.js:

```js
import Header from "./Header";
import Content from "./Content";
import Footer from "./Footer";

function App() {
  return (
    <div className="App">
      <Header title="Groceries" />
      <Content />
      <Footer />
    </div>
  );
}

export default App;
```

\*Using Props -

Header.js:

```js
import React from "react";

const Header = (props) => {
  return (
    <header>
      <h1>{props.title}</h1>
    </header>
  );
};

export default Header;
```

\*Destructuring -

Header.js:

```js
import React from "react";

const Header = ({ title }) => {
  return (
    <header>
      <h1>{title} List</h1>
    </header>
  );
};

export default Header;
```

</details>

<details>
  <summary>126. Default Props</summary>

App.js:

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

Header.js:

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

</details>

<details>
  <summary>127. Passing Props</summary>

App.js:

```js
import Header from "./Header";
import Content from "./Content";
import Footer from "./Footer";
import React, { useState } from "react";

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
      <Header title="Groceries List" />
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

Header.js:

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

Content.js:

```js
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
                onClick={() => handleCheck(item.id)}
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
        <p style={{ marginTop: "2rem" }}>Your List is empty!</p>
      )}
    </main>
  );
};

export default Content;
```

Footer.js:

```js
import React from "react";

const Footer = ({ itemLength }) => {
  const today = new Date();

  return (
    <footer>
      <p>
        {itemLength} List {itemLength === 1 ? "item" : "items"}
      </p>
      <p>Copyright &copy; {today.getFullYear()}</p>
    </footer>
  );
};

export default Footer;
```

</details>

<details>
  <summary>128. ItemList, LineItem & Prop Drilling</summary>

App.js -> Content.js -> ItemList.js -> LineItem.js

App.js:

```js
import Header from "./Header";
import Content from "./Content";
import Footer from "./Footer";
import React, { useState } from "react";

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
      <Header title="Groceries List" />
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

Content.js:

```js
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
        <p style={{ marginTop: "2rem" }}>Your List is empty!</p>
      )}
    </main>
  );
};

export default Content;
```

ItemList.js:

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

LineItem.js:

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
        onClick={() => handleCheck(item.id)}
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

</details>

<details>
  <summary>129. React Forms - AddItem</summary>

Move React icons to Production Dependency:

```bs
npm i react-icons --save-prod
```

App.js:

```js
import Header from "./Header";
import AddItem from "./AddItem";
import Content from "./Content";
import Footer from "./Footer";
import React, { useState } from "react";

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

  const addItem = (item) => {
    const id = items.length ? items[items.length - 1].id + 1 : 1;
    const myNewItem = { id, checked: false, item };
    const listItems = [...items, myNewItem];
    setAndSaveItems(listItems);
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

AddItem.js:

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

Index.css:

```js
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
  align-items: center;
  overflow-y: auto;
}

footer {
  width: 100%;
  padding: 0.25em;
  background-color: mediumblue;
  color: aliceblue;
  display: grid;
  place-content: center;
  text-align: center;
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

</details>

<details>
  <summary>130. Fetch from LocalStorage Database</summary>

```js
const [items, setItems] = useState(
  JSON.parse(localStorage.getItem("shoppinglist"))
);
```

App.js:

```js
import Header from "./Header";
import AddItem from "./AddItem";
import Content from "./Content";
import Footer from "./Footer";
import React, { useState } from "react";

function App() {
  const [items, setItems] = useState(
    JSON.parse(localStorage.getItem("shoppinglist"))
  );

  const [newItem, setNewItem] = useState("");

  const setAndSaveItems = (newItems) => {
    setItems(newItems);
    localStorage.setItem("shoppinglist", JSON.stringify(newItems));
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

  const addItem = (item) => {
    const id = items.length ? items[items.length - 1].id + 1 : 1;
    const myNewItem = { id, checked: false, item };
    const listItems = [...items, myNewItem];
    setAndSaveItems(listItems);
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

</details>

<details>
  <summary>131. Search Functionality </summary>

App.js:

```js
import Header from "./Header";
import AddItem from "./AddItem";
import SearchItem from "./SearchItem";
import Content from "./Content";
import Footer from "./Footer";
import React, { useState } from "react";

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

  const addItem = (item) => {
    const id = items.length ? items[items.length - 1].id + 1 : 1;
    const myNewItem = { id, checked: false, item };
    const listItems = [...items, myNewItem];
    setAndSaveItems(listItems);
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

SearchItem.js:

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

index.css:

```bs
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
  align-items: center;
  overflow-y: auto;
}

footer {
  width: 100%;
  padding: 0.25em;
  background-color: mediumblue;
  color: aliceblue;
  display: grid;
  place-content: center;
  text-align: center;
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

</details>

<details>
  <summary>132. Using useRef Hook</summary>

AddItem.js:

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

</details>

+COLOR SELECTOR APP

<details>
  <summary>133. Color Selector App - Introduction</summary>

Install React App:

```bs
npx create-react-app .
npx create-react-app color-selector
```

Index.js:

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

App.js:

```js
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

Square.js:

```js
import React from "react";

const Square = () => {
  return <h2>Square</h2>;
};

export default Square;
```

Input.js:

```js
import React from "react";

const Input = () => {
  return <h2>Input</h2>;
};

export default Input;
```

</details>

<details>
  <summary>134. Color Selector App - Setup Square.js and Input.js components</summary>

colors.json:

```json
{
  "lilac": "#c8a2c8"
}
```

App.js:

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

Square.js:

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

Input.js:

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

index.css:

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

</details>

<details>
  <summary>135. Color Selector App - Passing Hex Values</summary>

```bs
npm i colornames -S
```

App.js:

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

Square.js:

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

Input.js:

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

colors.json:

```js
{
  "lilac": "#c8a2c8",
  "rose": "#ff007f"
}

```

</details>

<details>
  <summary>136. Color Selector App - Toggling Black and White Text</summary>

App.js:

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

Square.js:

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

Input.js:

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

index.css:

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

</details>

<details>
  <summary>137. Using useEffect to save Data</summary>

App.js

```js
import Header from "./Header";
import AddItem from "./AddItem";
import SearchItem from "./SearchItem";
import Content from "./Content";
import Footer from "./Footer";
import React, { useState, useEffect } from "react";

function App() {
  const [items, setItems] = useState([]);
  const [newItem, setNewItem] = useState("");
  const [search, setSearch] = useState("");

  useEffect(() => {
    setItems(JSON.parse(localStorage.getItem("shoppinglist")) || []);
  }, []);

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

</details>

+JSON-SERVER

<details>
  <summary>138. JSON sever - Using JSON Server</summary>

Install and start JSON Server:

```bs
npm i json-server
npm install -g json-server

json-server -p 3500 --watch data/db.json
```

OR

```bs
npx json-server -p 3500 -w data/db.json
```

data/db.json:

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

Fetch call for item 1:

```bs
http://localhost:3500/items/1
```

```js
// {
// "id": 1,
// "checked": false,
// "item": "Almonds, Unsalted, in the blue bag"
}
```

</details>

<details>
  <summary>139. JSON sever - Fetch JSON API Data & Catch Errors</summary>

App.js:

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

Content.js:

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

</details>

<details>
  <summary>140. JSON sever - SetTimeout to simulate a slow REST API Response</summary>

```bs
setTimeout(() => {
  fetchItems();
  //(async () => await fetchItems())();
}, 2000);
```

App.js:

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

</details>

<details>
  <summary>141. JSON sever - Set isLoading Hook</summary>

App.js:

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

</details>

<details>
  <summary>142. JSON server - Building API Request Function </summary>

src/apiRequest.js:

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

</details>

<details>
  <summary>143. JSON server - Create/Add an Item </summary>

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

App.js:

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

</details>

<details>
  <summary>144. JSON server - Update an Item</summary>

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

App.js:

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

</details>

<details>
  <summary>145. JSON server - Delete an Item</summary>

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

App.js:

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

  //Delete an item in DB
  const handleDelete = async (id) => {
    const listItems = items.filter((item) => item.id !== id);
    setItems(listItems);

    const deleteOptions = { method: "DELETE" };
    const reqUrl = `${API_URL}/${id}`;
    const result = await apiRequest(reqUrl, deleteOptions);
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

</details>

+FETCH API TASK

<details>
  <summary>146. Fetch API Task (PART A) - users, posts, comments</summary>

```bs
https://jsonplaceholder.typicode.com/

https://jsonplaceholder.typicode.com/users
https://jsonplaceholder.typicode.com/posts
https://jsonplaceholder.typicode.com/comments
```

index.js:

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

First Implementation:

App.js:

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

Index.css:

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

Second Implementation:

App.js:

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

Form.js:

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

Button.js:

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

List.js:

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

ListItem.js:

```js
import React from "react";

const ListItem = ({ item }) => {
  return <li>{JSON.stringify(item)}</li>;
};

export default ListItem;
```

index.css:

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

</details>

<details>
  <summary>147. Fetch API Task (PART B) - Tables</summary>

App.js:

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

Table.js:

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

Row.js:

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

Cell.js:

```js
import React from "react";

const Cell = ({ cellData }) => {
  return <td>{cellData}</td>;
};

export default Cell;
```

index.css:

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

</details>

+BLOG APP

<details>
  <summary>148. Blog App - Introduction</summary>

Create React App:

```bs
npx create-react-app .
```

Install React Router DOM:

```bs
npm i react-router-dom -S
npm i react-router-dom@6 -S
```

Update React Router DOM:

```bs
npm update react-router-dom
```

Run React Server:

```bs
npm run start
```

index.js:

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

App.js:

```js
function App() {
  return (
    <div className="App">
      <h1>App</h1>
    </div>
  );
}

export default App;
```

</details>

<details>
  <summary>149. Blog App - Setup React Router DOM</summary>

index.js:

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

</details>

<details>
  <summary>150. Blog App - Routing Components</summary>

index.js:

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

App.js:

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

Heading.js:

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

Nav.js:

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

Home.js:

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

NewPost.js:

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

PostPage.js:

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

About.js:

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

Missing.js:

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

Footer.js:

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

</details>

<details>
  <summary>151. Blog App - Reading and Deleting Blog Data</summary>

App.js:

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

Header.js:

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

Nav.js:

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

Home.js:

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

Feed.js:

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

Post.js:

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

PostPage.js:

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

index.css:

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

</details>

<details>
  <summary>152. Blog App - Adding New Post</summary>

Install Date-Functions Module:

```bs
npm i date-fns -S
```

App.js:

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

NewPost.js:

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

</details>

<details>
  <summary>153. Blog App - Adding Search Functionality</summary>

App.js:

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

Feed.js:

```js
import React from "react";
import Post from "./Post";

const Feed = ({ posts }) => {
  return (
    <>
      {posts.map((post) => (
        <Post key={post.id} post={post} />
      ))}
    </>
  );
};

export default Feed;
```

</details>

<details>
  <summary>154. Blog App - Page Not Found (Missing Page)</summary>

Missing.js:

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

</details>

<details>
  <summary>155. Blog App - Footer Component</summary>

Footer.js:

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

</details>

<details>
  <summary>156. Blog App - About Component</summary>

About.js:

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

</details>

<details>
  <summary>157. Blog App - Customise CSS Width and Height Properties</summary>

```bs
#root {
  flex-grow: 1;
  display: flex;
  justify-content: center;
  align-items: center;
}
```

Index.css:

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

</details>

<details>
  <summary>158. Blog App - Setup data/db.json file for JSON Server and Axios</summary>

Install Axios:

```bs
npm i axios -S
```

data/db.json:

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

App.js:

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

</details>

<details>
  <summary>159. Blog App - Fetch Data with Axios</summary>

Install JSON Server:

```bs
npm i json-server
npm install -g json-server

json-server -p 3500 --watch data/db.json
```

OR

Lunch JSON Server:

```bs
npx json-server -p 3500 -w data/db.json
```

api/posts.js

```js
import axios from "axios";

export default axios.create({ baseURL: "http://localhost:3500" });
```

App.js:

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

</details>

<details>
  <summary>160. Blog App - Post/Create Data with Axios</summary>

App.js:

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

App.js:

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

</details>

<details>
  <summary>161. Blog App - Delete Data with Axios</summary>

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

App.js:

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

</details>

<details>
  <summary>162. Blog App - Update Data with Axios</summary>

App.js:

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

EditPost.js:

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

PostPage.js:

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

index.css:

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

</details>

<details>
  <summary>163. Blog App - Create useWindowSize Custom Hook</summary>

Install react-icons:

```bs
npm i react-icons -S
```

hooks/useWindowSize.js:

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

App.js:

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

Header.js:

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

</details>

<details>
  <summary>164. Blog App - Create useAxiosFetch Custom Hook</summary>

hooks/useAxiosFetch.js:

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

App.js:

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

Home.js:

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

</details>

<details>
  <summary>165. Blog App - Create Context API</summary>

context/DataContext.js:

```js
import React, { createContext, useState, useEffect } from "react";

const DataContext = createContext({});

export const DataProvider = ({ children }) => {
  return <DataContext.Provider value={{}}>{children}</DataContext.Provider>;
};

export default DataContext;
```

App.js:

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

</details>

<details>
  <summary>166. Blog App - Refactor Header with Context API</summary>

context/DataContext.js:

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

App.js:

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

Header.js:

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

</details>

<details>
  <summary>167. Blog App - Refactor Nav and Home with Context API</summary>

context/DataContext.js:

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

App.js:

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

Nav.js:

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

Home.js:

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

</details>

<details>
  <summary>168. Blog App - Refactor NewPost with Context API</summary>

context/DataContext.js:

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

App.js:

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

NewPost.js:

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

</details>

<details>
  <summary>169. Blog App - Refactor PostPage and EditPost with Context API</summary>

context/DataContext.js:

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

App.js:

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

PostPage.js:

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

EditPost.js:

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

</details>

<details>
  <summary>170. Blog App - Isolating Header and Footer Component State from Shared Context API</summary>

App.js:

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

context/DataContext.js:

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

Header.js:

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

Footer.js:

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

</details>

+EASY PEASY REDUX

<details>
  <summary>171. Using Easy Peasy v5 for State Management</summary>

Install Easy Peasy:

```bs
npm install easy-peasy
```

Create your store -

store.js:

```js
import { createStore, action } from "easy-peasy";

const store = createStore({
  todos: ["Create store", "Wrap application", "Use store"],
  addTodo: action((state, payload) => {
    state.todos.push(payload);
  }),
});
```

Wrap your application -

App.js:

```js
import { StoreProvider } from "easy-peasy";
import { store } from "./store";

function App() {
  return (
    <StoreProvider store={store}>
      <TodoList />
    </StoreProvider>
  );
}
```

Use the store state in your components -

TodoList.js:

```js
import { useStoreState, useStoreActions } from "easy-peasy";

function TodoList() {
  const todos = useStoreState((state) => state.todos);
  const addTodo = useStoreActions((actions) => actions.addTodo);
  return (
    <div>
      {todos.map((todo, idx) => (
        <div key={idx}>{todo}</div>
      ))}
      <AddTodo onAdd={addTodo} />
    </div>
  );
}
```

</details>

<details>
  <summary>172. Blog App - Create Easy Peasy store </summary>

Remove unused packages:

```bs
npm uninstall @testing-library/jest-dom @testing-library/react @testing-library/user-event web-vitals
```

Install Easy Peasy v5 Redux:

```bs
npm install easy-peasy
```

Start npx server:

```bs
npx json-server -p 3500 -w data/db.json
```

store.js:

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

</details>

<details>
  <summary>173.  Blog App - Refactoring Index.js and App.js </summary>

index.js:

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

App.js:

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

</details>

<details>
  <summary>174. Blog App - Refactoring Nav.js</summary>

Nav.js:

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

</details>

<details>
  <summary>175. Blog App - Refactoring Home.js</summary>

Home.js:

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

</details>

<details>
  <summary>176. Blog App - Refactoring PostPage.js</summary>

PostPage.js:

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

</details>

<details>
  <summary>177. Blog App - Refactoring NewPost.js</summary>

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

</details>

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

</details>

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

</details>

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

</details>

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

</details>

<details>
  <summary>182. sample</summary>

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

</details>

<details>
  <summary>183. sample</summary>

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

</details>

<details>
  <summary>184. sample</summary>

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

</details>

<details>
  <summary>185. sample</summary>

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

</details>

<details>
  <summary>186. sample</summary>

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

</details>

<details>
  <summary>187. sample</summary>

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

</details>

<details>
  <summary>188. sample</summary>

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

</details>

<details>
  <summary>189. sample</summary>

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

</details>

<details>
  <summary>190. sample</summary>

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

</details>

<details>
  <summary>191. sample</summary>

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

</details>

<details>
  <summary>192. sample</summary>

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

</details>

<details>
  <summary>193. sample</summary>

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

</details>

<details>
  <summary>194. sample</summary>

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

</details>

<details>
  <summary>195. sample</summary>

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

</details>

<details>
  <summary>196. sample</summary>

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

</details>

<details>
  <summary>197. sample</summary>

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

</details>

<details>
  <summary>198. sample</summary>

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

</details>

<details>
  <summary>199. sample</summary>

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

</details>

<details>
  <summary>200. sample</summary>

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

</details>
