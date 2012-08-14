##Baby's First Steps
Normally, the first thing you would learn to do here is write a “hello world”
program. This is stupid and boring, so we're not going to do it. Instead, we're
going to do something else that's stupid and boring. Maths!

Computers are pretty much big calculators with pretty pictures. Whoever knew
that calculators could be used for so much stuff other than writing "`80085`",
or cheating your way through remembering the times tables?

Well, they can. But you're familiar with those things, so let's start with the
times tables one.

```javascript
2 * 8;
```

###Wait, what's with the '`*`'?
It's the "multiply" symbol. It's like 'x' when you're writing it down with pen
and paper. It's used because 'x' turns up in words a fair bit (at least more
often than you would expect), and it would get confusing.

###And what about that semi-colon?
I'll level with you. Computers are stupid. The semi-colons tell the computer
where an instruction finishes. Think of it like saying "and then" to the
computer, because the next thing will usually be a new instruction. If there's
no new instruction, then that's the end of the program.

###OK then. So that multiplied 2 by 8. That's boring!
Yes, it is! But it's still a program! Congratulations, you just wrote a program!

###But I could have done that with my calculator without reading all this.
Yes, you could. You could have also done it in your head, I'm sure. Let's get a
little more complex then. What would happen if you wanted to multiply 2 by 8,
and then by 6, and then by 20? Then add 3? Well you could write this:

```javascript
2 * 8 * 6 * 20 + 3;
```

What if I told you a few more things to do there? It would start to be a very
long line. What if we could pick a name, and then do all that stuff to the name?
Well, we can! Programming is all about names. Let's use the name "Larry".

```javascript
Larry = 2;
Larry = Larry * 8;
Larry = Larry * 6;
Larry = Larry * 20;
Larry = Larry + 3;
```

###That's not easier!
OK that's fair a point, but what if we had two names, and different things
happened to them before they met? Larry and Steve. They are collectors of cat
pictures. Larry has 2035 cat pictures, and Steve has 3942 cat pictures.

```javascript
Larry = 2035;
Steve = 3942;
```

Larry buys a "Best of Cat Pictures"  CD with about 1000 pictures, while Steve
loses a CD with 548 cat pictures.

```javascript
Larry = Larry + 1000;
Steve = Steve - 548;
```

Larry finds "catmatch.com" and uploads his collection. After a week it emails
him to say that his collection has tripled! Someone breaks into Steve's house
and steals a laptop with 1082 cat pictures on it.

```javascript
Larry = Larry * 3;
Steve = Steve - 1082;
```

Larry and Steve meet at "Cat Pic Lover's Con", and trade pictures. Steve gives
Larry a copy of everything that he has left, and Larry gives Steve his top 100.

```javascript
Larry = Larry + Steve;
Steve = Steve + 100;
```

Later that day, Steve's bad luck continues and he loses everything Larry gave
him.

```javascript
Steve = Steve - 100;
```

So, Mr. Smarty Pants, How many cat pictures do they both have?

###Fine. I'll play it your way. Names make some things easier.
Glad to see that you came around. Programming isn't just putting numbers into
names, though. Let's move on so that you can see what else we can do.