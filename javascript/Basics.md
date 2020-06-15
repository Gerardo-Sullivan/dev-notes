# Basics

## Variables

### Primitive Types

## Underfined

Can think of underfined when a variable is declared but not assigned.

e.g. ``var x;``

[MDN docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined)

### Operators

## Strict vs Non strict comparison

Javascript has two operators for comparing equality, ``==`` and ``===``.

### ``==``

Uses a special algorithm ([Abstract Equalty Comparison Algorithm](http://www.ecma-international.org/ecma-262/5.1/#sec-11.9.3)) to compare two operands. This will try to compare two operands of the same type, meaning that it will try to convert to the same type before comparing.

[MDN docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Equality)

### ``===``

Unlike the ``==`` operator this strict equality operator will check two operands for equality, but will consider operands of different types to be different.

[MDN docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Strict_equality)

## Exceptions

Javascript contains the ability to throw an object as a exception.

[W3 docs](https://www.w3schools.com/js/js_errors.asp)