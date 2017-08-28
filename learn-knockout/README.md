# Learn KnockoutJS

## Model-View-ViewModel (MVVM) pattern

Can define a UI's appearance using **views** and **declarative bindings**, its data and behavior using **viewmodels** and **observables**, and how everything stays in sync automatically with **dependency tracking**

[Knockout.js documentation](http://knockoutjs.com/documentation/introduction.html)

### The View

`data-bind` attributes are how Knockout lets you declaratively associate view model properties with DOM elements. You just used the text binding to assign text to your DOM elements.


```html
<p>First name: <strong data-bind="text: firstName"></strong></p>
```

`Click binding` is a way to associate clicks with the view model function.

```html
<button data-bind="click: capitalizeLastName">Go caps</button>
```

`enable` is a way to set a condition for a button to be enabled
```html
<button data-bind="click: addFriend, enable: friends().length < 5">Add Friend</button>
```

### The ViewModel

`applyBindings` activates knockout.js

```javascript
ko.applyBindings(new AppViewModel());
```

`observable` are properties that automatically issue notifications whenever their value changes.

```javascript
this.firstName = ko.observable(“Bert”);
```

`computed` properties are observable (they’ll notify on change) and they are computed based on the values of other observables.

```javascript
this.fullName = ko.computed(function() {
    return this.firstName() + " " + this.lastName();    
}, this);
```

To read or write an observable’s value, you call it as a function.

```javascript
this.capitalizeLastName = function() {
    var currentVal = this.lastName();        // Read the current value
    this.lastName(currentVal.toUpperCase()); // Write back a modified value
};
```
