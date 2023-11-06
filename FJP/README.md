
# FJP Practical Questions
* [Coding Questions](#coding)
* [Viva Questions](#tech) 
* [References](#ref)
____
<b name="coding">Coding questions</b><br/>

### Coding questions

1. **All assignment questions.**

2. **Find the missing element in an array (sorted consecutive positive integers).**

```java
import java.util.Scanner;

public class Smallest_Missing_Element {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        System.out.println("Enter no. of elements in an array: ");
        int num = s.nextInt();
        System.out.println("Enter the elements of your sorted array: ");
        int arr[] = new int[num];
        for (int i = 0; i < num; i++) {
            arr[i] = s.nextInt();
        }

        int count = 0;
        for (int i = 0; i < arr.length - 1; i++) {
            if ((arr[i + 1] - arr[i]) > 1) {
                if (count == 0) {
                    count = arr[i];
                    count++;
                }
            }
        }
        System.out.println(count);
    }
}
```

3. **Constructor overloading (call parameterized constructor through a default constructor).**

```java
class Box {
    int length, breadth, height, box_no;

    Box() {
        length = breadth = height = 0;
        System.out.println(length + " " + breadth + " " + height);
    }

    Box(int n) {
        // Calling a default constructor via a parameterized constructor
        this();
        box_no = n;
        System.out.println(length + " " + breadth + " " + height + " " + box_no);
    }

    Box(int l, int b, int h, int n) {
        length = l;
        breadth = b;
        height = h;
        box_no = n;
        System.out.println(length + " " + breadth + " " + height + " " + box_no);
    }
}

public class ConstructorOverloading {
    public static void main(String args[]) {
        Box b1 = new Box();
        Box b2 = new Box(5);
        Box b3 = new Box(3, 4, 5, 10);
    }
}
```

4. **Swap 2 elements by passing an object as a reference.**

```java
class Exam {
    int marks = 0;

    Exam(int m) {
        marks = m;
    }
}

class Operation {
    int temp = 0;

    public void swap(Exam e1, Exam e2) {
        temp = e1.marks;
        e1.marks = e2.marks;
        e2.marks = temp;
    }
}

public class SwapElementsRef {
    public static void main(String arg[]) {
        Exam e1 = new Exam(65);
        Exam e2 = new Exam(33);
        Operation o = new Operation();
        o.swap(e1, e2);
        System.out.println(e1.marks);
        System.out.println(e2.marks);
    }
}
```

5. **Find and print duplicate elements in an array.**

```java
import java.util.Scanner;

public class DuplicateElements {
    public static void main(String arg[]) {
        Scanner s = new Scanner(System.in);
        System.out.println("Enter no. of elements in an array: ");
        int num = s.nextInt();
        System.println("Enter the elements of your sorted array: ");
        int arr[] = new int[num];
        for (int i = 0; i < num; i++) {
            arr[i] = s.nextInt();
        }

        // for duplicate elements
        for (int i = 0; i < arr.length - 1; i++) {
            for (int j = i + 1; j < arr.length - 1; j++) {
                if (arr[i] == arr[j]) {
                    System.out.println(arr[j]);
                }
            }
        }
    }
}
```

6. **Hierarchical Inheritance.**

```java
class Shape {
    int radius;
    int length, breadth;

    public void display() {
        System.out.println("This is a shape.");
    }
}

class Circle extends Shape {
    public void area(int r) {
        radius = r;
        System.out.println("Area: " + (Math.PI * radius * radius));
    }
}

class Rectangle extends Shape {
    public void area(int l, int b) {
        length = l;
        breadth = b;
        System.out.println("Area: " + (length * breadth));
    }
}

public class HierarchicalInheritance {
    public static void main(String arg[]) {
        Circle c = new Circle();
        c.display();
        c.area(5);
        Rectangle r = new Rectangle();
        r.display();
        r.area(5, 9);
    }
}
```

7. **Create a method to print a string in a mirrored form with a pipe '|' separator, for example: 'PICT | TCIP'.**

```java
import java.util.Scanner;

class Reverse {
    public void reverse(String str) {
        // Reverse the String
        char c;
        String str1 = "";
        for (int i = 0; i < str.length(); i++) {
            c = str.charAt(i);
            str1 = c + str1;
        }

        System.out.println(str + " | " + str1);
    }
}

public class MirroredString {
    public static void main(String arg[]) {
        Scanner s = new Scanner(System.in);
        System.out.println("Enter the string: ");
        String str = s.nextLine();
        Reverse r = new Reverse();
        r.reverse(str);
    }
}
```

8. **Exception handling.**

```java
import java.util.Scanner;

public class ExceptionHandling {
    public static void main(String arg[]) {
        Scanner s = new Scanner(System.in);
        int arr[] = new int[2];
        System.out.println("Enter two numbers: ");
        arr[0] = s.nextInt();
        arr[1] = s.nextInt();

        try {
            int result = arr[0] / (5 - arr[2]);
            System.out.println(result);
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Wrong index of array.");
        } catch (ArithmeticException e) {
            System.out.println("Divide by zero is not possible.");
        } finally {
            System.out.println("All possible operations are completed.");
        }
    }
}
```

9. **Input: "Hello world". Output: 21.** Print pairs of characters in "world" that are lexicographically in order. For example, in "hello," 'e' and 'l' and 'l' and 'o' are in order, so the first number is 2. In the second word "world," 'o' and 'r' are in order, so it's 1.

```java
import java.util.Scanner;

public class LexicographicalOrder {
    public static void main(String arg[]) {
        Scanner s = new Scanner(System.in);
        System.out.println("Enter the string: ");
        String str = s.nextLine();
        int num = str.indexOf(" ");
        String str1 = str.substring(0, num);
        String str2 = str.substring(num + 1);

        String c1

, c2;
        int result1;
        int count1 = 0;
        for (int i = 0; i < str1.length() - 1; i++) {
            c1 = String.valueOf(str1.charAt(i));
            c2 = String.valueOf(str1.charAt(i + 1));
            result1 = c1.compareToIgnoreCase(c2);
            if (result1 < 0) {
                count1++;
            }
        }

        int result2;
        int count2 = 0;
        for (int i = 0; i < str2.length() - 1; i++) {
            c1 = String.valueOf(str2.charAt(i));
            c2 = String.valueOf(str2.charAt(i + 1));
            result2 = c1.compareToIgnoreCase(c2);
            if (result2 < 0) {
                count2++;
            }
        }

        System.out.println(count1 + "" + count2);
    }
}
```

10. **Create a `swapnum` function.**

   Input: `a = 'A', z = 'Z'`
   Output: `a = 'Z', z = 'A'`

```java
import java.util.Scanner;

public class SwapNumber {
    public static void swapnum(int a, int b, float c, float d) {
        // between a and c
        float temp1;
        temp1 = a;
        a = (int) c;
        c = temp1;

        // between b and d
        float temp2;
        temp2 = b;
        b = (int) d;
        d = temp2;

        System.out.println("After swapping: ");
        System.out.println("integer 1 = " + a);
        System.out.println("integer 2 = " + b);
        System.out.println("float 1 = " + c);
        System.out.println("float 2 = " + d);
    }

    public static void main(String arg[]) {
        int a, b;
        float c, d;
        Scanner s = new Scanner(System.in);
        System.out.println("Enter two integer values: ");
        a = s.nextInt();
        b = s.nextInt();
        System.out.println("Enter two float values: ");
        c = s.nextFloat();
        d = s.nextFloat();

        swapnum(a, b, c, d);
    }
}
```

11. **Swapping of integers and float numbers.**

12. **Print "thread is running" by extending the Thread class.**

```java
class MyThread extends Thread {
    public void run() {
        System.out.println("Thread is running");
    }
}

public class Multithreading {
    public static void main(String arg[]) {
        MyThread t = new MyThread();
        t.start();
    }
}
```

13. **Write a Java program where data is read from one file and should be written in another file line by line. (File Handling)**

```java
import java.io.File;
import java.io.FileWriter;
import java.io.IOException;
import java.util.Scanner;

public class FileHandling {
    public static void main(String arg[]) throws IOException {
        File f1 = new File("Demo1.txt");
        if (!f1.createNewFile()) {
            f1.delete();
            f1.createNewFile();
        }
        FileWriter fout = new FileWriter(f1);
        fout.write("All the best for your JAVA practical!");
        fout.close();
        Scanner fin = new Scanner(f1);
        File f2 = new File("Demo2.txt");
        if (!f2.createNewFile()) {
            f2.delete();
            f2.createNewFile();
        }
        fout = new FileWriter(f2);
        while (fin.hasNextLine()) {
            String data = fin.nextLine();
            fout.write(data);
        }
        fin.close();
        fout.close();
    }
}
```

14. **A class `Shape` is defined with two overloading constructors in it. Another class `Test` is partially defined, which inherits the class `Shape`. The class `Test` should include two overloading constructors as appropriate for some object instantiation shown in the main method. You should define the constructors using the superclass constructors. Also, override the method `calculate()` in `Test` to calculate the volume of the shape.**

15. **Find the distance between two points using the `Math` package.**

```java
import java.util.Scanner;

public class DistanceBetweenPoints {
    public static void main(String arg[]) {
        System.out.println("Enter two values to find the difference between: ");
        Scanner s = new Scanner(System.in);
        long d1 = s.nextLong();
        long d2 = s.nextLong();
        long result = Math.subtractExact((long) d1, (long) d2);
        System.out.println("Distance between two points: " + result);
    }
}
```

I've formatted your code to make it more readable and structured in Markdown. You can copy and paste this into your document.
Let me know if you need further details or explanations on any of these tasks.

---
<b name="tech">Viva Questions</b>
<br/>

* **Java Programming:**

    1. How is user input obtained in Java, and why is the `Scanner` class commonly used?
    2. Explain the purpose of constructors in Java and their role in object creation.
    3. What is the difference between a default constructor and a parameterized constructor?
    4. In the "Swap_elements_ref" code, how does the `swap` method swap the marks of two `Exam` objects?
    5. What is the significance of the `Operation` class in the "Swap_elements_ref" code?
    6. How is exception handling implemented in Java, and what are the primary exception types?
    7. Describe the role of the `Math` class in Java and how it is used in the code for finding the distance between two points.
    8. In the "Mirrored_String" code, how is the string reversed, and what is the purpose of the pipe separator?
    9. Explain the concept of hierarchical inheritance and how it is demonstrated in the "Hierarchical_inheritance" code.
    10. What is the output of the "Multithreading" code when executed?

* **Code Analysis:**

    11. In the "Smallest_Missing_Element" code, how does it find the missing element in a sorted array, and what is the time complexity?
    12. How is constructor chaining achieved in the "ConstructorOverloading" code, and what is the order of constructor invocation?
    13. In the "Duplicate_elements" code, how does it identify and print duplicate elements in an array?
    14. Describe the difference between method overloading and constructor overloading.
    15. In the "Lexicographical_order" code, how are pairs of characters that are in lexicographical order counted?
    16. What is the output of the "SwapNumber" code when provided with input values?
    17. How does method overriding work, and what is the purpose of the `@Override` annotation?
    18. Explain the purpose of the `super` keyword in Java, as seen in the "Hierarchical_inheritance" code.
    19. What is the purpose of file handling in Java, and how is it demonstrated in the "FileHandling" code?
    20. In the "Multithreading" code, how is multithreading implemented using the `Thread` class?

* **Object-Oriented Programming:**

    21. Discuss the key principles of object-oriented programming (OOP) and how they are applied in Java.
    22. Explain the concept of encapsulation and how it relates to classes and objects.
    23. How are objects created and initialized in Java, and what is the role of constructors?
    24. Describe the advantages of inheritance in OOP, and how is it achieved in the code examples?
    25. What is the purpose of polymorphism in OOP, and how is it demonstrated in the code?
    26. In the "Swap_elements_ref" code, how are objects passed by reference, and what happens during the swap?
    27. What are the characteristics of a subclass in the context of inheritance?
    28. Explain the concept of method overriding and how it contributes to code extensibility.
    29. What is the significance of the `extends` keyword in Java, and how is it used in class inheritance?
    30. In the "FileHandling" code, how are exceptions related to file operations handled?

* **File Handling:**

    31. What is the role of file handling in software development, and why is it important?
    32. How are files created and written to in Java, as demonstrated in the "FileHandling" code?
    33. What are the common exceptions that can occur during file operations, and how can they be managed?
    34. Explain the purpose of the `File` class in Java and its role in file-related operations.
    35. In the "FileHandling" code, how is the creation of a file ensured if it does not exist?
    36. Describe the difference between character-based and byte-based file handling in Java.
    37. How is file reading accomplished in Java, and what classes are typically used for this purpose?
    38. What is the `FileWriter` class used for, and how is it applied in the code for writing to files?
    39. What is the role of the `Scanner` class in reading from files, and what methods does it provide?
    40. In the "FileHandling" code, how are the contents of one file transferred to another file?

* **General Programming Concepts:**

    41. Explain the significance of code reusability in software development and how it is achieved in Java.
    42. What is the purpose of comments in code, and how do they contribute to code readability and documentation?
    43. Describe the importance of error handling and exception management in software development.
    44. How are data types used in Java programs, and what are their primary categories?
    45. How can code readability and maintainability be improved through proper naming conventions?
    46. Explain the concept of code modularity and its advantages in software development.
    47. What is multithreading, and how does it differ from single-threading in terms of execution?
    48. Discuss the role of the `Math` class in performing mathematical operations in Java programs.
    49. How does object-oriented programming differ from procedural programming, and what are the advantages?
    50. What are the key principles of object-oriented programming, and how are they demonstrated in the code examples?

These additional viva questions provide further coverage of Java programming concepts and code analysis topics based on the provided code examples.

