#JS Day 1 Homework

Go through each sample code and work out what the output will be and explain what happened.

### Episode 1
```
var name = 'Keith';

var printName = function() {
  console.log('My name is ' + name );
}

printName();

Output = "My name is Keith"
printName has access to the variable name because it is global.


```

### Episode 2
```
score = 5;

var result = function() {
  var score = 3;
  return score;
}

console.log(result());


Output = 3
The local variable "var score = 3" with override the global variable "score = 5"



```

### Episode 3
```
var myAnimals = ['Chickens', 'Cats', 'Rabbits'];

var listAnimals = function() {
  myAnimals = ['Ducks', 'Dogs', 'Lions'];
  for(var i=0;i<myAnimals.length; i++){
    console.log(i + ": " + myAnimals[i]);
  }
}

listAnimals();


Output = 
"0 : Ducks
1 : Dogs
3 : Lions"

Local variable with overide global vaiable. It will loop through the local array and print the formatted string with index and animal.



```

### Episode 4

```
var suspectOne = 'Jay';
var suspectTwo = 'Val';
var suspectThree = 'Keith';
var suspectFour = 'Rick';

var allSuspects = function() {
  var suspectThree = 'Harvey'
  console.log('Suspects include: ' + suspectOne + ', ' + suspectTwo + ', ' + suspectThree + ', ' + suspectFour)
}

allSuspects();
console.log( 'Suspect three is:' + suspectThree )



Output of allSuspects() = 
"Suspects include: 
Jay
Val
Harvey
Rick"
because the local variable for suspectThree will override the global variable.


Output of console.log( 'Suspect three is:' + suspectThree ) =
Suspect three is: Keith
because the information inside the allSuspects function is outside it's scope.



```

### Episode 5

```
var detective = {
    name : 'Ace Ventura',
    pet : 'monkey'
  }

var printName = function(detective) {
  return detective.name
}

var detectiveInfo = function() {
  detective['name'] = 'Poirot'
  return printName(detective);
}

console.log(detectiveInfo());

Output of "console.log(detectiveInfo())" = 
"Poirot"
because  detectiveInfo() get's called, which then calls printName(detective) passing in the local variable 'detective['name'] = 'Poirot'' in as an argument, which returns 'Poirot' as the name.




```

### Episode 6
```
var murderer = 'rick';

var outerFunction = function(){
  var murderer = 'marc';

  var innerFunction = function(){
    murderer = 'valerie';
  }

  innerFunction();
}

outerFunction();
console.log('the murderer is ', murderer);
```

Output of outerFunction() = 
nothing, because nothing is returned

Output of console.log('the murderer is ', murderer) =
"the murderer is rick"
because when the console accesses murderer, it will access the global variable.





### Episode 7 - Make up your own episode/s!

Make up your own episode which can be whatever you wish and the rest of the class will work out together what happened and what the output will be.