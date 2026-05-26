# Angular + JavaScript Interview Questions & Answers

## 1. Brief Introduction About Yourself

Hi, my name is Adarsh Dixit. I am a Full Stack Developer with 5+ years of experience mainly in Angular, Node.js, and PostgreSQL/MongoDB.

I have worked on scalable web applications, admin panels, CRM systems, travel platforms, payment integrations, and real-time communication systems.

On frontend, I have strong experience with Angular (latest versions), RxJS, NgRx, Reactive Forms, Routing, Guards, Interceptors, Tailwind, and TypeScript.

On backend, I have worked with Node.js, Express.js, Prisma, Sequelize, JWT Authentication, Redis, BullMQ, AWS Lambda, Stripe Connect, Twilio, and REST APIs.

Currently, I am working on enterprise-level backoffice and multi-tenant platforms where I handle frontend architecture, API integrations, authentication, role-based access, and performance optimization.

I also have team-leading experience where I handled task distribution, code reviews, client discussions, mentoring junior developers, and project delivery.

---

# JavaScript Questions

---

## 2. What is Closure?

A closure is when a function remembers variables from its outer scope even after the outer function execution is completed.

```js
function outer() {
  let count = 0;

  return function inner() {
    count++;
    console.log(count);
  };
}

const fn = outer();
fn(); // 1
fn(); // 2
```

### Real Use

* Data hiding
* Private variables
* Callbacks
* Event handlers

### Real World Example (10-Year-Old Style)

Imagine your mom gives you a secret chocolate box.

Then your mom leaves the room.

But you still remember:

* where the chocolate is
* how many chocolates are left

Even though mom is gone, you still have access to the chocolate information.

That memory is called Closure in JavaScript.

The inner function remembers the outer function’s variables.
---

## 3. What is Hoisting?

Hoisting means variables and functions are moved to the top during execution phase.

```js
console.log(a);
var a = 10;
```

Output:

```js
undefined
```
### Real World Example

Imagine school attendance sheet.

Teacher already knows your name exists in class before you enter.

But marks are not assigned yet.

So:

* Name exists → declaration hoisted
* Value not assigned yet → undefined

---

## 4. If Function is Called Before Declaration What Happens?

### Function Declaration

It works because of hoisting.

```js
test();

function test() {
  console.log("Hello");
}
```

### Function Expression

It fails.

```js
test();

var test = function () {};
```

Output:

```js
test is not a function
```

---

## 5. Callback and Promise

### Callback

Function passed into another function.

```js
function greet(callback) {
  callback();
}
```

### Promise

Used for handling async operations.

```js
const p = new Promise((resolve, reject) => {
  resolve("Success");
});
```

---

## 6. Hoisting with let and var

### var

Hoisted and initialized with undefined.

### let

Hoisted but in Temporal Dead Zone.

```js
console.log(a); // undefined
var a = 10;

console.log(b); // error
let b = 20;
```

---

## 7. Can You Execute Undefined Function?

No.

```js
test();
```

Output:

```js
test is not defined
```

---

## 8. What is Prototype?

Prototype is mechanism through which objects inherit properties and methods.

```js
function Person() {}

Person.prototype.sayHi = function () {
  console.log("Hi");
};
```

---

## 9. ES6 Features

* let & const
* Arrow functions
* Template literals
* Destructuring
* Spread operator
* Promises
* Classes
* Modules
* Default parameters

---

## 10. Difference Between Normal and Arrow Function

| Normal Function    | Arrow Function   |
| ------------------ | ---------------- |
| Has own this       | Uses parent this |
| Can use arguments  | No arguments     |
| Can be constructor | Cannot           |

---

## 11. Use of Destructuring

Extract values easily.

```js
const user = { name: "Adarsh", age: 25 };

const { name, age } = user;
```

---

## 12. What is Callback Function?

Function passed as argument into another function.

```js
function main(callback) {
  callback();
}
```

---

## 13. What is Recursive Function?

Function calling itself.

```js
function fact(n) {
  if (n === 1) return 1;
  return n * fact(n - 1);
}
```

### Use Cases

* Tree structure
* Nested comments
* File systems

---

## 14. Get Keys from Object

```js
Object.keys(obj)
Object.values(obj)
Object.entries(obj)
for...in
```

---

## 15. Shallow vs Deep Copy

### Shallow Copy

Copies reference.

```js
Object.assign({}, obj)
{...obj}
```

### Deep Copy

```js
structuredClone(obj)
```

### Lodash

```js
_.cloneDeep(obj)
```

---

## 16. Authentication vs Authorization

### Authentication

Who are you?

### Authorization

What can you access?

### Methods

* JWT
* OAuth
* Session-based auth

---

# Angular Questions

---

## 17. Authorization in Angular

Using:

* Route Guards
* Role checks
* JWT token validation

---

## 18. How Many Guards Can Be Added?

Multiple guards.

```ts
canActivate: [AuthGuard, RoleGuard]
```

---

## 19. Basic Fundamentals of Angular

* Components
* Modules
* Services
* Dependency Injection
* Routing
* Directives
* Pipes
* RxJS

---

## 20. What is Data Binding?

Connecting TS data with HTML.

### Types

* Interpolation
* Property binding
* Event binding
* Two-way binding

---

## 21. Angular 15+ Changes

### Major Changes

* Standalone Components
* app.config.ts
* Functional Guards
* Improved lazy loading
* Signals (latest versions)
* Better performance

---

## 22. Difference Between app.module and app.config

| app.module        | app.config             |
| ----------------- | ---------------------- |
| Old module system | New standalone setup   |
| Uses NgModule     | Uses ApplicationConfig |
| More boilerplate  | Cleaner                |

---

## 23. Use of Interceptor

Used for:

* Adding token
* Error handling
* Logging
* Request modification

---

## 24. Where to Store Token?

Better ways:

* HttpOnly Cookies
* Memory state

Local/session storage less secure.

---

## 25. Reactive Forms Two Ways

* FormControl
* FormBuilder

---

## 26. Detect Field Changes in Reactive Forms

```ts
control.valueChanges.subscribe()
```

---

## 27. Angular Routing

### Features

* Route params
* Query params
* Lazy loading
* Guards
* Child routes

### Params

```ts
this.route.params.subscribe()
```

---

## 28. Function Expression

Function stored in variable.

```js
const test = function () {};
```

---

## 29. Use of Promises

Used for async operations like:

* API calls
* Timers
* Database operations

---

## 30. How to Create Promise?

```js
const p = new Promise((resolve, reject) => {
  resolve();
});
```

---

## 31. Promise Callbacks

* resolve
* reject

---

## 32. Promise States

* Pending
* Fulfilled
* Rejected

---

## 33. How Many .then Can Be Used?

Unlimited chaining possible.

```js
promise.then().then().then()
```

---

## 34. API Call in Plain JavaScript

```js
fetch('/api')
  .then(res => res.json())
```

---

## 35. Difference Between let const var

| var                | let         | const       |
| ------------------ | ----------- | ----------- |
| Function scope     | Block scope | Block scope |
| Re-declare allowed | No          | No          |
| Reassign allowed   | Yes         | No          |

---

## 36. map vs forEach vs reduce

| Method  | Return       | Use       |
| ------- | ------------ | --------- |
| map     | New array    | Transform |
| forEach | Nothing      | Loop      |
| reduce  | Single value | Sum/group |

---

## 37. Route Objects in Angular

* Routes
* ActivatedRoute
* Router
* RouterState

---

## 38. Template vs Reactive Forms

| Template Form | Reactive Form |
| ------------- | ------------- |
| HTML based    | TS based      |
| Simple forms  | Complex forms |
| Less scalable | More scalable |

---

## 39. Component Communication

### Parent to Child

```ts
@Input()
```

### Child to Parent

```ts
@Output()
```

### Siblings

Using shared service.

---

## 40. Custom Pipe

### Create

```bash
ng generate pipe custom
```

### Main Function

```ts
transform(value: any)
```

---

## 41. Custom Directive

### Create

```bash
ng generate directive custom
```

### Used For

DOM manipulation.

---

## 42. Route Params Passing

### Pass

```ts
this.router.navigate(['/user', id])
```

### Access

```ts
this.route.params.subscribe()
```

---

## 43. Use of RxJS

Used for:

* Async programming
* Observables
* Event handling
* API streams

---

## 44. Use of NgRx

State management library.

### Used In

Large scalable apps.

### Major Parts

* Store
* Actions
* Reducers
* Effects
* Selectors

### Flow

Component → Action → Reducer → Store → Selector

---

## 45. RxJS Operators

### map

```ts
map(data => data.name)
```

### filter

```ts
filter(x => x > 5)
```

### switchMap

Used for API chaining.

---

## 46. Ways to Create Observable

```ts
of()
from()
new Observable()
fromEvent()
```

---

## 47. Difference Between of and from

### of

Treats complete value as single item.

```ts
of([1,2,3])
```

### from

Converts iterable into stream.

```ts
from([1,2,3])
```

---

## 48. Unsubscribe Difference in of and from

Both stop emissions after unsubscribe.

But:

* of emits single value
* from emits multiple sequential values

---

## 49. Which Projects Need State Management?

* Large enterprise apps
* Multiple shared states
* Dashboard systems
* Ecommerce
* CRM

---

## 50. Why Not Only BehaviorSubject Instead of NgRx?

| BehaviorSubject   | NgRx               |
| ----------------- | ------------------ |
| Small apps        | Large apps         |
| Manual management | Structured         |
| Hard debugging    | Devtools available |

---

# Unit Testing

---

## 51. What are Unit Test Cases?

Testing small isolated parts of application.

### Why Needed?

* Bug prevention
* Stable code
* Refactoring safety

---

## 52. Jasmine and Karma

### Jasmine

Testing framework.

### Karma

Test runner.

---

## 53. Service Call in Unit Test

Using TestBed and spy objects.

```ts
spyOn(service, 'getData')
```

---

## 54. Use of beforeEach

Runs before every test case.

Used for setup.

---

## 55. Alternatives of Jasmine/Karma

* Jest
* Cypress
* Vitest
* Playwright

---

# Bonus Interview Tip

For interviews:

* Keep answers 30–60 seconds
* Start with definition
* Give real project example
* Avoid over-explaining
* Be confident and structured
