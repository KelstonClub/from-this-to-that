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
