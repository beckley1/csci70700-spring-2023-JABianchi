ADVENTURER

** Task 1: Thoughts?** 
# How would you rate coding in Racket from a scale of 1 to 5? In your opinion, how does coding in Racket compare to coding in Java or Python? Do you find Racket’s syntax and approach more or less intuitive than those of the other languages? Explain your reasoning and provide examples to support your views.

Current rating for Racket: 2/5.  I'm very familiar with Java and understand how it handles different data types. Python is very forgiving with data types.  Racket threw me for endless exceptions about Real, Number, and Integer data types, that didn't play as nicely together as I would have expected.  There is something nice about calling a series of functions with the simplicity of parentheses (and avoiding all of the weird space issues and curly braces & semi-colons of Python & Java).  There may be some applications where Racket is preferred, but I wouldn't want to write general purpose code with it.


** Task 2: The Code **
#lang typed/racket
#Author: Joel Bianchi
#Date: 3/17/2023
#Assignment: If you are given three sticks, you may or may not be able to arrange them in a triangle. For any three lengths, there is a simple test to see if it is possible to form a triangle. If any of the three lengths is greater than the sum of the other two, you cannot form a triangle. Write a method name is-triangle that takes three integers as arguments and return either true or false, depending on whether you can or cannot form a triangle from sticks with the given lengths. 

"What's making all that racket?"

; triangle function
(define is-triangle
  (lambda ([a : Real] [b : Real] [c : Real]) 

    ; find the biggest side of the triangle
    (define big (max a b c))

    ; find the smallest side of the triangle
    (define small (min a b c))

    ; find mid by subtracting b + s from sum
    (define mid (- (- (+ a b c) big) small))

    ; the mid one should be greater than the difference
    (define diff (- big small))
    
    (if (> mid diff) #t #f)

))

; test out function
"Does 7, 8, 9 make a triangle?"
(is-triangle 7 8 9)

"Does 1, 2, 3 make a triangle?"
(is-triangle 1 2 3)

"Does 5, 12, 13 make a triangle?"
(is-triangle 5 12 13)



; "done with code"

#|
  ; conditional test
  (if (equal? 2 2) 
    'yes
    'no
  )
|#

