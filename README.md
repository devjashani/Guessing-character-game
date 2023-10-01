# Guessing-character-game
In this repository i have write a code for  a game  which is Guessing a character and you have 5 chance only to guess a correct character.All code are written in JAVA programming.

import java.util.Scanner;

public class CharacterGuessingGame {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        char targetChar = generateRandomChar();
        int chances = 5;
        boolean hasGuessedCorrectly = false;

        System.out.println("Welcome to the Character Guessing Game!");
        System.out.println("Try to guess the character!");

        while (chances > 0) {
            System.out.print("Enter your guess: ");
            char userGuess = scanner.next().charAt(0);

            if (userGuess == targetChar) {
                hasGuessedCorrectly = true;
                break;
            } else {
                chances--;
                System.out.println("Incorrect guess! Chances left: " + chances);
            }
        }

        if (hasGuessedCorrectly) {
            System.out.println("Congratulations! You guessed the character: " + targetChar);
        } else {
            System.out.println("Sorry, you've run out of chances! The correct character was: " + targetChar);
        }

        scanner.close();
    }

    private static char generateRandomChar() {
        return (char) (Math.random() * 26 + 'a');
    }
}
