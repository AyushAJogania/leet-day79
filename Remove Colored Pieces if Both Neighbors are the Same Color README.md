# leet-day79

# Winning the Color Game

You are given a string `colors` representing a line of colored pieces. The goal of the game is to determine if Alice can win the game by making optimal moves against Bob. The game has the following rules:

- Alice and Bob take alternating turns to remove pieces from the line.
- Alice can only remove a piece colored 'A' if both its neighbors are also colored 'A'.
- Bob can only remove a piece colored 'B' if both its neighbors are also colored 'B'.
- Players cannot remove pieces from the edge of the line.
- If a player cannot make a move on their turn, they lose, and the other player wins.

The task is to determine if Alice can win the game if they play optimally. If Alice can win, the function returns `true`. Otherwise, it returns `false`.

## Algorithm

The algorithm works as follows:

1. Initialize a map `c` to keep track of the consecutive 'A' pieces that can be removed. Initialize it to zero.
2. Iterate through the `colors` string using an iterator `it`.
3. For each character `x` at the current position `it`, find the consecutive 'A' pieces.
4. Update the count of removable 'A' pieces in the map `c` based on the number of consecutive 'A's found.
5. Continue the iteration until the end of the string is reached.

After processing the entire string, compare the counts of removable 'A' and 'B' pieces in the map `c`. If the count of 'A' pieces is greater than the count of 'B' pieces, return `true`, indicating that Alice can win. Otherwise, return `false`.

## Usage

To use this solution, create an instance of the `Solution` class and call the `winnerOfGame` function with the input string `colors`. It will return a boolean indicating whether Alice can win the game.

Example:


Solution solution;
std::string colors = "AAABABB";
bool aliceWins = solution.winnerOfGame(colors);
if (aliceWins) {
    std::cout << "Alice wins!" << std::endl;
} else {
    std::cout << "Bob wins!" << std::endl;
}


## Complexity Analysis

- Time Complexity: O(n), where n is the length of the `colors` string. The algorithm iterates through the string once.
- Space Complexity: O(1), as the map `c` has a constant number of entries (for 'A' and 'B').

This algorithm efficiently determines the winner of the color game by considering consecutive pieces of the same color.

