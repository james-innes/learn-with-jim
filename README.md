# Learn With Jim 🧙🏼‍♂️

No bullshit, hardly any reading 🥱 lets go 🏃🏻‍♂️

## ⚒️ Setup the tools you need

- Install 💙 [Visual Studio Code](https://code.visualstudio.com) which is our
  code editor. (Like MS Word but for code)

### Github Account

- Create a 😺 [Github](https://github.com) account
- Make your username `first-last` for example `john-smith`

This naming style is called `kebab-case` 🥙. We also have "camelCase" 🐫 and
"snake_case" 🐍.

### Create a new repository

- Create a new repository on Github ✔️
  - Call it `shitty-website`
  - Make it public
  - Select `Add a README file`

### Install Git

In the normie world people do things like name a Word document like this 🤮

- "My Project.docx"
- "My Project (2).docx"
- "My Project (3).docx"
- "My Project Nearly finished.docx"
- "My Projt 100% done.docx"

And people email the document about to each other. Programmers use a tool called
Git to keep track of changes to their code. And we use Github to store our code
and make it easy to share with others.

So instead we use the following workflow:

- Make a change to the code
- Select which of the changes we are happy with and "commit" them
- We can make make as many "commits" as we like but they are just on our
  computer
- When we are ready we can "push" our changes to Github and everyone else can
  see them

If we want to work with more people on different bits we can use "branches".
This is a bit more advanced but we will cover it later. Imagine multiple authors
having a "branch" for each chapter of a book and then merging them all together
to make a book. When someone want to merge there changes into the "main" branch
(the actual book) they have to resolve any conflicts and create a "pull request"
to ask that the changes are merged.

Your used to downloading software and installing it. Instead we will use a
"package manager" to install Git.

You will need to use the application called "Terminal" to run commands.

- Install 🍺 [Homebrew](https://brew.sh) which is a package manager for Mac

Now we can use Homebrew to install Git:  
`brew install git`

Now to check git is installed:  
`git --help`

### Push your first commit

You have created a repository on Github which is a place to store your code. Now
we need to get the code from Github onto your computer.

- Open Visual Studio Code
- Press `Shift + CMD + P` to open the command palette
- Type `Git: Clone` and press enter
- Select "Clone from GitHub"
- Select the repository you created earlier

You now have a copy of the repo on your computer.

## 👷🏿‍♂️ Create a basic website

### Create a basic HTML page

- Create a new file called `index.html`
- Resist the urge to name things with capital letters

We will use a tandy little tool called Emmet to help us write HTML quickly
without making mistakes.

Open up the `index.html` and type `html:5` and press `TAB`. Magic!

Now what is HTML anyway? It stands for "Hyper Text Markup Language". The World
Wide Web is just lots of fancy documents linked together.

Imagine you write a header and a paragraph on a chalk board. To make the header
you just write it in bigger letters. You can't write "bigger" on a keyboard
unless you go around "SHOUTING IN ALL CAPS". In a Word document there is a
button to style text but under the hood it still has to store this information
somehow.

In HTML we use "tags" which make an "element" to define what things are.

So we use two `p` tags to make a paragraph and a `h1` tag to make a header. In
coding we have "syntax" which is like grammar in English. We have to follow the
rules otherwise it would be utter chaos and nothing would work.

The "syntax" for HTML elements is as follows:

```html
<p><--- Opening "tag" Some text <--- Content</p>
<--- Closing "tag"
```

Now with Emmet we can just type `p` and press `TAB` to get a paragraph.

Checkout [how many](https://www.w3schools.com/TAGS/ref_byfunc.asp) tags there
are for HTML.

A huge thing to understand is that HTML documents are not just a list of
elements but they are nested in a data structure called a "tree".

For example below you can see that the "title" of the document is a child of the
"head" element and the "head" element is a child of the "html" element.

```html
<html>
  <head>
    <title>My Website</title>
  </head>
  <body>
    <h1>My Website</h1>
    <p>Some text</p>
    <section>
      <h2>Section 1</h2>
      <p>Some more text</p>
    </section>
  </body>
</html>
```

### But where my website at?

Well we have the HTML now we just need to display it in a browser. Right Click
the index.html in the sidebar and "Show in Finder". Then double click to open it
in Safari. If you change the HTML and then refresh the page you will see your
changes.

### Add an Image

It's great to tell the computer "hey this is a header" but we often want to give
it more information like "I want this text to be massive and red".

We do this with "attributes". Attributes are like extra information about an
element. We can add attributes to any element.

```html
<h1 style="color: red;">My Website</h1>
```

Above we used the `style` attribute but there are special ones for different
tags.

Now we will use the `src` (that means source) to tell the browser where to find
an image.

```html
<img src="https://placekitten.com/500/500" />
```

Add this and refresh the page. Great and image of a cat! But wait this new `img`
tag doesn't have a closing tag. This is because it is a "self closing" tag. It
doesn't have any content so we don't need to close it.

### Add some CSS

Every browser already has CSS styles built in. People forget this but if they
didn't then your page would just be blank white right now! But the styles are
from the 90s and they are ugly.

Play around by selecting different CSS "Cascading Style Sheets" options in the
rop left of this [cool website](https://dohliam.github.io/dropin-minimal-css/).

See how it looks completely different. So it's much more complicated to write
HTML then use chalk but look at what fun we can have to make it look nice.

Lets add some CSS to our page. Create a new file called `style.css` and add the
following:

```css
body {
  background-color: hotpink;
  color: yellow;
  font-family: "Comic Sans MS", cursive, sans-serif;
}
```

Now we need to tell the browser to use this CSS file. We do this by adding a
`link` element to the `head` of our HTML.

```html
<link rel="stylesheet" href="style.css" />
```

Now refresh the page and see the changes. Great it looks hideous well we called
it "shitty website" after all 😉.

Notice how instead of it being `text-color` it is `color`. Lots of things in CSS
just don't make sense and you just get used to it.

The way the CSS works is you have a "selector" which says "Hey I'm talking about
**this** thing in my document I want you to style".

You have select the body `element` by calling it directly by it's name.

You can also select elements by their `class` or `id`. These are attributes that
you can add to any element.

```html
<p class="omelette">My Website</p>
```

```css
.omelette {
  color: brown;
  background-color: yellow;
  padding: 10px;
}
```

This means if you have lots of `p` elements you can specify to only style one of
them as an omelette.

And then within the curly braces (more great syntax for you to remember) you
have a list of "properties" with "values".

There are so many properties and values and new ones come along all the time.
Lfe is tough you just have to learn them this way:

1. How do I make something look like this?
2. Google it
3. Copy and paste the code
4. Fiddle with it until it looks right
5. Forget about it 🫤
6. Repeat until you remember it

W3 Schools will always come up in Google - they are your friends.

## 🌎 Get the project online!

### We need to install Node

Don't worry about what this is just do it.

Open up terminal and type `node -v`. If you get a version number then you are
good to go.

Otherwise install `fnm` (fast node manager) by typing
`curl -fsSL https://fnm.vercel.app/install | bash`.

To install Node using `fnm` type: `fnm install --lts`.

Another thing u'll learn is we have different versions of everything. Instead of
picking a number like `v12.18.3` by using `--lts` we are saying "give me the
latest version that is stable". LTS stands for "Long Term Support".

### Create your surge.sh account

Go to [surge.sh](https://surge.sh) and take a look at their cool Walrus logo. We
will use this to host our website.

So you used Homebrew to install Git and you used `fnm` to install Node... now
just to be more confusing we have to use NPM (Node Package Manager) to install
Surge.js.

So open up terminal and type `npm install --global surge`. This will install
surge globally on your computer (not just for one project).

So far we have been using your "terminal" application but there is one built
into VS Code anyway. Press `Ctrl + ~` a few times and notice the terminal. That
weird squiggle `~` is called a "tilde" which sounds like Matilda to me. Matilda
is on the same key as the `backtick` above the `Ctrl` key.

Imagine this is the first time you have ever pressed this key on your MacBook.

Anyway now type `surge` in the integrated terminal and follow the instructions
to publish your shitty website.

Your using a CLI (Command Line Interface) not a GUI (Graphical User Interface)
here so you can't just waggle your mouse over the options you have to type them
or select them with the arrow keys and press `Enter` to make a selection.

## 🏆 Make it look better

If you get this far we can explore CSS more to make this look like a polished
portfolio website or we make make a pie shop with Apple Pay.
