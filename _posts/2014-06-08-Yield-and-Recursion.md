---
layout: post
title: Week 1, Yield and Recursion
img: /images/recursion.jpg
---

##Week 1, Phase 1

Whew! What a week! This week it looks like I've clocked in at just about 70 hours so far, in part because I got sick on Thursday and skipped some of the exercises in favor of sleep. I'm hoping to catch up on those tonight. We'll see.

One of our review exercises this weekend is to make a list of some of the major topics we covered, and choose 2 to write about with code examples. What a great opportunity for a blog post! See my ruminations below...

###Yield, and Recursion
Recursion, in theory, can be simple to describe: it's when a method is called inside of its own definition. Like defining a word by using that word, but way better. When you define a word using that word, you just get to a dead end. With recursion, you open up so many more possibilities...

It's like a fractal: take a picture of part of it, and you can see the whole of it again. Take a picture of that picture of part of it, and there's the whole... etc.

The only trick with recursion in computer programming is that, unlike with fractals, the mathematical theory we're working with in computers is finite. You have to tell your program when to stop, or it'll keep running forever.

Here's a simple example of recursion:

```
def recursive_method(x)
  return "IT'S OVER!" if x == 0
  puts "...#{x}!"
  recursive_method(x-1)
end
```
When called, this method will output:
```
recursive_method(3)
=> "...3!"
   "...2!"
   "...1!"
   "IT'S OVER!"
```

Yield is a different story, kind of the opposite. Yield exits the method, runs whatever code is in the provided block, and then re-enters the method. This gives programs a TON of flexibility.

Here's a simple (and kind of classic) example of yield:
```ruby
def yield_method
	puts "Here we are within the method!"
	yield
	puts "Safe and warm again, back in the method."
end

yield_method {puts "Where is this? It looks like a block..."}
=> "Here we are within the method!"
   "Where is this? It looks like a block..."
   "Safe and warm again, back in the method."
```

I had initially wanted to combine them as an example. in my head, it looks like this:

```ruby
def method(x)
	return "Oh, THAT'S where this rabbit hole leads..." if x = 1
	yield(x-1)
end

method(x) { method(x) }
```

But of course, this code doesn't run, partially because our block has no idea what x is- that's an example of variable scope, another topic we went over this week, but which I won't cover here.

It looks like the other reason the code above doesn't run is because the block isn't consistently recognized. Based on some breif research, this seems to have something to do with blocks being a type of Proc. Lots of StackOVerflow posts recommend passing the block in as an argument using the ampersand.... but that's still just slightly over my head. I'll check back in when we've studied procs a bit more, and I can tell you if it's even possible to write a recursive method with yield by passing a block in containing the method. It may not be. To be continued!