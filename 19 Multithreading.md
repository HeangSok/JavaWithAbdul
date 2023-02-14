Multiprogramming
- Multi-user
- Multi Tasking → Multithreading

- Thread Class // if you want a class to perform multithreading, you extend that class to **Thread** class
- Runnable Interface // if your class already extends to other class, and you want to use multthreading, you have to use Runnable Interface

**Note:** In Java, a class can extend to only one class

**Thread Class example:**

![image](https://user-images.githubusercontent.com/77439221/217709426-e3b9c553-e2f6-4d0d-a202-23fca579d437.png)


![image](https://user-images.githubusercontent.com/77439221/217709763-46359ef0-b81f-41cd-96de-19402c45132b.png)


**Runnable Interface example**

![image](https://user-images.githubusercontent.com/77439221/217710505-bb3d592f-1315-4a7b-aee1-af0699330020.png)

![image](https://user-images.githubusercontent.com/77439221/217710611-cd1bdef6-42d2-4fe4-88e8-cdb1676093d2.png)

````Java
package threadtest;

/*class MyThread extends Thread
{
    public void run()
    {
        int i=1;
        while(true)
        {
            System.out.println(i+"Hello");
            i++;
        }
    }
}*/

class MyRunnable implements Runnable
{
    public void run()
    {
        int i=1;
        while(true)
        {
            System.out.println(i+"Hello");
            i++;
        }
    }
}
public class ThreadTest //implements Runnable //extends Thread
{
    /*public void run()
    {
        int i=1;
        while(true)
        {
            System.out.println(i+"Hello");
            i++;
        }
    }*/
    
    public static void main(String[] args) {
        
        //MyThread t=new MyThread();
        //ThreadTest t=new ThreadTest();
        MyRunnable t=new MyRunnable();
        Thread th=new Thread(t);
        
        th.start();
        
        int i=1;
        while(true)
        {
            System.out.println(i+"World");
        }
        
    }
    
}

````


**Thread Class**:

![image](https://user-images.githubusercontent.com/77439221/218590466-7148e35b-f5e9-4c86-863c-d66d8d0f7fe0.png)


**Synchronization:**

**_Locking/Mutex_**
![image](https://user-images.githubusercontent.com/77439221/218613481-d1a895cc-2eca-4cfc-b34c-7b01ba0351fc.png)


**_Semaphor_e**
![image](https://user-images.githubusercontent.com/77439221/218613640-4e434406-020e-4762-8956-3fecdbbb72df.png)


**_Monitor_**
![image](https://user-images.githubusercontent.com/77439221/218613774-754b3961-1a23-4be9-bc68-39e0b67a9cb2.png)


**Monitor Example in Syncronization: **

````Java
package syncdemo;

class MyData
{
    synchronized public void display(String str)  // Monitor part; just use synchornized keyword
    {
            for(int i=0;i<str.length();i++)
            {
                 System.out.print(str.charAt(i));
                 try{Thread.sleep(100);}catch(Exception e){}
            }
        
    }
}

class MyThread1 extends Thread
{
    MyData d;
    public MyThread1(MyData d)
    {
        this.d=d;
    }
    
    public void run()
    {
        d.display("Hello World");
    }
            
    
}

class MyThread2 extends Thread
{
    MyData d;
    public MyThread2(MyData d)
    {
        this.d=d;
    }
    
    public void run()
    {
        d.display("Welcome All");
    }
            
    
}

public class SyncDemo 
{
    public static void main(String[] args) 
    {
        MyData data=new MyData();
        
        MyThread1 t1=new MyThread1(data);
        MyThread2 t2=new MyThread2(data);
        
        t1.start();
        t2.start();
        
        
    
    }    
}

````


