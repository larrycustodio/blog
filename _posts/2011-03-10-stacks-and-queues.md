---
layout: post
title: "Tackling on Data Structures: Stacks and Queues (Part I)" 
date: 2018-07-29 19:48:01
categories: ["programming", "python", "data-structures"]
---

💵 💵 Let's start on the topic of stacks and queues! 💵 💵

<!--more-->

## So what is a stack?
 Stacks is one of many instances of a <em>linear data structure</em>, meaning that its collection of values/information are organized a very specific way (hence the term, data structure). As for why the linear part, you can think of its individual nodes/elements being arranged and described with having two adjacent ends...a left/right, top/bottom, before/after, and so on. For instance, an array, `[1,2,3,4]`, or whatever list of things, would fit the base definition of a linear data structure. 
 
 For a data structure to fit the definition of a stack, we treat the collection such that items are added at the tail-end of the collection, and removal of items are also at the tail-end of our collection. In short, we normally see the stack described as <strong>LIFO</strong>, meaning <strong>L</strong>ast <strong>I</strong>n, <strong>F</strong>irst <strong>O</strong>ut.


## The Stack [Pseudo]Code with Additional Explanations
Jumping straight into the code definitions, open up a new `.py` file on a local drive, or use an online Python sandbox. I like [repl.it](https://repl.it/) myself, but whatever floats your boat.

For starters, let's define the basic methods associated with stacks. For simplicity purposes, we can treat a list as our base structure:
~~~
ice_cream_stack = ['chocolate','vanilla','strawberry']
~~~

To push a new entry on top of our stack, we append the new entry at the end of the list:
~~~
ice_cream_stack.append('caramel')    # adds chocolate chips on the stack
ice_cream_stack.append('sprinkles')  # ...some sprinkles
ice_cream_stack.append('cherry')     # add cherry on top

print(ice_cream_stack)               # which yields the following collection of values:
> ['chocolate','vanilla','strawberry','caramel','sprinkles','cherry']
~~~

To remove the element(s) of a stack, we take out the topmost element. In this case we apply `pop()`:
~~~
ice_cream_stack.pop()              # We pop off the rightmost/last element... 
ice_cream_stack.pop()              # ...no more sprinkles!
~~~

To <em>peek</em> at the stack would mean checking the newest/topmost element of the collection:
~~~
def stack_peek(collection):
  return collection[len(collection)-1]

print(stack_peek(ice_cream_stack))
> ['caramel']
~~~

To check for the stack's existence:
~~~
def isEmpty(collection):
  return len(collection) == 0
~~~

~~~
def size(collection):
  return len(collection)
~~~

To encapsulate all these methods to characterize the Stack "class":  
~~~
class Stack:
  def __init__(self):
    self.elems = []

  def push(self, elem):
    return self.elems.append(elem)
  
  def pop(self):
    return self.elems.pop()

  def peek(self):
    return self.elems[len(self.elems)-1]

  def isEmpty(self):
    return len(self.elems) == 0

  def size(self):
    return len(self.elems)
~~~

## The Challenge: how to apply a stack
Let's walk through a coding problem that can be efficiently solved by implementating a stack.