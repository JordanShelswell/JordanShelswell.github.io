---
layout: post
title:  "Euler Project: 1"
date:   2019-03-22 00:00:00 -0500
categories: python math programming portfolio
thumbnail: Euler_1.png
publish: y
---
<!--Needs editing and final result added before release-->
As of late I have been expanding my mathematics skills and been familiarizing myself with several programming languages. While doing so I encountered a site that is called Project Euler. The site is a collection of mathematical, logic and computational puzzles that seek to challenge people with progressively harder questions. I thought I might try my hand at these problems and share my experiences with them. I am by no means a mathematician or computer scientist.
With that in mind, you can find the problem here: [Project Euler #1][project-euler], if you would like to check out the source and maybe try a few of the problems yourself.

# Euler Problem 1: Multiples of 3 and 5
If we list all the natural numbers below 10 that are multiples of 3 or 5, we get 3, 5, 6 and 9. The sum of these multiples is 23.
Find the sum of all the multiples of 3 or 5 below 1000.

# My breakdown
I started this project by breaking it down into the following steps:
1. Create objects to hold the two sets of numbers.
2. Populate the objects with their respective sets.
3. Amalgamate the two sets and eliminate duplicates.
4. Sum amalgamated set to find solution.
This breakdown aligned quite well with what I ended up needing to implement in python.

You can take a look at what my code ended up looking like below:
{% highlight python %}
	# If we list all the natural numbers below 10 that are multiples of 3 or 5, we
	# get 3, 5, 6 and 9.
	# The sum of these multiples is 23.
	# Find the sum of all the multiples of 3 or 5 below 1000.

	# Defining Initial Loop Variables
	Mul3 = [0]
	Mul5 = [0]

	# While loops to create number series
	while Mul5[-1] < 995:
	    result = Mul5[-1] + 5
	    Mul5.append(result)

	while Mul3[-1] < 999:
	    result = Mul3[-1] + 3
	    Mul3.append(result)

	# Cleaning Function: converts list object to dictionary and back
	# Dictionaries can not containe duplicates - removes duplicate values
	def clean(x):
	  return list(dict.fromkeys(x))

	# Combines lists, removes duplicates and sums returned value
	mySum = sum(clean(Mul5 + Mul3))

	# Prints Result
	print(mySum)
{% endhighlight %}

As you can see, I created the variable objects as arrays to hold the two sets of multiples.

These multiples are just a series of increasing values.
So, I crated a while loop to append a value to one of the arrays that is equal to the last value in the array value plus one integer of the series. I then copied and modified it so that both arrays would be filled with appropriate values.

I then tried figuring out a modification to the loop structure or some other method to deal with the fact that 3 and 5 share some multiples, while doing so I stumbled upon information pertaining to Python's dictionary function and how it can not contain duplicate values so I utilized it to create a function I could integrate into a call that simultaneously merges, purges and sums the arrays and contain the answer. In this case the arrays were joined then converted to a dictionary object then returned back as a list that is capable of being summed.

The answer ended up being __________


# Thoughts
Although this was a simpler problem I found the application and use of Python language and syntax a nice entry project to practice the basics I have been working on as of late.

In the future:
	The project could be modified to take into account user inputs and expand functionality to include other multiples.
	The code could also be rewritten to utilize a more mathematically clever and efficient way of computing this.

[project-euler]: https://projecteuler.net/problem=1
