
# Hello Students ! :ghost:

Sharing with you all ES6 tips that will help you throughout your challenges of the day ! :rocket:


# Table of Contents : 

1. [String Interpolation](#string-interpolation-in-js)
2. [Variable Declarations](#let-vs-const-vs-var)
3. [filter](#filter)
4. [reduce](#reduce)
5. [find](#find)
6. [findIndex](#findIndex)
7. [Destructuring](#destructuring)
8. [Spreading](#spreading)
9. [Arrow Functions](#arrow-functions)
10. [Object methods](#object-methods)
11. [Regular Expressions](#regexp)

## String interpolation in JS

We used String interpolation in Ruby during your first 3 weeks, a similar approach exists in Javascript, instead of using double-quotes **"#{}"** , we use backticks with a dollar sign to use interpolations **`${}`**. 

```ruby 
"The sum of 1+1 is : #{1+1}"
```

```javascript
`The sum of 1 + 1 is ${1+1}`
```

## let vs const vs var

Variable declarations are different in Javascript compared to Ruby, since you started your journey at Le Wagon,
you've been used to declare your variables in either a local,regular variable or an instance variable inside a Class

Javascript have three different ways to declare a variable 

**var** declarations are globally accessible either in local, function or global scope. 

### Example 

#### var
```javascript
// var 
var myMood = 'Happy' 
var myMood = 'Super Happy'
myMood = 'Happy' 

function mood() {
    return myMood
}

mood()
// It will return the variable myMood although it is outside the function scope
// let can also behave the same yet there is a difference in declaration
```
**let and const** declarations are both accessible in a block scope.

The difference between **let** and **const** is that *let* can be re-assigned but cannot be re-declared, *const* is a constant, it cannot be re-assigned nor re-declared . 


#### let 

```javascript
let myMood = 'Happy' 
let myMood = 'Super Happy'

// you will get an error message : Uncaught SyntaxError: Identifier 'myMood' has already been declared
// declaring let would obstruct your variable declaration, the alternative to change the value of your variable
// would be to simply call it again without using 'let'

myMood = 'Super Happy'
//=> it will return the new value
```

#### const 

```javascript
const myMood = 'Happy'

const myMood = 'Sad'

//it will return => Uncaught SyntaxError: Identifier 'myMood' has already been declared

myMood = 'Sad'

//it will return => Uncaught TypeError: Assignment to constant variable.

```

## filter()

The filter() method creates a new array with the implemented filter provided in the testing function.

### Example 

```javascript
let studentsName = ['Abdullah','Salma','Loubna','Abdelhak','Amine','Yassine','Zakaria','Assem']

studentsName.filter( x => x[0] === 'A')

// It returns an array of students name starting with the letter A : 
// ['Abdullah', 'Abdelhak', 'Amine', 'Assem' ]
```

## reduce()

The reduce() method executes a callback function that return the calculation value of an array, also called a reducer, it allows you to walk through the array element-by-element and incrementing each values into an accumulator
until there is no element left. 

### Example
```javascript
let array = [1,3,4,5]
array.reduce((accumulator, initialValue) => accumulator + initialValue)
//This sums the total value of the array

```


## find() 

```javascript
let studentsName = ['Abdullah','Salma','Loubna','Abdelhak','Amine','Yassine','Zakaria','Assem']

studentsName.find(student => student === 'Salma' )

```

## findIndex() 

Unlike find(), findIndex returns the index of the first element of an array according to the provided testing function, otherwise, it will return -1 if no element pass the test. 

```javascript
let studentsName = ['Abdullah','Salma','Loubna','Abdelhak','Amine','Yassine','Zakaria','Assem']

studentsName.findIndex( student => student === 'Salma')

//Returns the index of the student : 1 
```

It is possible to add two parameters on the testing function such as a value and an index 

```javascript
let studentsName = ['Abdullah','Salma','Loubna','Abdelhak','Amine','Yassine','Zakaria','Assem']

studentsName.findIndex((student,index) => index && student === 'Salma')

//Similar result as the previous example adding both an index and value, 
//the AND operator is a different approach for an inline IF conditioning
// without using ELSE or a ternary operator
```


## Destructuring

Destructuring helps you extract values inside an object and store them in separate variables.

### Destructuring arrays 

```javascript
    let students = ['Abdullah','Salma','Loubna','Abdelhak','Amine','Yassine','Zakaria','Assem']

    let [abdullah, salma, ...others ] = students 

    console.log(abdullah)
    //Return => Abdullah 
    console.log(salma)
    //Return => Salma
    console.log(others)
    //Return => Loubna Abdelhak Amine Yassine Zakaria Assem
```

### Destructuring objects 

```javascript
    let coding = {frontEnd:'html+css+js', backEnd: 'ruby', database: 'postgresql'}
    let {frontEnd, backEnd, ...others} = coding 
    frontEnd // Return 'html+css+js'
    backEnd // Return 'ruby'
    others // Return 'postgresql'
```

## Spreading 

You might have noticed in the two previous examples in destructuring, we used this kind of arguments ***...others***, others isn't a built-in object in JS, the (...syntax) allows an iterable such as an array or string to be expanded in places where arguments are expected such as indexed objects or a key-value pairs.



### Example

```javascript
let tasks = ['lecture','coding','livecode']
let last_task = 'FLASHCARDS!'

tasks = [...tasks, last_task]

tasks //Will return => [ 'lecture', 'coding', 'livecode', 'FLASHCARDS!' ]
```

## Arrow functions 

One of the best features of ES6 is the new standards to declare functions, it is a compact alternative to the traditional function expression *function()*.

### How we used to declare functions in JS 
```javascript
    function sum2Number(a,b){
        return a + b  
    }
```

### using Arrow Functions now 
```javascript
    const sum2Number = (a,b) => { return a + b}
```


## Object methods

The only way to loop through an object before ES6 was to use a regular *for..in* loop, Object method will help you iterate through a Hash and convert the keys or values into an array. 

### Object.keys()

```javascript
    const GDP_countries = {
        morocco: '112.9 billion USD',
        france: '2.603 trillion USD',
        finland: '362 billion USD'
    }

    Object.keys(GDP_countries)
    //Will return [ 'morocco', 'france', 'finland' ]
```

### Object.values()


```javascript
    const GDP_countries = {
        morocco: '112.9 billion USD',
        france: '2.603 trillion USD',
        finland: '362 billion USD'
    }

    Object.values(GDP_countries)
    //Will return [ '112.9 billion USD', '2.603 trillion USD', '362 billion USD' ]
```

## Regexp 

Some of your challenges will involve using Regular expressions in Javascript, see below few examples of Regexp

### match 

```javascript
    let myDiv = '<div class="myClass">Stuff</div>'

    myDiv.match(/>(.*?)</)
    // Will return a matching informations below
    // [
    //     '>Stuff<',
    //     'Stuff',
    //     index: 20,
    //     input: '<div class="myClass">Stuff</div>',
    //     groups: undefined
    // ]   
    myDiv.match(/>(.*?)</)[1]
    //will return Stuff

```

### replace 
```javascript
    let exReplace = 'The world is an amazing place'
    exReplace.replace(/amazing/, 'awesome')

    //will return the new variable with the replaced value

    //'The world is an awesome place'
```
