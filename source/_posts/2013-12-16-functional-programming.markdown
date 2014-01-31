---
layout: post
title: "Functional Programming"
date: 2013-12-16 17:55:37 -0500
comments: true
categories: 
---

A lot of programmers start with C, or C++, or Java. They're currently the big three in the industry, with good reason: they're time-tried, and cross-platform.  

Other areas have their own (preferred) languages:

- Web:
	- Ruby (Rails, Sinatra, Padrino)
	- Python (Django, Flask)
	- Java/Scala (Play)
	- Javascript (Node.js)
- Academia (PLT): 
	- Haskell
	- Standard ML
	- OCaml
	- Scheme
- Systems Programming:
	- C/C++ (especially embedded)
	- Go
	- Rust
	- D

Of course, these languages can also be used for general-use programming. I regularly use Ruby for quick prototyping, and then move to another language more suited to what I actually need.

Functional programming is based on Alonzo Church's [λ-calculus](http://en.wikipedia.org/wiki/Lambda_calculus).

One of the first real implementations of this was LISP in the late 1950's. Lisp attempted to offer a simple mathematical style of programming to the then only imperitive field.

Later, other so-called "functional" languages emerged: Standard ML, Clean, Scheme, Common Lisp, Caml, OCaml, Haskell, Pure, etc. Only two of these are object-oriented: Common Lisp and OCaml, and neither are languages that traditional O-O programmers feel comfortable just look at. Common Lisp is obviously a Lisp, and OCaml is obviously an ML. Both are very powerful, but the syntax takes some getting used to.

In the age of languages like Ruby and Python, this shouldn't be the case anymore. Ruby gives people a very close taste of what functional O-O might feel like. Scala does too. It just hasn't been done well (Have you ever tried to curry a method in Scala?). And if you're wondering why I'm not counting Javacript in here, it's because Javascript doesn't have a 'classic' object system, and instead uses prototypal inheritance (it's also not technically functional, but that's another rant).

This is something I'd like to have. Objects in functional language, that looks something like Ruby or Python. So I came up with Brick.

Brick is functional.  
Brick is object-oriented.  
Brick looks (something) like Ruby, Python, and Scala.  

Here's a taste:

```brick
class Color(r : Fixnum, g : Fixnum, b : Fixnum) impl ToStr
	members
	    r = r 
	    g = g
	    b = b

    impl ToStr
        method to_str
            "rgb({:d}, {:d}, {:d})".format!(this.r, this.g, this.b)


fn main
	let | c = Color(12, 18, 39)
		puts(c.to_str()) 
```

So let's look at this. We have classes, declared with the `class` keyword. Following that is the class' name, the default constructor, and the list of traits that we implement, here just `ToStr`. 

After that is the members list, which lists all the slots our class has.

After the members list comes method declarations. Methods specifically all have the type of `ThisClass -> something....`. This means that there is an implicit first parameter that has the type of the current class. The name of this parameter is `this`.

The previous example can be simplified to

```brick
class Color(r:Fixnum, g:Fixnum, b:Fixnum) impl ToStr
    impl ToStr
        method to_str
            "rgb({:s}, {:s}, {:s})".format!(this.r, this.g, this.b)


fn main
	let | c = Color(12, 18, 39)
		puts(c.to_str()) 
```

So what do you think? Do you like this syntax? I like it. (It's pretty clean)