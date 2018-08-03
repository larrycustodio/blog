---
layout: post
title: "Tackling on Data Structures: Stacks and Queues (Part I)" 
date: 2018-07-29 19:48:01
categories: ["programming", "python", "data-structures"]
---

💵 💵 Let's start on the topic of stacks and queues! 💵 💵

<!--more-->

## So what is a stack?
Let's start with the term that's typically thrown in when describing a stack: it is a type of a <em>linear data structure</em>, meaning that its collection of values/information are organized a very specific way (hence the term, data structure). As for why the linear part, you can think of its individual nodes/elements being arranged and described with having two adjacent ends...a left/right, top/bottom, before/after, and so on. For instance, an array, `[1,2,3,4]`, or whatever list of things, fits our description of a linear data structure. 

What distinguishes stacks from other linear data structures is how its individual members are systematically read, added, and removed. In the case of the stack, our collection is arranged such that newer items are piled at the end of the collection, and removal of items are also done only at the end of our collection. Newer additions to the collection are at the top, while the oldest items sit at the bottom. 


To abbreviate this definitions, you may normally see the stack described as <strong>LIFO</strong>, meaning <strong>L</strong>ast <strong>I</strong>n, <strong>F</strong>irst <strong>O</strong>ut.

So what's the point of setting our data up in a stack?

CTRL Z

Say, your actions are somehow being logged by your software. As you hit the undo button, it pops off the latest logged action, reverting your changes to its previous state.     


## The Stack [Pseudo]Code with Additional Explanations
Focusing on practicing this concept, feel free to skip through the whole local setup process, and jump straight into using a code sandbox. I like [repl.it](https://repl.it/) myself, but whatever floats your boat. 

For readability, I've decided to use Python for demo purposes. Mainly since I'm most comfortable with explaining my code Python...). Again, Feel free to either follow along and write the code yourself, or simple copy + paste the code below and watch the magic happen.

For starters, let's define the basic methods associated with stacks. For simplicity purposes, treat a list as our base structure,
~~~
ice_cream_stack = ['chocolate','vanilla','strawberry']
~~~

To push a new entry on top of our stack, we append the new entry at the end of the list
~~~
ice_cream_stack.append('caramel')    # adds chocolate chips on the stack
ice_cream_stack.append('sprinkles')  # ...some sprinkles
ice_cream_stack.append('cherry')     # add cherry on top

print(ice_cream_stack)               # which yields a collection of:
> ['chocolate','vanilla','strawberry','caramel','sprinkles','cherry']
~~~

To remove the element(s) of a stack, we take out the topmost element. In this case we apply `pop()`
~~~
ice_cream_stack.pop()              # We pop off the rightmost/last element... 
ice_cream_stack.pop()              # ...no more sprinkles!
~~~

To <em>peek</em> at the stack would mean checking the newest/topmost element of the collection
~~~
def stack_peek(collection):
  return collection[len(collection)-1]

print(stack_peek(ice_cream_stack))
> ['caramel']
~~~

To check for the stack's existence
~~~
def isEmpty(collection):
  return len(collection) == 0
~~~

To encapsulate all these methods to define a Stack `class`:  
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