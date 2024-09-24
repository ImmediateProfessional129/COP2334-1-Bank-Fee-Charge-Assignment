# COP2334-1-Bank-Fee-Charge-Assignment
This is a repository link of the COP2334-1 Module 4 Assignment

// This program is created to calculate the monthly fee charge for a bank account.

// Include the header file.
#include <iostream>
#include <iomanip>
using namespace std;

int main() {
    // Declare the variables.
  int number_of_checks;
  double beginningBalance, totalFee, checkFee;
  const int monthlyFee = 10;
  const double Check20 = 0.10, Check39 = 0.08, Check59 = 0.06, Check60 = 0.04;
// Prompt the user to enter the beginning balance.
  cout << "Enter the beginning balance: $";
  cin >> beginningBalance;
  // If the beginning balance is less than 0, an error message will display.
  cout << "Enter the number of checks written: ";
  cin >> number_of_checks;
// If the number of checks is less than 0, display an error message.
  if (beginningBalance < 0) {
    cout << "URGENT: The account is overdrawn!" << endl;
  } else if (number_of_checks < 0) {
    cout << "The number of checks cannot be below zero." << endl;
    // If the number of checks is less than 20, the check fee is $0.10.
  } else {
    if (beginningBalance < 400) {
      totalFee = monthlyFee + 15;
    }
    if (number_of_checks < 20) {
      checkFee = number_of_checks * Check20;
    } else if (number_of_checks >= 20 && number_of_checks <= 39) {
      checkFee = number_of_checks * Check39;
    } else if (number_of_checks >= 40 && number_of_checks <= 59) {
      checkFee = number_of_checks * Check59;
    } else {
      checkFee = number_of_checks * Check60;
    }
    // Calculate the total fee.
    totalFee = monthlyFee + checkFee;
    cout << setprecision(2) << fixed;
    cout << "The bank's service fees for the month are: $" << totalFee << endl;
    return 0;
  }
}
