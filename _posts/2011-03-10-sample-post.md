---
layout: post
title: "Tackling on Data Structures: Stacks and Queues (Part I)" 
date: 2018-07-29 19:48:01
categories: ["intro", "tutorials", "python", "data-structures"]
---

💵 💵 Let's start on the topic of stacks and queues! 💵 💵

<!--more-->

## So what is a stack?
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
### Let's explore the concepts of a stack by defining its methods

pancake_stack = ['apple','bacon','cinnamon']   # first, let's define a linear collection 

### To add a new element on top of the stack, 
### we push our new item at the end of the collection
### In python, we can use the `append()`.

pancakes.append('banana')   # We add 'banana' to the stack
pancakes.append('buckwheat')   # We add 'cherry' to the stack
print(pancakes)             # sanity check: we now got ourselves collection of:
                            # ['apple','bacon','cinnamon','banana','buckwheat'] 

### To remove the element(s) of a stack, 
### we take out the top/rightmost/newest element.
### For this example, we can use `pop()`.

pancakes.pop()              # We pop off the rightmost/last element, 'buckwheat' 
pancakes.pop()              # ...no more banana 
pancakes.pop()              # ...and no more cinnamon
print(pancakes)             # which leaves us with ['apple','bacon']

### By checking the newest or topmost element in our stack, we take a "peek" at it
def stack_peek(collection):
  return collection[len(collection)-1]

print(stack_peek(pancakes)) # which gives us 'bacon'

### To check if our stack contains any elements:
def isEmpty(collection):
  return len(collection) == 0

print(isEmpty(pancakes)) # gives us 'False'
pancakes.pop()
pancakes.pop()
print(isEmpty(pancakes)) # and we got ourselves an empty stack!

### To arrange the operations above in an object oriented manner,
### We can define the stack and its related operations syntactically:
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

## Purposes & Possible Applications


## Challenge