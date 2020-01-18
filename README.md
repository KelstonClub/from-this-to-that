# from-this-to-that
An implementation of the game "From This to That"

## Rules

The rules are very simple: given two words of equal length (for example
"this" and "that") you have to find a way to go from one to the other
by :(a) changing one letter in each move; and (b) always resulting in a
real intermediate word.

So, to go from "this" to "that" you might do:

THIS
THIN
THAN
THAT

### Valid Words

There is a file -- `words.txt` -- which contains a lot of words of many
lengths. All the words are uppercase. None of them contains dashes or
apostrophes. The words are in no particular order.

## The Challenge

Your challenge is to accept two words from the user and then to find a
route -- if one exists -- from one to the other using the rules above:
one letter changes each time; each change results in a valid word

## Possible approach

(This assumes that you're able to accept the two words from the user)

### Step 1: Get all the words of the same length from words.txt

### Step 2: Starting from one word, make a change which results in another words

You've got two possible approaches here:

a) Try each position in the word; try each letter in the alphabet; see if the result makes a word

b) Try every other word of the same length and see if any differs from this word by only one letter

### Step 3: Find a path using one-letter changes

Here you use the fact that you can go from Word A -> Word B with one change;
you then apply the same thing, but going from Word B -> Word C; and so on.
If at any point you end up with Word Z (ie the Word you're aiming for) then
you've found a way.

## Hints

* To find the length of a word use `len`
* To read all the words from a file you've opened use `read().split()`
* To find all the words of a certain length, loop over the list of all the
  words and create a new list where the length is correct
* You can't change a letter in a string. But you can use `list` to convert
  the string to a list and change letters in the list
* If you want to compare two things of equal length you can use
  `zip` to match each thing against the other. (Think of a real zip).
  NB `zip` itself gives you an opaque object which you have to iterate over.
  You can use `list(zip(...))` to see the matching pairs.

