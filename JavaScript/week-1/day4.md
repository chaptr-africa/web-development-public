# Arrays and Objects

## Arrays
[Watch video](https://www.youtube.com/watch?v=S2JVtEwa-kU) JavaScript Arrays

[Watch video](https://www.youtube.com/watch?v=hZF_0dZnpvo) JavaScript Array Methods

## Objects
[Watch video](https://www.youtube.com/watch?v=CNGv0soYFn0&t=11s) JavaScript Object Literals

[Watch video](https://www.youtube.com/watch?v=_AQ9RBQcNMA) JavaScript Date Object


# Challenge: GroupBy

Write a function called groupBy that takes two parameters: an array of objects and a string that represents a property name. The function should group the objects in the array by the value of the specified property, and return an object where each key is the distinct value of the specified property, and the value is an array of objects that have that property value.

For example, if the array of objects is:

```
[
  { name: 'Alice', age: 25, city: 'New York' },
  { name: 'Bob', age: 30, city: 'Chicago' },
  { name: 'Charlie', age: 35, city: 'New York' },
  { name: 'Dave', age: 40, city: 'Chicago' }
]
```
and the property name is `"city"`, the function should return:

```
{
  'New York': [
    { name: 'Alice', age: 25, city: 'New York' },
    { name: 'Charlie', age: 35, city: 'New York' }
  ],
  'Chicago': [
    { name: 'Bob', age: 30, city: 'Chicago' },
    { name: 'Dave', age: 40, city: 'Chicago' }
  ]
}
```
If the property name is "`age`", the function should return:

```
{
  25: [{ name: 'Alice', age: 25, city: 'New York' }],
  30: [{ name: 'Bob', age: 30, city: 'Chicago' }],
  35: [{ name: 'Charlie', age: 35, city: 'New York' }],
  40: [{ name: 'Dave', age: 40, city: 'Chicago' }]
}
```
**Note:** Your solution should be able to handle arrays of any length and objects with any number of properties.