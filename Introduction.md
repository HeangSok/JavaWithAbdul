![image](https://user-images.githubusercontent.com/77439221/212803025-6e42c0fc-8898-49c7-a978-f80114d4648a.png)

![image](https://user-images.githubusercontent.com/77439221/212803553-da35bfc5-6491-4841-bf91-445791c95ec4.png)



````Java

import java.lang.*;

public class MyFirst {

    public static void main(String arg[]) {
       System.out.println("Hello World");
       System.out.println(arg[0]);
    }
    
}
# public: if you want this method to be accessed from anywhere use public
# static: if we want to use anything from the class without creating an object, we use static. It is just like the concept of "static" in Swift when we work with "Struct".
# if it is static we can execute just by using the class name.
# void: it is a return type; since we don't return anything we use void
# main: is a method
# (String arg[]): it is command line argument; In Java, though we use it or not, we must have it

````

**Reading from Keyboard**

_Class Scanner_:
- nextInt()
- nextFloat()
- nextDouble()
- next() # read only one word - String
- nextLine() # read a line of words - String
- nextByte()
- nextShort
- nextLong()
- nextBoolean()
- hasNextInt()
- hasNextFloat()

Example1:
````Java
package readkeyboard;

import java.util.*;

public class ReadKeyboard {

    public static void main(String[] args) {
        Scanner sc=new Scanner(System.in);
        
        //int  x=sc.nextInt();
        //float x=sc.nextFloat();
        //String x=sc.nextLine();
        
        int x,y;
        System.out.println("Eneter 2 numbers: ");
        x=sc.nextInt();
        y=sc.nextInt();
        
        int z=x+y;
        System.out.println("Sum is "+z);
        
        
        /*sc.useRadix(2); // this line take the input of binary type (base 2)
        int x=sc.nextInt();
        System.out.println(x); // it prints in base 10
        */
    }
    
}
````

Example2:
````Java

package first;

import java.util.*;

public class First {

    public static void main(String[] args) {
        String name;
        
        Scanner sc=new Scanner(System.in);
        System.out.println("May I know your Name: ");
        name=sc.nextLine();
        
        System.out.println("Welcome "+name);
    }
    
}

````
use **Javap** to show all the method of a Class: javap java.util.Scanner
<img width="1016" alt="image" src="https://user-images.githubusercontent.com/77439221/213258520-f2b6ef75-bace-47ad-8bfa-7cb4b58ff813.png">
