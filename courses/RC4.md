### [B4-NEXTJS TUTORIAL - NET NINJA](/courses/B4.md)

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