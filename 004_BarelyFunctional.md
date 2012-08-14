##Barely functional
So now that you know about variables, loops, and comparison symbols, let's move
on. Let's say that you have a piece of code that you want to run a few times,
but not in a loop. Wouldn't it be nice if you could take this piece of code out,
and put it in one place, then call it whenever you want?

Let's say that Steve is staying in a hotel that is 6 blocks away from Cat Pic
Lover's Con., and his doctor asked him to keep track of how much sun light he
gets in a day. He knows that it takes him 5 minutes to walk each block, but
sometimes he walks it at night time, so he can't count those.

```javascript
time_in_sun = 0
 
function walk_in_sun() {
    time_in_sun = time_in_sun + (6 * 5);
}
```

###I suppose that you're about to explain `function` and `()` now?
Would I leave you hanging? Of course I'll explain them. First up, the word
`function` is a keyword that tells the computer "I'm about to define a function".
Next, we tell the computer the name of the function, in this case `walk_in_sun`.
After that, we use the brackets to tell the computer if we want to hand anything
to the `function`. If we don't, then we just leave empty brackets. Finally is
the block of code that the computer has to run whenever you call the function.

###I ran the code, but `time_in_sun` is still 0. What gives?
A function isn't run immediately when it's written. The computer reads it and
puts it aside, saying "When I see `walk_in_sun()` again, I'll run this code".
Try running it after defining the function like this:

```javascript
walk_in_sun();
```

You will notice that we still have the brackets there. This is so that the
computer knows you are trying to call a function. Without the brackets, the
computer would think that you are trying to use a variable, and nothing would
happen.

###You said that the brackets are for handing things to the function?
Yes, I did. When you define a function, you can give it some variable names,
known as parameters. These names are used only within the function, and can't be
seen by the rest of the code. You can pass variables, numbers, or whatever you
want to a function, and the function will see them as the parameter names you
defined.

###That doesn't sound particularly useful. Can I see how they work?
Sure you can. Steve doesn't always walk directly back to the hotel. Sometimes
he'll walk for two blocks to a pet shop, where he can take some new cat
pictures. After that, he might walk another block to the theatre, where he'll
watch a production of Cats. When he comes out, it's night time, so the original
function won't be accurate (he would have walked three blocks in sunlight, not
six). Instead, we should change it so that Steve can say how many blocks he
walked in the sunlight.

```javascript
time_in_sun = 0;
 
function walk_in_sun(blocks) {
    time_in_sun = time_in_sun + (blocks * 5);
}
 
walk_in_sun(2);
walk_in_sun(1);
```

As you can see, 'blocks' is the parameter, and it can be used like a regular
variable inside the function. You can pass any value you like to it, and 'blocks'
will be set to that value before the function runs.

###Can I pass more than one thing to a function?

Yes, you can! You simply separate parameters with a comma like this:

```javascript
function difference(x, y) {
    if (x > y) {
        return x - y;
    } else {
        return y - x;
    }
}
 
difference(3, 10);
difference(20, 0);
difference(3201, 44024);
```

###Uhh... What does `return` mean?
Well parameters are the way to pass things to a function, and `return` is the
way that a function passes things back. As soon as the code gets to a `return`
statement, it passes whatever is after it back, and the function exits.

In the example above, if `x` is greater than `y`, the function would return the
value of `x - y`. If not, then it would return the value of `y - x`. 

###So how is that useful?
Steve's doctor rings Steve and says that he wants to know how much time he
spends walking outside at night, too. Steve still takes 5 minutes per block at
night time, so it doesn't make sense to have two functions to do the same thing
when one will do fine.

```javascript
time_in_sun = 0;
time_at_night = 0;
 
function walk (blocks) {
    return blocks * 5;
}
 
time_in_sun = time_in_sun + walk(2);
time_in_sun = time_in_sun + walk(1);
time_at_night = time_at_night + walk(3);
```

This is a better solution because the function is more useful, and also
self-contained. It doesn't rely on any variables outside of the function, which
means that it's useful for day time and night time walks.

###I could do that without a function. Why is this better?
Sure, you could write the code like this:

```javascript
time_in_sun = 0;
time_at_night = 0;
 
time_in_sun = time_in_sun + (2 * 5);
time_in_sun = time_in_sun + (1 * 5);
time_at_night = time_at_night + (3 * 5);
```

Consider what would happen if Steve hurt his foot, and walked slower. Say he now
takes 8 minutes to walk a block. With the function, you only have to change the
code in one place, but without you would have to change it in every place. It's
also not particularly clear what is happening in the second example, but the
function can be given a name that makes the code clearer.

##Time to recap
Well that was a short chapter! Don't be fooled, though, functions are a big part
of programming. If you haven't been doing the Extra Credit up until now, I
suggest you go back and do them, then do the Extra Credit here, too.

So let's quickly go over what we've learned in this chapter.

* A function is a block of code that you can call at any time through the rest of your code.
* You can pass values to a function as parameters.
* Parameters are variables that only exist within the function.
* You can use return to get a value out of the function.
* Once return is called, the function exits.

###How do I practice this?
Write a function that takes any number and adds 42.

Write a function that takes two numbers and returns the smallest one.

###Extra Credit
Consider the following code:

```javascript
function average(total, number) {
    return total / number;
}
 
function percent(total, amount) {
    return (amount / total) * 100;
}
 
melons = 40;
truck_capacity = 50;
hours = 8;
 
percent_full = percent(truck_capacity, melons);
melons_per_hour = average(melons, hours);
```

Figure out what percentage of the truck was filled every hour.