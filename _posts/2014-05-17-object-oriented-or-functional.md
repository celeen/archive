---
layout: post
title: Object-Oriented or Functional
image: /images/oovfp.jpg
---

<h3>Object Oriented, or Functional Programming?</h3>

<p>True.</p>

<p>I've found this sort of thing to be very difficult to write about; it's an incredibly varied topic, and while these two perspectives are often thought of as opposing, I have trouble understanding why. They seem like two angles of the same view.</p>

<p>From what I've read, Object Orientation and Functional Orientation aren't intrinsic methods, or automatically built into certain languages, they're more like design principles, or even philosophies. These two philosophies are just two different methods of breaking up the messy bits of abstract thinking that's required in computer programming.</p>

<h4>Object Oriented Design</h4>

<p>is often attributed to  Alan Kay, who wasn't really its inventor, but did a lot of thinking and writing on the topic. Rumor has it he compared object-oriented programming to biology: one living being is made up  of a large number of cells, which all talk to each other and send little messages back and forth, making up the whole.</p>

<p>Goals of the object oriented way of thinking are, among other things, ease of maintenence, and ease of expansion of any given program. The line of thinking goes that if you have encapsulated data structues well, then you can easily alter as needed either the larger makeup of the entire structure, presumably by altering the relationship between objects, or adding objects to the mix.</p>

<h4>Functional Programming</h4>

<p>focuses on organizing actions into a simplistic structure that can be easily altered and added to because of the simplicity of the processes. Because of the focus on processes, functional programming is (in my opinion) more easily described by its features than its goals. Object oriented features are pretty straight forward: objects, and the "hiding" of information within them. Functional programming has similar goals- simplicity, ease of maintenence, ease of expandability- but different ways of going about getting there. Rather than working largely with nouns as it were, functional programming focuses on verbs, or functions. </p>

<p>One of the core tenants of this style is that the initial data set is immutable; that is to say, it doesn't get changed, even if you <strong>can</strong> change it. Because of the focus on functions, creating copies of objects and variable ensures that you know exactly what is going in and our of a function at any given point in the program. You don't have to trace the program linearly in order to know what data you're dealing with, you can just check whatever variable is concurrent with that piece of the program.</p>

<p>Another key feature of functional programming is the use of higher order functions. My understanding is that this basically means you can use a function as an argument in another function. We see #map and #reduce used as examples of this in other languages.</p>

<h4>Comparing the two, practically</h4>

<p>If you wanted to iterate over the members of an array using a certain function, and output another array, you could easily do so in ruby using the #each method:</p>
<p><pre><code>
array = [1,2,3,4,5]

array_squared = []

array.each {|n| array_squared << n*n }

array_squared => [1,4,9,16,25]

</code></pre></p>

<p>Notice a few things about this example that make it a (small) example of the functional style:
<ul>
<li>-We have defined a new array, rather than trying to change the original data set</li>
<li>-There is a function within a function</li>
</ul>
</p>

<p>Let's take it even farther, though. Iterating through an array to return a new array is a thing I find I do a lot in the programs I write. So I might want to define a function, er method, that does just that:</p>

<p><pre><code>
class Array

def map(array, function)
  new_array = []
  array.each {|n| function}
  
</code></pre></p>

<p>Wait a minute... That's not quite going to work. Ruby freaks out a little bit when I try to pass an undefined variable through as an argument. Does that mean that Ruby doesn't support higher order function?</p>

<p>Not necessarily. From what I've read, There are a lot more ways to peel this apple, namely with the use of Procs. But I will come back to that in a later post.</p>

<p>We've got some medium level functions here with just the use of blocks. It seems pretty clear at this point in my learning that Ruby has some features of functional programming, and can be used in a functional style, but the functional style is perhaps more naturally suited on a broad scale to other languages. Ruby is generally known as an object oriented language, and I think our difficulty in passing a function as an argument using this structure illustrates that point.</p>

<p>We have here an example of what <strong>doesn't</strong> make our example a good illustrations of functional style, as well: while we saw above that we can contain functions within functions, passing functions in as arguments gets a little trickier.</p>

<p>Obviously, the #map method is built in to ruby, and we <strong>could</strong> write our own, but it will take a few more skills than what we've learned so far.</p>

<h4>The Difference</h4>

<p>So, if I am to recap, object oriented verses functional programming, are two different ways of structuring and approaching code. Some languages more naturally lean toward one way than the other. So far, one of the beautiful parts of ruby to me is that it seems relatively easy to use both strategies.</p>

<p>In philosophical terms, <a href = "http://rubyrogues.com/065-rr-functional-vs-object-oriented-programming-with-michael-feathers/">it's been said</a> (around minute 15:06), that object oriented programming sets context boundaries on the inputs, or hides information, while functional programming puts its context boundary on the outputs, or hides its effects.</p>

<p><a href = "http://michaelfeathers.typepad.com/michael_feathers_blog/2012/03/tell-above-and-ask-below-hybridizing-oo-and-functional-design.html">Another interesting argument</a>, on the whole of programming strategies, says that perhaps functional programming style is best suited for the lower parts of a program, or the building blocks, while object oriented can help those functional building blocks play together in a well structured large-scale way. A good analogy would be functionally programmed sports games: they're focuses on the rules of the game, what actions are allowed, with Object-oriented tournaments: two teams play against each other for a given result, etc.</p>

<p>There are countless arguments out on the web bashing one or the other method, or telling us why one style is clearly superior. It seems to me as if most any argument comes into play best when working with large systems, rather than the small examples I've been seeing in my learning so far. And at that level, why not consider both philosophies, even when constrained slightly by whatever language you happen to be working in. I personally love the "tell above, ask below" idea, and I can't wait to learn more about programming as a whole, so that I can impliment that strategy, or perhaps even see it in practice.</p>

	