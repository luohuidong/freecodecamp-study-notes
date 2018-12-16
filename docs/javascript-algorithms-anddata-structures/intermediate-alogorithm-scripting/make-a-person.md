---
id: make-a-person
title: Make a Person
---

```js
var Person = function(firstAndLast) {
  let nameArr = firstAndLast.split(" ");

  this.getFirstName = function() {
    let firstName = nameArr[0];
    return firstName;
  };
  this.getLastName = function() {
    let lastName = nameArr[1]
    return lastName;
  };
  this.getFullName = function() {
    const fullName = nameArr.join(" ");
    return fullName;
  };
  this.setFirstName = function(firstName) {
    nameArr[0] = firstName;
  };
  this.setLastName = function(lastName) {
    nameArr[1] = lastName;
  };
  this.setFullName = function(firstAndLast) {
    nameArr = firstAndLast.split(" ");
  }
};

var bob = new Person('Bob Ross');
bob.getFullName();
```
