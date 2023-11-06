
# FJP Practical Questions
* [Coding Questions](#coding)
* [Viva Questions](#tech) 
* [References](#ref)
____
<b name="coding">Coding questions</b><br/>

1. All assignment questions.

2. Find the missing element in an array (sorted consecutive positive integers).
3. Constructor overloading (call parameterized constructor through a default constructor).

class Box{
   int length,breadth,height,box_no;

   Box(){
       length = breadth = height = 0;
       System.out.println(length + " " + breadth + " " + height);
   }

   Box(int n){
       //calling a default constructor via a parameterized constructor
       this();
       box_no = n;
       System.out.println(length + " " + breadth + " " + height + " " + box_no );
   }

   Box(int l,int b, int h, int n){
       length = l;
       breadth = b;
       height = h;
       box_no =n;
       System.out.println(length + " " + breadth + " " + height + " " + box_no );
   }
}

public class Constructor_Overloading {
    public static void main(String arg[]){
        Box b1 = new Box();
        Box b2 = new Box(5);
        Box b3 = new Box(3,4,5,10);
    }
}

4. Swap 2 elements by passing an object as a reference.
5. Find and print duplicate elements in an array.
6. Hierarchical Inheritance.
7. Create a method to print a string in a mirrored form with a pipe '|' separator, for example: 'PICT | TCIP'.
8. Exception handling.

9. Input: "Hello world". Output: 21. Print pairs of characters in "world" that are lexicographically in order. For example, in "hello," 'e' and 'l' and 'l' and 'o' are in order, so the first number is 2. In the second word "world," 'o' and 'r' are in order, so it's 1.
10. Create a `swapnum` function.
   Input: `a = 'A', z = 'Z'`
   Output: `a = 'Z', z = 'A'`
11. Swapping of integers and float numbers.
12. Print "thread is running" by extending the Thread class.
13. Write a Java program where data is read from one file and should be written in another file line by line.
14. A class `Shape` is defined with two overloading constructors in it. Another class `Test` is partially defined, which inherits the class `Shape`. The class `Test` should include two overloading constructors as appropriate for some object instantiation shown in the main method. You should define the constructors using the superclass constructors. Also, override the method `calculate()` in `Test` to calculate the volume of the shape.
15. Find the distance between two points using the `Math` package.
    import java.util.Scanner;

public class Distance_between_2_points {
    public static void main(String arg[]){
        System.out.println("Enter two values to find the difference between: ");
        Scanner s = new Scanner(System.in);
        long d1 = s.nextLong();
        long d2 = s.nextLong();
        long result = Math.subtractExact((long) d1, (long) d2);
        System.out.println("Distance between two points: " + result);
    }
}

Let me know if you need further details or explanations on any of these tasks.

---
<b name="tech">Technical Interview Questions</b>
<br/>
<i><u name="dsalg">Data Structures and Algorithms</u></i>
- Write a program to pair groups of people into randomized pairs, assign leftover people to pairs to make a group of three.
- Given a set of users subscribed data and several updated data sorted by time, return a list of users whose subscribe status is changed after the update.
- Giving a list of the event name, occurrence, and business id. And return the business id with at least two event name, and has a greater number of the event than the average across all business. 
- How many times do strings in a list exist in three sentences? 
- Giving a list of the event name, occurrence, and business id. And return the business id with at least two event name, and has a greater number of the event than the average across all business.  
- Prefix Matching
- Find the median of restaurant's review rating scores
- Merge intervals. find keyword from the customers' review 
- Find out longest substring without duplicates in a string. 
- Top K frequent elements, how would you run it on multiple nodes
- Given a sequence of words, print all anagrams together 
- List manipulation using language of your preference
- two sum, then follow up with k sum. 
  

<i><u name="dbms">DBMS</u></i>
- Some questions about database principle and system design
<br>


<i><u name="os">Operating System</u></i>
- Should you encrypt and then compress, or compress and then encrypt? why?  
- All interviews had many UNIX specific trivia style questions which required knowledge of UNIX utilities and their options.  
- What happens when I hit submit on URL of a browser? (e.g. google.com on Safari).
- What port does an http server run on?
- Explain Servlet and JSP
- Given a list of IP address and corresponding hits, asked how to get the top 10 hit IP address
<br>

<i><u name="misc">Miscellaneous</u></i>
- One of the three servers is slow. What can be the possible reasons and how would you take care of these things? 
- How can you find all instances of a class
"'X' is a tool we use here internally, it does 'Y'. Here's some skeleton code, implement these requirements." 
- What changes would you like to make on Yelp website 
- Output one review for the business that is the most representative of all the other reviews. How would you evaluate your model 
- Explain Spring and Hibernate
- Projects and Internship
- Tell me about your recent project?


