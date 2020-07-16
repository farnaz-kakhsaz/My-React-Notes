# My React Notes

> This is my random React notes ;)

---

## Table of Contents:

- [Difference between **NVM**, **NPX** and **NPM**](difference-between-nvm-npx-and-npm)
- [What is NPM and Yarn?](#what-is-npm-and-yarn)
- [What is a **Script** and **`react-scripts`** in `create-react-app`?](#what-is-a-script-and-react-scripts-in-create-react-app)
- [Single Page Application (SPA)](#single-page-application-spa)
- [Why **`setState`** doesn't update the state immediately?](#why-setstate-doesnt-update-the-state-immediately)
- [What is **`package-lock.json`**?](#what-is-package-lockjson)

---

## Difference between **NVM**, **NPX** and **NPM**:

### NVM:

Stand for **N**ode **V**ersion **M**anager, and it's a tool to manage and switch between versions of **Node** very easily. But it's also useful to easily install or upgrade the current version of **Node**.

### NPM:

The **npm** stands for **N**ode **P**ackage **M**anager and it is the default package manager for **Node.js**. It is written entirely in **JavaScript**, it was initially released on January 12, 2010. The **npm** manages all the packages and modules for **Node.js** and consists of command–line client **npm**. It gets installed into the system with the **installation of Node.js**. The required packages and modules in the Node project are installed using **npm**. A package contains all the files needed for a module and modules are the JavaScript libraries that can be included in the Node project according to the requirement of the project.
It provides a way for developers to install packages both globally and locally.

**Execute package with npm:**

- **By typing the local path:** You have to write down the local path of your package like below:

  ```
  ./node_modules/.bin/your-package-name
  ```

- **Locally installed:** You have to open the **package.json** file and write down the below scripts:

  ```JSON
  {
      "name": "Your app",
      "versiuon":  "1.0.0",
      "scripts":  {
              "your-package":  "your-package-name"
      }
  }
  ```

**To run package:** After that, you can run your package by running the below command:

```properties
npm run your-package-name
```

### NPX:

The npx stands for **N**ode **P**ackage e**X**ecute and it comes with the npm, when you installed npm **above 5.2.0** version then automatically npx will installed. **It is an npm package runner that can execute any package that you want from the npm registry without even installing that package.** The npx is useful during a single time use package. If you have installed npm below 5.2.0 then npx is not installed in your system. You can check npx is installed or not by running the following command:

```properties
npx -v
```

If npx is not installed you can install that separately by running the below command.

```properties
npm install -g npx
```

**Execute package with npx:**

Sometimes you might want to take a look at a specific package and try out some commands. But you cannot do that without installing the dependencies in your local node_modules folder.
That’s where npx comes in.

- **Directly runnable:** You can execute your package without installation, to do so run the following command.

  ```properties
  npx your-package-name
  ```

**Differences between npm and npx:**

|                                                                   NPM                                                                   |                                                                                    NPX                                                                                    |
| :-------------------------------------------------------------------------------------------------------------------------------------: | :-----------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
|      If you wish to run package through npm then you have to specify that package in your `package.json` and installed it locally.      | A package can be executable without installing the package, it is an npm package runner so if any packages that aren’t already installed it will installed automatically. |
| To use `create-react-app` in npm the commands are `npm install create-react-app` then `create-react-app myApp` (Installation required). |              But in npx you can use that without installing like `npx create-react-app myApp`, this command is required in every app’s life cycle only once.              |
|                                               Npm is a tool that use to install packages.                                               |                                                                Npx is a tool that use to execute packages.                                                                |
|                     Packages used by npm are installed globally you have to care about pollution for the long term.                     |                               Packages used by npx are not installed globally so you have to carefree for the pollution for the long term.                                |

---

## What is NPM and Yarn?

**NPM** and **Yarn** are both package managers. **Package Managers is essentially a way to automate the process of installing, upgrading, configuring or removing software.**

We know that **Yarn** was created by Facebook as an alternative to **NPM**. They created **Yarn** to solve the problems they were having while using **NPM** particularly the problems with consistency, security and speed. **Yarn** has the same feature set while operating faster, more securely and most importantly more reliable.

**NPM Version 5.0**: With their newest release if npm 5 many of the shortcomings of NPM were addressed.

- NPM 5 introduced the `package-lock.json` file for better versioning control.

- NPM 5 is now much faster, but Yarn still edges them out in terms of speed.

- Now supports offline installation for previously downloaded packages.

---

## What is a **Script** and **`react-scripts`** in `create-react-app`?

In programming, **a script is basically a list of instructions that dictates to another program what to do.**

React is no exception; it has scripts to do things.
`create-react-app` ships with four main scripts.

In React apps, scripts are located in the `package.json` file. This file has some default scripts, but it’s still possible to edit them.

```JSON
 "scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test",
    "eject": "react-scripts eject"
  }
```

As you can see, a fresh React app comes with four scripts that use the package `react-scripts`.

---

## Single Page Application (SPA):

With a single page application instead of requesting a page from the server, it's turned more into requesting for data. And this is when we have the ability to communicate with outside servers, maybe servers that we don't control like third-party servers (like Google Firebase database), or we might talk to some different API endpoints so that now we can communicate with different APIs, back and forth and using JavaScript just receive the data (Like what we do in JSONPlaceholder website. By entering into this website we don't get an HTML page, all we get is data that formatted in what we call `JSON`. So this `JSON` data can be converted into a JavaScript object that we can use).

--

A SPA application or website is a web software that downloads all the required content at the time you enter a website. They don't need to download it a dozen more times when you browse to different pages of this site.

--

A single-page application works in the browser and requires no page reloads and no extra time for waiting. The page doesn’t need to be updated since content is downloaded automatically. We use these types of applications every day. Just think of Facebook or Trello. These are excellent examples of single-page apps.

SPAs use AJAX and HTML5 to build responsive apps. JavaScript frameworks such as Angular, React, Vue, and Ember are responsible for handling the heavy lifting on the client side for a single-page app.

---

## Why **`setState`** doesn't update the state immediately?

> `setState()` enqueues changes to the component state and tells React that this component and its children need to be re-rendered with the updated state. This is the primary method you use to update the user interface in response to event handlers and server responses.
>
> Think of `setState()` as a _request_ rather than an immediate command to update the component. **For better perceived performance, React may delay it, and then update several components in a single pass. React does not guarantee that the state changes are applied immediately.**
>
> `setState()` does not always immediately update the component. It may batch or defer the update until later. This makes reading `this.state` right after calling `setState()` a potential pitfall. **Instead, use `componentDidUpdate` or a `setState` callback (`setState(updater, callback)`), either of which are guaranteed to fire after the update has been applied.**
>
> If you need to set the state based on the previous state, read about the `updater` ((`setState(updater, callback)`)) argument below.
>
> `setState()` will always lead to a re-render unless `shouldComponentUpdate()` returns false. If mutable objects are being used and conditional rendering logic cannot be implemented in `shouldComponentUpdate()`, calling `setState()` only when the new state differs from the previous state will avoid unnecessary re-renders.
>
> The first argument is an `updater` function with the signature:
>
> `state` is a reference to the component state at the time the change is being applied. It should not be directly mutated. Instead, changes should be represented by building a new object based on the input from `state` and `props`. For instance, suppose we wanted to increment a value in state by `props.step`:
>
> ```JavaScript
> this.setState((state, props) => {
>   return {counter: state.counter + props.step};
> });
> ```
>
> Both `state` and `props` received by the updater function are guaranteed to be up-to-date. The output of the updater is shallowly merged with `state`.
>
> The second parameter to `setState()` is an optional callback function that will be executed once `setState` is completed and the component is re-rendered. Generally we recommend using `componentDidUpdate()` for such logic instead.
>
> You may optionally pass an object as the first argument to `setState()` instead of a function:
>
> ```JavaScript
> setState(stateChange[, callback])
> ```
>
> This performs a shallow merge of `stateChange` into the new state, e.g., to adjust a shopping cart item quantity:
>
> ```JavaScript
> this.setState({quantity: 2})
> ```
>
> **This form of `setState()` is also asynchronous, and multiple calls during the same cycle may be batched together.** For example, if you attempt to increment an item quantity more than once in the same cycle, that will result in the equivalent of:
>
> ```JavaScript
> Object.assign(
>   previousState,
>   {quantity: state.quantity + 1},
>   {quantity: state.quantity + 1},
>   ...
> )
> ```
>
> Subsequent calls will override values from previous calls in the same cycle, so the quantity will only be incremented once. If the next state depends on the current state, we recommend using the updater function form, instead:
>
> ```JavaScript
> this.setState((state) => {
>   return {quantity: state.quantity + 1};
> });
> ```
>
> [React's documentation](https://reactjs.org/docs/react-component.html#setstate)

**The `setState` is asynchronous.** It means you can’t call setState on one line and assume state has changed on the next.

**_Why would they make setState async:_**

This is because `setState` alters the state and causes rerendering. This can be an expensive operation and making it synchronous might leave the browser unresponsive.

Thus the `setState` calls are asynchronous as well as batched for better UI experience and performance.

--

I was thinking if `setState` in React is asynchronous (which is), so I can use async/await on it. I definitely did NOT suggest using it on the product or any kind of project, but it's good to know it actually works ;)

For example, we can solve the below problem:

```JavaScript
import React, { Component } from "react";

class App extends Component {
  constructor() {
    super();
    this.state = {
      count: 0,
    };
    this.handleClick = this.handleClick.bind(this);
  }

  handleClick() {
    this.setState(
      (state) => ({
        count: state.count + 1,
      }),
      () => console.log("Count value in callback:", this.state.count)
    );
    console.log("Count value next line:", this.state.count);
  }

  render() {
    return (
      <div className="App">
        {console.log("Component renderd!")}
        <h1>{this.state.count}</h1>
        <button onClick={this.handleClick}>Click to add!</button>
      </div>
    );
  }
}

export default App;

// Output:
// Count value next line: 0
// Component renderd!
// Component renderd!
// Count value in callback: 1
```

With async/await function:

```JavaScript
import React, { Component } from "react";

class App extends Component {
  constructor() {
    super();
    this.state = {
      count: 0,
    };
    this.handleClick = this.handleClick.bind(this);
  }

  handleClick() {
    this.setState(
      (state) => ({
        count: state.count + 1,
      }),
      () => console.log("Count value in callback:", this.state.count)
    );
    console.log("Count value next line:", this.state.count);
  }

  render() {
    return (
      <div className="App">
        {console.log("Component renderd!")}
        <h1>{this.state.count}</h1>
        <button onClick={this.handleClick}>Click to add!</button>
      </div>
    );
  }
}

export default App;

// Component renderd!
// Component renderd!
// Count value in callback: 1
// Count value next line: 1
```

But do **NOT** use it in your project. Because I'm not aware of consequences it (if there was). So this is only for education purpose.

---

## What is **`package-lock.json`**?

So before we get into `package-lock.json` let's talk about semantic versioning and `package.json`.

### Semantic Versioning

Semantic versioning or SemVer is the ideal way of versioning packages. They are usually written like `1.4.5` (major.minor.patch)

![Semantic versioning (SemVer)](https://res.cloudinary.com/practicaldev/image/fetch/s--vTMVK06i--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://thepracticaldev.s3.amazonaws.com/i/uyw4yois1mkqr967ufb8.png)

#### Bug fix/patch version

Includes bug fixes/documentation spelling mistakes etc.

#### Minor version

Includes additions of functions or API which does not break anything from the older versions So anything that runs on `v1.1.0` should work on `v1.9.0` as well.

#### Major version

Includes version which breaks stuff. It can include removing APIs or changing names of functions so anything that works on `v1.0.0` may not necessarily work on `v2.0.0`.

### Package.json

The `package.json` is a file that contains information about your project (name, version, etc) and it lists the packages that your project is dependent on.

![package.json](https://res.cloudinary.com/practicaldev/image/fetch/s--m2oVg4vL--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://thepracticaldev.s3.amazonaws.com/i/btvz35yyxvrj4tsbmpzl.png)

So as you can see in the picture above after every dependency listed under `package.json` there's a number something like `^2.20.0` which is the version of that package but before the version, there is `^`. So `^` this little guy can be a total destroyer for your project.

**The `^` sign before the version tells npm that if someone clones the project and runs `npm install` in the directory then install the latest minor version of the package in his `node_modules`.**

So lets say I am having express with `^2.20.0` in `package.json` and then express team releases version `2.24.0` and now when someone clones my repo and runs `npm install` in that directory they will get the version `2.24.0` **(You can also put `~` instead of `^` it will update to latest patch version)**.

However, this can be a huge issue if package developers break any of the functions on the minor version as it can make your application break down.

So npm later released a new file called `package-lock.json` to avoid such scenarios.

### package-lock.json

**The `package-lock.json` will simply avoid this general behavior of installing updated minor version so when someone clones your repo and runs `npm install` in their machine. NPM will look into `package-lock.json` and install exact versions of the package as the owner has installed so it will ignore the `^` and `~` from `package.json`.**

**Also, it contains some other meta information which saves time of fetching that data from npm while you do `npm install`.**

You can refer [npm blog](https://docs.npmjs.com/files/package-lock.json) for some more information on `package-lock.json`.

Article source: [dev.to](https://dev.to/saurabhdaware/but-what-the-hell-is-package-lock-json-b04)

---

## React Router (Client-Side Routing):

**React Router** is the de facto standard routing library for React. When you need to navigate through a React application with multiple views, you’ll need a router to manage the URLs. React Router takes care of that, keeping your application UI and the URL in sync.

React is a popular library for creating single-page applications (SPAs) that are rendered on the client side. An SPA might have multiple **views** (aka **pages**), and unlike the conventional multi-page apps, navigating through these views shouldn’t result in the entire page being reloaded. Instead, we want the views to be rendered inline within the current page.

**Routing** is the process of keeping the browser URL in sync with what’s being rendered on the page.

### Conventional Routing

In general, when the user types an URL in the browser, an HTTP request is sent to the server, which then retrieves the HTML page. For each _new URL_, the user is redirected to a **new** HTML page. You can refer to the below diagram to get a better understanding of how Routing works.

![Routing Diagram](https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2017/09/routing_blog.png)

Article source: [edureka.co](https://www.edureka.co/blog/react-router/)

### Routing In React

In React, there is only a **single** ‘Html’ file involved. Whenever a user types in a **new** URL request, instead of fetching data from the server, the Router swaps in a different **Component** for each new URL request. The user is tricked into switching among multiple pages but in reality, each separate **Component re-renders** achieving multiple views as per our needs.

How does React achieve this?

This is where the concept of **‘History’** comes into the picture. In React, the Router looks at the History of each **Component** and when there is any change in the History, that **Component** re-renders. **Until Router version 4 we had to _manually_ set the _History_ value. However, from Router v4 the base path is bypassed by the <BrowserRouter> saving us a lot of work.** If you still need to access History, HTML5 offers a built-in API which allows us to modify the **History** object through **pushState** and **replaceState** methods.

### Benefits Of React Router v4

We essentially want to call the Router Component inside React’s render method. This is because the entire Router API is all about Components. Of course, each Component’s role is to render UI just as any React application.

### `<Switch>`

Renders the first child `<Route>` or `<Redirect>` that matches the location.

**How is this different than just using a bunch of <Route>s?**

`<Switch>` is unique in that it renders a route _exclusively_. In contrast, every `<Route>` that matches the location renders _inclusively_. Consider these routes:

```JavaScript
import { Route } from "react-router";

let routes = (
  <div>
    <Route path="/about">
      <About />
    </Route>
    <Route path="/:user">
      <User />
    </Route>
    <Route>
      <NoMatch />
    </Route>
  </div>
);
```

If the URL is `/about`, then `<About>`, `<User>`, and `<NoMatch>` will all render because they all match the path. This is by design, allowing us to compose `<Route>`s into our apps in many ways, like sidebars and breadcrumbs, bootstrap tabs, etc.

Occasionally, however, we want to pick only one `<Route>` to render. If we’re at `/about` we don’t want to also match `/:user` (or show our “404” page). Here’s how to do it with **Switch**:

```JavaScript
import { Route, Switch } from "react-router";

let routes = (
  <Switch>
    <Route exact path="/">
      <Home />
    </Route>
    <Route path="/about">
      <About />
    </Route>
    <Route path="/:user">
      <User />
    </Route>
    <Route>
      <NoMatch />
    </Route>
  </Switch>
);
```

Now, if we’re at `/about`, `<Switch>` will start looking for a matching `<Route>`. `<Route path="/about"/>` will match and `<Switch>` will stop looking for matches and render `<About>`. Similarly, if we’re at `/michael` then `<User>` will render.

This is also useful for animated transitions since the matched `<Route>` is rendered in the same position as the previous one.

```JavaScript
let routes = (
  <Fade>
    <Switch>
      {/* there will only ever be one child here */}
      <Route />
      <Route />
    </Switch>
  </Fade>
);

let routes = (
  <Fade>
    {/* there will always be two children here,
        one might render null though, making transitions
        a bit more cumbersome to work out */}
    <Route />
    <Route />
  </Fade>
);
```

### location: object

A **location** object to be used for matching children elements instead of the current history location (usually the current browser URL).

### children: node

**All children of a `<Switch>` should be `<Route>` or `<Redirect>` elements. Only the first child to match the current location will be rendered.**

`<Route>` elements are matched using their path prop and `<Redirect>` elements are matched using their from prop. A `<Route>` with no path prop or a `<Redirect>` with no from prop will always match the current location.

When you include a `<Redirect>` in a `<Switch>`, it can use any of the `<Route>`'s location matching props: path, exact, and strict. from is just an alias for the path prop.

If a location prop is given to the `<Switch>`, it will override the location prop on the matching child element.

```JavaScript
import { Redirect, Route, Switch } from "react-router";

let routes = (
  <Switch>
    <Route exact path="/">
      <Home />
    </Route>

    <Route path="/users">
      <Users />
    </Route>
    <Redirect from="/accounts" to="/users" />

    <Route>
      <NoMatch />
    </Route>
  </Switch>
);
```

### <Route>

The Route component is perhaps the most important component in React Router to understand and learn to use well. **Its most basic responsibility is to render some UI when its path matches the current URL.**

Consider the following code:

```JavaScript
import React from "react";
import ReactDOM from "react-dom";
import { BrowserRouter as Router, Route } from "react-router-dom";

ReactDOM.render(
  <Router>
    <div>
      <Route exact path="/">
        <Home />
      </Route>
      <Route path="/news">
        <NewsFeed />
      </Route>
    </div>
  </Router>,
  node
);
```

If the location of the app is `/` then the UI hierarchy will be something like:

```JavaScript
<div>
  <Home />
  <!-- react-empty: 2 -->
</div>
```

And if the location of the app is `/news` then the UI hierarchy will be:

```JavaScript
<div>
  <!-- react-empty: 1 -->
  <NewsFeed />
</div>
```

The `“react-empty”` comments are just implementation details of React’s `null` rendering. But for our purposes, it is instructive. **A Route is always technically `“rendered”` even though its rendering `null`. When the `<Route>`'s path matches the current URL, it renders its children (your component).**

If the same component is used as the child of multiple `<Route>`s at the same point in the component tree, React will see this as the same component instance and the component’s state will be preserved between route changes. If this isn’t desired, a unique key prop added to each route component will cause React to recreate the component instance when the route changes.

### Route render methods

match
A match object contains information about how a <Route path> matched the URL. match objects contain the following properties:

params - (object) Key/value pairs parsed from the URL corresponding to the dynamic segments of the path
isExact - (boolean) true if the entire URL was matched (no trailing characters)
path - (string) The path pattern used to match. Useful for building nested <Route>s
url - (string) The matched portion of the URL. Useful for building nested <Link>s

---
