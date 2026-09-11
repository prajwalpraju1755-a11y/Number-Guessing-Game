# Number-Guessing-Game
#include <iostream>
#include <cstdlib>
#include <ctime>

using namespace std;

int main() {
    char playAgain;

    do {
        srand(time(0));

        int secretNumber = rand() % 100 + 1;
        int guess, attempts = 0;

        cout << "\n===== NUMBER GUESSING GAME =====" << endl;
        cout << "Guess the number between 1 and 100." << endl;

        do {
            cout << "Enter your guess: ";
            cin >> guess;
            attempts++;

            if (guess > secretNumber) {
                cout << "Too High! Try Again.\n";
            } 
            else if (guess < secretNumber) {
                cout << "Too Low! Try Again.\n";
            } 
            else {
                cout << "\nCongratulations! You guessed the correct number." << endl;
                cout << "Total Attempts: " << attempts << endl;

                if (attempts <= 5)
                    cout << "Score: Excellent!" << endl;
                else if (attempts <= 10)
                    cout << "Score: Good!" << endl;
                else
                    cout << "Score: Keep Practicing!" << endl;
            }

        } while (guess != secretNumber);

        cout << "\nDo you want to play again? (Y/N): ";
        cin >> playAgain;

    } while (playAgain == 'Y' || playAgain == 'y');

    cout << "\nThank you for playing!" << endl;

    return 0;
}