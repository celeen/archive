---
layout: post
title: Objects and Classes
image: ../images/classes.jpg
---
<p><a href = "http://scottjason.github.io">One of my colleagues</a> recently shared with me one question from interview that Rolling Stone did with Steve Jobs back in 1994:</p>
<blockquote cite = "http://www.quora.com/Object-Oriented-Programming/What-is-object-oriented-programming"><p><strong>Jeff Goodell: </strong>Would you explain, in simple terms, exactly what object-oriented software is? </p> 
        
<p><strong>Steve Jobs: </strong>Objects are like people. They’re living, breathing things that have knowledge inside them about how to do things and have memory inside them so they can remember things. And rather than interacting with them at a very low level, you interact with them at a very high level of abstraction, like we’re doing right here.</p>

<p>Here’s an example: If I’m your laundry object, you can give me your dirty clothes and send me a message that says, “Can you get my clothes laundered, please.” I happen to know where the best laundry place in San Francisco is. And I speak English, and I have dollars in my pockets. So I go out and hail a taxicab and tell the driver to take me to this place in San Francisco. I go get your clothes laundered, I jump back in the cab, I get back here. I give you your clean clothes and say, “Here are your clean clothes.”</p>
<p>You have no idea how I did that. You have no knowledge of the laundry place. Maybe you speak French, and you can’t even hail a taxi. You can’t pay for one, you don’t have dollars in your pocket. Yet I knew how to do all of that. And you didn’t have to know any of it. All that complexity was hidden inside of me, and we were able to interact at a very high level of abstraction. That’s what objects are. They encapsulate complexity, and the interfaces to that complexity are high level.</p></blockquote>

<p>Part of the reason I quote this is because it's just such a great example. Understanding objects is key to understanding classes, because in Ruby, everthing is an object, and every object belongs to a class. Even a class object belongs to the class class.</p>

<h2>Howabout a Metaphor!</h2>
<p>If objects are like people, then classes are like clubs or organizations. Your laundry object might belong to the chores committe, which might be a part of the Responsibilities organization. Each of these classes, groups, or organizations has a different set way of doing things. And in fact, yourt Laundry object could be a class of its own.<p>

<p>Each of these clubs is also an object (or "living, breathing thing", per se), and can belong to other organizations. Like I said earlier, every class is an object that belongs to the class "Classes". So, in our metaphor, the club "Responsibilities" is also a member of a club called "Clubs".</p>
<h3>The Ruby Of It</h3>
<p>In ruby, classes contain things like instance variables, initialization, and methods. As we get deeper into the actual code, I will make sure to mention their metaphorical parallels.</p>
<p>First, let's take a look at what a class might look like, using some labels we've garnered from Steve's apropos metaphor:</p>

<p><pre><code>class Laundry
	def initialize(quantity)
		@quantity = quantity
		@laundry_machine = []
	end

	def laundry_people_assemble
		self.show
	end

	def wash
		@laundry_machine << [@quantity, water, soap]
		@laundry_machine.run
	end

	def dry
		dryer << @laundry_machine
		dryer.run
	end
end</code></pre></p>

<p>Okay, so, that's not actually Ruby. But I've attempted to make it syntactically consistent. Setting aside the fact that we have no idea what exactly the #wash and #dry methods do, let's take a look at what we do have.</p>

<h3>A Class Above Itself</h3>

<p>First up: we've defined a <strong>class</strong>. As you can see, this is done by prefacing the name of the class with the word "class", and by capitalizing, or CamelCasing the name of the class. Typically in Ruby, we name variables in lower case, separating words with an underscore, like so: a_new_variable. But in the case of classes, we want their names to be CamelCase, so that they're easy to differentiate from other types of variables when we're skimming code.</p>

<h3>Various Variables</h3>
<p>Speaking of other variables, what other kinds of variables do we have here? I see some standard method names, and some <strong>local variables</strong>. Local variables are the variable names like "dryer". They're regular old lower case, with nothing special in front. They can only be seen by the method that contains them. So our "dryer" variable? Only #dry knows it's there. If I decide I need for another method to reference it later in this program, I might want to make it into an instance variable.</p>
<p><strong>Instance variables</strong> are the ones like @laundry_machine, with the "@" symbol in front of them. They can be seen by the whole class, but they only apply to one instance of the class. That is to say, their value changes depending on which laundry object they are contained within. They're kind of like attributes for the class object.</p>
<p>For example, going back to Steve's metaphor, let's say you actually have enough laundry that you need two laundry people. You have two objects performing the same, or similar functions. There's two laundry objects who have the same ways of doing things, but maybe they're doing different things. They both know how to get the laundry done the best way, but you have two to make the work more efficient. Maybe one is doing your dirty-clothes laundry, and the other is taking care of the sheets and towels and stuff.</p>
<p>In this instance, it's likely that the @quantity that each Laundry Person has to work with is different. The instance variable can still be seen by all the methods within the class, it's just handled differently by each object of the class, because the value is different for each object of the class.</p>
<p>But what if you only have one laundry machine? That particular variable would need to be accessed by all members of the class at some time or another. In that case, it becomes a <strong>class variable</strong>, and instead of one "@" symbol, you put two in front, like so: <code class = "inline">@@laundry_machine</code>. Class variables maintain the same value for every member of the class.</p>
<h3>Method Methodology</h3>
<p>Perhaps unsurprisingly, this differentiation can also be applied to methods. The method #laundry_people_assemble is what's called a class method, because it applies to the class itself, rather than any particular member of that class. On the other hand, #wash and #dry are instance methods, and apply to an individual instance of the class.</p>
<p>One last thing to talk about: the initialize method. This method can be found at the top of our class, largely because whenever we create a new object within this class, it internally calls upon this method to figure out what attributes it has by default. In this case, whatever quantity we give as an argument when we create a new object (ie. <code class = "inline">Laundry.new(10)</code>)
	<h3>So What?</h3>
	<p>So what's the point of all this? Being able to apply classes to different objects helps us to organize data and functions in ruby. Like our friend Steve said, it allows us to leave most of the knowing to the program, rather than having to know all of it ourselves. All of this organization also helps keep code DRY. Two simple methods of organization, objects, and classes, can give a language, and thus our programs, an immense amount of power through flexibility.</p>
