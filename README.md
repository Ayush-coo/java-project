# java-project
public class BubbleSort {

    public static void main(String[] args) {
        int[] arr = {64, 34, 25, 12, 22, 11, 90};

        bubbleSort(arr);

        System.out.println("Sorted array");
        printArray(arr);
    }

    static void bubbleSort(int[] arr) {
        int n = arr.length;
        for (int i = 0; i < n - 1; i++)
            for (int j = 0; j < n - i - 1; j++)
                if (arr[j] > arr[j + 1]) {
                    // swap arr[j] and arr[j+1]
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                }
    }

    static void printArray(int arr[]) {
        int n = arr.length;
        for (int i = 0; i < n; ++i)
            System.out.print(arr[i] + " ");
        System.out.println();
    }
}
2. Implementing a Simple Linked List

Java

public class LinkedList {

    static class Node {
        int data;
        Node next;

        Node(int d) {
            data = d;
            next = null;
        }
    }

    Node head; // head of list

    LinkedList() {
        head = null;
    }

    // Method to insert a new node
    public void push(int new_data) {
        // 1 & 2: Allocate the Node &
        // Put in the data
        Node new_node = new Node(new_data);

        // 3. Make next of new Node as head
        new_node.next = head;

        // 4. Move the head to point to the new Node
        head = new_node;
    }

    // This function prints contents of
    // linked list starting from the
    // given node
    public void printList() {
        Node n = head;
        while (n != null) {
            System.out.print(n.data + " ");
            n = n.next;
        }
    }

    public static void main(String[] args) {
        LinkedList llist = new LinkedList();
        llist.push(7);
        llist.push(1);
        llist.push(3);
        llist.push(2);

        System.out.println("\nCreated Linked list is: ");
        llist.printList();
    }
}
3. Finding the Largest Element in an Array

Java

public class FindLargest {

    public static int findLargest(int[] arr) {
        int n = arr.length;
        int largest = arr[0];

        for (int i = 1; i < n; i++) {
            if (arr[i] > largest) {
                largest = arr[i];
            }
        }

        return largest;
    }

    public static void main(String[] args) {
        int[] arr = {10, 32, 45, 90, 20};
        System.out.println("Largest in given array is " + findLargest(arr));
    }
}
public class Stack {

    private int arr[];
    private int top;
    private int capacity;

    // Constructor to initialize stack
    Stack(int size) {
        arr = new int[size];
        capacity = size;
        top = -1;
    }

    // Utility function to check if stack is empty
    public boolean isEmpty() {
        return (top == -1);
    }

    // Utility function to check if stack is full
    public boolean isFull() {
        return (top == capacity - 1);
    }

    // Function to add an item to stack. It increases
    // top by 1
    public void push(int item) {
        if (isFull()) {
            System.out.println("Stack Overflow");
            System.exit(1);
        }

        System.out.println("Pushing item: " + item);
        arr[++top] = item;
    }

    // Function to remove an item from stack. It
    // decreases top by 1
    public int pop() {
        if (isEmpty()) {
            System.out.println("Stack Underflow");
            System.exit(1);
        }

        System.out.println("Popping item: " + arr[top]);
        return arr[top--];
    }

    // Function to get the top element of stack
    public int peek() {
        if (isEmpty()) {
            System.out.println("Stack is Empty");
            System.exit(1);
        }
        return arr[top];
    }

    public static void main(String[] args) {
        Stack stack = new Stack(1000);
        stack.push(10);
        stack.push(20);
        stack.push(30);
        System.out.println(stack.pop() + " Popped from stack");
        System.out.println("Top element is: " + stack.peek());
    }
}
2. Implementing a Binary Search

Java

public class BinarySearch {

    // Returns index of x if it is present in arr[],
    // else return -1
    public static int binarySearch(int arr[], int x) {
        int l = 0, r = arr.length - 1;
        while (l <= r) {
            int m = l + (r - l) / 2;

            // Check if x is present at mid
            if (arr[m] == x)
                return m;

            // If x greater, ignore left half
            if (arr[m] < x)
                l = m + 1;

            // If x is smaller, ignore right half
            else
                r = m - 1;
        }

        // If we reach here, the element was not present
        return -1;
    }

    // Driver method to test above
    public static void main(String args[]) {
        int arr[] = { 2, 3, 4, 10, 40 };
        int x = 10;
        int result = binarySearch(arr, x);
        if (result == -1)
            System.out.println("Element not present");
        else
            System.out.println("Element found at index " + result);
    }
}
3. Implementing a Simple Queue

Java

import java.util.LinkedList;
import java.util.Queue;

public class QueueExample {

    public static void main(String[] args) {
        // Create a queue for integers
        Queue<Integer> queue = new LinkedList<>();

        // Add elements to the queue
        queue.add(10);
        queue.add(20);
        queue.add(30);

        // Print the queue
        System.out.println("Queue: " + queue);

        // Remove the head of the queue
        int removed = queue.remove();
        System.out.println("Removed element: " + removed);

        // Print the queue after removal
        System.out.println("Queue after removal: " + queue);

        // Check if the queue is empty
        System.out.println("Is queue empty? " + queue.isEmpty());

        // Get the size of the queue
        System.out.println("Size of queue: " + queue.size());

        // Peek at the head of the queue without removing it
        int head = queue.peek();
        System.out.println("Head of queue: " + head);
    }
}
import java.util.Scanner;

public class StringManipulation {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter a string: ");
        String inputString = scanner.nextLine();

        // 1. Convert to uppercase
        String uppercaseString = inputString.toUpperCase();
        System.out.println("Uppercase: " + uppercaseString);

        // 2. Convert to lowercase
        String lowercaseString = inputString.toLowerCase();
        System.out.println("Lowercase: " + lowercaseString);

        // 3. Find the length of the string
        int length = inputString.length();
        System.out.println("Length: " + length);

        // 4. Check if the string is empty
        boolean isEmpty = inputString.isEmpty();
        System.out.println("Is Empty: " + isEmpty);

        // 5. Check if the string starts with a specific character
        boolean startsWithA = inputString.startsWith("A");
        System.out.println("Starts with 'A': " + startsWithA);

        // 6. Check if the string ends with a specific character
        boolean endsWithZ = inputString.endsWith("z");
        System.out.println("Ends with 'z': " + endsWithZ);

        // 7. Find the index of a specific character
        int indexOfE = inputString.indexOf('e');
        System.out.println("Index of 'e': " + indexOfE);

        // 8. Replace a character
        String replacedString = inputString.replace('a', 'o');
        System.out.println("Replaced 'a' with 'o': " + replacedString);

        // 9. Extract a substring
        String substring = inputString.substring(2, 5);
        System.out.println("Substring (from index 2 to 4): " + substring);

        // 10. Split the string into an array of words
        String[] words = inputString.split(" ");
        System.out.println("Words in the string:");
        for (String word : words) {
            System.out.println(word);
        }

        scanner.close();
    }
}
public class Example {

    // A simple method to calculate the factorial of a number
    public static int factorial(int n) {
        if (n == 0 || n == 1) {
            return 1;
        }
        return n * factorial(n - 1);
    }

    // A simple method to check if a number is prime
    public static boolean isPrime(int num) {
        if (num <= 1) {
            return false;
        }
        for (int i = 2; i <= Math.sqrt(num); i++) {
            if (num % i == 0) {
                return false;
            }
        }
        return true;
    }

    // A method to print Fibonacci series up to n terms
    public static void printFibonacci(int n) {
        int t1 = 0, t2 = 1;
        System.out.print("Fibonacci Series: " + t1 + ", " + t2);

        for (int i = 2; i < n; i++) {
            int sum = t1 + t2;
            System.out.print(", " + sum);
            t1 = t2;
            t2 = sum;
        }
        System.out.println();
    }

    // A method to reverse a string
    public static String reverseString(String str) {
        StringBuilder reversed = new StringBuilder();
        for (int i = str.length() - 1; i >= 0; i--) {
            reversed.append(str.charAt(i));
        }
        return reversed.toString();
    }

    // A method to find the largest number in an array
    public static int findLargest(int[] numbers) {
        int max = numbers[0];
        for (int num : numbers) {
            if (num > max) {
                max = num;
            }
        }
        return max;
    }

    // A method to sort an array using bubble sort
    public static void bubbleSort(int[] arr) {
        int n = arr.length;
        for (int i = 0; i < n - 1; i++) {
            for (int j = 0; j < n - i - 1; j++) {
                if (arr[j] > arr[j + 1]) {
                    // Swap arr[j] and arr[j+1]
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                }
            }
        }
    }

    // A method to find the GCD of two numbers
    public static int findGCD(int a, int b) {
        while (b != 0) {
            int temp = b;
            b = a % b;
            a = temp;
        }
        return a;
    }

    // A method to calculate the power of a number
    public static double power(double base, int exponent) {
        double result = 1;
        for (int i = 0; i < Math.abs(exponent); i++) {
            result *= base;
        }
        return exponent < 0 ? 1 / result : result;
    }

    // A method to count vowels in a string
    public static int countVowels(String str) {
        int count = 0;
        for (char c : str.toLowerCase().toCharArray()) {
            if ("aeiou".indexOf(c) != -1) {
                count++;
            }
        }
        return count;
    }

    // A method to check if a string is a palindrome
    public static boolean isPalindrome(String str) {
        String reversed = reverseString(str);
        return str.equalsIgnoreCase(reversed);
    }

    public static void main(String[] args) {
        // Test factorial method
        int number = 5;
        System.out.println("Factorial of " + number + " is: " + factorial(number));

        // Test isPrime method
        int primeCheck = 29;
        System.out.println(primeCheck + " is prime: " + isPrime(primeCheck));

        // Test Fibonacci series
        int fibonacciTerms = 10;
        printFibonacci(fibonacciTerms);

        // Test reverseString method
        String original = "Hello, World!";
        System.out.println("Reversed String: " + reverseString(original));

        // Test findLargest method
        int[] numbers = {34, 78, 12, 45, 89, 23};
        System.out.println("Largest number in array: " + findLargest(numbers));

        // Test bubbleSort method
        System.out.print("Original Array: ");
        for (int num : numbers) {
            System.out.print(num + " ");
        }
        System.out.println();

        bubbleSort(numbers);
        System.out.print("Sorted Array: ");
        for (int num : numbers) {
            System.out.print(num + " ");
        }
        System.out.println();

        // Test GCD method
        int a = 56, b = 98;
        System.out.println("GCD of " + a + " and " + b + " is: " + findGCD(a, b));

        // Test power method
        double base = 2.0;
        int exponent = 3;
        System.out.println(base + " to the power of " + exponent + " is: " + power(base, exponent));

        // Test countVowels method
        String text = "This is a simple text.";
        System.out.println("Number of vowels in text: " + countVowels(text));

        // Test isPalindrome method
        String palindromeCandidate = "Madam";
        System.out.println("Is '" + palindromeCandidate + "' a palindrome? " + isPalindrome(palindromeCandidate));
    }

}
import java.util.Scanner;
import java.util.Random;

public class Example {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Random random = new Random();
        
        System.out.println("Welcome to the Guess the Number Game!");
        System.out.println("I have selected a number between 1 and 100. Try to guess it.");

        int targetNumber = random.nextInt(100) + 1;
        int attempts = 0;
        boolean hasWon = false;

        while (!hasWon) {
            System.out.print("Enter your guess: ");
            int playerGuess = scanner.nextInt();
            attempts++;

            if (playerGuess == targetNumber) {
                hasWon = true;
                System.out.println("Congratulations! You guessed the number in " + attempts + " attempts.");
            } else if (playerGuess < targetNumber) {
                System.out.println("Too low! Try again.");
            } else {
                System.out.println("Too high! Try again.");
            }
        }

        System.out.println("Would you like to play another game? (yes/no): ");
        String playAgain = scanner.next();

        if (playAgain.equalsIgnoreCase("yes")) {
            main(null); // Restart the game
        } else {
            System.out.println("Thank you for playing! Goodbye.");
        }

        scanner.close();
    }

}
