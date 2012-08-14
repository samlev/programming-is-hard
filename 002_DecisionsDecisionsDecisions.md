##Decisions, decisions, decisions
Now that we know about naming things, and how to do some basic maths, let's ramp
it up. Remember "Cat Pic Lover's Con"? Well the organisers of the convention
were paid by Big Cat Pictures inc. to do some research. They wanted to know how
many people had over 5000 cat pictures, and how many people had less than 5000.
They have a big list with the ticket number for each attendee, along with how
many cat pictures they have. Over 10000 people came, so it would take a lot of
time to go through this list and figure these things out. After hours of looking
at numbers, it would be hard to be right every time. If only there was an easier
way...

```javascript
if (pictures >= 5000) {
    over = over + 1;
} else {
    under = under + 1;
}
```

###WOAH! That doesn't make sense! What are all those funny symbols?
I suppose we had to come to this at some point. This is where I give you some
new words to remember, and your eyes glaze over. I'll try to make it as painless
as possible.

* **Variables** - We actually already met these. Variables are a type of name
that holds on to a value, which can be changed (or varied). Larry and Steve were
variables, because they held on to numbers that could be changed.
* **Code Blocks** - See those curly braces there? They are known as code blocks.
They are a way of grouping a bunch of commands together.

###So what does it mean?

Let's replace some things with English.

```
If (the person has 5000 or more pictures) {
    Add 1 to the number of people with over 5000 pictures;
} otherwise {
    Add 1 to the number of people with under 5000 pictures;
}
```

###OK, that makes sense, I guess.
Good. Now let's push it a little further. Big Cat Pictures inc. wants not only
the numbers of people over and below 5000 pictures, but wants to count the total
number of pictures in each group (so they can get an average). They also want to
do the same for "VIPs" who have over 10000 cat pictures.

```javascript
if (pictures >= 10000) {
    vips = vips + 1;
    vip_total = vip_total + pictures;
}

if (pictures >= 5000) {
    over = over + 1;
    over_total = over_total + pictures;
} else {
    under = under + 1;
    under_total = under_total + pictures;
}
```

Now we have two commands in each code block, it's easier to see how they group
commands together. You can also see that the first `if` doesn't have an `else`
option; if the condition (`pictures >= 10000`) isn't true, the computer simply
skips past that code block, and moves on.

##Time to recap
So let's go over what we've learned so far, and then you can give your brain a rest.

* Computers are basically complicated, novelty sized calculators.
* Programming is writing down what you want a computer to do, in a way that it
can understand.
* Semi-colons tell the computer when a command or instruction ends.
* You can use names (variables) to keep track of things that might change.
* You can use `if` statements to tell the computer to do different things in
different situations.
* You can use curly braces to group a bunch of commands together.

###How do I practice this?
Look at this code, and figure out what will happen.


```javascript
Joe = 300;
Peter = 400;

if (Peter > Joe) {
    Peter = Peter + Joe;
    Joe = 0;
} else {
    Joe = Joe + Peter;
    Peter = 0;
}
```

Answer the following questions:
* What would happen if Joe was a bigger number than Peter?
* What would happen if Joe was the same number as Peter?
Test the code to see if you were right.

###Extra Credit
Figure out what the following code does.

```javascript
Joe = 400;
Peter = 400;

if (Peter > Joe) {
    Peter = Peter + (Joe / 2);
    Joe = Joe / 2;
} else if (Joe > Peter) {
    Joe = Joe + (Peter / 2);
    Peter = Peter / 2;
} else {
    Steve = (Joe + Peter) / 2;
    Joe = Joe / 2;
    Peter = Peter / 2;
}
```

Then answer the following questions (don't be afraid to google for any answers -
researching for yourself is better than being told):
* What would happen if Peter was a bigger number than Joe?
* What would happen if Joe was a bigger number than Peter?
* What does `/` do to numbers?
* Why is that symbol used?
* How is `else if` different to `else`?