1. Difference between getElementById, getElementsByClassName, and
querySelector / querySelectorAll
All of them are very important part of JavaScript DOM. They are used to pick/select elements from
the HTML page. They may look like same purpose but they actually behave differently.
a) getElementById: Finds an element by it’s id. Since id must be unique it will always return only
one element object.
b) getElementsByClassName: Finds elements by class name. Many elements can have the
same class so it return multiple elements. We must loop through them. It gives a live HTML
collection.
c) querySelector: Can use id, class, attribute, pseudo selector etc. Always returns the first
matching element only.
d) querySelectorAll: Selects all elements matching a CSS selector. Returns a static NodeList
.

2. How to Create and Insert a New Element into the DOM
First we make new div and store it inside variable:
const meow = document.createElement('div');
Then give it  class:
meow.classList.add('meow-styles');
Add content:
meow.innerHTML = "<p>Hello!</p>";
Finally insert into DOM:
document.body.appendChild(meow); (end)
or document.body.prepend(meow); (start).

3. Event Bubbling
When you click on an element, the event goes up to its parent, then parent of parent, and so on.
Like a bubble moving in water upwards.
Example: Button inside div inside body:
Button’s event → Div’s event → Body’s event.
We can stop this, but sometimes it is useful (for event delegation).

4. Event Delegation
A smart technique using bubbling. Instead of putting listener on every child, we put one on parent.
Parent checks which child triggered it.
Benefits:
I ) Better performance – fewer listeners.
II ) Works on dynamic content – new children still work.
III ) Cleaner code – less repetition.

5. Difference between preventDefault() and stopPropagation()
preventDefault(): Stops browser default action. Example: stop form from refreshing page on
submit.
stopPropagation(): Stops event from bubbling up to parent elements.