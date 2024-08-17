---
author: Tom
pubDatetime: 2023-01-23T15:22:00Z
title: Object methods in Javascript
slug: object-methods-in-javascript
featured: false
draft: false
tags:
  - javascript
description:  In this post, I will show you some of the methods available on the Object object in JavaScript.
---

In JavaScript, the Object object has several methods available to it, including:

- `Object.assign()`: copies the values of all enumerable own properties from one or more source objects to a target object.
- `Object.create()`: creates an object with the specified prototype object and properties.
- `Object.defineProperties()`: defines new or modifies existing properties directly on an object, returning the object.
- `Object.defineProperty()`: defines a new property directly on an object, or modifies an existing property on an object, and returns the object.
- `Object.entries()`: returns an array of a given object\'s own enumerable property `[key, value]` pairs.
- `Object.freeze()`: prevents new properties from being added to an object, and prevents existing properties from being removed or their values from being changed.
- `Object.getOwnPropertyDescriptor()`: returns a property descriptor for an own property of an object.
- `Object.getOwnPropertyDescriptors()`: returns all own property descriptors of an object.
- `Object.getOwnPropertyNames()`: returns an array of all properties (enumerable or not) found directly upon a given object.
- `Object.getOwnPropertySymbols()`: returns an array of all symbol properties found directly upon a given object.
- `Object.getPrototypeOf()`: returns the prototype (i.e., the value of the internal `[[Prototype]]` property) of the specified object.
- `Object.is()`: determines whether two values are the same value.
- `Object.isExtensible()`: determines if an object is extensible (whether it can have new properties added to it).
- `Object.isFrozen()`: determines if an object is frozen.
- `Object.isSealed()`: determines if an object is sealed.
- `Object.keys()`: returns an array of a given object\'s own enumerable property names.
- `Object.preventExtensions()`: prevents new properties from ever being added to an object.
- `Object.seal()`: seals an object, preventing new properties from being added to it and marking all existing properties as non-configurable.
- `Object.setPrototypeOf()`: sets the prototype (i.e., the internal `[[Prototype]]` property) of a specified object to another object or null.
- `Object.values()`: returns an array of a given object\'s own enumerable property values.

Please note that this list is not exhaustive, and there are some additional methods that you can use depending on the JavaScript engine and environment you are running.