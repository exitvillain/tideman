# tideman
This project implements the Tideman Voting Method, a ranked-choice voting algorithm that determines the Condorcet winner in an election if one exists. It was developed as part of Harvard's CS50x: Introduction to Computer Science, known for its challenging programming assignments. Most people would agree this is the hardest assignment in the class. 

The Tideman method uses ranked ballots to produce a graph of candidate preferences and ensures no cycles occur when determining the winner.

##About the Project
This program allows for:

###Ranked-Choice Voting: Voters rank candidates in order of preference.
###Condorcet Winner: Identifies the candidate who would win all head-to-head matchups.
###Cycle Prevention: Ensures the graph of preferences does not create a cycle.
###Dynamic Input: Supports elections with up to 9 candidates and any number of voters.

##Key Features
###Voting System:

Voters rank candidates by preference.
Votes are recorded and tallied.

###Pair Comparison:

Head-to-head results are computed between all candidate pairs.
Pairs are sorted by the strength of victory.

###Graph Construction:

A directed graph of candidate preferences is constructed.
Edges are locked in order of victory strength, ensuring no cycles.

###Winner Determination:

The graph is analyzed to find the "source" node, representing the winner.
Code Highlights
The program implements six primary functions:

vote: Records a voter's preferences.
record_preferences: Updates the global preference matrix based on voter rankings.
add_pairs: Creates candidate pairs for head-to-head comparisons.
sort_pairs: Sorts candidate pairs by the strength of victory.
lock_pairs: Constructs the graph while preventing cycles.
print_winner: Identifies and prints the election winner.
Example
Given the following ranked ballots:


Copy code
3 voters, 3 candidates: Alice, Bob, Charlie
Voter 1: Alice > Charlie > Bob
Voter 2: Bob > Charlie > Alice
Voter 3: Charlie > Alice > Bob
The program calculates the winner using the Tideman method:

Pair Comparisons:

Alice > Bob: 2-1
Bob > Charlie: 2-1
Charlie > Alice: 2-1
Sorting Pairs:

Alice > Bob
Bob > Charlie
Charlie > Alice
Locking Pairs:

Lock Alice > Bob
Lock Bob > Charlie (skip Charlie > Alice to avoid a cycle).
Determine Winner:

Alice is the source node with no incoming edges.
Result: Alice wins the election.

How to Use
Clone the repository:
bash
Copy code
git clone https://github.com/yourusername/tideman
cd tideman
Compile the program:
bash
Copy code
make tideman
Run the program with custom input:
bash
Copy code
./tideman
How to Test
Use the provided check50 tests for correctness:
bash
Copy code
check50 cs50/problems/2024/x/tideman
Style-check your code:
bash
Copy code
style50 tideman.c
