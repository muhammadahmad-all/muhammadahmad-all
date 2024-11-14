#include <iostream>

using namespace std;

void checkBalance(int balance) {
    cout << "Your current balance is: $" << balance << endl;
}

void deposit(int& balance) {
    int amount;
    cout << "Enter the amount to deposit: ";
    cin >> amount;
    balance += amount;
    cout << "Deposit successful. New balance: $" << balance << endl;
}

void withdraw(int& balance) {
    int amount;
    cout << "Enter the amount to withdraw: ";
    cin >> amount;
    if (amount <= balance) {
        balance -= amount;
        cout << "Withdrawal successful. New balance:   
 $" << balance << endl;
    } else {
        cout << "Insufficient balance." << endl;
    }
}

int main() {
    int balance = 0;
    int choice;

    do {
        cout << "\nATM Menu\n";
        cout << "1. Check Balance\n";
        cout << "2. Deposit\n";
        cout << "3. Withdraw\n";
        cout << "4. Exit\n";
        cout << "Enter your choice: ";
        cin >> choice;

        switch (choice) {
            case 1:   

                checkBalance(balance);
                break;
            case 2:
                deposit(balance);
                break;
            case 3:
                withdraw(balance);
                break;
            case 4:
                cout << "Thank you for using the ATM." << endl;
                break;
            default:
                cout << "Invalid choice. Please try again." << endl;
        }
    } while (choice != 4);

    return 0;
}
