# Generic Maximum Finder in Java

A simple, interactive Java console application that demonstrates the power of **Java Generics** and the `Comparable` interface to find the maximum element from various data types.

## 🚀 Features
* Uses a single **Generic Method** (`findMax`) to handle multiple data types.
* Supports **Integers**, **Doubles**, **Characters**, and **Strings**.
* Interactive command-line menu using `Scanner`.

---

## 🛠️ Code Implementation

```java
import java.util.Scanner;

class Maximum {

    // Generic function to find maximum
    public static <T Comparable<T extends>> T findMax(T[] arr) {
        T max = arr[0];

        for (T element : arr) {
            if (element.compareTo(max) > 0) {
                max = element;
            }
        }

        return max;
    }

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter number of elements: ");
        int n = sc.nextInt();

        System.out.println("Choose data type:");
        System.out.println("1. Integer");
        System.out.println("2. Double");
        System.out.println("3. Character");
        System.out.println("4. String");

        System.out.print("Enter choice: ");
        int choice = sc.nextInt();

        switch (choice) {

            case 1:
                Integer[] a = new Integer[n];
                System.out.println("Enter elements:");
                for (int i = 0; i < n; i++)
                    a[i] = sc.nextInt();
                System.out.println("Maximum Element = " + findMax(a));
                break;

            case 2:
                Double[] b = new Double[n];
                System.out.println("Enter elements:");
                for (int i = 0; i < n; i++)
                    b[i] = sc.nextDouble();
                System.out.println("Maximum Element = " + findMax(b));
                break;

            case 3:
                Character[] c = new Character[n];
                System.out.println("Enter elements:");
                for (int i = 0; i < n; i++)
                    c[i] = sc.next().charAt(0);
                System.out.println("Maximum Element = " + findMax(c));
                break;

            case 4:
                String[] d = new String[n];
                System.out.println("Enter elements:");
                for (int i = 0; i < n; i++)
                    d[i] = sc.next();
                System.out.println("Maximum Element = " + findMax(d));
                break;

            default:
                System.out.println("Invalid choice");
        }

        sc.close();
    }
}
