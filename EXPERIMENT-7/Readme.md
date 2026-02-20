# EXPERIMENT-7
## 7.A.Creation of User Defined Exception
## Source code:
``` java
import java.util.Scanner;

// Custom Exception Class
class InvalidCountryException extends Exception {

    // Default Constructor
    InvalidCountryException() {
        super();
    }

    // Parameterized Constructor
    InvalidCountryException(String message) {
        super(message);
    }
}

// User Registration Class
class UserRegistration {

    void registerUser(String username, String userCountry) 
            throws InvalidCountryException {

        if (!userCountry.equalsIgnoreCase("India")) {
            throw new InvalidCountryException(
                "User outside India cannot be registered."
            );
        } else {
            System.out.println("User registered successfully.");
        }
    }
}

// Main Class
public class  UserRegion {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        try {
            System.out.print("Enter the user name: ");
            String uname = sc.nextLine();

            System.out.print("Enter the country name: ");
            String ucountry = sc.nextLine();

            UserRegistration ur = new UserRegistration();
            ur.registerUser(uname, ucountry);

        } 
        catch (InvalidCountryException e) {
            System.out.println(e.getMessage());
        } 
        catch (Exception e) {
            System.out.println("Unknown error: " + e);
        } 
        finally {
            sc.close();
            System.out.println("Finally block executed successfully.");
            System.out.println("Program terminated properly.");
        }
    }
}
```
## output:
![output of 7a](7a.png)

## 7.B.Creates threads by extending thread class
## Source code:
``` java
// Thread 1
class GoodMorningThread extends Thread
{
    public void run()
    {
        try
        {
            while(true)
            {
                System.out.println("Good Morning");
                Thread.sleep(1000);
            }
        }
        catch(InterruptedException e)
        {
            System.out.println(e);
        }
    }
}

// Thread 2
class HelloThread extends Thread
{
    public void run()
    {
        try
        {
            while(true)
            {
                System.out.println("Hello");
                Thread.sleep(2000);
            }
        }
        catch(InterruptedException e)
        {
            System.out.println(e);
        }
    }
}

// Thread 3
class WelcomeThread extends Thread
{
    public void run()
    {
        try
        {
            while(true)
            {
                System.out.println("Welcome");
                Thread.sleep(3000);
            }
        }
        catch(InterruptedException e)
        {
            System.out.println(e);
        }
    }
}

// Main class
public class TestThreads
{
    public static void main(String[] args)
    {
        GoodMorningThread t1 = new GoodMorningThread();
        HelloThread t2 = new HelloThread();
        WelcomeThread t3 = new WelcomeThread();

        t1.start();
        t2.start();
        t3.start();
    }
}
```
## output:
![output of 7b](7b.png)

## 7.C.illustrating is Alive and join().Scenario
## Source code:
``` java
// Long running task thread
class LongRunningTask extends Thread
{
    public void run()
    {
        try
        {
            System.out.println("Long running task started...");
            for(int i = 1; i <= 5; i++)
            {
                System.out.println("Working... " + i);
                Thread.sleep(1000);
            }
            System.out.println("Long running task completed!");
        }
        catch(InterruptedException e)
        {
            System.out.println(e);
        }
    }
}

// Main class
public class ThreadDemo
{
    public static void main(String[] args)
    {
        LongRunningTask task1 = new LongRunningTask();

        System.out.println("Before starting task1: " + task1.isAlive());

        task1.start();

        System.out.println("After starting task1: " + task1.isAlive());

        try
        {
            System.out.println("Main thread waiting for task1 to complete using join()...");
            task1.join();
        }
        catch(InterruptedException e)
        {
            System.out.println(e);
        }

        System.out.println("After join(): " + task1.isAlive());
        System.out.println("Main thread continues after task1 completed");
    }
}
```
## output :
![output of 7c](7c.png)
