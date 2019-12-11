# Assignment3
Assignment 3 for Data Structures
# cisc3130


Instructor: Katherine Chuang \
Brooklyn College
Kujtim Hakaj


## Objective:

To build a program that is able to count each word in a .txt file and bring back the amount of times each word appears in order.

### Solution:

What I did was create two seperate methods, one that counts the words line by line using a hashmap to keep track, and one that transfers the keys of the hashmaps into an array to ensure they're printed in order.
I did this by using insertion sorting. Without doing this, the hashmap would print out the words in a randomized order.

To ensure the most efficient code is working, it is best to first remove the obstructions (!,?," ", etc.) first and implement each word from this line into an array, which is then read by a for loop that implements it into the hashmap.
Once this is done the .keySet() method could be used to transfer it back into an array to make sure we can print out the results in size order.

Example:
file.txt 'pop. pop! DROP drOp,'

output:
        2: pop
        2: drop
        
I made sure to take care of anything that could potentially get in the way of counting the words, like punctuation or capitalization.
