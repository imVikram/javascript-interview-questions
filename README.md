
# javascript-interview-questions

Updated JS interview questions list


## How do we create objects in JavaScript?
We can create an empty object is using the Object constructor.

```javascript
var object = Object();
```

The Object() is a built-in constructor function so "new" keyword is not required here.


# Difference between Call, Apply and Bind

Call: The call() method invokes a function with a given this value and arguments provided one by one

Apply: Invokes the function with a given this value and allows you to pass in arguments as an array

Bind: returns a new function, allowing you to pass any number of arguments

Call and apply are pretty interchangeable. Both execute the current function immediately. You need to decide whether it’s easier to send in an array or a comma separated list of arguments. You can remember by treating Call is for comma (separated list) and Apply is for Array.

Whereas Bind creates a new function that will have this set to the first parameter passed to bind().



```javascript

/*****Call*****/
/*---------------------------------*/
var employee1 = { firstName: "Vikram", lastName: "Singh" };

function invite(greeting1, greeting2) {
  console.log(
    greeting1 + " " + this.firstName + " " + this.lastName + ", " + greeting2
  );
}

invite.call(employee1, "Hello", "How are you?"); // Hello Vikram Singh, How are you?

/*---------------------------------*/

/*****Apply*****/
/*---------------------------------*/
var employee1 = { firstName: "Vikram", lastName: "Singh" };

function invite(greeting1, greeting2) {
  console.log(
    greeting1 + " " + this.firstName + " " + this.lastName + ", " + greeting2
  );
}

invite.apply(employee1, ["Hello", "How are you?"]); // Hello Vikram Singh, How are you?

/*---------------------------------*/

/*****Bind*****/
/*---------------------------------*/
var employee1 = { firstName: "Manvik", lastName: "Chaudhary" };

function invite(greeting1, greeting2) {
  console.log(
    greeting1 + " " + this.firstName + " " + this.lastName + ", " + greeting2
  );
}

var inviteEmployee1 = invite.bind(employee1);
inviteEmployee1("Hello", "How are you?"); // Hello Manvik Chaudhary, How are you?


/*---------------------------------*/


```

# Explain setTimeOut

The setTimeout() method is used to call a function or evaluate an expression after a specified number of milliseconds. For example, let's log a message after 3 seconds using setTimeout method


## Example:

```javascript
setTimeout(function () {
  console.log("Hi Vikram");
}, 3000);
```


# Explain setInterval

The setInterval() method is used to call a function or evaluate an expression at specified intervals (in milliseconds). For example, let's log a message after 3 seconds using setInterval method


## Example:

```javascript
setInterval(function () {
  console.log("Good morning vikram ji");
}, 3000);
```


# Explain the difference between Shallow and Deep copy

There are two ways to copy an object:-
Shallow Copy & Deep copy


Shallow Copy: Shallow copy is a bitwise copy of an object. A new object is created that has an exact copy of the values in the original object. If any of the fields of the object are references to other objects, just the reference addresses are copied i.e., only the memory address is copied.


## Example:

```javascript
var empDetails = {
  name: "Vikram",
  age: 18,
  expertise: "Senior Software Developer",
};
```


Now to create a duplicate:

```javascript
var empDetailsShallowCopy = empDetails; //Shallow copying!
```


if we change some property value in the duplicate one like this:


```javascript
empDetailsShallowCopy.name = "Manvik";
```


The above statement will also change the name of empDetails, since we have a shallow copy. That means we're losing the original data as well.

Deep copy: A deep copy copies all fields, and makes copies of dynamically allocated memory pointed to by the fields. A deep copy occurs when an object is copied along with the objects to which it refers.


```javascript
var empDetails = {
  name: "Vikram",
  age: 18,
  expertise: "Software Developer",
};
```

Create a deep copy by using the properties from the original object into new variable

```javascript
var empDetailsDeepCopy = {
  name: empDetails.name,
  age: empDetails.age,
  expertise: empDetails.expertise,
};
```
Now if you change empDetailsDeepCopy.name, it will only affect empDetailsDeepCopy & not empDetails












