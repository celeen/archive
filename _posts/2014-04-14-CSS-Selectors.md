---
layout: post
title: CSS Selectors
image: ../images/lights.JPG
---

<h1>CSS Selectors</h1>

<h2>The Basics</h2>

<p>When working with CSS and HTML there are so many ways to organize your work, and if you haven't found out already, organization is a key part of working with CSS and HTML.</p>

<p>You remember that CSS stands for "Cascading Style Sheets", right? And you know that bits of css need HTML elements to be able to point to in order apply style, yeah?</p>

<p>So, you're pointing to various elements in your Cascading Style Sheet. Cascading, in theory, means a couple of different things:</p>

<p>1) The styles on the bottom will override the styles on the top</p>

<p>2) You can be general, or specific with how you point your styles to elements.</p>

<p>That's where selectors come in!</p>

<h2>There are Two Types of Selectors</h2>

<p>(that I know of)</p>


<h3>ID Selectors</h3>

<p>ID Selectors are denoted in HTML with the following syntax:</p>

 	<p><pre><code> &lt;element ID = "AWESOME"&gt; </code></pre></p>
 
 <p>In CSS you call upon an ID Selector to point to with the following syntax:</p>
 	
 	<p><pre><code>#AWESOME {
 
 	}</code></pre></p>
 
 
<p>ID Selectors are each unique. In terms of your HTML, this means that THERE CAN BE ONLY ONE id selector of each name. They are only effective if they are once. Not more. </p>

<p>However, in CSS, you can call upon each unique ID selector as many times as you wish.</p>

<p>ID Selectors hold great power. And, as we all know, with great power, comes great responsibility.</p>

<p>ID Selectors are like the name a starship carries. For, example, within one universe and time period, there is only one <strong>U.S.S. Enterprise D</strong>. Just like, in one HTML page, there can be only one <code class = "inline">&lt;element ID = "AWESOME"&gt;.</code></p>

<h3>Class Selectors</h3>

<p>Class selectors are denoted in HTML with the following syntax:</p>

	<pre><code>&lt;element class = "AWESOME"&gt;</code></pre>
	
<p>In CSS, you call upin a class selector to point to with the following syntax:</p>

	<pre><code>.AWESOME {
	
	}</code></pre>

<p>Class selectors are **not** unique. You can throw as many class selectors of one name into a page as you want to, AND you can call on <em>all of them</em> <strong>at the same time</strong>! Class selectors are flexible. And while it's not a dorky quote, with great flexibility comes great power.</p>

<p>Class Selectors are like the make of the starship. There is only one U.S.S. Enterprise D in our universe at one time, but there are probably a TON of <strong>Galaxy Class Starships</strong>!</p>

<h3>A More Accessible Metaphor</h3>

<p>So you're not into star trek? Or navy at all? That's fine, take a bite out of this metaphor:</p>

<p>If you, like my cousin and his fiance, are a **four dog family**, then you have many dogs. And a couple cats. And, like, a gerbil. He's always loved having the zoo at home. So, here's how you express **dogs** in your home in HTML:</p>

	<pre><code>&lt;div class = "dog"&gt; Pitbull &lt;&#47div&gt;
&lt;div class = "dog"&gt; Pitbull &lt;&#47div&gt;
&lt;div class = "dog"&gt; Mutt &lt;&#47div&gt;
&lt;div class = "dog"&gt; Mutt &lt;&#47div&gt;</code></pre>
	
<p>Here's how you express dogs in your home in CSS:</p>

	<pre><code>.dog {
	take: a bath;
}</code></pre>
	
<p>Now, say Pi was a good dog, and didn't play in the mud with the other three. Well, he doesn't need a bath. So you might express your HTML like so:</p>

	<pre><code>&lt;div ID = "Pi" class = "dog"&gt; Pitbull </div>
&lt;div ID = "Carmen" class = "dog"&gt; Pitbull &lt;&#47div&gt;
&lt;div ID = "Rory" class = "dog"&gt; Mutt &lt;&#47div&gt;
&lt;div ID = "Billy" class = "dog"&gt; Mutt&lt;&#47div&gt;</code></pre>
	
<p>And here's what your CSS might looks like:</p>

	
	<pre><code>#Pi {
	take: a walk;
}
	
.dog {
	take: a bath;
}</code></pre>
	
	
<p>Please note that the ID selector overrides the isntructions from the class selector, even though the class selector comes second. </p>

<p><strong>That's where the theory behind cascading fails us: it doesn't apply to ID Selectors.</strong></p>

<h2>What Now?</h2>

<p><a href="http://www.impressivewebs.com/difference-class-id-css/">This Guy</a> doesn't recommend using ID selectors often or at all. I have to say, I agree with him. With HTML5, and the advent of more specific element containers, they aren't needed quite as often. And if you use them less often, they are less likely to get all tangled up in you CSS, messing up the cascade. <strong>Leaving them out, or using them sparsely  makes your code easier to keep track of.</strong></p>

<p><a href= "http://www.smashingmagazine.com/2010/04/07/css-specificity-and-inheritance/">Here</a> is a fantastic resource regarding the nature of specificity (selectors, eg) and inheritance (the cascade, eg) if you want to dig deeper into it.</p>

<p>And, <a href = "http://www.smashingmagazine.com/2011/12/12/an-introduction-to-object-oriented-css-oocss-2/">here</a> is a really fantastic article that introduces the concept of "Oject Oriented CSS" for anyone who thinks of themselves either as more advanced, or who just really like object oriented code. I really love some of the strategies in this article. Do take a peek.</p>

<h2>That's all Folks!</h2>



