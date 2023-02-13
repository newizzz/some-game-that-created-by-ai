# Some games that created by ai
## Example:
### Me
Make a simple game ideas to write on python
### AI
Here are three simple game ideas that can be implemented using Python:

Tic Tac Toe: A classic two-player game where each player takes turns marking spaces on a 3x3 grid. The first player to place three of their marks in a row (horizontally, vertically, or diagonally) wins the game.

Rock-Paper-Scissors: A game where two players make gestures simultaneously and the winner is determined based on the following rules: rock beats scissors, scissors beats paper, and paper beats rock.

Hangman: A word guessing game where the player tries to guess a word by suggesting letters one at a time. For each incorrect guess, a part of a stick figure is drawn, and the game is lost if the stick figure is fully drawn before the word is guessed.
### Me
make a Hangman game using python

### AI
```py
import random

def hangman(word):
    wrong = 0
    stages = ["",
             "________        ",
             "|               ",
             "|        |      ",
             "|        0      ",
             "|       /|\     ",
             "|       / \     ",
             "|               "
             ]
    rletters = list(word)
    board = ["_"] * len(word)
    win = False
    print("Welcome to Hangman")
    while wrong < len(stages) - 1:
        print("\n")
        msg = "Guess a letter: "
        char = input(msg)
        if char in rletters:
            cind = rletters.index(char)
            board[cind] = char
            rletters[cind] = '$'
        else:
            wrong += 1
        print((" ".join(board)))
        e = wrong + 1
        print("\n".join(stages[0: e]))
        if "_" not in board:
            print("You win!")
            print(" ".join(board))
            win = True
            break
    if not win:
        print("\n".join(stages[0: wrong]))
        print("You lose! It was {}.".format(word))

words = ["python", "java", "kotlin", "javascript", "ruby"]
hangman(random.choice(words))
```
