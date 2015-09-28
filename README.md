# Puzzles
A repository for collecting all interesting puzzles found in interviews and internet

## Hard Interview Puzzles([Source](http://everything2.com/))
1. There is a village of wizards and a village of dwarves. Once a year, the wizards go over to the village of dwarves and line all the dwarves up in increasing height order, such that each dwarf can only see the dwarves smaller than himself. The wizards have an infinite supply of white and black hats. They place either a white or black hat on the head of each dwarf. Then, starting with the tallest dwarf (in the back of the line), they ask each what color hat he is wearing. If the dwarf answers incorrectly, the wizards kill him (the other dwarves can hear his answer, but can't tell if he was killed or not). What strategy can the dwarves use to minimize the number of dwarves that are killed? What is the most number of dwarves that will be killed using this optimal strategy?

Solution:
The dwarves have a strategy that will cost the life of at most one dwarf. If you want to know what this strategy is, read on.
Let black hats signify 1's and white hats signify 0's. Each dwarf calculates the parity (sum modulo 2) of the hats in front of him. The first (tallest) dwarf announces the color corresponding to the parity he calculated. He may or may not be killed (depending on his luck... of course the Wizards can always engineer it so he dies, because they know this is the optimal strategy).
The next dwarf compares the parity he calculated and the parity the first dwarf announced. If the two parities are the same, that means his hat is white, otherwise it is black. He announces this color, and lives.
Each successive dwarf, armed with the original parity of all but the first dwarf and the colors of the hats of all the preceding dwarves (but the first), can easily calculate the color of his own hat. An inductive proof of correctness is pretty easy.
Thus only the first (and tallest) dwarf dies... which I guess explains why dwarves are so short.
