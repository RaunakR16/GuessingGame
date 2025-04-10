# 🎮 Simple Word Guessing Game

This is a basic command-line Word Guessing Game (similar to Hangman) written in Python. It's a fun little project for beginners to understand loops, conditionals, user input, and list operations.

## 🚀 How to Play

1. The game randomly selects a word from a predefined list.
2. The player is prompted to guess one letter at a time.
3. If the guessed letter is in the word, it will be revealed in its correct position.
4. The game continues until the player:
   - Correctly guesses all the letters in the word, or
   - Exceeds the number of allowed guesses (equal to the word's length).

## 🧠 Features

- Random word selection
- Interactive input/output in the terminal
- Letter-by-letter guessing with feedback
- Simple win/lose conditions

## 📝 Code Sample

```python
import random

# Name input
print("HEY!!")
name = input("What's your Name: ")

print("\nLet's start the Game!", name)

# Create a list of words
words = ["apple", "banana", "cat", "dog", "elephant"]

# Choose a random word from the list
random_word = random.choice(words)

# Create a list to store the user's guesses
guesses = []

# Start the game
while True:
    guess = input("Guess a letter: ")

    if guess in random_word:
        guesses.append(guess)

        for i in range(len(random_word)):
            if random_word[i] == guess:
                print(guess, end=" ")
            else:
                print("_", end=" ")

        if "".join(guesses) == random_word:
            print()
            print("Congratulations! You guessed the word correctly!")
            break
    else:
        print("Incorrect guess.")

    if len(guesses) == len(random_word):
        print()
        print("You ran out of guesses. The word was", random_word)
        break
