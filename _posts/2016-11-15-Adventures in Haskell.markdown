---
layout: blog
comments: true
title:  "Adventures in Haskell"
date:   2016-11-15 00:00:00
categories: haskell
---

I have recently started learning some Haskell, in case you have not heard about it already Haskell is a purely functional
language, this means you can only program with pure functions which can have no side effects. A pure function always
returns the same value when called with the same arguments. This can make coding a bit more predictable, if a function
has side effects then it does something under the hood that is hidden from view, like accessing or changing some state.

This means that when you call the function in order to tell what it does, you must keep this hidden state in mind. This
can easily add complexity to coding since you have to constantly keep in mind all of the state in your app that may
effect the execution of your code.

In Haskell you are forced to make all of these effects explicit, so you can rely on a functions signature to tell what
it does.

Ok, sounds good? Well... there are some problems with this too as I have come to find out. Haskell can make you jump
through a lot of hoops just to do something simple. You have to be very clear about the types of everything, and make
sure to return the right types. I am used to the freedom of JavaScript so sometimes I feel it is a bit constraining.

That is the price you pay for clarity though, relying on side effects and hidden state might look simple, it may even
be a lot less code. However the added complexity is a price that you still have to pay.

Haskell is still a difficult language, especially if you have learned to code in imperative languages before (basically
most popular modern programming languages are more to the imperative side). Many modern languages have started incorporating
functional programming concepts, basically all of them have lambda expressions by now. But it takes a lot more to overcome
the decades of imperative style coding. Haskell is functional from the start and only functional so you cannot do anything
else, this makes it difficult to grasp.

Since the designers of Haskell knew they wanted to make a functional only language, they optimized the syntax for this
which makes working with functions really simple and expressive.

For example, here is a recursive definition of the factorial function:

{% highlight haskell %}
fac :: Int -> Int
fac n | n <= 0 = 1
      | otherwise = n * fac (n-1)
{% endhighlight %}

The top line is an optional type declaration which says that the function fac takes an Int as argument and returns an Int.
It is mostly for making the code more clear and easier to read, it also checked by the compiler so it compares it to the
actual function and shows an error if they are not the same. If you are used to comments going out of date as the functions
change this is a great feature!
The | is a guard which together with pattern matching can define the different cases, for example in this function when
n is <= 0 the function just returns one (this is not strictly mathematically correct but it keeps the function from
endlessly looping with a negative number as input). In the recursive case the function returns n * the function called
again with n-1.

In Haskell you just write arguments to the function, no () or , needed! For example you could write:

{% highlight haskell %}
add x y = x + y
{% endhighlight %}

The Haskell compiler can determine the types with type inference. So it will guess that x and y are numbers, strictly
speaking they have to implement the Num type class. If you ask the compiler for the type of the function it will say:

{% highlight haskell %}
add :: Num a => a -> a -> a
{% endhighlight %}
Num a => means it must implement the Num type class, which is kind of like an interface (if you are used to Java or C#).
The remaining 3 a's means the function takes two a's as arguments (x and y) and returns an a. The type a means it is a
generic type, so it can be int or float. This is parametric polymorphism. The types must however be the same so adding
two int's together must produce an int.

So in short Haskell can be tricky, but in many ways it is actually a lot simpler. It is very different for sure so if
you want to learn something new it may be a good language to try. Especially if you are interested in learning about
functional programming.

Curry on!
