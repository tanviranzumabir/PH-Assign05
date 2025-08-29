1.What is the difference between getElementById, getElementsByClassName, and querySelector / querySelectorAll?

--> All of them are a very crucial part of JavaScript DOM. The are used to select elements from the html code. They might serve the save purpose but all of them behave differently.

I ) getElementById: This Selects an element by it's id and because of the fact that multiple elements cannot share the same id meaning id's are need to be unique we cannot get multiple elements with getElementById. it only returns a single element object.

II ) getElementsByClassName: This selects elements by their class names. Multiple elements can share the same class so we can get multiple elemets using getElementsByClassName. But there is a fact that to achieve those elements using getElementsByClassName we must loop through those elements. it return a live HTML collection.

III ) querySelector: This can use id, class, attribute, pseudo-selectors, to select an element. But querySelector only selects the frist element. suppose there are multiple elements with one specific classname, querySelector will select only select the first element and it will not select the rest of them. It only returns a single element.

IV ) querySelectorAll: This selects all elements that matches a css selector and it supports all css selectors. suppose there are multiple elements with one specific classname, it will select all the elements. It returns a static nodlist.



2.How do you create and insert a new element into the DOM?

--> First we have to create a new div and keep it inside a variable to create a new element inside JavaScript and insert it tn the DOM.

such as const meow = document.createElement('div'); // here meow is the variable and we will keep our new element inside this div and insert it in the DOM later.

After creating the new div we neet to assign or add a classname for that div.

such as meow.classList.add('meow-styles'); this will pick the styles for the div from the css file where this styles with this classname is added. but if tailwind is being used then styles can be directly applied when we create the new element in the next step tor inline css can also be used.

After that we have to create the new element that we want to insert. we must write it between `` template strings.

such as meow.innerHTML = ``; we need to create the new elemt inside that template string.

After we are done creating the element we need to insert it in the dom.  To insert it in the dom we can use appendChild() or prepend() to insert it. appendChild inserts the element as a last child and prepend adds it as first child. 

such as document.body.appendChild('meow');



3.What is Event Bubbling and how does it work?

--> When we click on a button or an element and a event is caused it does not stop there and it then moves to it's parent element and then the parent element of that parenet element and then it's parent element and so on all the way to the top untill the whole code ends. It acts like a bubble in the watter moving from the bottom to the top and this is why it is called event bubbling. 

for example,

if you click a button inside a div inside another dive inside a body.

The button event happens then div's event then the parent div's event then the body's event.

we can aslo stop it from happening.

but in some cases it is a very useful thing  as it allowes event delegation.



4.What is Event Delegation in JavaScript? Why is it useful?

--> Event Delegation is a useful technique in Event Bubbling. In event delegation we only attach a single event listner to a element or parent insted of attaching an event listner to many child elenents. Event Bubbling happens and it gets every child element or parent. All we have to do is just put one event listner to a common parent.

It is usefull in many terms, such as

I ) Performance and effeciency
Attaching many listners on a large code makes it heavy we can shortan the code and make it lighter using event delegation.

II ) Handleling dynamic content
When adding new elements we dont need to attach event listner to them again the parent listner will catch them.

III ) Clear Code
Event Delegation makes the code easier to mantain because it makes the code smaller in size and organized and repetative codes are less.



5.What is the difference between preventDefault() and stopPropagation() methods?

preventDefault() stops the browsers default actions in a function or in the code. It has nothing to do with Event Bubbling.
Event Bubbiling will happen. for example

if we have a form with some input fields. whenver an event occures the browser will automatically relod the page. sometimes it makes our wrok a bit fustrating because there is no data left in the conso as the browser relods. So we use preventDefault() to make this stop from happinig.

on the other hand stopPropagation() is used to prevent the event from bubbling. it has nothing to do with the browsers default functionalities it just stops the Event Bubbling. Event Bubbling is a very usefull and powerful feature but in some cases we need to stop the events from bubbling so we use stopPropagation().

