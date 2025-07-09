

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
