20--
1. import javax.swing.*;
   import java.awt.*;

class Slip20A {

    public static void main(String args[]) {

        JFrame frame = new JFrame("TYBBACA");

        frame.setSize(400, 400);

        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        frame.getContentPane().setBackground(Color.RED);

        frame.setVisible(true);

    }

}


2. import java.util.*;

    public class Slip20B{

        public static void main (String args[]){

            LinkedList al = new LinkedList<>();

            al.add("CPP");

            al.add("JAVA");

            al.add("Python");

            al.add("PHP");

            System.out.println("Display content using Iterator...");

            Iterator il=al.iterator();

            while(il.hasNext()){

                System.out.println(il.next());

            }

            System.out.println("Display Content Revverse Using ListIterator");

            ListIterator li1=al.listIterator();

            while(li1.hasNext()){

                li1.next();

            }

            while(li1.hasPrevious()){

                System.out.println("" + li1.previous());

            }

        }

    }



   3.from math import pi
class Circle():
    def __init__(self,Radius):
        self.Radius=Radius
    def area(self):
        a=pi*self.Radius*self.Radius      
        return round(a,2)
    def circumference(self):
        c=2*self.Radius*pi
        return round(c,2)
    
r= int(input('enter radius of circle : '))
a=Circle(r)
print('Area of circle is : ',a.area())
print('Circumference of circle is : ',a.circumference())



4.n=int(input("Input a number : "))
d ={}
for x in range(1,n+1):
    d[x]=x*x
print(d)




16---

Q.1.A

Write a java program to calculate sum of digits of a given number using recursion.




import java.io.*;

 

public class SumOfDigits {

    public static void main(String[] args) {

        int number = 123;  // Change this to the number you want to calculate the sum for

        int sum = calculateSumOfDigits(number);

        System.out.println("The sum of digits in " + number + " is: " + sum);

    }

 

    public static int calculateSumOfDigits(int num) {

        if (num == 0) {

            return 0;  // Base case: If the number is 0, the sum is 0

        } else {

            // Calculate the sum of digits for the remaining part of the number

            int lastDigit = num % 10; // Get the last digit

            int remainingNumber = num / 10; // Remove the last digit

            return lastDigit + calculateSumOfDigits(remainingNumber); // Recursive call

        }

    }

}



Q.1.B


Write a java program to accept n employee names from user. Sort them in ascending 

order and Display them.(Use array of object and Static keyword)

             

 

import java.io.*;

 

import java.util.Scanner;

 

public class EmployeeSort

 {

    static class Employee

{

        String name;

 

        Employee(String name)

{

            this.name = name;

        }

 

        static void sortEmployeesByName(Employee[] employees)

           {

            for (int i = 0; i < employees.length; i++)

             {

                for (int j = i + 1; j < employees.length; j++)

                  {

                    if (employees[i].name.compareTo(employees[j].name) > 0)

                          {

                        Employee temp = employees[i];

                        employees[i] = employees[j];

                        employees[j] = temp;

                    }

                }

            }

        }

    }

 

    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter the number of employees (n): ");

        int n = scanner.nextInt();

        scanner.nextLine(); // Consume the newline character

 

        Employee[] employees = new Employee[n];

 

        // Accept employee names from the user

        for (int i = 0; i < n; i++) {

            System.out.print("Enter the name of employee " + (i + 1) + ": ");

            String name = scanner.nextLine();

            employees[i] = new Employee(name);

        }

 

        // Sort the employee names in ascending order using a static method

        Employee.sortEmployeesByName(employees);

 

        // Display the sorted employee names

        System.out.println("Sorted Employee Names:");

        for (int i = 0; i < n; i++) {

            System.out.println(employees[i].name);

        }

 

        scanner.close();

    }

}

Q.2.A


A) Write a python script to create a class Rectangle with data member’s length,
width and methods area, perimeter which can compute the area and perimeter of
rectangle.
class Ractangle():
 def __init__(self,l,w):
 self.l=l
 self.w=w
 def rectangle_area(self):
 return self.l*self.w
 def rectangle_Perimeter(self):
 return (self.l*2)+(self.w*2)

L=int(input('enter Length of Rectangle :'))
W=int(input('enter Width of Rectangle :'))
a1=Ractangle(L,W)
print("Area=",a1.rectangle_area())
print("Perimeter",a1.rectangle_Perimeter())

Q.2.B



B) Write Python GUI program to add items in listbox widget and to print and
delete the selected items from listbox on button click. Provide three separate
buttons to add, print and delete.
import tkinter as tk
def add_item():
 item = entry.get()
 if item:
 listbox.insert(tk.END, item)
 entry.delete(0, tk.END)
def print_items():
 selected_items = listbox.curselection()
 for index in selected_items:
 print(listbox.get(index))
def delete_items():
 selected_items = listbox.curselection()
 for index in selected_items:
 listbox.delete(index)
# Create the main window
root = tk.Tk()
root.title("Listbox Example")
# Create a Listbox widget
listbox = tk.Listbox(root, selectmode=tk.MULTIPLE)
listbox.pack()
# Entry widget for adding new items
entry = tk.Entry(root)
entry.pack()
# Add, Print, and Delete buttons
add_button = tk.Button(root, text="Add", command=add_item)
print_button = tk.Button(root, text="Print", command=print_items)
delete_button = tk.Button(root, text="Delete", command=delete_items)
add_button.pack()
print_button.pack()
delete_button.pack()
root.mainloop()



11----
Q.1.A

Write a menu driven java program using command line arguments for the following:         

1.  Addition

2.  Subtraction

3.  Multiplication

4.  Division.

 

import java.io.*;

public class CommandLineCalculator {

    public static void main(String[] args) {

        if (args.length != 3) {

            System.out.println("CommandLine Argument");

            return;

        }

 

        String operation = args[0];

        double num1 = Double.parseDouble(args[1]);

        double num2 = Double.parseDouble(args[2]);

 

        double result = 0;

 

        switch (operation) {

            case "1":

                result = num1 + num2;

                System.out.println("Addition Result: " + result);

                break;

            case "2":

                result = num1 - num2;

                System.out.println("Subtraction Result: " + result);

                break;

            case "3":

                result = num1 * num2;

                System.out.println("Multiplication Result: " + result);

                break;

            case "4":

                if (num2 == 0) {

                    System.out.println("Error: Division by zero is not allowed.");

                } else {

                    result = num1 / num2;

                    System.out.println("Division Result: " + result);

                }

                break;

            default:

                System.out.println("Invalid operation. Please choose 1 for Addition, 2 for Subtraction, 3 for Multiplication, or 4 for Division.");

        }

    }

}

Q.1.B

Write an applet application to display Table lamp.The color of lamp should get change randomly

 import java.applet.*;

 import java.awt.*;

  

public class Lamp extends java.applet.Applet {

   public void init() {

     resize(300,300);

   }

     

  public void paint(Graphics g) {

     // the platform

     g.fillRect(0,250,290,290);

     // the base of the lamp

     g.drawLine(125,250,125,160);

     g.drawLine(175,250,175,160);

 

    // the lamp shade; two arcs

     g.drawArc(85,157,130,50,-65,312);

     g.drawArc(85,87,130,50,62,58);

     g.drawLine(85,177,119,89);

     g.drawLine(215,177,181,89);

 

     // pattern on the shade

     g.fillArc(78,120,40,40,63,-174);

     g.fillOval(120,96,40,40);

     g.fillArc(173,100,40,40,110,180);

   }

 }

 

Lamp.html

<html> 

<body> 

<applet code="Lamp.class" width="300" height="300"> 

</applet> 

</body> 

</html>


Q.2.A

A) Write a Python program to compute element-wise sum of given tuples.
Original lists: (1, 2, 3, 4) (3, 5, 2, 1) (2, 2, 3, 1)
Element-wise sum of the said tuples: (6, 9, 8, 6)
x = (1,2,3,4);y = (3,5,2,1);z = (2,2,3,1)
print("Original lists:")
print(x)
print(y)
print(z)
print("\nElement-wise sum of the said tuples:")
result = tuple(map(sum, zip(x, y, z)))
print(result)


Q.2.B


B) Write Python GUI program to add menu bar with name of colors as options to
change the background color as per selection from menu option.
from tkinter import Menu, Tk, mainloop
def redcolor():
 root.configure(background = 'red')
def greencolor():
 root.configure(background = 'green')
def yellowcolor():
 root.configure(background = 'yellow')
def violetcolor():
 root.configure(background = 'violet')
def bluecolor():
 root.configure(background = 'blue')
def cyancolor():
 root.configure(background = 'cyan')

root = Tk()
root.title('COLOR MENU')
menubar = Menu(root)
color = Menu(menubar, tearoff = 0)
menubar.add_cascade(label ='color', menu = color)
color.add_command(label ='Red', command = redcolor,activebackground='red',
 activeforeground='cyan')
color.add_command(label ='Green',command = greencolor,activebackground='green',
 activeforeground='blue')
color.add_command(label ='Blue',command = bluecolor,activebackground='blue',
 activeforeground='yellow')
color.add_command(label ='Yellow',command = yellowcolor,activebackground='yellow',
 activeforeground='blue')
color.add_command(label ='Cyan',command = cyancolor,activebackground='cyan',
 activeforeground='red')
color.add_command(label ='Violet',command = violetcolor,activebackground='violet',
 activeforeground='green')
color.add_separator()
color.add_command(label ='Exit',command = root.destroy)


10----

Q.1.A

Write a java program to count the frequency of each character in a given string.

import java.util.HashMap;

import java.util.Map;

import java.io.*;

 

public class CharacterFrequencyCounter {

    public static void main(String[] args) {

        String inputString = "Hello, World!";

       

        // Create a HashMap to store character frequencies

        Map<Character, Integer> charFrequencyMap = new HashMap<>();

       

        // Iterate through the characters in the string

        for (char c : inputString.toCharArray()) {

            if (charFrequencyMap.containsKey(c)) {

                // Character already exists in the map, increment the count

                charFrequencyMap.put(c, charFrequencyMap.get(c) + 1);

            } else {

                // Character does not exist in the map, add it with a count of 1

                charFrequencyMap.put(c, 1);

            }

        }

       

        // Print the character frequencies

        for (Map.Entry<Character, Integer> entry : charFrequencyMap.entrySet()) {

            System.out.println("Character: " + entry.getKey() + ", Frequency: " + entry.getValue());

        }

    }

}

Q.2.B

Write a java program to calculate Total amount and Interest amount Using textbox,label and 3 button for Calculate Button ,Clear Button ,Close Button.

 

import java.awt.*;

import java.awt.event.*;

 

public class InterestCalculatorAWT extends Frame {

    private TextField p, r, time1, total, interestAmount;

    private Button calculate, clear, close;

 

    public InterestCalculatorAWT() {

        setTitle("Interest Calculator");

        setSize(400, 200);

        setLayout(null);

 

        Label l1 = new Label("Principal Amount:");

        l1.setBounds(20, 30, 120, 20);

        add(l1);

 

        p = new TextField();

        p.setBounds(160, 30, 200, 20);

        add(p);

 

        Label r1 = new Label("Rate of Interest (%):");

        r1.setBounds(20, 60, 120, 20);

        add(r1);

 

        r = new TextField();

        r.setBounds(160, 60, 200, 20);

        add(r);

 

        Label l3 = new Label("Time (years):");

        l3.setBounds(20, 90, 120, 20);

        add(l3);

 

        time1 = new TextField();

        time1.setBounds(160, 90, 200, 20);

        add(time1);

 

        calculate = new Button("Calculate");

        calculate.setBounds(20, 120, 100, 30);

        add(calculate);

 

        clear = new Button("Clear");

        clear.setBounds(140, 120, 100, 30);

        add(clear);

 

        close = new Button("Close");

        close.setBounds(260, 120, 100, 30);

        add(close);

 

        total = new TextField();

        total.setBounds(20, 160, 340, 20);

        total.setEditable(false);

        add(total);

 

        interestAmount = new TextField();

        interestAmount.setBounds(20, 190, 340, 20);

        interestAmount.setEditable(false);

        add(interestAmount);

 

        calculate.addActionListener(new ActionListener() {

            public void actionPerformed(ActionEvent e) {

                calculate();

            }

        });

 

        clear.addActionListener(new ActionListener() {

            public void actionPerformed(ActionEvent e) {

                clear();

            }

        });

 

        close.addActionListener(new ActionListener() {

            public void actionPerformed(ActionEvent e) {

                System.exit(0);

            }

        });

 

        addWindowListener(new WindowAdapter() {

            public void windowClosing(WindowEvent we) {

                dispose();

            }

        });

 

        setVisible(true);

    }

 

    private void calculate() {

        try {

            double principal = Double.parseDouble(p.getText());

            double rate = Double.parseDouble(r.getText());

            double time = Double.parseDouble(time1.getText());

 

            double interest = (principal * rate * time) / 100;

            double totalAmount = principal + interest;

 

            total.setText("Total Amount: " + totalAmount);

            interestAmount.setText("Interest Amount: " + interest);

        } catch (NumberFormatException e) {

            // Handle invalid input

            total.setText("Invalid input");

            interestAmount.setText("Invalid input");

        }

    }

 

    private void clear() {

        p.setText("");

        r.setText("");

        time1.setText("");

        total.setText("");

        interestAmount.setText("");

    }

 

    public static void main(String[] args) {

        new InterestCalculatorAWT();

    }

}


Q.2.A

A) Write Python GUI program to display an alert message when a button is
pressed.
from tkinter import *
from tkinter import messagebox
def clicked():
 messagebox.showinfo('Button','Button is pressed.')
root=Tk()
root.geometry('300x200')
word= Label(root,text='messagebox from button')
Button1=Button(root,text='BUTTON',command=clicked)
word.pack()
Button1.pack()
root.mainloop()


Q.1.B


B) Write a Python class to find validity of a string of parentheses, '(', ')', '{', '}',
'[' ']’.
These brackets must be close in the correct order. for example "()" and
"()[]{}" are
valid but "[)", "({[)]" and "{{{" are invalid.
class py_solution:
 def is_valid_parenthese(self, str1):
 stack, pchar = [], {"(": ")", "{": "}", "[": "]"}
 for parenthese in str1:
 if parenthese in pchar:
 stack.append(parenthese)
 elif len(stack) == 0 or pchar[stack.pop()] != parenthese:
 return False
 return len(stack) == 0
print(py_solution().is_valid_parenthese("(){}[]"))
print(py_solution().is_valid_parenthese("()[{)}"))
print(py_solution().is_valid_parenthese("()"))
root.config(menu = menubar)


17---

Q.1.A

Write a java Program to accept ‘n’ no’s through command line and store only Armstrong no’s into the array and display that array.

import java.util.ArrayList;

import java.io.*;

public class ArmstrongNumbers {

    public static void main(String[] args) {

        if (args.length == 0) {

            System.out.println("Please provide some numbers as command-line arguments.");

            return;

        }

 

        int n = args.length;

        int[] numbers = new int[n];

 

        for (int i = 0; i < n; i++) {

            try {

                numbers[i] = Integer.parseInt(args[i]);

            } catch (NumberFormatException e) {

                System.out.println("Invalid input: " + args[i] + " is not a valid number.");

                return;

            }

        }

 

        ArrayList<Integer> armstrongNumbers = new ArrayList<>();

        for (int number : numbers) {

            if (isArmstrongNumber(number)) {

                armstrongNumbers.add(number);

            }

        }

 

        if (armstrongNumbers.isEmpty()) {

            System.out.println("No Armstrong numbers found in the provided input.");

        } else {

            System.out.println("Armstrong numbers in the input:");

            for (int armstrongNumber : armstrongNumbers) {

                System.out.println(armstrongNumber);

            }

        }

    }

 

    public static boolean isArmstrongNumber(int number) {

        int originalNumber, remainder, result = 0;

        originalNumber = number;

 

        while (originalNumber != 0) {

            remainder = originalNumber % 10;

            result += Math.pow(remainder, 3);

            originalNumber /= 10;

        }

 

        return result == number;

    }

}

Q.1.B


Define a class Product (pid, pname, price, qty). Write a function to accept the product details, display it and  calculate total amount. (use array of Objects)




import java.util.Scanner;

import java.io.*;

class Product {

    int pid;

    String pname;

    double price;

    int qty;

 

    public Product(int pid, String pname, double price, int qty) {

        this.pid = pid;

        this.pname = pname;

        this.price = price;

        this.qty = qty;

    }

 

    public double calculateTotal() {

        return price * qty;

    }

 

    public void displayProduct() {

        System.out.println("Product ID: " + pid);

        System.out.println("Product Name: " + pname);

        System.out.println("Price: $" + price);

        System.out.println("Quantity: " + qty);

    }

}

 

public class ProductDemo {

    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);

       

        System.out.print("Enter the number of products: ");

        int numProducts = scanner.nextInt();

       

        Product[] products = new Product[numProducts];

 

        for (int i = 0; i < numProducts; i++) {

            System.out.println("Enter details for product #" + (i + 1));

            System.out.print("Product ID: ");

            int pid = scanner.nextInt();

            scanner.nextLine(); // Consume newline

            System.out.print("Product Name: ");

            String pname = scanner.nextLine();

            System.out.print("Price: $");

            double price = scanner.nextDouble();

            System.out.print("Quantity: ");

            int qty = scanner.nextInt();

            products[i] = new Product(pid, pname, price, qty);

        }

 

        System.out.println("Product Details:");

        double totalAmount = 0;

 

        for (Product product : products) {

            product.displayProduct();

            double productTotal = product.calculateTotal();

            System.out.println("Total Amount for this product: $" + productTotal);

            totalAmount += productTotal;

            System.out.println();

        }

 

        System.out.println("Total Amount for all products: $" + totalAmount);

    }

}

Q.2.A


A) Write Python GUI program that takes input string and change letter to upper
case when a button is pressed.
import tkinter as tk
# Function to convert the input text to uppercase
def convert_to_uppercase():
 input_text = input_entry.get()
 uppercase_text = input_text.upper()
 output_label.config(text=uppercase_text)
# Create the main window
window = tk.Tk()
window.title("Uppercase Converter")
# Create a label to instruct the user
instruction_label = tk.Label(window, text="Enter a string:")
instruction_label.pack()
# Create an entry widget for input
input_entry = tk.Entry(window)
input_entry.pack()
# Create a button to trigger the conversion
convert_button = tk.Button(window, text="Convert to Uppercase",
command=convert_to_uppercase)
convert_button.pack()
# Create a label to display the result
output_label = tk.Label(window, text="")
output_label.pack()
# Start the Tkinter main loop
window.mainloop()

Q.2.B



B) Define a class Date (Day, Month, Year) with functions to accept and display it.
Accept date from user. Throw user defined exception “invalid Date Exception” if
the date is invalid.
class InvalidDateException(Exception):
 def __init__(self, message="Invalid Date"):
 self.message = message
 super().__init__(self.message)
class Date:
 def __init__(self, day, month, year):
 self.day = day
 self.month = month
 self.year = year
 def is_valid_date(self):
 if self.year < 1:
 return False
 if not 1 <= self.month <= 12:
 return False
 days_in_month = [0, 31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31]
 if self.year % 400 == 0 or (self.year % 100 != 0 and self.year % 4 == 0):
 days_in_month[2] = 29
 if not 1 <= self.day <= days_in_month[self.month]:
 return False
 return True
 def accept_date(self):
 try:
 self.day = int(input("Enter day: "))
 self.month = int(input("Enter month: "))
 self.year = int(input("Enter year: "))
 if not self.is_valid_date():
 raise InvalidDateException("Invalid Date Exception: The provided date is
invalid.")
 except ValueError:
 raise InvalidDateException("Invalid Date Exception: Please enter valid numeric
values for day, month, and year.")
 def display_date(self):
 print(f"Date: {self.day:02d}/{self.month:02d}/{self.year}")
try:
 my_date = Date(0, 0, 0) # Initialize with default values
 my_date.accept_date()
 my_date.display_date()
except InvalidDateException as e:
 print(e)
mainloop()

