#include <iostream>
#include <cstdlib>
#include <ctime>

int main() {
    srand(time(0)); // Seed the random number generator

    int secretNumber = rand() % 100 + 1; // Generate random number between 1 and 100
    int guess;
    int attempts = 0;

    std::cout << "Hello! Welcome to the Number Guessing Game!\n";
    std::cout << "choose a number between 1 and 100.\n";

    while (attempts < 5) {
        std::cout << "Now, Enter your guess (Attempt " << attempts + 1 << "/5): ";
        std::cin >> guess;
        attempts++;

        if (guess == secretNumber) {
            std::cout << "Congratulations! You guessed the number (" << secretNumber << ") in " << attempts << " attempts.\n";
            return 0;
        } else if (guess < secretNumber) {
            std::cout << "ugh oh. Too low! Try a higher number.\n";
        } else {
            std::cout << "ugh oh. Too high! Try a lower number.\n";
        }
    }

    std::cout << "Sorry, you've reached the maximum number of attempts. The number was " << secretNumber << ".\n";
    return 0;
}
