---
layout: post
title: "Tackling on Data Structures: Stacks and Queues (Part I)" 
date: 2018-07-29 19:48:01
categories: ["intro", "tutorials", "python", "data-structures"]
---

💵 💵 Let's start on the topic of stacks and queues! 💵 💵

<!--more-->

## Defintion: What is a stack?
Let's start with the term that's typically thrown in when describing a stack: it is a type of a <em>linear data structure</em>, meaning that its collection of values/information are organized a very specific way (hence the term, data structure). As for why the linear part, you can think of its individual nodes/elements being arranged and described with having two adjacent ends...a left/right, top/bottom, before/after, and so on. For instance, an array, `[1,2,3,4]`, or whatever list of things, fits our description of a linear data structure. 

What distinguishes <strong>stacks</strong> from other linear data structures is how its individual members are systematically read, added, and removed. In the case of the stack, our collection is arranged such that newer items are piled at the end of the collection, and removal of items are also done only at the end of our collection. Newer additions to the collection are at the top, while the oldest items sit at the bottom. 


To abbreviate this definitions, you may normally see the stack described as <strong>LIFO</strong>, meaning <strong>L</strong>ast <strong>I</strong>n, <strong>F</strong>irst <strong>O</strong>ut.

So what's the point of setting our data up in a stack?

CTRL Z

Say, your actions are somehow being logged by your software. As you hit the undo button, it pops off the latest logged action, reverting your changes to its previous state.     


## The Stack [Pseudo]Code with Additional Explanations
Focusing on practicing this concept, feel free to skip through the whole local setup process, and jump straight into using a code sandbox. I like [repl.it](https://repl.it/) myself, but whatever floats your boat. 

For readability, I've decided to use Python for demo purposes (but mainly since I'm comfortable using Python...). Again, Feel free to either follow along and write the code yourself, or simple copy+paste the code below and watch the magic happen.

~~~ python
pancakes = ['apple','bacon','cinnamon']   # definition 

### To add a new element on top of the stack, we can use `append()`.

pancakes.append('banana')   # We add 'banana' to the stack
pancakes.append('cherry')   # We add 'cherry' to the stack
print(pancakes)             # Sanity check: we now got a "stack" of ['apple','bacon','cinnamon','banana','cherry'] 

### To retrieve the topmost element of the stack, we can use `pop()`.

pancakes.pop()              # We pop off the cherry 
pancakes.pop()              # ...banana 
pancakes.pop()              # ...and cinnamon
print(pancakes)             # which leaves us with ['apple','bacon']

### Other operations - to check the status of our stack, we can also implement 

def
  return stack[len(stack) -1]


### Now let's encapsulate the stack operations that we've learned via a class definition
class Stack:
  def __init__(self):
    self.elems = []

  def isEmpty(self):
    return self.elems == []

  def push(self, elem):
    return self.elems.append(elem)
  
  def pop(self):
    return self.elems.pop()
  
  def peek(self):
    return self.elems[len(self.elems)-1]

  def size(self):
    return len(self.elems)

~~~

## Purposes & Possible Applications


## Challenge