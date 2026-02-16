# Additional_exp4
## Title:To check if a number is a perfect number
## Source code:
``` java
import java.util.Scanner;
class PerfectNumber {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        // Input number
        System.out.print("Enter a positive integer: ");
        int num = sc.nextInt();
        int sum = 0;
        // Find sum of proper divisors
        for (int i = 1; i <= num - 1; i++) {
            if (num % i == 0) {
                sum = sum + i;
            }
        }
        // Check perfect number
        if (sum == num) {
            System.out.println(num + " is a perfect number");
        } else {
            System.out.println(num + " is not a perfect number");
        }
        sc.close();
    }
}
```
## output:
![output of addexp4](addexp4.png)
