---
layout: post
title: "A Brick a Day"
date: 2013-10-15 00:56
comments: true
categories: brick
---

I know a lot of programming languages, but I'm still not really happy with any of them. It started with PBASIC, then Objective-C, C, Common Lisp, Python, C++, Java, Ruby, Scheme, Assembly (Propeller), and now OCaml and Rust, in that order. Of all these languages, my favorites are probably Ruby, Common Lisp, and Rust.

As you can probably tell from that, I like functional programming. The idea that any call is merely a transformation of the initial data is really cool. But there's a couple of bad problems I have with those three languages:

- Speed
- Portability, specifically to new architectures
- Adoption

Each of these problems applies to at least two of the languages. 

[Ruby](http://www.ruby-lang.org) is flexible and powerful, but is slow as molasses. The [Rubinius](http://rubini.us) project is definitely helping with this, being a JIT for Ruby, but ~~they still have a ways to go, as they're currently working on 1.9.3 support~~. And, the overhead of a VM still exists. Out of the three languages, this definitely has the best community support (probably because of Rails, but beggers can't be choosers). EDIT: Apparently, rubinius reached 2.0.0 without me noticing, and now supports Ruby 2.1 syntax. Way to go, RBX!

[Common Lisp](http://common-lisp.net) is _the_ langauge for firsts. GC, cons pairs, compile-time AST editing (macros), type inference. If you can think of it, CL probably has it. And it has the speed Ruby doesn't, with 30+ years of academic research poured into projects like [SBCL](http://www.sbcl.org). But it still falls short. The CL library scene is sad, and only recently has a decent dependency management system come to fruition. Yes, I'm looking at you, [quicklisp](http://www.quicklisp.org). However, cross-compiling clisp is no easy feat, and running that on a microcontroller is not going to happen.

[Rust](http://www.rust-lang.org) is the newcomer to the scene, the proverbial hipster. There's a great deal of hype surrounding Rust, at least at my school, and it looks absolutely amazing. But it's a bit too C-like and low-level for my taste. Plus, there's next to no documentation for the language, the best thing being the symbiotic project the language is being developed with, [Servo](https://github.com/mozilla/servo). Out of all these languages, Rust is probably the closest to what I would like to work with on a daily basis.

Since no language has the features I want, or the facilities to modify it to the degree I want, I've decided to write my own language, called Brick.

This is not a small project.

Language design is a big deal, and I've spent the last two and a half months writing syntax ideas, reconciling possible conflicts, working out how systems might interact. And slowly, I came to a point where I started to know what this would be like. Next post, I'll talk about some of the design decisions, and the syntax.
