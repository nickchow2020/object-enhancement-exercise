# Object Enhancements Exercise
In this exercise, you’ll refactor some ES5 code into ES2015. Write your code in the sections with a comment to “Write an ES2015 Version”.

### 1 Same keys and values
```javascript
function createInstructor(firstName, lastName){
  return {
    firstName: firstName,
    lastName: lastName
  }
}
```
### 1 solution  
```javascript
function createInstructor(firstName,lastName){
    return{firstName,lastName}
}
```

===

### 2 Computed Property Names
```javascript
var favoriteNumber = 42;

var instructor = {
  firstName: "Colt"
}

instructor[favoriteNumber] = "That is my favorite!"
```
### 2 Solution 
```javascript
const favoriteNumber = 42;
const instructor = {
    firstName : "Colt"
    [favoriteNumber] : "This is my favorite"
}
```

=== 

### 3 Object Methods
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
### 3 Solution
```javascript
const instructor = {
    firstName : "Colt",
    sayHi(){return "Hi!"},
    sayBye(){return this.firstName + " says bye!"}
}
```

===

### 4 createAnimal function
Write a function which generates an animal object. The function should accepts 3 arguments:

species: the species of animal (‘cat’, ‘dog’)
verb: a string used to name a function (‘bark’, ‘bleet’)
noise: a string to be printed when above function is called (‘woof’, ‘baaa’)
Use one or more of the object enhancements we’ve covered.
```javascript
const d = createAnimal("dog", "bark", "Woooof!")
// {species: "dog", bark: ƒ}
d.bark()  //"Woooof!"

const s = createAnimal("sheep", "bleet", "BAAAAaaaa")
// {species: "sheep", bleet: ƒ}
s.bleet() //"BAAAAaaaa"
```
### 4 solution 
```javascript 
function createAnimal(species,talk,noise){
    return {
        species,
        [talk]: function(){return noise}
    }
}

function createAnimal(species,talk,noise){
    return {
        species,
        [talk](){return noise}
    }
}
```