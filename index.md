---
title       : Fibonacci Number Generator
subtitle    : Developing Data Products - Assignment deck
author      : orcacodes
job         : student
framework   : deckjs        # {io2012, html5slides, shower, dzslides, ...}
deckjs      : {theme: web-2.0, transition: vertical-slide}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [mathjax]            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
--- 

## Fibonacci Number Generator
Developing Data Products - Assignment deck  


by: orcacodes

--- 

## Introduction to this app

This simple Fibonacci Number Generator shiny app will take a number input from the user representing the nth Fibonacci number they want to find, and output the corresponding Fibonacci number in the sequence.  

The overall app does these steps:  

1. Allows the user to enter a value for n, representing the nth Fibonacci term they want to find
2. Has a button "Find my Fibonacci number" that the user must click before retrieving a result
3. The server side takes the n input and performs calculations to produce the nth Fibonacci number
4. The UI outputs the resulting Fibonacci number to the screen  

--- 

## Fibonacci number introduction

Here is a quick introduction of the Fibonacci number sequence in case you need a refresher.  

The Fibonacci number sequence starts with 0 as the 0th term, 1 as the 1st term, and each subsequent number in the sequence is the sum of the previous two numbers in the sequence.  Mathematically, this is represented as:  
$$F_n = F_{n-1} + F_{n-2}$$  

In this shiny app, we are starting our Fibonacci sequence with 0 as the 0th term of the sequence.  As a result, here are the 0th to the 15th terms of this sequence:  

0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, 233, 377, 610  

--- 

## How this app works

One can calculate all the previous values of the Fibonacci sequence to arrive at the next value, but there is a simpler formula which involves the Golden Ratio.  

The Golden Ratio is a special number found by dividing a line into two parts so that the longer part divided by the smaller part is also equal to the whole length divided by the longer part.  

The Golden Ratio is denoted by phi ($\varphi$) and $\varphi = \frac{1+\sqrt{5}} {2}$  

A related number psi ($\psi$) is $\psi = 1-\varphi = \frac{1-\sqrt{5}} {2}$  

The formula for a specific nth Fibonacci number is:  
$$F_n = \frac{\varphi^n - \psi^n} {\varphi - \psi} = \frac{\varphi^n - \psi^n} {\sqrt{5}}$$
From the equation above, we can calculate the nth Fibonacci term from the n that the user inputs.

---

## Sample calculation

Suppose that the user wants to find the 30th Fibonacci number in the sequence.  

```r
n <- 30
phi <<- (1+sqrt(5))/2
psi <<- (1-sqrt(5))/2
fibonacci <- ((phi^n)-(psi^n))/sqrt(5)
fibonacci
```

```
## [1] 832040
```
The n=`30`th Fibonacci number is `832040`.
---




