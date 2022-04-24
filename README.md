# clean-code-JS
Software engineering principles, from Robert C. Martin's book Clean Code, adapted for JavaScript. This is not a style guide. It's a guide to producing readable, reusable, and refactorable software in JavaScript.


# Variables
Use meaningful and pronounceable variable names

#### Incorrect:
```javascript
const yyyymmdstr = moment().format("YYYY/MM/DD");
```
#### Correct:
```javascript
const currentDate = moment().format("YYYY/MM/DD");
```

## Use the same vocabulary for the same type of variable

#### Incorrect:
```javascript
getUserInfo();
getClientData();
getCustomerRecord();
```
#### Correct:
```javascript
getUser();
```

## We will read more code than we will ever write. It's important that the code we do write is readable and searchable. By not naming variables that end up being meaningful for understanding our program, we hurt our readers. Make your names searchable. Tools like buddy.js and ESLint can help identify unnamed constants.

#### Incorrect:
```javascript
// What the heck is 86400000 for?
setTimeout(blastOff, 86400000);
```
#### Correct:
```javascript
// Declare them as capitalized named constants.
const MILLISECONDS_PER_DAY = 60 * 60 * 24 * 1000; //86400000;

setTimeout(blastOff, MILLISECONDS_PER_DAY);
```
