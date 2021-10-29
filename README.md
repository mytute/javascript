## javascript

### Primitive(not an object and has no methods)

1.string    
2.number    
3.bigint    
4.boolean    
5.undefined    
6.symbol    
7.null    
All primitives are immutable.

### Mutable

1.Object    
2.Array    
using "immer" we can get fully immutable copy of variable.    
//JSON.parse(JSON.stringify(obj))

### spread operator

let x = [1,2,3,4];    
let y1 = x; // clone of x (reference / mutable  )    
let y2 = Object.assign([],x); // (immutable)    
let y3 = [...x]; // (immutable)    

let y = [5,6,7];    
...x = 1,2,3,4    
...y = 5,6,7    
...x,...y = 1,2,3,4,5,6,7    
[...x,...y] = [ 1,2,3,4,5,6,7];    

[...x,...y] = x.concat(...y); // same thing    

// for function    
let func = function(...arg){  
  console.log(...x)
}

func(...x) // func(1,2,3,4)
func.apply(null, x); // old school    

Math.hypot(...x); // sq(2+4+9+16)
Math.min(...x); // 1  
Math.max(...x); // 4  

Object.assign([],x) // only one argument for Array, many for Objects    

### bitwise operator  

//0 - 000     
//1 - 001    
//2 - 010  
//3 - 011  
//4 - 100    

// AND  
// 0 & 0 = 0;   
// 0 & 1 = 0;   
// 1 & 1 = 1;   

// OR   
// 0 | 0 = 0;   
// 0 | 1 = 1;   
// 1 | 1 = 1;   

// 0 ^ 0 = 0;   
// 0 ^ 1 = 1;   
// 1 ^ 1 = 0;   

// convert to binary    
(4555).toString(2); // 1000111001011   argument 2 mean convert to binary numbers  

// convert to decimal (both are same)   
parseInt("1000111001011", 2) // argument 2 mean convert from binary numbers   
(ob1000111001011).toString(10)    

// 001    
// 011    
1 & 3 // 1  001   
1 | 3 // 3  011   
1 ^ 3 // 2  010   


9 << 2 // 36  = 1001 + 00  = 100100 = 36    
9 >> 2 // 22  = 00 - 1001   = 10 = 2    

bitwise operator using : encryption hash algorithms   

### Async Await   

* this method block the code .    
* Async function always return promise.
* we can use async await with normal promises.
ex:
```javascript
const preMove = async ()=>{

    const promiseForBringTikets= new Promise((resolve,reject)=>{
        setTimeout(()=>{
           resolve(`get tikets`);
        },3000);
    });

    const getPopCorn = new Promise((resolve,reject)=> resolve(`get popcorn`));
    const getCream = new Promise((resolve,reject)=> resolve(`get creme`));

    const m = await promiseForBringTikets;

    let [pop, cream] = await  Promise.all([getPopCorn, getCream]);
    console.log(`pop ${pop} cream ${cream}`);
    return m;
}
  preMove().then((m)=>{ console.log(m)});
```

### Mixins in JavaScript

build new object using exist objects

Function Mixins
```javascript
const humanFactory= function(obj){
    let isCrying= false;

    return Object.assign({}, obj, {
        cry(){
            isCrying= true;
            return this;
        },
        isCrying(){
            return isCrying;
        }
    });
}
const flyFactory= function(obj){
    let isFlying= false;

    return Object.assign({}, obj, {
        fly(){
            isFlying= true;
            return this;
        },
        isFlying(){
            return isFlying;
        }
    });
}

const superman= humanFactory(flyFactory({}));
console.log(superman);
superman.fly().cry().isCrying();
```

### JavaScript Sets and Weaksets

sets are reference datatype.  
sets are iterable object like Array.  
set have no order like Array.
set not repeat any numbers.

set should define with constructor. not like Array  
const ary = [];
const myArray = new Array();  
const mySet = new Set(); // only with constructor.  

// add values to set with add method    
const mySet = new Set();  
mySet.add(1).add(2); // return this can chain it.

// add values to set with add array    
const ary = [1,2,3];  
const mySet = new Set(ary); // array convert to set    
const mySet = new Set([1,2,3,4]);   

// delete values from set   
mySet.delete(2);    

// iterable   
for(let val of mySet){  
  console.log(val);
}

// array convert to unique values using   
const ary= [1, 2, 2, 3];    
[...new Set(ary)]; // [1, 2, 3]   
Array.from(new Set(ary)); // [1, 2, 3]    


Weaksets only store objects   
const ws = new WeakSet();   
ws.add({a:1});    

define Weaksets with array    
const ws = new WeakSet([{a:1},{b,2}]);    

Weaksets functions    
ws.delete(); // delete object   
ws.has(); // check object   
ws.add();   


### JavaScript Maps and Weakmaps    

// only one object can use as key in js object.   
const a ={};    
const b ={};    
const c ={};    

a[b]='b'; // a={[objct]:'b'}    
a[c]='c'; // a={[objct]:'c'} // overwrite object key as same key    

so that's why we are using maps.    

const map = new Map();    
map.add({a:'a'}).add({b:'b'}).add({b:'c'}); // same key will overwrite    
map.delete(a); // delete    

// iterable   
for(let [key, value] of map.entries()){   
  console.log(key, value); // {} 'a', {} 'b',   
}   

// map convert to array   
const ary = [...map]; // create two dimension array [[], []]    

// Weakmaps   
Maps store object as a key and it will not found by garbage collector.    
for that we are using a weakmaps    
const wm = new WeakMap();   
wm.set(x, "x");   

### array   

// create array and process   
console.log(Array.from([1, 2, 3], x => x + x)); // [2, 4, 6]    
Array.from(array, (element, index) => { ... } )   

// apply() method takes arguments as an array   
function my(...b){    
    console.log(b);// [1,2,3,4]   
    console.log(this.name) // "kangaroo"    
}
my.apply({name:  "kangaroo"},  [1,2,3,4]);    
my.apply({},  [1,2,3,4]); // only with arguments    

// call() method takes arguments as an set    
function my(message, print){    
    console.log(message, print); // "message", "print"    
    console.log(this.name); // "kangaroo"   
}
my.call( {name:  "kangaroo"}, "message", "print");    

###  Destructuring

Object >  extract individual values from object    

```javascript

   const person={
       name:'samadhi',
       age:31,
       country="sri lanka"
   }

   let {name, age, country="russia"} = person;
   console.log(name) // samadhi
   console.log(age) // 31

   function print({name, age}){
       console.log(name); // samadhi
       console.log(age); // 31
       console.log(country) // sri lanka
   }
   print(person);
   
```

Array > extract individual values from array    

```javascript
   let numbers = [1, 2, 3];

   let [one, two, three= 200] = numbers;

   console.log(one); // 1
   console.log(two); // 2
   console.log(three); // 3


   function bottle(){
       return ['Bottle', 'water'];
   }

   let [red, blue]= bottle();
   console.log(red); // bottle
   console.log(blue); // water


```

### OOP programming   


Classes

// TODO


Inherit constructor functions  

```JavaScript
function Shape(name){
    this.name= name;
}

Shape.prototype.print = function (){
    console.log("print : ", this.name);
}

function Triangle(name){
    Shape.call(this, name)
}

// only need when "Shape" outside of class ex:  Shape.prototype.print
Triangle.prototype = Object.create(Shape.prototype);

const t1 = new Triangle("sam");
t1.print();

console.log(t1.name)
```



string interpolation  = `string text ${expression} string text`   
api = appication programming interface    
node js : it's opensource , crose plateform , runtime enviroment, where we can run javascript.    
none bloking asynchromuse arcitecture   

create(post) ,read(get), update(put), delete(delete) (CRUD operations)    
