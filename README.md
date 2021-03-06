# Gilded Rose Refactoring Challenge

## Makers Academy week 10 tech test #2

This kata was originally created by Terry Hughes.  The goal is to refactor the nested `if` statement, and then implement the functionality to deal with the "Conjured" item type (see Requirements below).

## Approach

My first step was to write a "Golden Master" test suite.  This involved determining every input type the program currently accepted, and writing test cases for every possible resulting output.  I wrote tests for Conjured items as well, but pended these until I was finished with refactoring.

Once the test suite was ready, I tackled the input types and solved one `describe` block at a time.  I wrote separate methods to override each input as I went along, while keeping the nested if statement in place, then deleted this once I was satisfied I had covered every possibility, and made sure the test suite still passed.

Once I had a collection of small methods, I extracted these to small objects (subclasses of the Item class, each with their own updateQuality method).

After these refactoring steps I was ready to implement conjured - because of the structure of the other item classes I had created, implementing conjured was incredibly easy :)

## Requirements

Hi and welcome to team Gilded Rose. As you know, we are a small inn with a prime location in a
prominent city ran by a friendly innkeeper named Allison. We also buy and sell only the finest goods.
Unfortunately, our goods are constantly degrading in quality as they approach their sell by date. We
have a system in place that updates our inventory for us. It was developed by a no-nonsense type named
Leeroy, who has moved on to new adventures. Your task is to add the new feature to our system so that
we can begin selling a new category of items. First an introduction to our system:

	- All items have a SellIn value which denotes the number of days we have to sell the item
	- All items have a Quality value which denotes how valuable the item is
	- At the end of each day our system lowers both values for every item

Pretty simple, right? Well this is where it gets interesting:

	- Once the sell by date has passed, Quality degrades twice as fast
	- The Quality of an item is never negative
	- "Aged Brie" actually increases in Quality the older it gets
	- The Quality of an item is never more than 50
	- "Sulfuras", being a legendary item, never has to be sold or decreases in Quality
	- "Backstage passes", like aged brie, increases in Quality as its SellIn value approaches;
	Quality increases by 2 when there are 10 days or less and by 3 when there are 5 days or less but
	Quality drops to 0 after the concert

We have recently signed a supplier of conjured items. This requires an update to our system:

	- "Conjured" items degrade in Quality twice as fast as normal items

Feel free to make any changes to the UpdateQuality method and add any new code as long as everything
still works correctly. However, do not alter the Item class or Items property as those belong to the
goblin in the corner who will insta-rage and one-shot you as he doesn't believe in shared code
ownership (you can make the UpdateQuality method and Items property static if you like, we'll cover
for you).

Just for clarification, an item can never have its Quality increase above 50, however "Sulfuras" is a
legendary item and as such its Quality is 80 and it never alters.
