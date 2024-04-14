# Object Enhancements Exercise
***
### ES5
```javascript
function createInstructor(firstName, lastName){
  return {
    firstName: firstName,
    lastName: lastName
  }
}
```
### Same keys and values ES2015
```javascript
/* Write an ES2015 Version */
const createInstructor = (firstName, lastName) => ({
    firstName,
    lastName
});
```
+ console.log(createInstructor("First Name Parameter", "Last Name Name Parameter"));
    - returns `{firstName: 'First Name Parameter', lastName: 'Last Name Name Parameter'}`
---
### Computed Property Names
```javascript
var favoriteNumber = 42;

var instructor = {
  firstName: "Colt"
}

instructor[favoriteNumber] = "That is my favorite!"
```
### Computed Property Names ES2015
```javascript
/* Write an ES2015 Version */
const favoriteNumber = 42;
const instructor = {
    firstName : "Colt",
    [favoriteNumber] : "That is my favorite!"
}
```
+ console.log(instructor);
    - returns `{42: 'That is my favorite!', firstName: 'Colt'}`
---
### Object Methods
```javascript
var instructor = {
  firstName: "Colt",
  sayHi: function(){
    return "Hi!";
  },
  sayBye: function(){
    return this.firstName + " says bye!";
  }
}
```
### Object Methods ES2015
```javascript
/* Write an ES2015 Version */
const instructor = {
    firstName: "Colt",
    sayHi() {
        return "Hi!";
    },
    sayBye() { 
        return this.firstName + " says bye!"
    }
}
```
+ console.log(instructor);
    - returns `{firstName: 'Colt', sayHi: ƒ, sayBye: ƒ}`
+ console.log(instructor.sayHi());
    - returns `Hi!`
+ console.log(instructor.sayBye());
    - returns `Colt says bye!`
---
### createAnimal function
Write a function which generates an animal object. The function should accepts 3 arguments:
- species: the species of animal (‘cat’, ‘dog’)
- verb: a string used to name a function (‘bark’, ‘bleet’)
- noise: a string to be printed when above function is called (‘woof’, ‘baaa’)
Use one or more of the object enhancements we’ve covered.
```javascript
const d = createAnimal("dog", "bark", "Woooof!")
// {species: "dog", bark: ƒ}
d.bark()  //"Woooof!"

const s = createAnimal("sheep", "bleet", "BAAAAaaaa")
// {species: "sheep", bleet: ƒ}
s.bleet() //"BAAAAaaaa"
```

```javascript
const createAnimal = (species, verb, noise) => ({
    species,
    [verb]() {
        console.log(noise)
    }
})
```
+ const d = createAnimal("dog", "bark", "Woooof!");d.bark();
    - prints `Woooof!`
+ const s = createAnimal("sheep", "bleet", "BAAAAaaaa");s.bleet();
    - prints `BAAAAaaaa`

