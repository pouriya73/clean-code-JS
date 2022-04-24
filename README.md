# clean-code-JS
Software engineering principles, from Robert C. Martin's book Clean Code, adapted for JavaScript. This is not a style guide. It's a guide to producing readable, reusable, and refactorable software in JavaScript.


### Variables
Use meaningful and pronounceable variable names

#### Bad:
```javascript
const yyyymmdstr = moment().format("YYYY/MM/DD");
```
#### Good:
```javascript
const currentDate = moment().format("YYYY/MM/DD");
```

### Use the same vocabulary for the same type of variable

#### Bad:
```javascript
getUserInfo();
getClientData();
getCustomerRecord();
```
#### Good:
```javascript
getUser();
```

### We will read more code than we will ever write. It's important that the code we do write is readable and searchable. By not naming variables that end up being meaningful for understanding our program, we hurt our readers. Make your names searchable. Tools like buddy.js and ESLint can help identify unnamed constants.

#### Bad:
```javascript
// What the heck is 86400000 for?
setTimeout(blastOff, 86400000);
```
#### Good:
```javascript
// Declare them as capitalized named constants.
const MILLISECONDS_PER_DAY = 60 * 60 * 24 * 1000; //86400000;

setTimeout(blastOff, MILLISECONDS_PER_DAY);
```


### Use explanatory variables

#### Bad:
```javascript
const address = "One Infinite Loop, Cupertino 95014";
const cityZipCodeRegex = /^[^,\\]+[,\\\s]+(.+?)\s*(\d{5})?$/;
saveCityZipCode(
  address.match(cityZipCodeRegex)[1],
  address.match(cityZipCodeRegex)[2]
);
```
#### Good:
```javascript
const address = "One Infinite Loop, Cupertino 95014";
const cityZipCodeRegex = /^[^,\\]+[,\\\s]+(.+?)\s*(\d{5})?$/;
const [_, city, zipCode] = address.match(cityZipCodeRegex) || [];
saveCityZipCode(city, zipCode);
```



### Avoid Mental Mapping , Explicit is better than implicit.

#### Bad:
```javascript
const locations = ["Austin", "New York", "San Francisco"];
locations.forEach(l => {
  doStuff();
  doSomeOtherStuff();
  // ...
  // ...
  // ...
  // Wait, what is `l` for again?
  dispatch(l);
});
```
#### Good:
```javascript
const locations = ["Austin", "New York", "San Francisco"];
locations.forEach(location => {
  doStuff();
  doSomeOtherStuff();
  // ...
  // ...
  // ...
  dispatch(location);
});
```


