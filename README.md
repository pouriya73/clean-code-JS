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
