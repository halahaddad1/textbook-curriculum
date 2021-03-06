# React Hello World

## Learning Goals

- Create a new React application
- Read through a basic React component
- Introduction to JSX & CSS in React

### Setup

The React developers have created a nice tool to help you get started with creating a new React application. Since most React applications require the same npm packages and information, this tool that we'll use will install each of these for us by default.


Although it is not the same, we'll use `npx create-react-app` in a similar way to the way we used `rails new`.

```bash
npx create-react-app hello-world
cd hello-world
```

#### What's Included?

Let's go ahead and open this project up in your text editor to examine the files that have been created for us. We'll start in the `src` folder.

Take a look at the `index.js` file that was created. Some questions for you as you check out this code:

- What looks familiar?
- What looks new?

Next, take a look at the `App.js` file that was created. Some questions for you as you check out this code:

- What do you think this code is doing?
- How is this code related to the code you looked at in `index.js`?

#### Functional Components

This code contains a function! However this function looks like it returns HTML!  It also starts with a capital letter.  In React, component names always start with a capital letter.

In React, you can build a component as either a class or a function. We will be sticking with functional components to start, and `create-react-app` will start with a function for the top-level `App` component. For now, we will work with that function.

#### Running the Server

Now that we've examined the code that was generated for us, we can go ahead and run our web server for this application by running `npm start` from our terminal. This command is set up to start our application and then open the browser where the server is running.

**Question**: Where is the HTML that is displayed on the web page coming from? Figure out with your neighbor.

### Component's function determines how it's rendered
The `App.js` file contains our first (auto-generated) component. How exciting!

Now let's examine the pieces of code within the `App` function and identify the key pieces.

```javascript
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
```

Here are some important things to note about this function:

- The pieces that look like HTML are **JSX**
- Every component is either a function or a class, and each gets its own file
- Every component is a function that returns a bunch of JSX
  - As we'll see later for a class component, it's the `render` function
  - For a functional component, the whole component is the function!
- The function that is responsible for rendering must return a single object.
  - It must be one of the following:
    - A *single* element.
    - An array of elements.
    - A String.
  - In this case, this rendering function returns the outermost `div`. Every other element in the function is contained within that outermost `div`.

**Try It!** Change something about the `App` function above and see how it immediately affects the page.

#### What is JSX?

JSX is a pre-processor (similar to ERB in Rails) that adds XML syntax to JavaScript. JSX and React can technically be used independently, but you almost always see them together. JSX looks a lot like HTML though there are a few important differences.

**Adding CSS Classes**

Since JSX is within our JavaScript code, we cannot use the `class` keyword the way we would directly in our HTML. Instead, we must use `className` to avoid the reserved word. You'll notice this in several lines of the rendering function that we were examining above.

**Making it Dynamic**

Take a look at the code above and see if you can identify a location within the `App` function that is rendered dynamically. HINT: You'll be able to identify it because the syntax looks a bit different.

In ERB, we were familiar with using the `<%` and `<%=` elements to dynamically generate content for our views. In JSX, we utilize `{}` to pass in code that we'll use to dynamically generate view data.

**Important Notes**

- JSX cannot contain if-statements. If you need to include logic within your render function, you can do so _before_ the return statement.
- A React Component must return or _render_ a **single element**, an **array of elements** or a **string**. This does not mean that there can't be more complicated JSX in the `return`, but it does mean that if you have multiple elements they need to be wrapped in **one** outermost element or contained within **one** array.

## Key Takeaway

- We can use `npx create-react-app` to create a new boilerplate React application.
- Once our React application is created, we can run `npm start` in the terminal to start it up.
- JSX is the pre-processor associated with React that we will utilize to generate dynamic HTML.

## Additional Resources

- [`create-react-app`](https://github.com/facebookincubator/create-react-app)
- [JSX Tutorial](http://buildwithreact.com/tutorial/jsx)
