

#### Why React?


What problems was React designed to solve? Select all that apply.
- Complexity caused by implicit state changes
- HTML not being powerful enough
- Unpredictable DOM mutations
- Lack of reusable components
?x
- Complexity caused by implicit state changes
- Unpredictable DOM mutations
- Lack of reusable components

What are the advantages of using React? Select all that apply.
- Smaller bundle sizes
- Rich ecosystem of 3rd party components
- Declarative API
- Your view becomes a function of your application's state
?x
- Rich ecosystem of 3rd party components
- Declarative API
- Your view becomes a function of your application's state


#### What is the difference between imperative and declarative?
Look at the following code and state why each is either imperative or declarative
code a
```js
function add(arr) {
    let result = n;
    for (let i = 0; i < arr.length; i++) {
        result += arr[i];
    }
    return result;
}
const btn = document.getElementById('btn')
btn.addEventListener('click', () => {
    btn.classList.toggle('highlight')
    btn.innerText === 'Add Highlight'
        ? btn.innerText = 'Remove Highlight'
        : btn.innerText = 'Add Highlight'
})
```
code b
```js
function add(arr) {
    return arr.reduce(
        (total, number) => number + total,
        0
    );
}
<btn />
SELECT * FROM Users WHERE Country='Mexico';
<article>
    <header>
        <h1>Declarative Programming</h1>
        <p>
            Sprinkle "Declarative" in
            your vocabulary to sound smart
        </p>
    </header>
</article>
```

??x
Imperative programming is **how** you do something, and declarative programming is more like **what** you do.
Imperative is how you do it (How a developer thinks)
Declarative is what you do (How a machine thinks)
The second one (b) is **declarative**
However note that many (if not all) **declarative** APIs have some sort of imperative implementation

MPERATIVE
C
C++
Java

DECLARATIVE
HTML
SQL

~BOTH
JavaScript
C#
Python
x??


Code that is declarative: Select all that apply.
Is often an abstraction over imperative code
Is typically context independent
Is written primarily for humans, not computers
Emphasizes how code executes
?x
Is often an abstraction over imperative code
Is typically context independent
Is written primarily for humans, not computers


Code that is imperative: Select all that apply.
1. Relies on context making it difficult to reuse
2. Gives procedural instructions on how to do something
3. Is usually easily understood at a glance
4. Is explicit about the changes it wants to make
?x
5. Relies on context making it difficult to reuse
6. Gives procedural instructions on how to do something
7. Is explicit about the changes it wants to make


What makes React Declarative? Select all that apply.
It's easy to manipulate the DOM
It describes what the Ul is based on state
It allows you to trace the code as it runs
It is an abstraction over imperative code
?x
It describes what the UI is based on State
It is an abstraction ovver imperative code

### Pure Functions

- Have a return value, should return the same type of ouput
- no side effects:doesnt delete anything outside of it
- testable (given certain input, expected output)


#### The benefits
Composable

Because these functions don't depend on the context of the application and instead receive their inputs via explicit arguments, they're entirely program agnostic and therefore, extremely composable and reusable.

You can take these functions and compose them into or reuse them in any application, and they'll Just Work™.

Cacheable

Because these functions always return the same output given a certain input, the results can be cached. There's no use in calling these functions more than once given the same input, since the output will always be the same.


Is this a pure function?
```js
function getGameProgress(gameId)
{ return localStorage.getItem(gameId); }
```
?x
- no
Among a few other reasons, if we call this function multiple times, we could get a different result each time – making it an impure function.


Why isn't this a pure function?
```js
function upperCaseName(name) {
  return name.toUpperCase();
}
```
Because it does string manipulation
Because the output is not guaranteed to be the same for the same input
Because name isn't guaranteed to be a string
It is a pure function
?x
- Is a pure function
While it's true that we can't be sure that name is a string, that alone does not make it an impure function. It will still return the same result given the same input, and does not rely on external state.

A pure function: Select all that apply.
- Always returns the same output for a given input
- Has side effects
- Is composable
- Depends on external context
?x
- Always returns the same output for a given input
- Depends on external context
Since a pure function will always return the same output for a given input, they are predictable and easy to compose together. Impure functions with side effects, in contrast, are less predictable.


### Components


#### Practice Questions

Which of the following are benefits of HTML? Select all that apply.
- [ ] It is declarative
- [ ] It has semantic structure
- [ ] It gives us tools for managing application complexity
- [ ] It has a robust module system
?x
- [ ] It is declarative
- [ ] It has semantic structure
HTML is great for declaratively structuring a document, but it lacks the power and expressivity of JavaScript. React components bring these together to give us a "more powerful HTML".


Is this a valid React component?
```jsx
export default function search() {
  return <div>
    <label htmlFor="search">Search</label>
    <input id="search" placeholder="Enter some text" />
  </div>
}
```
?x
No, it is not. The function (component) name needs to be capitalized in order for React (JSX) to understand the difference between an HTML element and a component.


(True/False) As a rule, every React component must follow the Single Responsibility Principle.
?x
False,There is no rule stating that every React component must follow the single responsibility principle. However, it is a good guideline to follow.


What is a React component?
a function that returns some UI
a function that returns a description of the UI
?x
a function that returns a description of the UI

How do you use variables in JSX?
Wrap them in $\{\{\}\}$
Wrap them in \{\}
Wrap them in []
Wrap them in
?x
Is wrapped on brackets: {}


What's wrong with this code? Select all that apply.
```jsx
function home () {
  return (
    <Header />
    <content />
    <Footer />
  )
}
```
Nothing
You can't render adjacent parent elements in JSX
The browser will throw an error when it sees the opening ()
You need to wrap the return value in <React.Fragment>
You can't have lowercase component names
?x
You can't render adjacent parent elements in JSX
You need to wrap the return value in <React.Fragment>
You can't have lowercase component names


Lets say that you  had tweets and want to create a list on jsx
What to consider?
?x
- Use the declarative way to map the tweet per each
- Show the list of tiems
- Show the idon each list to make it different and track its state
```jsx
<ul id="tweets">
    {tweets.map((tweet) => (
        <li key={tweet.id}>{tweet.text}</li>
    ))}
</ul>
```

#### Rendering List challenge
Given an array of friends, create a list item for every friend inside of our unordered list. Note: The items in our friends array don't have their own unique keys. You need to improvise.
- Render an unordered list with all of the friends
- Each list item should display the correct name
- Each list item should be given a unique key
:p Complete this UI Leetcode Challenge
[Rendering Lists Challenge - ui.dev](https://ui.dev/c/react/rendering-lists-challenge)
?x
```jsx
function List() {
  const friends = [
    { id: 893, name: "Lynn" },
    { id: 871, name: "Alex" },
    { id: 982, name: "Ben" },
    { id: 61, name: "Mikenzi" }
  ];
  return (
    <ul> 
      {friends.map((friend) => (
      <li key={friend.id}>
        {friend.name}
      </li>
      ))}  
    </ul>
  );
}
export default function App() {
  return <List />;
}
```


### Props






