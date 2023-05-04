1. #include <iostream>
using namespace std;

// Define an inline function to find the maximum of two numbers
inline int max(int x, int y) {
  return (x > y) ? x : y;
}

// Define an inline function to find the minimum of two numbers
inline int min(int x, int y) {
  return (x < y) ? x : y;
}

int main() {
  int a, b;

  // Get input from user
  cout << "Enter the first number: ";
  cin >> a;

  cout << "Enter the second number: ";
  cin >> b;

  // Use the inline functions to find the maximum and minimum
  int maxNum = max(a, b);
  int minNum = min(a, b);

  // Output the results
  cout << "The maximum of " << a << " and " << b << " is " << maxNum << endl;
  cout << "The minimum of " << a << " and " << b << " is " << minNum << endl;

  return 0;
}


2.const message = "HELLO WORLD!";
const upperCaseMessage = message.toUpperCase();
console.log(upperCaseMessage);

