
# Ways of sizing CSS Fonts

Now, currently, our font size is set to be 90 pixels.
So on certain browsers, if the user goes into preferences and they change their default font size for
their web page, for example, if they need super large text in order to see, then you'll notice that
font size does not change, even though the rest of the text does.
And this is because this is not a dynamic size, so in order to make it dynamic, there's two options.
So let's head back over here and go back to the medium size.
And if we go into Atom, then instead of using pixels instead, we can use something like a percentage.
So 100% in terms of font size is actually a 16-pixel size. 100% = 16px, 90px = (9,000/16) 562.5%
And so that means if we want 90 pixels, so that means 90 divided by 16, and that would be equal to
562.5.
Then we would need 562.5% in order to get the equivalent of 90 pixels.
So if we hit save and we go back to our website and I hit refresh, you'll notice that absolutely nothing
happens because we're specifying exactly the same font size, but instead we're using a percentage this
time.
So that means that if we're going to say preferences and we change our font size to very small or very
large, then that font size will scale with it. 
Now, the other way of specifying a dynamic font size is by using a unit called the em.
Now we've seen em before inside our HTML and we used it as a tag in order to emphasize a particular
section of text, and that stylistically means that you'll make something italicized.
Now, in this case, this is actually a completely different em, and the em in this case is actually
the phonetic pronunciation of the letter M.
And the reason is because in typesetting in the olden days that em or the M rather is the width of
the capital letter M.
And so that means that when you say 1em, then you want the font size to be one times the width of
the capital letter M.
And if you want 2, then that's double the size of the M, et cetera, et cetera.Now, in modern days, this is no longer true.
But what is true is that (1em = 16px = 100% ), as we've seen with our percentages.
So (16px = 100%) when you're talking about fonts and it's equal to 1m or 1em.
And that means that you can achieve whatever size you want dynamically using either of these methods.
So for example, as we calculated before, 90 pixels is equal to 5.625em (90px=5.625em, 90/16).
And sothat means that if we replace our font size with that number and we hit save and we go back to our site and we hit refresh, then you'll see again, the font size does not change because they are all the same.
It's just using different ways of specifying the same size.
So then the question you might have is why would you use one over the other?
What does it matter?
And if you look on different websites, for example, take uber.com and you know, if we inspect
on their title here, then you'll notice that their font size is specified in pixels, whereas on TechCrunc it's specified in ems, and on other sites you might get percentages.
Now, as we mentioned before, if we change the font size, for example, say somebody with accessibility
issues to very large, then these static sized fonts do not change because it stays exactly the same
size.
Whereas the things that are dynamically sized, for example, things using em or percentages, they do scale up so that users who have maybe visual impairments, et cetera, who might want to have a higher
font setting will be able to view the website more comfortably.
And that's quite important in terms of making your website accessible to everybody.
Now, the argument against that is some web designers say that people with visual impairment these days
are more likely to zoom in rather than changing their default font size, and they're more likely to
have a higher zoom in order to read all the text on page.
And with zoom, it doesn't actually matter whether if your text is statically or dynamically sized because it will just scale up the website depending on what you're asking it to do.
So maybe that's not such an important distinction between statically and dynamically sized fonts any
more.
But there is one thing that is really important, and that's the fact that when you're using em
or when you're using percentages, that value is inherited.
So if I go into the body here and I specify a font size for everything inside the body, so that's everything on my website to be say 2em,
and then in my H1, I leave my font size as the previous dynamic size. I hit Save, and let's head back to our website and we refresh, then you'll notice that our H1 has now become absolutely gigantic.
And that's because the font size gets inherited and added on top of whatever it got from its parent.
So the parent of the H1 is the body here because it's contained inside the body. And in the body
we said that font size should be 2em across the entire body of the website.
Now, when it gets to the h1, it's already got that 2em applied.
And then it adds that 5.625 on top of the 2em which is why we end up with something so gigantic.
And this is exactly the same with percentages.
So if I said, say, 200% in our font size and I change this to 562.5%,
then again, we still get this gigantic font size. But say, if I said, you know, the font size should
be 20 pixels and over here, it should be 90 pixels and we go over here, we head back, and we refresh, then you see that that font size is staying as 90 pixels.
It does not matter what its parent's font size was because these are static sizes. So that means it
can get a little bit dangerous. For example, if you wanted all the text inside your body to be 200%, which remember is 2 times 16 pixels, which is 32 pixels, now that works fine until you get to a point and you forgot that you did that and over here, you ended up setting your 5.625%
and then all of a sudden, Oh, what? What's going on? Why does it look like this?
And you have to go and debug and try and figure out, where did it get this font size from?
So, for example, we can inspect in our Chrome developer tools and you see, OK, so it's got font
size 5.625, that's what I want.
But do I have any font sizes anywhere else and here in the body, even though it's crossed out, that
200% is still being applied?
So in order to avoid this, one of the things that we got in the latest version of CSS, which is the
version that we're using currently or the version I'm teaching you about, is CSS 3 and inside CSS 3
there is something called the (rem) and that refers to the root em. So that means ignore all of the parent settings for the font size and just set it to this relative to the root.
So that means that it doesn't matter what we've done here or in its enclosing containers or parents.
It will be 5.625 times 16 pixels as long as we add the 'r' in front of the em.
So if we hit save and we head back over to our website hit refresh, then you can see that we still
get that size that we wanted, which is the 5.625rem.
So the beauty of the root em is that it does not get affected by upstream size changes, and it means
that it's easier to debug and it's less likely that something will go wrong.
So when sizing text, my personal recommendation to you is to use rem instead of em or percentages
or pixels, because that is the most adaptable and also the most reliable and least error-prone.
So now if we head back over to our site and refresh and also change our font size in our preferences
back to the medium that's recommended, then you can see that we've got the exact size that we were looking for, which is the same as the 90 pixels that we specified but this is done using rem rather than em or percentages.


