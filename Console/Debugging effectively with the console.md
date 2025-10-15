
### Console.log

Consider three objects that you want to log

const foo = { name: "dave", age: 21, awesome: true };
const bar = { name: "thanh", age: 21, awesome: false };
const foobar = { name: "Marcel", age: 25, awesome: true};

```
console.log(foobar, foo, bar)

 {name: 'Marcel', age: 25, awesome: true} 
 {name: 'dave', age: 21, awesome: true} 
 {name: 'thanh', age: 21, awesome: false}
```

Destructure the objects in the log

```
console.log ({foobar: {…}, foo: {…}, bar: {…})

 bar: {name: 'thanh', age: 21, awesome: false}
 foo: {name: 'dave', age: 21, awesome: true}
 foobar: {name: 'Marcel', age: 25, awesome: true}
```

Nice but the data could be improved with a label and some custom styles, adding %c and a space before the label in your log, with the next argument being the styles themselves

```
console.log('%c nameList', 'color: red; font-weight: bold', {foobar, foo, bar})
nameList > {foobar: {…}, foo: {…}, bar: {…}}
```

Organise your object ouput in a table

```
console.table({foobar, foo, bar})

```

Outputs the following in the console

![[console+table.png]]

Time logs 

```
console.time("looper")

while(i < 1000000) {
 i ++
}

console.timeEnd('looper')
```


Stack trace 

```
const deleteMe = () => console.trace("bye bye database")

deteleMe() 
```

Should return a log defning where in the code the function was executed