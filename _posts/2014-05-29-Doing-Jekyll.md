---
layout: post
title: Doing Jekyll
image: ../images/jekyll.jpg
imgpos: 50% 38%
---
##Migrating to Jekyll

Doing so took a lot longer than I thought it would. It took me a minute to wrap my head around all the different pieces of what was going on, but now that I'm up to speed, I LOVE it!

Almost every time I wrote a blogpost over the past two months, I thought to myself, "I wish I could jsut do this in markdown..." and many times, I did anyway, just add p tags and changing the syntax as I inserted the post into my HTML document.

What time I've saved!

###Surprise!

I thought I'd already updated my blog to make it look professional when I fixed some of the styling, and added those cool hover shados on the blog navigation page. (BTW, I did those entirely with CSS, no JavaScript. I think it's super cool, and I learned a bunch.)

Then, at the last minute, after seeing how excited [Ron Ishak](http://www.ronaldishak.com) was about migrating... I decided to give it a try.

###HillClimbs

I ran into trouble when trying to figure out how to maintain the css background images I have on my current layout. I spent a lot of time trying to think up a new theme, and I tihnk I've got on in mind... However, I wanted to get *something* up and running, so here I am. Please stay tuned for an awesome new theme that is a bit more complex code-design-wise, but hopefully more simple visually. Also it will take less time to load...

On that note, I played around with [data URI's](http://css-tricks.com/data-uris/) for these images, and soon discovered that every single image I am using is too big to be converted to a data URI (and it looks pretty nasty when I try to make it small enough to be converted). So, there's that. 

A layout that's less image-heavy would definitely be better for load time. Although, practically speaking, while I'm hoping to have to deal with issues of scale for this blog later on, it's certainly not an issue now. Regardless, it's definitely more professional even at this scale to avoid images that fill in from top to botoom because they're so big, or there are so many of them. And mine has BOTH of those! As much as I like the concept of this layout, and am proud of myself for thinking of it and building it, it's time to move on, and explore more challenging CSS.

On another note, it took me a bit to get used to thinking of snippets of html code in object-oriented terms. It's super cool.

###Things Learned

Details matter. They always matter with code, but the kinds of details that matter are different with jekyll, and I have gathered so far that they matter more. For example: in the yaml front matter of this post, I have specified a variable for the background image. I call it "image". IT's kept in its own image folder, with all the other images. The pathname that the variable "image" points to is "/images/jekyll.jpg". There **has** to be a forward slash in front of the file name, or jekyll won't find it.

For a minute when I was rearranging everything, my formatting was all messed up, I thought it was the CSS file, and it ended up kind of being true... My css applies style to the "article" object in the DOM. I had taken the "article" object out and just put the body of the post into the shell HTML. 

##TADA

All things said, I'm really pleased. Setting jekyll up took me longer than I expected, but in the grand scheme of things, not very long. I love its flexibility. It is going to make a layout redesign super easy! After that, I look forward to migrating all of this over to a domain I own [where I was playing around with a ghost blog for a minute](http://celeen.info).

Does anyone have any opinions on Ghost vs Jekyll? I suppose it largely depends on whether you're mode comfortable with javascript (Ghost is built on node.js) or ruby.