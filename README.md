import java.util.Random;
import java.util.Scanner;

public class EnhancedTreasureHuntGame {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Random random = new Random();

        int score = 0;
        int attempts = 3; // Number of attempts allowed for each chest
        boolean gameOver = false;

        System.out.println("Welcome to the Enhanced Treasure Hunt Game!");

        while (!gameOver) {
            int num1 = random.nextInt(100) + 10; // Generate random number between 10 and 109
            int num2 = random.nextInt(100) + 10; // Generate random number between 10 and 109

            System.out.println("\nYou find yourself in a room filled with treasure chests.");
            System.out.println("To open the main treasure chest, you must solve a calculation.");

            System.out.println("The calculation is: " + num1 + " + " + num2);
            int answer = num1 + num2;

            System.out.print("Enter your answer: ");
            int userAnswer = scanner.nextInt();

            if (userAnswer == answer) {
                System.out.println("Congratulations! You have opened the main treasure chest!");
                score += 10; // Award points for opening the chest
            } else {
                System.out.println("Oops! That's incorrect. You have " + (attempts - 1) + " attempts left.");
                if (--attempts == 0) {
                    System.out.println("You failed to open the main treasure chest.");
                    gameOver = true;
                }
            }
        }

        System.out.println("Your total score: " + score);
        System.out.println("Game over!");
    }
}
