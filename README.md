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
