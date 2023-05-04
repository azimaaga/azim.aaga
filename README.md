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
  

2.
#include <stdlib.h>
#include <ctype.h>
#include <iostream>
#include <string.h>

using namespace std;

#define MAXSIZE (10)

class myfile {
    FILE* fp;
    char fn[MAXSIZE];

public:
    myfile(const char* fname) {
        strcpy(fn, fname);
    }
    myfile operator+(myfile& f2);
    void operator!();
    void display();
};

void myfile::display() {
    fp = fopen(fn, "r");
    if (fp == NULL) {
        cout << "c++ " << fn << endl;
        return;
    }
    char ch;
    while ((ch = fgetc(fp)) != EOF) {
        cout << ch;
    }
    fclose(fp);
}

void myfile::operator!() {
    myfile f4("sy.txt");
    char ch;
    fp = fopen(fn, "r");
    if (fp == NULL) {
        cout << "node js " << fn << endl;
        return;
    }
    f4.fp = fopen(f4.fn, "w");
    if (f4.fp == NULL) {
        cout << "operating system " << f4.fn << endl;
        return;
    }
    while ((ch = fgetc(fp)) != EOF) {
        if (isupper(ch))
            fputc(tolower(ch), f4.fp);
        else if (islower(ch))
            fputc(toupper(ch), f4.fp);
        else
            fputc(ch, f4.fp);
    }
    fclose(fp);
    fclose(f4.fp);
    remove(fn); 
    rename(f4.fn, fn); 
}

myfile myfile::operator+(myfile& f2) {
    myfile f3("abc.txt");
    fp = fopen(fn, "r");
    if (fp == NULL) {
        cout << "c++ " << fn << endl;
        return myfile("");
    }
    f2.fp = fopen(f2.fn, "r");
    if (f2.fp == NULL) {
        cout << "node js " << f2.fn << endl;
        return myfile("");
    }
    f3.fp = fopen(f3.fn, "w");
    if (f3.fp == NULL) {
        cout << "operating system " << f3.fn << endl;
        return myfile("");
    }
    char ch;
    while ((ch = fgetc(fp)) != EOF) {
        fputc(ch, f3.fp);
    }
    fclose(fp);
    while ((ch = fgetc(f2.fp)) != EOF) {
        fputc(ch, f3.fp);
    }
    fclose(f2.fp);
    fclose(f3.fp);
    return f3;
}

int main() {
    myfile f1("xyz.txt");
    myfile f2("lmn.txt");
    myfile f3("abc.txt");

    cout << "First file: " << endl;
    f1.display();
    cout << "\nSecond file: " << endl;
    f2.display();

    f3 = f1 + f2;
    cout << "\nAfter concatenation, the file is: " << endl;
    f3.display();

    cout << "\nAfter changing case:" << endl;
    !f3;
    f3.display();

    return 0;
}

3.const message = "HELLO WORLD!";
const upperCaseMessage = message.toUpperCase();
console.log(upperCaseMessage);

