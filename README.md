# Academic Honesty
If you are taking Harvard's CS50 - Introduction to Computer Science course you **must follow the course's [Academic Honesty philosophy](https://cs50.harvard.edu/x/2021/honesty/)**.

It is not reasonable to access a solution to some assessement prior to (re-)submitting your own.

The essence of all work that you submit to the CS50 course **must be your own**. 

# CS50's Runoff
Not familiar with the term Runoff Election?

In an instant runoff election, voters can rank as many candidates as they wish. If any candidate has a majority (more than 50%) of the first preference votes, that candidate is declared the winner of the election.

If no candidate has more than 50% of the vote, then an “instant runoff” occurrs. The candidate who received the fewest number of votes is eliminated from the election, and anyone who originally chose that candidate as their first preference now has their second preference considered. 

The process repeats: if no candidate has a majority of the votes, the last place candidate is eliminated, and anyone who voted for them will instead vote for their next preference (who hasn’t themselves already been eliminated). Once a candidate has a majority, that candidate is declared the winner.

# System Algorithm (How it operates)
This is a command-line application and it was fully developed in **C**.

In this exercise, we needed to implement the 6 functions below listed to emulate a runoff election.
  
  1. Record preference if vote is valid:
  
    bool vote(int voter, int rank, string name);
    
  2. Tabulate votes for non-eliminated candidates:
  
    void tabulate(void);
    
  3. Print the winner of the election, if there is one:
  
    bool print_winner(void);
    
  4. Return the minimum number of votes any remaining candidate has:

    int find_min(void);
    
  5. Return true if the election is tied between all candidates, false otherwise:

    bool is_tie(int min);
  
  6. Eliminate the candidate (or candidates) in last place:

    void eliminate(int min);
  
# Usage
To use and test this program, you will need [CS 50 Library](https://cs50.readthedocs.io/libraries/cs50/c/). Copy this repository and through the command line, enter the program's folder and run the following command to compile:

$ make runoff

Then you run the program in the command-line as bellow:

    ./runoff <candidate 1> <candidate 2> <candidate 3> ... <candidate n>
    
Example:

    ./runoff Alice Bob Charlie
    
 Then the program will ask for the number of voters in the election. The number must to be an integer. For example:
 
    Number of voters: 5

Then it will ask you to rank (from 1 to 3) the votes of each person voting (number of voters above). Example:

    Rank 1: Alice
    Rank 2: Charlie
    Rank 3: Bob
    
    Rank 1: Alice
    Rank 2: Charlie
    Rank 3: Bob
    
    Rank 1: Bob
    Rank 2: Charlie
    Rank 3: Alice

    Rank 1: Bob
    Rank 2: Charlie
    Rank 3: Alice

    Rank 1: Charlie
    Rank 2: Alice
    Rank 3: Bob
    
And lastly it will prompt the winner:
    
    Alice

    
  
