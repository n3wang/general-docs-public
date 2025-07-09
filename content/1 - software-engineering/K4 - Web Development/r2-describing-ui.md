## JSX


#### JSX React Fragments

jsx returned sould be inside a singular component, To make the following into jsx compliant
```jsx
export default function Authors () {
  return (
    <h2>Authors</h2>
    <ul>
      <li>Tyler McGinnis</li>
      <li>Ben Adam</li>
      <li>Alex Brown</li>
    </ul>
  )
}
```
Should be fixed into:

??x
```jsx
export default function Authors () {
  return (
    <div>
      <h2>Authors</h2>
      <ul>
        <li>Tyler McGinnis</li>
        <li>Ben Adam</li>
        <li>Alex Brown</li>
      </ul>
    </div>
  )
}
```

or

```jsx
import * as React from "react"

export default function Authors () {
  return (
    <React.Fragment>
      <h2>Authors</h2>
      <ul>
        <li>Tyler McGinnis</li>
        <li>Ben Adam</li>
        <li>Alex Brown</li>
      </ul>
    </React.Fragment>
  )
}

```
There also exists a shorthand syntax for React Fragment (`<>`), but it feels a little _too_ magical to me, so I don't use it much.

x??

#### Closing Brackets in JSX
Let's do another one. Can you spot what's wrong with this JSX?
```jsx
function Form () {
  return (
    <form method="get" action="/search">
      <img src="search.png" alt="search icon">
      <br>
      <label>
        Search
        <input name="term" type="text">
      </label>
      <button type="submit">Search</button>
    </form>
  )
}
```
?x
Whenever you have a "Self-closing tag" (the most popular being `input`, `br`, and `img`), you need to make sure that you explicitly close them.
```
<input> 👎
<input /> 👍
<br> 👎
<br /> 👍
<img> 👎
<img /> 👍
```


#### Classess in JSX
```jsx
function Avatar () {
  return (
    <img
      src="avatar.png"
      alt="Avatar"
      class="avatar"
    />
  )
}
```
:p How about this one? Can you spot what's wrong with this JSX?
?x
The error is that class should be className.
```jsx
function Avatar () {
  return (
    <img
      src="avatar.png"
      alt="Avatar"
      className="avatar"
    />
  )
}
```
#### Strokes
A similar thing to look out for is that you can't have variable names that have a - in them. So any normal HTML attributes that have a - in them (like stroke-width) you need to convert to..
?x
camelCase.
```jsx
function Icon () {
  return (
    <svg width="200" height="200">
      <rect
        x="10"
        y="10"
        width="180"
        height="180"
        fill="none"
        stroke="black"
        strokeWidth="5"
      />
    </svg>
  )
}
```



#### Conditional Rendering
```jsx
// Angular
<h1 *ngIf="authed; else elseBlock">Welcome back!</h1>
<ng-template #elseBlock>
  <h1>Login to see your dashboard</h1>
</ng-template>
// Vue
<h1 v-if="authed">Welcome back!</h1>
<h1 v-else>Login to see your dashboard</h1>
```
How is this displayed on JSX?
??x
You can have conditional rendering return statements
```jsx
function Dashboard () {
  const authed = isAuthed()

  if (authed === true) {
    return <h1>Welcome back!</h1>
  } else {
    return <h1>Login to see your dashboard</h1>
  }
}
```


```jsx
function Dashboard () {
  const authed = isAuthed()
  const firstLogin = isNew()
  if (firstLogin === true) {
    return <h1>👋 Welcome!</h1>
  } else if (authed === true) {
    return <h1>Welcome back!</h1>
  } else {
    return  <h1>Login to see your dashboard</h1>
  }
}
```

x??









