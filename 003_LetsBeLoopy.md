##Let's be loopy
Had a good rest? Brain all refreshed? Did you actually answer the questions? Did
you even look at the extra credit? Ready to continue? Good.

Let's have a think about what we know how to do. We know how to do some basic
maths, we know how to use names (or variables), and we know how to make
decisions in code with `if` statements. We've come a long way in only a few
pages.

Now `if` statements are neat, but what if you have to do things over and over
again? Let's say you have to write a program for selling hot dogs at the Cat Pic
Lover's Convention. You can only sell as many hot dogs as you have ready, and
any others have to go into the hot dog order queue.

```javascript
if (hotdogs_ready > 0) {
    hotdogs_ready = hotdogs_ready - 1;
} else {
    hotdogs_ordered = hotdogs_ordered + 1;
}
```

The problem is that sometimes someone will order three or four hot dogs at a
time, and you only have one or two ready; sometimes none!

```javascript
if (hotdogs_ready > 0) {
    hotdogs_ready = hotdogs_ready - 1;
} else {
    hotdogs_ordered = hotdogs_ordered + 1;
}
 
if (hotdogs_ready > 0) {
    hotdogs_ready = hotdogs_ready - 1;
} else {
    hotdogs_ordered = hotdogs_ordered + 1;
}
 
if (hotdogs_ready > 0) {
    hotdogs_ready = hotdogs_ready - 1;
} else {
    hotdogs_ordered = hotdogs_ordered + 1;
}
```

Then a tour bus comes in, and everyone is hungry! There's 50 starving people
there, and you're trying to type all of this in between orders. If only there
was a way to run this code as many times as you need without having to count how
many times you've typed it in.

```javascript
customers = 50;
 
while (customers > 0) {
    if (hotdogs_ready > 0) {
        hotdogs_ready = hotdogs_ready - 1;
    } else {
        hotdogs_ordered = hotdogs_ordered + 1;
    }
    
    customers = customers - 1;
}
```

###Hold up! While? I just got used to if! How does this work?
Much like an `if`, a `while` tells the computer to do everything in a code
block. Unlike an `if`, the computer will keep doing everything in the code block
over and over again, until the condition (the part in the brackets) isn't true
any more. 

Think of it like an `if` that keeps looping over and over again. The main
difference, though, is that there is no `else` for a loop - if the condition
isn't true, the computer simply skips past the code block, and keeps running the
rest of the program.

To make it easier to understand, here is the same code with parts of it in plain
English.

```
there are 50 customers;
 
while (there are more than 0 customers) {
    if (there are more than 0 hot dogs ready) {
        take one hot dog that is ready;
    } otherwise {
        add one hot dog to the orders;
    }
    
    take one customer from the number of customers;
}
```

###Hey I just noticed! You can put code blocks inside code blocks!
Why, yes you can! You could have a loop inside a loop, or an if inside an if, or
all sorts of crazy things. Mostly programming is about putting all these parts
together in a way that does what you want it to. Remember that there's rarely a
'right' way to do anything, but some problems have a 'best' solution. Usually it
doesn't matter which way you do something, so long as it works.

###Cool! What's next? That while loop was a cinch!
Hold your horses there. There's a couple more things that I need to point out
about `while` loops. On line 10, we take one off `customers`. When we get to the
end of the code block, the computer loops back to the start, and tests the
condition (`customers > 0` or "are there more than 0 customers") again. What
would happen if we forgot to take one off the `customers` variable each time?

###Well... `customers` would never reach zero.
Exactly, and if `customers` never reached zero, then the `while` loop would
never exit. It would become an infinite loop, which is a common mistake that new
programmers accidentally make. I've done it myself more times than I can count,
and it still happens to me sometimes. It's nothing to be ashamed of, but it is
something to be wary of. When it happens, the computer often won't tell you
until it runs out of memory, and crashes.

###Is there any way to make sure that this never happens?
Well there is another type of loop. It's very similar to a `while` loop, but it
doesn't look as nice. In fact it looks a little scary the first time you see it.
Well your first look is now; let's re-write the program with a `for` loop.

```javascript
for (customers = 50; customers > 0; customers = customers - 1) {
    if (hotdogs_ready > 0) {
        hotdogs_ready = hotdogs_ready - 1;
    } else {
        hotdogs_ordered = hotdogs_ordered + 1;
    }
}
```

###What? There's semi-colons in the condition! You're setting customers to 50 in the condition, so it will never reach 0! It's all so confusing!
Settle down, the world hasn't ended. This is how a `for` loop works - it has
three parts in the condition statement. 

First, you tell it a starting point (`customers = 50`); this code is run once
only before part  two is checked for the first time.

Second, you tell it a condition to test for (`customers > 0`); this is like the
condition in the while loop - it is checked every time before the code in the
loop is run, and the code in the loop runs only if the condition is true. 

Finally, you tell it what to do at the end of each loop (`customers = customers - 1`);
this is run every time after the code in the loop finishes, but before the
condition is checked again. This lets you set things up easily for the next loop.

In reality we've done nothing different than we did with the `while` loop, only
now the computer will tell you when you've missed one of the parts, rather than
try to run forever.

###I want to stop again, this is hard
Don't give up just yet. Let's simplify it down a a little more. Pretend for a
moment that this was how your code looked.

```
A;
for ( B ; C ; D ) {
    E;
}
F;
```

Let's suppose that the computer ran into this `for` loop, and the loop ran three
times. The things that the computer would run would look like this:

```
A;
B;
  C? Yes;
    D;
   E;
  C? Yes;
    D;
   E;
  C? Yes;
    D;
   E;
  C? No;
F;
```

###OK, so this is pretty much exactly what we did with the `while`, then?
Yes! The `for` loop simply sets a starting point as well as a finishing point,
and also describes how to get from one to the other. All of this is possible
with a `while` loop, but in a `for` loop everything is written in one place.

###So why are there two types of loop?
Because sometimes a `while` loop is all you need; it's simple, to the point, and
maybe you don't have to set anything up before the loop. Other times you know
exactly where you want to start, where you want to end up, and what you need to
do to get there. A `for` loop makes this easier. Remember what I said about
there not being a 'right' way to write code? This is one of those times where
you just have to pick whatever you think is best for the situation.

###Is there anything else I need to know about loops?
Yes, one last thing. There is a special command which can help you out when
you're looping through lots of things:

* **break** - Stops the loop. Even in the middle of the code block, this will
immediately break out of the loop, and the program will behave like the loop
finished.

###Can I see this in action then?
Why, sure you can. Let's go back to the hot dog example. Suppose that there's a
limit to the number of hot dogs available in one day, so once you reach that
limit, everyone else goes hungry. It's not worth going through the loop for
everyone else if we run out of hot dogs, so we break out.

```javascript
hotdogs_total = 35;

for (customers = 50; customers > 0; customers = customers - 1) {
    if (hotdogs_total == 0) {
        break;
    }
        
    if (hotdogs_ready > 0) {
        hotdogs_ready = hotdogs_ready - 1;
    } else {
        hotdogs_ordered = hotdogs_ordered + 1;
    }
    
    hotdogs_total = hotdogs_total - 1;
}
```

###You did it again... you threw in stuff I don't understand! What is `==`?
If there is only one equals sign `=` (e.g. `Jeff = 5;`), then you are telling
the computer to set a variable to a particular value. Read it as a statement
like "Jeff is now 5", or "`hotdogs_ready` is now `hotdogs_ready - 1`".

The left side always has to be a variable, otherwise the computer will stop
running your program (and won't even be polite about it). The right side can be
anything with a value (like a number, another variable, some maths, etc.)

###OK, and the `==` that I asked you about?
If there are two equals signs `==` (e.g. `Jeff == 5`), the computer uses that to
compare both sides. Think of if like a question that the computer is asking
itself. "Is Jeff equal to 5?" or "is `hotdogs_total` equal to `0`?".

We have actually already met other comparison symbols, such as "Greater than"
(`>`),  and "Greater than or equal to" (`>=`). When they are in an `if`
statement, or a loop, you a telling the computer to ask itself the question, and
run the code only if the answer is 'yes'.

The most common comparison symbols are:

* `==` **Equal to**: `Jeff == 5` (Is Jeff equal to 5?)
* `<` **Less than**: `Jeff < 5` (Is Jeff less than 5?)
* `>` **Greater than**: `Jeff > 5` (Is Jeff greater than 5?)
* `<=` **Less than or equal to**: `Jeff <= 5` (Is Jeff less than or equal to 5?)
* `>=` **Greater than or equal to**: `Jeff >= 5` (Is Jeff greater than or equal to 5?)
* `!=` **Not equal to**: `Jeff != 5` (Is Jeff not equal to 5?)

###Please! No more new information! I need time to understand all of this!
Don't worry. All there is left to do is revision.

First off, let's look over everything we've learned, and then I'll give you some
things to practice with. After that, you can go, take a break, grab a drink,
have a shower, kick a ball, call your mother, feed your pet, whatever it is you
need to do. 

##Time to recap

* You can use a `while` statement to make code run several times.
* If the condition in a `while` statement is never false, then it will keep
looping until it crashes.
* A `for` statement is like a `while` statement, but it's harder to get caught
in an infinite loop.
* You can exit a loop at any time by using the break command.
* `=` sets a variable's value, and `==` compares values.
* Other symbols that compare values are `<`, `>`, `<=`, `>=`, and `!=`.

###How do I practice this?

* Try to write a program that uses a `while` loop to add up the numbers from 1 to 10.
* Try to write it again with a `for` loop.
* Try to write a program that uses a loop to take the numbers  from 1 to 10 from 100.
* Try to write a program that uses a loop to add up all the numbers from 1 to 50,
but stops if the total gets over 100.

###Extra Credit
Here is a program designed to redistribute Perry's wealth. Perry is generous,
but he doesn't want Steve to be richer than him. The program runs for a long
time, but Steve never gets any richer, and Perry never gets any poorer. Fix the
program.

```javascript
Steve = 2;
Perry = 70;
 
while (Steve < Perry) {
    Steve == Steve + 1;
    Perry == Perry - 1;
}
```

Perry remembers that he has a hot date tonight, and needs at least $50 to
impress her. Add a break to the program so that it stops when Perry has $50.

What is the value of total after this program runs? Why?

```javascript
total = 0;

for (count = 0; count > 10; count = count + 1) {
    total = total + count;
}
```

Even though infinite loops are harder to make with `for` loops, they are still
possible. Which one(s) of these would cause an infinite loop, and which one(s)
would never run their code? Why?

```javascript
1. for (count = 10; count > 0; count = count + 1)
2. for (count = 10; count < 0; count = count + 1)
3. for (count = 0; count < 10; count = count + 1)
4. for (count = 0; count > 10; count = count - 1)
5. for (count = 0; count < 10; count = count - 1)
```