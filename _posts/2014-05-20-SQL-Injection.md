---
image: /images/sql_injection.jpg
title: SQL Injection
imgpos: 50% 50%
---


###SQL Injection and How to Stop It
Most modern websites interact with the user in some way or another, most of the time through a login and password at first, and often in more complex ways after that. Think about something as creating a twitter account: you choose a username, and a password, put a photo up, tell them your email, and perhaps give a blurb about yourself. Twitter then communicates with its database. Your username choice is checked- is that combination of characters already assigned? If not, the website passes the other answers you provided through to the satabase, and saves them there, eventually by using some form of SQL to communicate with the database.

<h4>SQL Injection</h4>
<p>SQL injection is a technique used by hackers to gain access to a database. You can guess how it works: if the user inputs the right SQL statement, the webapp then communicates that statement back to the database, and if there aren't some checks between the input and the database, the user gains direct access and can do some real damage.</p>

<p>For example:</p>
<pre><code>
users.first("login = '#{:username_input}' AND 
password = '#{:password_input}'")

</code></pre>
<p>In <a href = "http://guides.rubyonrails.org/security.html#sql-injection">this example</a>, we are finding the first match in the database for what's in the method argument. Inside the method argument, we have a string made up of part of an SQL prompt. It will find the first entry that matches both the user input for password AND username.</p>

<p>If the user were to input something like this:</p>

<pre><code>
SELECT * FROM users WHERE login = '' OR '1'='1' AND 
password = '' OR '2'>'1' LIMIT 1

</code></pre>

<p>An unprotected (or unsanitized) structure would pass that input on to the database. Since '1' = '1' evaluates to true, AND '2'>'1' evaluates to true, the query would return the first entry of the database (LIMIT 1), granting the user access.</p>
<p>Incidentally, I pretty much pulled this example directly from <a href = "http://guides.rubyonrails.org/security.html#sql-injection">the ruby on rails security guide</a>, which makes sure to tell us that SQL injection isn't as big a problem with ruby on rails as it is with some other languages, because of some well defined methods internally that just don't allow direct access from user input to database. But how do you protect against the instances in which SQL injection <strong>is</strong> a danger?</p>

<h4>How to Stop it</h4>

<p><a href = "http://guides.rubyonrails.org/security.html#sql-injection">That same guide</a> has some countermeasures detailed.</p>
<p>First of all, ruby on rails has a built-in filter for special SQL characters, to prevent them from getting through and messing everything up. But in some methods- where("..."), thing.execute(), thing.find_by_sql()- the filter has to be applied manually, so it's not entirely reliable.</p>

<p>One thing you can do, instead of just passing a string directly through, is pass an array or a hash will prevent strings of SQL statements being passed directly through from the user without some kind of alteration or intervention by the program. USing arrays and hashes for this is only available in model instances.</p>

<p>I'll be the first to admit that I don't know what that means yet, but the idea, I take it, is that it's good to know the limitations and context of the webapps you're creating when they become public through the web, and what the particular security weaknesses are for your contexts and languages, so you can protect against them.</p>
<p>Protecting against SQL injection, ultimately involves putting at least one layer of checks between user input and the database. In some cases (passwords) that means encryption, in some all you really need is to play around with the data type and put in some parameters so that you know you have the right kind of input.</p>

	<p id = "footer">S. Celeen Rusk<br/>
		4/20/2014</p>

    