---
layout: post
title:  "Difference between == and === operators in JavaScript"
date:   2017-04-01 20:26:21 +0545
description: "What might be the Difference between == and === operators in JavaScript. The answer is here."
permalink: /difference-between-==-and-===-operators-in-javaScript/
---


Most of us think that the difference between `==` equality operator and `===` equality operator in JavaScript is that `==` equality operator compares two values while `===` equality operator compares the value and it’s type. Basically, this is a wrong concept. What actually is the difference then? Before I tell you about the difference, you first have to know about “coercion” in JavaScript. What exactly is “coercion”? “coercion” is just a fancy term for type conversion. For example, you want to convert a number into a string this conversion is called “coercion”.

{% highlight javascript %}
var a = “11”;
var b = Number(a);

console.log(a); // “11”
console.log(b); // 11

typeof a; // ”string”
typeof b; // “number”
{% endhighlight %}

As you know what “coercion” is, now let’s get back to our topic, What is the difference between `==` equality operator and `===` equality operator in JavaScript? The best way to explain is that `==` compares two values with coercion allowed, and `===` compares two values without coercion allowed.

For example:
{% highlight javascript %}
var a = “11”;
var b = 11;

a == b; //true
a === b; //false
{% endhighlight %}

In above example `a == b` JavaScript finds out that the types don’t match as `a` is of `“string”` type and `b` is of `“number”` type, then it coerces one or both values until both type match and then simple value comparison is done. In above example `a == b`, to give the result `true`, you can think JavaScript coerce value and end up with either `11 == 11` or `“11” == “11”`.

The `a === b` produces `false` as there is no coercion allowed, hence failing simple value comparison.


`Note: Reference taken form book by [Kyle Simpson](https://www.linkedin.com/in/getify) [You Don't Know JS: Up and Going](https://www.amazon.com/You-Dont-Know-JS-Going/dp/1491924462)`