# Creating a simple scroll-fix navbar

I have observed with excitment that some website's header would either change color or be fixed as I scrolled. I wondered, what should be responsible for this? Well I've found something interesting, and I'll share this new finding of mine with you.

## What we are going to build

![Sticky Navbar](assets/sticky_navbar.png)

We are going to build a simple webpage with the navbar below the hero section so that as you scroll down the page, the navbar gets fixed to the top of the browser.

Simple right? Yes it is. The idea is to build simple projects that teach you what you need to know. So let's get it.

## What you need

* vscode
* web browser
* laptop
* rapt attention

---

Setup your directory structure with `index.html`, `style.css` and a `main.js` file.

Open up the `index.html` file with your vscode and key in this `!` then hit the tab key. This should auto generate the boilerplate for you.

It should be looking this good by now

![index.html](assets/index_html.png)

Link up the `style.css` and the `main.js` files

```html
...
    <link rel="stylesheet" href="style.css">
  </head>

  <body>

    <script src="main.js"></script>
  </body>
</html>
```

Now let's add content to our `index.html` file real quick. Within the `<body></body>` tag insert this lines code...

```html
<header>
  <div class="hero">
    <div class="overlay">
      <h2>Learn new sticky tricks</h2>
    </div>
  </div>
</header>
<nav>
  <ul>
    <li class="logo">
      sticky<span>tricks</span>
    </li>
    <li>Home</li>
    <li>About</li>
    <li>Learn</li>
    <li>Connect</li>
  </ul>
</nav>

<section>
  <h3>The Language</h3>
  <p>
    Lorem ipsum dolor sit amet consectetur adipisicing elit. Ducimus molestiae ipsum nesciunt ipsa numquam corporis. Fugiat eveniet neque provident dolore similique doloribus ipsum, numquam obcaecati, quas laborum pariatur nihil! Commodi? Lorem ipsum dolor sit amet consectetur, adipisicing elit. Obcaecati, voluptatibus accusantium repellendus adipisci iste vitae labore architecto laboriosam, excepturi sit officiis maxime molestias placeat nesciunt unde voluptates dolore, veritatis ad?
  </p>

  <p>
    Lorem ipsum dolor sit amet, consectetur adipisicing elit. Veniam sapiente possimus eaque odio error magni voluptatum nisi, pariatur modi laboriosam. At odit quis explicabo, consectetur adipisci doloribus neque harum inventore. Lorem ipsum dolor, sit amet consectetur adipisicing elit. Tenetur labore porro facilis dignissimos mollitia, id earum ullam quos, et ratione cupiditate. Explicabo, veniam cum sit dicta ducimus magni consequatur perspiciatis?
  </p>

  <h3>The Structure</h3>
  <p>
    Lorem ipsum dolor sit amet consectetur adipisicing elit. Ducimus molestiae ipsum nesciunt ipsa numquam corporis.
    Fugiat eveniet neque provident dolore similique doloribus ipsum, numquam obcaecati, quas laborum pariatur nihil!
    Commodi? Lorem ipsum dolor sit amet consectetur, adipisicing elit. Obcaecati, voluptatibus accusantium repellendus
    adipisci iste vitae labore architecto laboriosam, excepturi sit officiis maxime molestias placeat nesciunt unde
    voluptates dolore, veritatis ad?
  </p>

  <p>
    Lorem ipsum dolor sit amet, consectetur adipisicing elit. Veniam sapiente possimus eaque odio error magni voluptatum
    nisi, pariatur modi laboriosam. At odit quis explicabo, consectetur adipisci doloribus neque harum inventore. Lorem
    ipsum dolor, sit amet consectetur adipisicing elit. Tenetur labore porro facilis dignissimos mollitia, id earum ullam
    quos, et ratione cupiditate. Explicabo, veniam cum sit dicta ducimus magni consequatur perspiciatis?
  </p>

  <h3>The Platform</h3>
  <p>
    Lorem ipsum dolor sit amet consectetur adipisicing elit. Ducimus molestiae ipsum nesciunt ipsa numquam corporis.
    Fugiat eveniet neque provident dolore similique doloribus ipsum, numquam obcaecati, quas laborum pariatur nihil!
    Commodi? Lorem ipsum dolor sit amet consectetur, adipisicing elit. Obcaecati, voluptatibus accusantium repellendus
    adipisci iste vitae labore architecto laboriosam, excepturi sit officiis maxime molestias placeat nesciunt unde
    voluptates dolore, veritatis ad?
  </p>

  <p>
    Lorem ipsum dolor sit amet, consectetur adipisicing elit. Veniam sapiente possimus eaque odio error magni voluptatum
    nisi, pariatur modi laboriosam. At odit quis explicabo, consectetur adipisci doloribus neque harum inventore. Lorem
    ipsum dolor, sit amet consectetur adipisicing elit. Tenetur labore porro facilis dignissimos mollitia, id earum ullam
    quos, et ratione cupiditate. Explicabo, veniam cum sit dicta ducimus magni consequatur perspiciatis?
  </p>

  <h3>The Method</h3>
  <p>
    Lorem ipsum dolor sit amet consectetur adipisicing elit. Ducimus molestiae ipsum nesciunt ipsa numquam corporis.
    Fugiat eveniet neque provident dolore similique doloribus ipsum, numquam obcaecati, quas laborum pariatur nihil!
    Commodi? Lorem ipsum dolor sit amet consectetur, adipisicing elit. Obcaecati, voluptatibus accusantium repellendus
    adipisci iste vitae labore architecto laboriosam, excepturi sit officiis maxime molestias placeat nesciunt unde
    voluptates dolore, veritatis ad?
  </p>

  <p>
    Lorem ipsum dolor sit amet, consectetur adipisicing elit. Veniam sapiente possimus eaque odio error magni voluptatum
    nisi, pariatur modi laboriosam. At odit quis explicabo, consectetur adipisci doloribus neque harum inventore. Lorem
    ipsum dolor, sit amet consectetur adipisicing elit. Tenetur labore porro facilis dignissimos mollitia, id earum ullam
    quos, et ratione cupiditate. Explicabo, veniam cum sit dicta ducimus magni consequatur perspiciatis?
  </p>
</section>

<footer>
  <div class="logo_footer">
    sticky<span>Tricks</span> 
  </div>
  <p>copyright&copy; 2018 | visit <a href="http://github.com/phavor" target="_blank">GitHub</a></p>
</footer>
```

Now open it up in your browser, we have to see what we have setup already. Mine looks like this...

![html_markup_preview](assets/html_markup_preview.png)

Am hoping yours looks just the same.

## Beautify with CSS

Now let's get to the fun part of styling our little project. Open your `style.css` and add these lines to normalize the client code.

```css
* {
  padding: 0;
  margin: 0;
}

body {
  font-family: Arial, Helvetica, sans-serif;
  background: #f3f3f3;
}
```

Now we get to the hero section, you can use any image of your choice... here is the code to insert

```css
.hero {
  background: url('../assets/images/ext.jpeg');
  background-size: cover;
  background-position: center center;
  height: 20rem;
}

.overlay {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.7)
}

.overlay h2 {
  color: white;
  text-transform: capitalize;
  font-size: 3rem;
}
```

Our page should be looking like this with your own picture obviosly

![hero_section_preview](assets/hero_section_preview.png)

Now we will style our navbar, so insert these code lines in your stylesheet

```css
nav {
  display: flex;
  background: #0e496b;
  width: 100%;
  position: relative;
}

ul {
  display: flex;
  list-style: none;
}

li {
  flex: 1;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 1rem 5vw;
  cursor: pointer;
  transition: all .4s ease-in-out;
}

li:hover {
  color: aliceblue;
  background: #032d46;
}

li.logo {
  max-width: 0;
  overflow: hidden;
  background: #faf3f3;
  transition: all 0.5s;
  font-size: 1.3rem;
  transition: all .3s ease-in-out;
  transform: translateX(-150px); /* pushes the logo off the screen */
}

li.logo span {
  font-weight: 600;
  color: #02121b;
  text-transform: capitalize;
}

li.logo:hover {
  background: #032d46;
}
```

When you preview your page, you should see a blue shaded navigation bar right below the hero section. The `logo` was sent off the screen with the css rule `transform: translateX(-150px);`

![navbar_preview](assets/navbar_preview.png)

