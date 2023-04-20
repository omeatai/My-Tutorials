### [A2-SCRIMBA JAVASCRIPT TUTORIAL - SCRIMBA](/courses/A2.md)

+INTRO TO APIS

<details>
  <summary>1. How to use Fetch with json</summary>

```Javascript
fetch('http://example.com/movies.json')
  .then((response) => response.json())
  .then((data) => console.log(data));
```

```Javascript
var myRequest = new Request('products.json');//GET
var myRequest = new Request('products.json', {method: "post"});//POST

fetch(myRequest)
  .then(response => response.json())
  .then(data => {
    console.log(data);
  })
  .catch(console.error);
```

</details>

<details>
  <summary>2. API Fetch</summary>

index.js:

```Javascript
fetch("https://dog.ceo/api/breeds/image/random")
    .then(response => response.json())
    .then(data => {
        console.log(data)
        document.getElementById("image-container").innerHTML = `
            <img src="${data.message}" />
        `
    })
```

```Javascript
fetch("https://apis.scrimba.com/bored/api/activity")
    .then(response => response.json())
    .then(data => {
        console.log(data)
        document.getElementById("activity-name").textContent = data.activity
    })
```

</details>

<details>
  <summary>3. Bored-Bot Javascript</summary>

index.js:

```Javascript
document.getElementById("get-activity").addEventListener("click", function() {
  fetch("https://apis.scrimba.com/bored/api/activity")
    .then(response => response.json())
    .then(data => {
      document.getElementById("activity").textContent = data.activity
    })
})

```

</details>

<details>
  <summary>4. Extra Styling</summary>

Index.js:

```Javascript
document.getElementById("get-activity").addEventListener("click", function() {
  fetch("https://apis.scrimba.com/bored/api/activity")
    .then(response => response.json())
    .then(data => {
      document.getElementById("activity").textContent = data.activity
      document.getElementById("title").textContent = "🦾 HappyBot🦿"
      document.body.classList.add("fun")
    })
})

```

Index.css:

```Javascript
body {
    /* uigradients.com */
    background: #bdc3c7;  /* fallback for old browsers */
    background: -webkit-linear-gradient(to top, #2c3e50, #bdc3c7);  /* Chrome 10-25, Safari 5.1-6 */
    background: linear-gradient(to top, #2c3e50, #bdc3c7); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
    background-repeat: no-repeat;
    height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    font-family: Oxygen, sans-serif;
}

button {
    height: 100px;
    width: 100px;
    border-radius: 50%;
    background-color: red;
    border: 1px solid darkred;
    cursor: pointer;
}

.fun {
    /* CSS generated from https://uigradients.com */
    background: #fc4a1a;  /* fallback for old browsers */
    background: -webkit-linear-gradient(to left, #f7b733, #fc4a1a);  /* Chrome 10-25, Safari 5.1-6 */
    background: linear-gradient(to left, #f7b733, #fc4a1a); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
}

```

</details>

+URLs & REST

<details>
  <summary>5. GET Method</summary>

index.js:

```Javascript
fetch("https://apis.scrimba.com/jsonplaceholder/todos", {method: "GET"})
    .then(res => res.json())
    .then(data => console.log(data))
```

</details>

<details>
  <summary>6. Get first 5 blog Posts</summary>

index.js:

```Javascript
fetch("https://apis.scrimba.com/jsonplaceholder/posts")
    .then(res => res.json())
    .then(data => {
        const postsArr = data.slice(0, 5)
        console.log(postsArr)
    })
```

</details>

<details>
  <summary>7. Display Blogs on Page</summary>

index.js:

```Javascript
fetch("https://apis.scrimba.com/jsonplaceholder/posts")
    .then(res => res.json())
    .then(data => {
        const postsArr = data.slice(0, 5)
        let html = ""
        for (let post of postsArr) {
            html += `
                <h3>${post.title}</h3>
                <p>${post.body}</p>
                <hr />
            `
        }
        document.getElementById("blog-list").innerHTML = html
    })

```

</details>

<details>
  <summary>8. BlogSpace - Adding Navbar</summary>

index.html:

```html
<html>
  <head>
    <link rel="preconnect" href="https://fonts.gstatic.com" />
    <link
      href="https://fonts.googleapis.com/css2?family=Karla:wght@200;400;700&display=swap"
      rel="stylesheet"
    />
    <link rel="stylesheet" href="index.css" />
  </head>
  <body>
    <nav>
      <h3>BlogSpace</h3>
    </nav>
    <div id="blog-list"></div>
    <script src="index.js"></script>
  </body>
</html>
```

Index.css:

```css
body {
  font-family: "Karla", sans-serif;
  margin: 0;
  padding: 0;
}

nav {
  background-color: beige;
  padding: 5px;
  height: 30px;
  display: flex;
  align-items: center;
  position: fixed;
  width: 100%;
}

nav > h3 {
  margin: 0;
}

#blog-list {
  padding: 30px 10px 10px;
}
```

Index.js:

```Javascript
fetch("https://apis.scrimba.com/jsonplaceholder/posts")
    .then(res => res.json())
    .then(data => {
        const postsArr = data.slice(0, 5)
        let html = ""
        for (let post of postsArr) {
            html += `
                <h3>${post.title}</h3>
                <p>${post.body}</p>
                <hr />
            `
        }
        document.getElementById("blog-list").innerHTML = html
    })

```

</details>

<details>
  <summary>9. BlogSpace - Adding Style to Form</summary>

index.css:

```css
body {
  font-family: "Karla", sans-serif;
  margin: 0;
  padding: 0;
}

nav {
  background-color: beige;
  padding: 5px;
  height: 30px;
  display: flex;
  align-items: center;
  position: fixed;
  width: 100%;
}

nav > h3 {
  margin: 0;
}

#blog-list {
  padding: 10px;
}

form {
  padding: 60px 10px 10px;
  display: grid;
  background-color: lightblue;
}

input#post-title,
textarea#post-body {
  margin-bottom: 10px;
}

button {
  padding: 10px;
  font-size: 18px;
  cursor: pointer;
}
```

index.html:

```html
<html>
  <head>
    <link rel="preconnect" href="https://fonts.gstatic.com" />
    <link
      href="https://fonts.googleapis.com/css2?family=Karla:wght@200;400;700&display=swap"
      rel="stylesheet"
    />
    <link rel="stylesheet" href="index.css" />
  </head>
  <body>
    <nav>
      <h3>BlogSpace</h3>
    </nav>
    <form>
      <label for="post-title">Title:</label>
      <input id="post-title" type="text" />
      <label for="post-body">Body:</label>
      <textarea id="post-body"></textarea>
      <button>Post</button>
    </form>
    <div id="blog-list"></div>
    <script src="index.js"></script>
  </body>
</html>
```

Index.js:

```Javascript
fetch("https://apis.scrimba.com/jsonplaceholder/posts")
    .then(res => res.json())
    .then(data => {
        const postsArr = data.slice(0, 5)
        let html = ""
        for (let post of postsArr) {
            html += `
                <h3>${post.title}</h3>
                <p>${post.body}</p>
                <hr />
            `
        }
        document.getElementById("blog-list").innerHTML = html
    })

```

</details>

<details>
  <summary>10. BlogSpace - Form prevent Default</summary>

Index.js:

```Javascript
fetch("https://apis.scrimba.com/jsonplaceholder/posts")
    .then(res => res.json())
    .then(data => {
        const postsArr = data.slice(0, 5)
        let html = ""
        for (let post of postsArr) {
            html += `
                <h3>${post.title}</h3>
                <p>${post.body}</p>
                <hr />
            `
        }
        document.getElementById("blog-list").innerHTML = html
    })

document.getElementById("new-post").addEventListener("submit", function(e) {
    e.preventDefault()
    const postTitle = document.getElementById("post-title").value
    const postBody = document.getElementById("post-body").value
    const data = {
        title: postTitle,
        body: postBody
    }
    console.log(data)
})

```

</details>

<details>
  <summary>11. Requests - Body & Headers</summary>

Index.js:

```Javascript
    method: 'POST', // *GET, POST, PUT, DELETE, etc.
    mode: 'cors', // no-cors, *cors, same-origin
    cache: 'no-cache', // *default, no-cache, reload, force-cache, only-if-cached
    credentials: 'same-origin', // include, *same-origin, omit
    headers: {
      'Content-Type': 'application/json'
      // 'Content-Type': 'application/x-www-form-urlencoded',
    },
    redirect: 'follow', // manual, *follow, error
    referrerPolicy: 'no-referrer', // no-referrer, *no-referrer-when-downgrade, origin, origin-when-cross-origin, same-origin, strict-origin, strict-origin-when-cross-origin, unsafe-url
    body: JSON.stringify(data) // body data type must match "Content-Type" header

```

```Javascript
fetch("https://apis.scrimba.com/jsonplaceholder/todos", {
    method: "POST",
    body: JSON.stringify({
        title: "Buy Milk",
        completed: false
    }),
    headers: {
        "Content-Type": "application/json"
    }
})
    .then(res => res.json())
    .then(data => console.log(data))

```

```Javascript
fetch("https://apis.scrimba.com/jsonplaceholder/posts")
    .then(res => res.json())
    .then(data => {
        const postsArr = data.slice(0, 5)
        let html = ""
        for (let post of postsArr) {
            html += `
                <h3>${post.title}</h3>
                <p>${post.body}</p>
                <hr />
            `
        }
        document.getElementById("blog-list").innerHTML = html
    })

document.getElementById("new-post").addEventListener("submit", function(e) {
    e.preventDefault()
    const postTitle = document.getElementById("post-title").value
    const postBody = document.getElementById("post-body").value
    const data = {
        title: postTitle,
        body: postBody
    }

    const options = {
        method: "POST",
        body: JSON.stringify(data),
        headers: {
            "Content-Type": "application/json"
        }
    }

    fetch("https://apis.scrimba.com/jsonplaceholder/posts", options)
        .then(res => res.json())
        .then(data => console.log(data))
})

```

</details>

<details>
  <summary>12. BlogSpace - Add new posts </summary>

Index.js:

```Javascript
let postsArray = []

function renderPosts() {
    let html = ""
    for (let post of postsArray) {
        html += `
            <h3>${post.title}</h3>
            <p>${post.body}</p>
            <hr />
        `
    }
    document.getElementById("blog-list").innerHTML = html
}

fetch("https://apis.scrimba.com/jsonplaceholder/posts")
    .then(res => res.json())
    .then(data => {
        postsArray = data.slice(0, 5)
        renderPosts()
    })

document.getElementById("new-post").addEventListener("submit", function(e) {
    e.preventDefault()
    const postTitle = document.getElementById("post-title").value
    const postBody = document.getElementById("post-body").value
    const data = {
        title: postTitle,
        body: postBody
    }

    const options = {
        method: "POST",
        body: JSON.stringify(data),
        headers: {
            "Content-Type": "application/json"
        }
    }

    fetch("https://apis.scrimba.com/jsonplaceholder/posts", options)
        .then(res => res.json())
        .then(post => {
            postsArray.unshift(post)
            renderPosts()
        })
})
```

</details>

<details>
  <summary>13. BlogSpace - Reset Form</summary>

Index.js:

```Javascript
let postsArray = []
const titleInput = document.getElementById("post-title")
const bodyInput = document.getElementById("post-body")
const form = document.getElementById("new-post")

function renderPosts() {
    let html = ""
    for (let post of postsArray) {
        html += `
            <h3>${post.title}</h3>
            <p>${post.body}</p>
            <hr />
        `
    }
    document.getElementById("blog-list").innerHTML = html
}

fetch("https://apis.scrimba.com/jsonplaceholder/posts")
    .then(res => res.json())
    .then(data => {
        postsArray = data.slice(0, 5)
        renderPosts()
    })

form.addEventListener("submit", function(e) {
    e.preventDefault()
    const postTitle = titleInput.value
    const postBody = bodyInput.value
    const data = {
        title: postTitle,
        body: postBody
    }

    const options = {
        method: "POST",
        body: JSON.stringify(data),
        headers: {
            "Content-Type": "application/json"
        }
    }

    fetch("https://apis.scrimba.com/jsonplaceholder/posts", options)
        .then(res => res.json())
        .then(post => {
            postsArray.unshift(post)
            renderPosts()
            titleInput.value = ""
            bodyInput.value = ""
            // form.reset()
        })
})

```

</details>

<details>
  <summary>14. URL Query Strings</summary>

```markdown
1. Get a list of all bike racks sold on the site?
   /bikeracks

2. Get a list of all bike racks available in the physical store right now?
   (Assume a query called "available" that is a boolean true/false)
   /bikeracks?available=true ==> {available: "true"} (Will be parsed as a string)

3. Get a list of all "Thule"-brand bike racks that can hold 4 bikes?
   (Assume there are "brand" and "numBikes" queries)
   /bikeracks?brand=thule&numBikes=4
```

</details>

+ASYNC JAVASCRIPT

<details>
  <summary>15. Callback Function</summary>

Index.js:

```Javascript
function handleClick() {
    fetch("https://apis.scrimba.com/deckofcards/api/deck/new/shuffle/")
        .then(res => res.json())
        .then(data => console.log(data))
}

document.getElementById("new-deck").addEventListener("click", handleClick)
```

</details>

<details>
  <summary>16. Callback with setTimeout</summary>

Index.js:

```Javascript
function callback() {
    console.log("I finally ran!")
}

setTimeout(callback, 2000)

```

</details>

<details>
  <summary>17. Callback with Filter</summary>

Index.js:

```Javascript
const people = [
    { name: "Jack", hasPet: true, age: 12 },
    { name: "Jill", hasPet: false, age: 18 },
    { name: "Alice", hasPet: true, age: 22 },
    { name: "Bob", hasPet: false, age: 32 },
]

function gimmeThePets(person) {
    return person.hasPet
}

const peopleWithPets = people.filter(gimmeThePets)
console.log(peopleWithPets)

```

```Javascript
const people = [
    { name: "Jack", hasPet: true, age: 12 },
    { name: "Jill", hasPet: false, age: 18 },
    { name: "Alice", hasPet: true, age: 22 },
    { name: "Bob", hasPet: false, age: 32 },
]

const adults = people.filter(person => person.age >= 18)

console.log(adults)

```

```Javascript
function handleClick() {
    fetch("https://apis.scrimba.com/deckofcards/api/deck/new/shuffle/")
        .then(res => res.json())
        .then(data => console.log(data))
}

document.getElementById("new-deck").addEventListener("click", handleClick)

const people = [
    { name: "Jack", hasPet: true },
    { name: "Jill", hasPet: false },
    { name: "Alice", hasPet: true },
    { name: "Bob", hasPet: false },
]

function filterArray(array, callback) {
    const resultingArray = []
    for (let item of array) {
        const shouldBeIncluded = callback(item)
        if (shouldBeIncluded) {
            resultingArray.push(item)
        }
    }
    return resultingArray
}

const peopleWithPets = filterArray(people, function(person) {
    return person.hasPet
})

console.log(peopleWithPets)

```

</details>

<details>
  <summary>18. Method chaining with Filter and Map</summary>

Index.js:

```Javascript
const voters = [
    {name: "Joe", email: "joe@joe.com", voted: true},
    {name: "Jane", email: "jane@jane.com", voted: true},
    {name: "Bo", email: "bo@bo.com", voted: false},
    {name: "Bane", email: "bane@bane.com", voted: false}
]

const finalResult = voters.filter(voter => voter.voted).map(voter => voter.email)
console.log(finalResult)

```

</details>

<details>
  <summary>19. Promises - passing basic values</summary>

Index.js:

```Javascript
fetch("https://apis.scrimba.com/bored/api/activity")
    .then(function(res) {
        return "Hello"
    })
    .then(function(whatever) {
        console.log(whatever)
        return "World"
    })
    .then(function(another) {
        console.log(another)
    })

```

</details>

<details>
  <summary>20. War - Draw 2 cards from Deck</summary>

Index.js:

```Javascript
let deckId

function handleClick() {
    fetch("https://apis.scrimba.com/deckofcards/api/deck/new/shuffle/")
        .then(res => res.json())
        .then(data => {
            console.log(data)
            deckId = data.deck_id
        })
}

document.getElementById("new-deck").addEventListener("click", handleClick)

document.getElementById("draw-cards").addEventListener("click", () => {
    fetch(`https://apis.scrimba.com/deckofcards/api/deck/${deckId}/draw/?count=2`)
        .then(res => res.json())
        .then(data => console.log(data))
})

```

</details>

<details>
  <summary>21. War - Display our Card Images</summary>

Index.js:

```Javascript
let deckId

function handleClick() {
    fetch("https://apis.scrimba.com/deckofcards/api/deck/new/shuffle/")
        .then(res => res.json())
        .then(data => {
            console.log(data)
            deckId = data.deck_id
        })
}

document.getElementById("new-deck").addEventListener("click", handleClick)

document.getElementById("draw-cards").addEventListener("click", () => {
    fetch(`https://apis.scrimba.com/deckofcards/api/deck/${deckId}/draw/?count=2`)
        .then(res => res.json())
        .then(data => {
            console.log(data.cards)
            document.getElementById("cards").innerHTML = `
                <img src=${data.cards[0].image} />
                <img src=${data.cards[1].image} />
            `
        })
})

```

</details>

<details>
  <summary>22. War - Styling</summary>

Index.html:

```html
<html>
  <head>
    <link rel="preconnect" href="https://fonts.gstatic.com" />
    <link
      href="https://fonts.googleapis.com/css2?family=Exo+2:wght@300&display=swap"
      rel="stylesheet"
    />
    <link rel="stylesheet" href="index.css" />
  </head>
  <body>
    <button id="new-deck">New Deck</button>
    <div id="cards">
      <div class="card-slot"></div>
      <div class="card-slot"></div>
    </div>
    <button id="draw-cards" class="draw">Draw</button>
    <script src="index.js"></script>
  </body>
</html>
```

Index.css:

```css
html,
body {
  margin: 0;
  padding: 0;
  background-image: url("img/table.png");
  font-family: "Exo 2", sans-serif;
  height: 100vh;
}

body {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
}

button {
  background-color: #fff100;
  cursor: pointer;
  border: none;
}

button#new-deck {
  align-self: flex-start;
  padding: 5px;
}

button.draw {
  font-size: 1.2em;
  padding: 5px;
  align-self: stretch;
}

div.card-slot {
  border: 1px solid black;
  border-radius: 5px;
  height: 120px;
  width: calc(120px * 5 / 7);
}

div.card-slot:nth-of-type(1) {
  margin-bottom: 50px;
}

img.card {
  width: 100%;
  height: 100%;
}
```

Index.js:

```Javascript
let deckId
const cardsContainer = document.getElementById("cards")
const newDeckBtn = document.getElementById("new-deck")
const drawCardBtn = document.getElementById("draw-cards")

function handleClick() {
    fetch("https://apis.scrimba.com/deckofcards/api/deck/new/shuffle/")
        .then(res => res.json())
        .then(data => {
            deckId = data.deck_id
        })
}

newDeckBtn.addEventListener("click", handleClick)

drawCardBtn.addEventListener("click", () => {
    fetch(`https://apis.scrimba.com/deckofcards/api/deck/${deckId}/draw/?count=2`)
        .then(res => res.json())
        .then(data => {
            cardsContainer.children[0].innerHTML = `
                <img src=${data.cards[0].image} class="card" />
            `
            cardsContainer.children[1].innerHTML = `
                <img src=${data.cards[1].image} class="card" />
            `
        })
})

```

</details>

<details>
  <summary>23. Determine Winning Card</summary>

Index.js:

```Javascript
let deckId
const cardsContainer = document.getElementById("cards")
const newDeckBtn = document.getElementById("new-deck")
const drawCardBtn = document.getElementById("draw-cards")
const header = document.getElementById("header")

function handleClick() {
    fetch("https://apis.scrimba.com/deckofcards/api/deck/new/shuffle/")
        .then(res => res.json())
        .then(data => {
            deckId = data.deck_id
            console.log(deckId)
        })
}

newDeckBtn.addEventListener("click", handleClick)

drawCardBtn.addEventListener("click", () => {
    fetch(`https://apis.scrimba.com/deckofcards/api/deck/${deckId}/draw/?count=2`)
        .then(res => res.json())
        .then(data => {
            cardsContainer.children[0].innerHTML = `
                <img src=${data.cards[0].image} class="card" />
            `
            cardsContainer.children[1].innerHTML = `
                <img src=${data.cards[1].image} class="card" />
            `
            const winnerText = determineCardWinner(data.cards[0], data.cards[1])
            header.textContent = winnerText
        })
})

function determineCardWinner(card1, card2) {
    const valueOptions = ["2", "3", "4", "5", "6", "7", "8", "9",
    "10", "JACK", "QUEEN", "KING", "ACE"]
    const card1ValueIndex = valueOptions.indexOf(card1.value)
    const card2ValueIndex = valueOptions.indexOf(card2.value)

    if (card1ValueIndex > card2ValueIndex) {
        return "Card 1 wins!"
    } else if (card1ValueIndex < card2ValueIndex) {
        return "Card 2 wins!"
    } else {
        return "War!"
    }
}

```

</details>

<details>
  <summary>24. Display Remaining Cards</summary>

Index.js:

```Javascript
let deckId
const cardsContainer = document.getElementById("cards")
const newDeckBtn = document.getElementById("new-deck")
const drawCardBtn = document.getElementById("draw-cards")
const header = document.getElementById("header")
const remainingText = document.getElementById("remaining")

function handleClick() {
    fetch("https://apis.scrimba.com/deckofcards/api/deck/new/shuffle/")
        .then(res => res.json())
        .then(data => {
            remainingText.textContent = `Remaining cards: ${data.remaining}`
            deckId = data.deck_id
            console.log(deckId)
        })
}

newDeckBtn.addEventListener("click", handleClick)

drawCardBtn.addEventListener("click", () => {
    fetch(`https://apis.scrimba.com/deckofcards/api/deck/${deckId}/draw/?count=2`)
        .then(res => res.json())
        .then(data => {
            remainingText.textContent = `Remaining cards: ${data.remaining}`
            cardsContainer.children[0].innerHTML = `
                <img src=${data.cards[0].image} class="card" />
            `
            cardsContainer.children[1].innerHTML = `
                <img src=${data.cards[1].image} class="card" />
            `
            const winnerText = determineCardWinner(data.cards[0], data.cards[1])
            header.textContent = winnerText
        })
})

function determineCardWinner(card1, card2) {
    const valueOptions = ["2", "3", "4", "5", "6", "7", "8", "9",
    "10", "JACK", "QUEEN", "KING", "ACE"]
    const card1ValueIndex = valueOptions.indexOf(card1.value)
    const card2ValueIndex = valueOptions.indexOf(card2.value)

    if (card1ValueIndex > card2ValueIndex) {
        return "Card 1 wins!"
    } else if (card1ValueIndex < card2ValueIndex) {
        return "Card 2 wins!"
    } else {
        return "War!"
    }
}

```

Index.css:

```css
html,
body {
  margin: 0;
  padding: 0;
  background-image: url("img/table.png");
  font-family: "Exo 2", sans-serif;
  height: 100vh;
}

body {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
  color: white;
}

button {
  background-color: #fff100;
  cursor: pointer;
  border: none;
}

button#new-deck {
  align-self: flex-start;
  padding: 5px;
}

button.draw {
  font-size: 1.2em;
  padding: 5px;
  align-self: stretch;
}

div.card-slot {
  border: 1px solid black;
  border-radius: 5px;
  height: 120px;
  width: calc(120px * 5 / 7);
}

div.card-slot:nth-of-type(1) {
  margin-bottom: 50px;
}

img.card {
  width: 100%;
  height: 100%;
}

div.top {
  display: flex;
  align-items: flex-start;
  align-self: flex-start;
}

div.top > p {
  margin: 0;
  margin-left: 10px;
}
```

</details>

<details>
  <summary>25. Disable the Draw button</summary>

Index.html:

```html
<html>
  <head>
    <link rel="preconnect" href="https://fonts.gstatic.com" />
    <link
      href="https://fonts.googleapis.com/css2?family=Exo+2:wght@300&display=swap"
      rel="stylesheet"
    />
    <link rel="stylesheet" href="index.css" />
  </head>
  <body>
    <div class="top">
      <button id="new-deck">New Deck</button>
      <p id="remaining"></p>
    </div>
    <h2 id="header">Game of War</h2>
    <div id="cards">
      <div class="card-slot"></div>
      <div class="card-slot"></div>
    </div>
    <button id="draw-cards" class="draw">Draw</button>
    <script src="index.js"></script>
  </body>
</html>
```

Index.js:

```Javascript
let deckId
const cardsContainer = document.getElementById("cards")
const newDeckBtn = document.getElementById("new-deck")
const drawCardBtn = document.getElementById("draw-cards")
const header = document.getElementById("header")
const remainingText = document.getElementById("remaining")

function handleClick() {
    fetch("https://apis.scrimba.com/deckofcards/api/deck/new/shuffle/")
        .then(res => res.json())
        .then(data => {
            remainingText.textContent = `Remaining cards: ${data.remaining}`
            deckId = data.deck_id
            console.log(deckId)
        })
}

newDeckBtn.addEventListener("click", handleClick)

drawCardBtn.addEventListener("click", () => {
    fetch(`https://apis.scrimba.com/deckofcards/api/deck/${deckId}/draw/?count=2`)
        .then(res => res.json())
        .then(data => {
            remainingText.textContent = `Remaining cards: ${data.remaining}`
            cardsContainer.children[0].innerHTML = `
                <img src=${data.cards[0].image} class="card" />
            `
            cardsContainer.children[1].innerHTML = `
                <img src=${data.cards[1].image} class="card" />
            `
            const winnerText = determineCardWinner(data.cards[0], data.cards[1])
            header.textContent = winnerText

            if (data.remaining === 0) {
                drawCardBtn.disabled = true
            }
        })
})

function determineCardWinner(card1, card2) {
    const valueOptions = ["2", "3", "4", "5", "6", "7", "8", "9",
    "10", "JACK", "QUEEN", "KING", "ACE"]
    const card1ValueIndex = valueOptions.indexOf(card1.value)
    const card2ValueIndex = valueOptions.indexOf(card2.value)

    if (card1ValueIndex > card2ValueIndex) {
        return "Card 1 wins!"
    } else if (card1ValueIndex < card2ValueIndex) {
        return "Card 2 wins!"
    } else {
        return "War!"
    }
}

```

Index.css:

```css
html,
body {
  margin: 0;
  padding: 0;
  background-image: url("img/table.png");
  font-family: "Exo 2", sans-serif;
  height: 100vh;
}

body {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
  color: white;
}

button {
  background-color: #fff100;
  cursor: pointer;
  border: none;
}

button#new-deck {
  align-self: flex-start;
  padding: 5px;
}

button.draw {
  font-size: 1.2em;
  padding: 5px;
  align-self: stretch;
}

div.card-slot {
  border: 1px solid black;
  border-radius: 5px;
  height: 120px;
  width: calc(120px * 5 / 7);
}

div.card-slot:nth-of-type(1) {
  margin-bottom: 50px;
}

img.card {
  width: 100%;
  height: 100%;
}

div.top {
  display: flex;
  align-items: flex-start;
  align-self: flex-start;
}

div.top > p {
  margin: 0;
  margin-left: 10px;
}

button:disabled {
  cursor: not-allowed;
  background: #dddddd;
}
```

</details>

<details>
  <summary>**26. Javascript ClassList</summary>

```javascript
-- HTML --
<div class='container'></div>

-- JAVASCRIPT --
element.classList.contains('container'); // True or false
element.classList.add('my-class'); // Adds the class if it isn't present yet
element.classList.remove('my-class'); // Removes the class if it’s present
element.classList.toggle('my-class'); // Adds if not present, else removes

```

```javascript
classList.item(index); // Returns the item in the list by its index, or undefined if index is greater than or equal to the list's length
classList.contains(token); // Returns true if the list contains the given token, otherwise false.
classList.add(token1[, ...tokenN]); // Adds the specified token(s) to the list.
classList.remove(token1[, ...tokenN]); // Removes the specified token(s) from the list.
classList.replace(oldToken, newToken); // Replaces token with newToken.
classList.supports(token); // Returns true if a given token is in the associated attribute's supported tokens.
classList.toggle(token[, force]); // Removes token from the list if it exists, or adds token to the list if it doesn't. Returns a boolean indicating whether token is in the list after the operation.
classList.entries(); // Returns an iterator, allowing you to go through all key/value pairs contained in this object.
classList.forEach(callback[ ,thisArg]); // Executes a provided callback function once per DOMTokenList element.
classList.keys(); // Returns an iterator, allowing you to go through all keys of the key/value pairs contained in this object.
classList.values(); // Returns an iterator, allowing you to go through all values of the key/value pairs contained in this object.
```

</details>

<details>
  <summary>27. War - Keep Score</summary>

Index.js:

```Javascript
let deckId
let computerScore = 0
let myScore = 0
const cardsContainer = document.getElementById("cards")
const newDeckBtn = document.getElementById("new-deck")
const drawCardBtn = document.getElementById("draw-cards")
const header = document.getElementById("header")
const remainingText = document.getElementById("remaining")
const computerScoreEl = document.getElementById("computer-score")
const myScoreEl = document.getElementById("my-score")

function handleClick() {
    fetch("https://apis.scrimba.com/deckofcards/api/deck/new/shuffle/")
        .then(res => res.json())
        .then(data => {
            remainingText.textContent = `Remaining cards: ${data.remaining}`
            deckId = data.deck_id
            console.log(deckId)
        })
}

newDeckBtn.addEventListener("click", handleClick)

drawCardBtn.addEventListener("click", () => {
    fetch(`https://apis.scrimba.com/deckofcards/api/deck/${deckId}/draw/?count=2`)
        .then(res => res.json())
        .then(data => {
            remainingText.textContent = `Remaining cards: ${data.remaining}`
            cardsContainer.children[0].innerHTML = `
                <img src=${data.cards[0].image} class="card" />
            `
            cardsContainer.children[1].innerHTML = `
                <img src=${data.cards[1].image} class="card" />
            `
            const winnerText = determineCardWinner(data.cards[0], data.cards[1])
            header.textContent = winnerText

            if (data.remaining === 0) {
                drawCardBtn.disabled = true
            }
        })
})

function determineCardWinner(card1, card2) {
    const valueOptions = ["2", "3", "4", "5", "6", "7", "8", "9",
    "10", "JACK", "QUEEN", "KING", "ACE"]
    const card1ValueIndex = valueOptions.indexOf(card1.value)
    const card2ValueIndex = valueOptions.indexOf(card2.value)

    if (card1ValueIndex > card2ValueIndex) {
        computerScore++
        computerScoreEl.textContent = `Computer score: ${computerScore}`
        return "Computer wins!"
    } else if (card1ValueIndex < card2ValueIndex) {
        myScore++
        myScoreEl.textContent = `My score: ${myScore}`
        return "You win!"
    } else {
        return "War!"
    }
}

```

</details>

<details>
  <summary>28. War - Display the Final Winner</summary>

Index.js:

```Javascript
let deckId
let computerScore = 0
let myScore = 0
const cardsContainer = document.getElementById("cards")
const newDeckBtn = document.getElementById("new-deck")
const drawCardBtn = document.getElementById("draw-cards")
const header = document.getElementById("header")
const remainingText = document.getElementById("remaining")
const computerScoreEl = document.getElementById("computer-score")
const myScoreEl = document.getElementById("my-score")

function handleClick() {
    fetch("https://apis.scrimba.com/deckofcards/api/deck/new/shuffle/")
        .then(res => res.json())
        .then(data => {
            remainingText.textContent = `Remaining cards: ${data.remaining}`
            deckId = data.deck_id
            console.log(deckId)
        })
}

newDeckBtn.addEventListener("click", handleClick)

drawCardBtn.addEventListener("click", () => {
    fetch(`https://apis.scrimba.com/deckofcards/api/deck/${deckId}/draw/?count=2`)
        .then(res => res.json())
        .then(data => {
            remainingText.textContent = `Remaining cards: ${data.remaining}`
            cardsContainer.children[0].innerHTML = `
                <img src=${data.cards[0].image} class="card" />
            `
            cardsContainer.children[1].innerHTML = `
                <img src=${data.cards[1].image} class="card" />
            `
            const winnerText = determineCardWinner(data.cards[0], data.cards[1])
            header.textContent = winnerText

            if (data.remaining === 0) {
                drawCardBtn.disabled = true
                if (computerScore > myScore) {
                    // display "The computer won the game!"
                    header.textContent = "The computer won the game!"
                } else if (myScore > computerScore) {
                    // display "You won the game!"
                    header.textContent = "You won the game!"
                } else {
                    // display "It's a tie game!"
                    header.textContent = "It's a tie game!"
                }
            }
        })
})

function determineCardWinner(card1, card2) {
    const valueOptions = ["2", "3", "4", "5", "6", "7", "8", "9",
    "10", "JACK", "QUEEN", "KING", "ACE"]
    const card1ValueIndex = valueOptions.indexOf(card1.value)
    const card2ValueIndex = valueOptions.indexOf(card2.value)

    if (card1ValueIndex > card2ValueIndex) {
        computerScore++
        computerScoreEl.textContent = `Computer score: ${computerScore}`
        return "Computer wins!"
    } else if (card1ValueIndex < card2ValueIndex) {
        myScore++
        myScoreEl.textContent = `My score: ${myScore}`
        return "You win!"
    } else {
        return "War!"
    }
}

```

</details>

<details>
  <summary>**29. Async/Await JS</summary>

Index.js:

```Javascript
let deckId
let computerScore = 0
let myScore = 0
const cardsContainer = document.getElementById("cards")
const newDeckBtn = document.getElementById("new-deck")
const drawCardBtn = document.getElementById("draw-cards")
const header = document.getElementById("header")
const remainingText = document.getElementById("remaining")
const computerScoreEl = document.getElementById("computer-score")
const myScoreEl = document.getElementById("my-score")

async function handleClick() {
    const res = await fetch("https://apis.scrimba.com/deckofcards/api/deck/new/shuffle/")
    const data = await res.json()
    remainingText.textContent = `Remaining cards: ${data.remaining}`
    deckId = data.deck_id
    console.log(deckId)
}

newDeckBtn.addEventListener("click", handleClick)

drawCardBtn.addEventListener("click", async () => {
    const res = await fetch(`https://apis.scrimba.com/deckofcards/api/deck/${deckId}/draw/?count=2`)
    const data = await res.json()
    remainingText.textContent = `Remaining cards: ${data.remaining}`
    cardsContainer.children[0].innerHTML = `
        <img src=${data.cards[0].image} class="card" />
    `
    cardsContainer.children[1].innerHTML = `
        <img src=${data.cards[1].image} class="card" />
    `
    const winnerText = determineCardWinner(data.cards[0], data.cards[1])
    header.textContent = winnerText

    if (data.remaining === 0) {
        drawCardBtn.disabled = true
        if (computerScore > myScore) {
            header.textContent = "The computer won the game!"
        } else if (myScore > computerScore) {
            header.textContent = "You won the game!"
        } else {
            header.textContent = "It's a tie game!"
        }
    }
})

function determineCardWinner(card1, card2) {
    const valueOptions = ["2", "3", "4", "5", "6", "7", "8", "9",
    "10", "JACK", "QUEEN", "KING", "ACE"]
    const card1ValueIndex = valueOptions.indexOf(card1.value)
    const card2ValueIndex = valueOptions.indexOf(card2.value)

    if (card1ValueIndex > card2ValueIndex) {
        computerScore++
        computerScoreEl.textContent = `Computer score: ${computerScore}`
        return "Computer wins!"
    } else if (card1ValueIndex < card2ValueIndex) {
        myScore++
        myScoreEl.textContent = `My score: ${myScore}`
        return "You win!"
    } else {
        return "War!"
    }
}

```

</details>

+PROMISE REJECTION

<details>
  <summary>30. Get Photo from Unsplash for background</summary>

Index.js:

```Javascript
fetch("https://apis.scrimba.com/unsplash/photos/random?orientation=landscape&query=nature")
    .then(res => res.json())
    .then(data => {
        document.body.style.backgroundImage = `url(${data.urls.full})`
    })

```

Index.css:

```css
html,
body {
  margin: 0;
  padding: 0;
}

body {
  background: no-repeat center center fixed;
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
}
```

</details>

<details>
  <summary>31. Add Author Info</summary>

Index.js:

```Javascript
fetch("https://apis.scrimba.com/unsplash/photos/random?orientation=landscape&query=nature")
    .then(res => res.json())
    .then(data => {
      document.body.style.backgroundImage = `url(${data.urls.regular})`
      document.getElementById("author").textContent = `By: ${data.user.name}`
    })

```

</details>

<details>
  <summary>32. Setup Layout</summary>

Index.js:

```Javascript
fetch("https://apis.scrimba.com/unsplash/photos/random?orientation=landscape&query=nature")
    .then(res => res.json())
    .then(data => {
        document.body.style.backgroundImage = `url(${data.urls.regular})`
		document.getElementById("author").textContent = `By: ${data.user.name}`
    })

```

Index.html:

```html
<html>
  <head>
    <link rel="stylesheet" href="index.css" />
  </head>
  <body>
    <main>
      <div class="top">
        <p>Crypto</p>
        <p>Weather</p>
      </div>

      <h1 class="time">TIME HERE</h1>

      <p id="author"></p>
    </main>
    <script src="index.js"></script>
  </body>
</html>
```

Index.css:

```css
body {
  margin: 0;
  padding: 15px;
  box-sizing: border-box;
  background: no-repeat center center fixed;
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
  color: white;
  font-family: Arial, Helvetica, sans-serif;
  text-shadow: 2px 2px 2px #474747;
}

main {
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

div.top {
  display: flex;
  justify-content: space-between;
}

h1.time {
  text-align: center;
}
```

</details>

<details>
  <summary>33. Catch Errors - Promise Rejection</summary>

Index.js:

```Javascript
fetch("https://apis.scrimba.com/unsplash/photos/random?orientation=landscape&query=;hjksdf;kljsdfgl;kdsjfgljksdfglkjhsdfg")
    .then(res => res.json())
    .then(data => {
      console.log(data)
      throw Error("I'm an error!")
      // document.body.style.backgroundImage = `url(${data.urls.regular})`
      // document.getElementById("author").textContent = `By: ${data.user.name}`
    })
    .catch(err => {
        console.log("Something went wrong! 😭", err)
        // This is where I can handle the error
        // Choose to use a default background image
    })

```

```Javascript
fetch("https://apis.scrimba.com/unsplash/photos/random?orientation=landscape&query=kjhgdsfljhalskjdhflaksdjhflkjhasdf")
    .then(res => res.json())
    .then(data => {
      console.log(data.urls.regular)
      document.body.style.backgroundImage = `url(${data.urls.regular})`
      document.getElementById("author").textContent = `By: ${data.user.name}`
    })
    .catch(err => {
        document.body.style.backgroundImage = `url(https://images.unsplash.com/photo-1497436072909-60f360e1d4b1?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&ixid=MnwyMTEwMjl8MHwxfHJhbmRvbXx8fHx8fHx8fDE2MjI4NDE2NzA&ixlib=rb-1.2.1&q=80&w=1080)`
        document.getElementById("author").textContent = `By: Ifeanyi Omeata`
        // Report the error to some kind of service
    })

```

</details>

<details>
  <summary>34. Get Dogecoin Data</summary>

Index.js:

```Javascript
fetch("https://apis.scrimba.com/unsplash/photos/random?orientation=landscape&query=nature")
    .then(res => res.json())
    .then(data => {
      document.body.style.backgroundImage = `url(${data.urls.regular})`
      document.getElementById("author").textContent = `By: ${data.user.name}`
    })
    .catch(err => {
        // Use a default background image/author
        document.body.style.backgroundImage = `url(https://images.unsplash.com/photo-1560008511-11c63416e52d?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&ixid=MnwyMTEwMjl8MHwxfHJhbmRvbXx8fHx8fHx8fDE2MjI4NDIxMTc&ixlib=rb-1.2.1&q=80&w=1080)`
        document.getElementById("author").textContent = `By: Dodi Achmad`
    })

fetch("https://api.coingecko.com/api/v3/coins/dogecoin")
    .then(res => res.json())
    .then(data => console.log(data))
    .catch(err => console.error(err))

```

</details>

<details>
  <summary>35. Check for Error Responses</summary>

Index.js:

```Javascript
fetch("https://api.coingecko.com/api/v3/coins/dogecoin")
    .then(res => res.json())
    .then(data => {
        throw Error("This is an error")
        console.log(data)
    })
    .catch(err => console.error(err))

```

```Javascript
https://httpstat.us/200
```

```Javascript
fetch("https://httpstat.us/404")
    .then(res => {
        console.log(res.ok)
        console.log(res.status)
        // return res.json()
    })
    // .then(data => {
    //     console.log(data)
    // })
    // .catch(err => console.error(err))
```

```Javascript
fetch("https://api.coingecko.com/api/v3/coins/dogecoinsdfkhsdlfkjhsldkjfhsdf")
    .then(res => {
        if (!res.ok) {
            throw Error("Something went wrong")
        }
        console.log(res.status)
        return res.json()
    })
    .then(data => {
        console.log(data)
    })
    .catch(err => console.error(err))

```

</details>

<details>
  <summary>36. Display Name and Icon</summary>

Index.js:

```Javascript
fetch("https://apis.scrimba.com/unsplash/photos/random?orientation=landscape&query=nature")
    .then(res => res.json())
    .then(data => {
        document.body.style.backgroundImage = `url(${data.urls.regular})`
		document.getElementById("author").textContent = `By: ${data.user.name}`
    })
    .catch(err => {
        // Use a default background image/author
        document.body.style.backgroundImage = `url(https://images.unsplash.com/photo-1560008511-11c63416e52d?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&ixid=MnwyMTEwMjl8MHwxfHJhbmRvbXx8fHx8fHx8fDE2MjI4NDIxMTc&ixlib=rb-1.2.1&q=80&w=1080
)`
		document.getElementById("author").textContent = `By: Dodi Achmad`
    })

fetch("https://api.coingecko.com/api/v3/coins/dogecoin")
    .then(res => {
        if (!res.ok) {
            throw Error("Something went wrong")
        }
        return res.json()
    })
    .then(data => {
        document.getElementById("crypto-top").innerHTML = `
            <img src=${data.image.small} />
            <span>${data.name}</span>
        `
    })
    .catch(err => console.error(err))

```

Index.html:

```html
<html>
  <head>
    <link rel="stylesheet" href="index.css" />
  </head>
  <body>
    <main>
      <div class="top">
        <div id="crypto">
          <div id="crypto-top"></div>
        </div>
        <p>Weather</p>
      </div>

      <h1 class="time">TIME HERE</h1>

      <p id="author"></p>
    </main>
    <script src="index.js"></script>
  </body>
</html>
```

Index.css:

```css
* {
  box-sizing: border-box;
}

body {
  margin: 0;
  background: no-repeat center center fixed;
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
  color: white;
  font-family: Arial, Helvetica, sans-serif;
  text-shadow: 0px 0px 20px #242424;
}

main {
  padding: 15px;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

div.top {
  display: flex;
  justify-content: space-between;
}

h1.time {
  text-align: center;
}

div#crypto {
  font-size: 1.3rem;
}

div#crypto-top {
  display: flex;
  align-items: center;
}

div#crypto-top > span {
  margin-left: 10px;
}
```

</details>

<details>
  <summary>37. Get Crypto Prices</summary>

Index.js:

```Javascript
fetch("https://apis.scrimba.com/unsplash/photos/random?orientation=landscape&query=nature")
    .then(res => res.json())
    .then(data => {
      document.body.style.backgroundImage = `url(${data.urls.regular})`
      document.getElementById("author").textContent = `By: ${data.user.name}`
    })
    .catch(err => {
      // Use a default background image/author
      document.body.style.backgroundImage = `url(https://images.unsplash.com/photo-1560008511-11c63416e52d?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&ixid=MnwyMTEwMjl8MHwxfHJhbmRvbXx8fHx8fHx8fDE2MjI4NDIxMTc&ixlib=rb-1.2.1&q=80&w=1080
)`
      document.getElementById("author").textContent = `By: Dodi Achmad`
      })

fetch("https://api.coingecko.com/api/v3/coins/dogecoin")
    .then(res => {
        if (!res.ok) {
            throw Error("Something went wrong")
        }
        return res.json()
    })
    .then(data => {
        document.getElementById("crypto-top").innerHTML = `
            <img src=${data.image.small} />
            <span>${data.name}</span>
        `
        document.getElementById("crypto").innerHTML += `
            <p>🎯: $${data.market_data.current_price.usd}</p>
            <p>👆: $${data.market_data.high_24h.usd}</p>
            <p>👇: $${data.market_data.low_24h.usd}</p>
        `
    })
    .catch(err => console.error(err))

```

Index.html:

```html
<html>
  <head>
    <link rel="stylesheet" href="index.css" />
  </head>
  <body>
    <main>
      <div class="top">
        <div id="crypto">
          <div id="crypto-top"></div>
        </div>
        <p>Weather</p>
      </div>

      <h1 class="time">TIME HERE</h1>

      <p id="author"></p>
    </main>
    <script src="index.js"></script>
  </body>
</html>
```

Index.css:

```css
* {
  box-sizing: border-box;
}

body {
  margin: 0;
  background: no-repeat center center fixed;
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
  color: white;
  font-family: Arial, Helvetica, sans-serif;
  text-shadow: 0px 0px 20px #242424;
}

main {
  padding: 15px;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

div.top {
  display: flex;
  justify-content: space-between;
}

h1.time {
  text-align: center;
}

div#crypto {
  font-size: 1.3rem;
}

div#crypto > p {
  margin: 0;
}

div#crypto-top {
  display: flex;
  align-items: center;
  margin-bottom: 5px;
}

div#crypto-top > span {
  margin-left: 10px;
}
```

</details>

<details>
  <summary>38. Full Digital Clock</summary>

Index.js:

```Javascript
function getDateTime() {
        var now     = new Date();
        var year    = now.getFullYear();
        var month   = now.getMonth()+1;
        var day     = now.getDate();
        var hour    = now.getHours();
        var minute  = now.getMinutes();
        var second  = now.getSeconds();
        if(month.toString().length == 1) {
             month = '0'+month;
        }
        if(day.toString().length == 1) {
             day = '0'+day;
        }
        if(hour.toString().length == 1) {
             hour = '0'+hour;
        }
        if(minute.toString().length == 1) {
             minute = '0'+minute;
        }
        if(second.toString().length == 1) {
             second = '0'+second;
        }
        var dateTime = year+'/'+month+'/'+day+' '+hour+':'+minute+':'+second;
         return dateTime;
    }

    // example usage: realtime clock
    setInterval(function(){
        currentTime = getDateTime();
        document.getElementById("time").innerHTML = currentTime;
    }, 1000);

```

```Javascript
const date = new Date()
console.log(date.toLocaleTimeString("en-us", {timeStyle: "short"}))

const date = new Date()
console.log(date.toLocaleTimeString("en-us"))

```

</details>

<details>
  <summary>39. Display Time on Page</summary>

Index.js:

```Javascript
fetch("https://apis.scrimba.com/unsplash/photos/random?orientation=landscape&query=nature")
    .then(res => res.json())
    .then(data => {
        document.body.style.backgroundImage = `url(${data.urls.regular})`
		document.getElementById("author").textContent = `By: ${data.user.name}`
    })
    .catch(err => {
        // Use a default background image/author
        document.body.style.backgroundImage = `url(https://images.unsplash.com/photo-1560008511-11c63416e52d?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&ixid=MnwyMTEwMjl8MHwxfHJhbmRvbXx8fHx8fHx8fDE2MjI4NDIxMTc&ixlib=rb-1.2.1&q=80&w=1080
)`
		document.getElementById("author").textContent = `By: Dodi Achmad`
    })

fetch("https://api.coingecko.com/api/v3/coins/dogecoin")
    .then(res => {
        if (!res.ok) {
            throw Error("Something went wrong")
        }
        return res.json()
    })
    .then(data => {
        document.getElementById("crypto-top").innerHTML = `
            <img src=${data.image.small} />
            <span>${data.name}</span>
        `
        document.getElementById("crypto").innerHTML += `
            <p>🎯: $${data.market_data.current_price.usd}</p>
            <p>👆: $${data.market_data.high_24h.usd}</p>
            <p>👇: $${data.market_data.low_24h.usd}</p>
        `
    })
    .catch(err => console.error(err))

function getCurrentTime() {
    const date = new Date()
    document.getElementById("time").textContent = date.toLocaleTimeString("en-us", {timeStyle: "medium"})
}

setInterval(getCurrentTime, 1000)

```

Index.html:

```html
<html>
  <head>
    <link rel="stylesheet" href="index.css" />
  </head>
  <body>
    <main>
      <div class="top">
        <div id="crypto">
          <div id="crypto-top"></div>
        </div>
        <p>Weather</p>
      </div>

      <h1 id="time" class="time">TIME HERE</h1>

      <p id="author"></p>
    </main>
    <script src="index.js"></script>
  </body>
</html>
```

</details>

<details>
  <summary>40. Geolocation.getCurrentPosition()</summary>

```Javascript
const options = {
  enableHighAccuracy: true,
  timeout: 5000,
  maximumAge: 0
};

function success(pos) {
  const crd = pos.coords;

  console.log('Your current position is:');
  console.log(`Latitude : ${crd.latitude}`);
  console.log(`Longitude: ${crd.longitude}`);
  console.log(`More or less ${crd.accuracy} meters.`);
}

function error(err) {
  console.warn(`ERROR(${err.code}): ${err.message}`);
}

navigator.geolocation.getCurrentPosition(success, error, options);

```

Watching the current position
If the position data changes (either by device movement or if more accurate geo information arrives), you can set up a callback function that is called with that updated position information. This is done using the watchPosition() function, which has the same input parameters as getCurrentPosition(). The callback function is called multiple times, allowing the browser to either update your location as you move, or provide a more accurate location as different techniques are used to geolocate you. The error callback function, which is optional just as it is for getCurrentPosition(), can be called repeatedly.

```Javascript
function success(position) {
  doSomething(position.coords.latitude, position.coords.longitude);
}

function error() {
  alert('Sorry, no position available.');
}

const options = {
  enableHighAccuracy: true,
  maximumAge: 30000,
  timeout: 27000
};

const watchID = navigator.geolocation.watchPosition(success, error, options);

```

The watchPosition() method returns an ID number that can be used to uniquely identify the requested position watcher; you use this value in tandem with the clearWatch() method to stop watching the user's location.

```Javascript
navigator.geolocation.clearWatch(watchID);

```

The GeolocationCoordinates instance contains a number of properties, but the two you'll use most commonly are latitude and longitude, which are what you need to draw your position on a map. Hence many Geolocation success callbacks look fairly simple:

```Javascript
function success(position) {
  const latitude  = position.coords.latitude;
  const longitude = position.coords.longitude;

  // Do something with your latitude and longitude
}

```

Current weather data

Access current weather data for any location on Earth including over 200,000 cities! We collect and process weather data from different sources such as global and local weather models, satellites, radars and a vast network of weather stations. Data is available in JSON, XML, or HTML format.

```Javascript
https://api.openweathermap.org/data/2.5/weather?lat={lat}&lon={lon}&appid={API key}

```

```Javascript
https://api.openweathermap.org/data/2.5/weather?lat=44.34&lon=10.99&appid={API key}

```

Index.js:

```Javascript
const options = {
  enableHighAccuracy: true,
  timeout: 5000,
  maximumAge: 0
};

function success(pos) {
  const crd = pos.coords;
  console.log('Your current position is:');
  console.log(`Latitude : ${crd.latitude}`);
  console.log(`Longitude: ${crd.longitude}`);
  console.log(`More or less ${crd.accuracy} meters.`);
  fetch(`https://apis.scrimba.com/openweathermap/data/2.5/weather?lat=${crd.latitude}&lon=${crd.longitude}&units=metric`)
    .then(res => res.json())
    .then(data => {
        console.log(data.main)
        document.getElementById("weather").textContent = `${data.main.temp}°C`
    })
}

function error(err) {
  console.warn(`ERROR(${err.code}): ${err.message}`);
}

navigator.geolocation.getCurrentPosition(success, error, options);

```

</details>

<details>
  <summary>41. Get User's current Weather</summary>

Index.js:

```Javascript
fetch("https://apis.scrimba.com/unsplash/photos/random?orientation=landscape&query=nature")
    .then(res => res.json())
    .then(data => {
        document.body.style.backgroundImage = `url(${data.urls.regular})`
		document.getElementById("author").textContent = `By: ${data.user.name}`
    })
    .catch(err => {
        // Use a default background image/author
        document.body.style.backgroundImage = `url(https://images.unsplash.com/photo-1560008511-11c63416e52d?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&ixid=MnwyMTEwMjl8MHwxfHJhbmRvbXx8fHx8fHx8fDE2MjI4NDIxMTc&ixlib=rb-1.2.1&q=80&w=1080
)`
		document.getElementById("author").textContent = `By: Dodi Achmad`
    })

fetch("https://api.coingecko.com/api/v3/coins/dogecoin")
    .then(res => {
        if (!res.ok) {
            throw Error("Something went wrong")
        }
        return res.json()
    })
    .then(data => {
        document.getElementById("crypto-top").innerHTML = `
            <img src=${data.image.small} />
            <span>${data.name}</span>
        `
        document.getElementById("crypto").innerHTML += `
            <p>🎯: $${data.market_data.current_price.usd}</p>
            <p>👆: $${data.market_data.high_24h.usd}</p>
            <p>👇: $${data.market_data.low_24h.usd}</p>
        `
    })
    .catch(err => console.error(err))

navigator.geolocation.getCurrentPosition(position => {
    fetch(`https://apis.scrimba.com/openweathermap/data/2.5/weather?lat=${position.coords.latitude}&lon=${position.coords.longitude}&units=imperial`)
        .then(res => {
            if (!res.ok) {
                throw Error("Weather data not available")
            }
            return res.json()
        })
        .then(data => {
            console.log(data)
        })
        .catch(err => console.error(err))
});


// position: GeolocationPosition
    // coords: GeolocationCoordinates
        // accuracy: 20
        // altitude: null
        // altitudeAccuracy: null
        // heading: null
        // latitude: 40.5269232
        // longitude: -111.916174
        // speed: null
        // __proto__: GeolocationCoordinates
    // timestamp: 1623170827394

```

</details>

<details>
  <summary>42. Add Weather Icon</summary>

Index.js:

```Javascript
fetch("https://apis.scrimba.com/unsplash/photos/random?orientation=landscape&query=nature")
    .then(res => res.json())
    .then(data => {
        document.body.style.backgroundImage = `url(${data.urls.regular})`
		document.getElementById("author").textContent = `By: ${data.user.name}`
    })
    .catch(err => {
        // Use a default background image/author
        document.body.style.backgroundImage = `url(https://images.unsplash.com/photo-1560008511-11c63416e52d?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&ixid=MnwyMTEwMjl8MHwxfHJhbmRvbXx8fHx8fHx8fDE2MjI4NDIxMTc&ixlib=rb-1.2.1&q=80&w=1080
)`
		document.getElementById("author").textContent = `By: Dodi Achmad`
    })

fetch("https://api.coingecko.com/api/v3/coins/dogecoin")
    .then(res => {
        if (!res.ok) {
            throw Error("Something went wrong")
        }
        return res.json()
    })
    .then(data => {
        document.getElementById("crypto-top").innerHTML = `
            <img src=${data.image.small} />
            <span>${data.name}</span>
        `
        document.getElementById("crypto").innerHTML += `
            <p>🎯: $${data.market_data.current_price.usd}</p>
            <p>👆: $${data.market_data.high_24h.usd}</p>
            <p>👇: $${data.market_data.low_24h.usd}</p>
        `
    })
    .catch(err => console.error(err))

// function getCurrentTime() {
//     const date = new Date()
//     document.getElementById("time").textContent = date.toLocaleTimeString("en-us", {timeStyle: "short"})
// }

// setInterval(getCurrentTime, 1000)

navigator.geolocation.getCurrentPosition(position => {
    fetch(`https://apis.scrimba.com/openweathermap/data/2.5/weather?lat=${position.coords.latitude}&lon=${position.coords.longitude}&units=imperial`)
        .then(res => {
            if (!res.ok) {
                throw Error("Weather data not available")
            }
            return res.json()
        })
        .then(data => {
            // console.log(data)
            const iconUrl = `http://openweathermap.org/img/wn/${data.weather[0].icon}@2x.png`
            document.getElementById("weather").innerHTML = `
                <img src=${iconUrl} />
            `
        })
        .catch(err => console.error(err))
});

```

Index.html:

```html
<html>
  <head>
    <link rel="stylesheet" href="index.css" />
  </head>
  <body>
    <main>
      <div class="top">
        <div id="crypto">
          <div id="crypto-top"></div>
        </div>
        <div id="weather"></div>
      </div>

      <h1 id="time" class="time">TIME HERE</h1>
      <p id="author"></p>
    </main>
    <script src="index.js"></script>
  </body>
</html>
```

</details>

<details>
  <summary>43. Create Chrome Extension</summary>

Manifest.json:

```Json
{
    "manifest_version": 3,
    "name": "Personal Dashboard",
    "version": "1.0.0",
    "description": "Just for practicing async JS",
    "action": {
        "default_icon": "icon.png"
    },
    "browser_action": {
        "default_popup": "index.html"
    }
    "chrome_url_overrides": {
        "newtab": "index.html"
    }
}

```

Index.html:

```html
<html>
  <head>
    <meta charset="UTF-8" />
    <link rel="stylesheet" href="index.css" />
    <title>Personal Dashboard</title>
  </head>
  <body>
    <main>
      <div class="top">
        <div id="crypto">
          <div id="crypto-top"></div>
        </div>
        <div id="weather"></div>
      </div>

      <h1 id="time" class="time"></h1>
      <p id="author"></p>
    </main>
    <script src="index.js"></script>
  </body>
</html>
```

Index.js:

```Javascript
fetch("https://apis.scrimba.com/unsplash/photos/random?orientation=landscape&query=nature")
    .then(res => res.json())
    .then(data => {
        document.body.style.backgroundImage = `url(${data.urls.regular})`
		document.getElementById("author").textContent = `By: ${data.user.name}`
    })
    .catch(err => {
        // Use a default background image/author
        document.body.style.backgroundImage = `url(https://images.unsplash.com/photo-1560008511-11c63416e52d?crop=entropy&cs=tinysrgb&fit=max&fm=jpg&ixid=MnwyMTEwMjl8MHwxfHJhbmRvbXx8fHx8fHx8fDE2MjI4NDIxMTc&ixlib=rb-1.2.1&q=80&w=1080
)`
		document.getElementById("author").textContent = `By: Dodi Achmad`
    })

fetch("https://api.coingecko.com/api/v3/coins/bitcoin")
    .then(res => {
        if (!res.ok) {
            throw Error("Something went wrong")
        }
        return res.json()
    })
    .then(data => {
        document.getElementById("crypto-top").innerHTML = `
            <img src=${data.image.small} />
            <span>${data.name}</span>
        `
        document.getElementById("crypto").innerHTML += `
            <p>🎯: $${data.market_data.current_price.usd}</p>
            <p>👆: $${data.market_data.high_24h.usd}</p>
            <p>👇: $${data.market_data.low_24h.usd}</p>
        `
    })
    .catch(err => console.error(err))

function getCurrentTime() {
    const date = new Date()
    document.getElementById("time").textContent = date.toLocaleTimeString("en-us", {timeStyle: "short"})
}

setInterval(getCurrentTime, 1000)

navigator.geolocation.getCurrentPosition(position => {
    fetch(`https://apis.scrimba.com/openweathermap/data/2.5/weather?lat=${position.coords.latitude}&lon=${position.coords.longitude}&units=imperial`)
        .then(res => {
            if (!res.ok) {
                throw Error("Weather data not available")
            }
            return res.json()
        })
        .then(data => {
            const iconUrl = `http://openweathermap.org/img/wn/${data.weather[0].icon}@2x.png`
            document.getElementById("weather").innerHTML = `
                <img src=${iconUrl} />
                <p class="weather-temp">${Math.round(data.main.temp)}º</p>
                <p class="weather-city">${data.name}</p>
            `
        })
        .catch(err => console.error(err))
});


```

Index.css:

```css
* {
  box-sizing: border-box;
}

body {
  margin: 0;
  background: no-repeat center center fixed;
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
  color: white;
  font-family: Arial, Helvetica, sans-serif;
  text-shadow: 0px 0px 20px #242424;
}

main {
  padding: 15px;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

div.top {
  display: flex;
  justify-content: space-between;
}

h1.time {
  text-align: center;
  font-size: 5rem;
}

div#crypto {
  font-size: 1.3rem;
}

div#crypto > p {
  margin: 0;
}

div#crypto-top {
  display: flex;
  align-items: center;
  margin-bottom: 5px;
}

div#crypto-top > span {
  margin-left: 10px;
}

div#weather {
  display: flex;
  align-items: center;
  flex-wrap: wrap;
  justify-content: flex-end;
  align-self: flex-start;
  margin-top: -20px;
}

div#weather > img {
  width: 70px;
}

p.weather-city {
  width: 100%;
  text-align: right;
  margin: 0;
  margin-top: -10px;
  font-size: 1.2rem;
}

p.weather-temp {
  margin: 0;
  font-size: 1.7rem;
  margin-left: -10px;
}

p#author {
  font-size: 1rem;
}
```

</details>

+AIRBNB

<details>
  <summary>44. sample</summary>

Index.js:

```Javascript


```

```Javascript


```

```Javascript


```

</details>

<details>
  <summary>45. sample</summary>

Index.js:

```Javascript

```

```Javascript


```

```Javascript


```

</details>
