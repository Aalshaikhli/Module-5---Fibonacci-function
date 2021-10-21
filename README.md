# Module-5---Fibonacci-function

/**
 * 
 */
// package fib;

/**
 * Implementation of fibonanci using iterative approach
 *
 */

public class Fibonanci {

	/**
	 * main Iterative class
	 */
	
	public int iterative(int n) {
		/*
		 * Time complexity - O(n)
		 * Space complexity - O(1)
		 */
		int fib = 0, j = 1;
		int swap; // swap element
		if(n <= 1) {
			// return if value of n less than 1
			return n;
		}
		// swap elements
		
		for(int i = 0; i < n; i++) {
			swap = fib;
			fib += j;
			j = swap;
		}
		// return fib
		return fib;
	}
	
	public int recursive(int n) {
		/*
		 * Time complexity - O(n)
		 * Space complexity - O(n)
		 */
		 if (n <= 1)
		        return n;
		    return recursive(n-1) + recursive(n-2);
	}

	/**
	 * @param args
	 */
	
	// main method
	public static void main(String[] args) {
		// method instantiation
		Fibonanci fib = new Fibonanci();
		int n = 10;
		for(int i = 0; i < n; i++) {
			// iterative
			System.out.println("\nIterative \n");
			long startTime = System.nanoTime();
			System.out.println(fib.iterative(i));
			long endTime = System.nanoTime();
			long finalTime = endTime - startTime;
			System.out.println(String.format("\nX %d : Y %d", i, finalTime));
			
			// recursive
			System.out.println("\nRecursive \n");
		    long startTime1 = System.nanoTime();
			System.out.println(fib.recursive(i));
			long endTime1 = System.nanoTime();
			long finalTime1 = endTime1 - startTime1;
			System.out.println(String.format("\nX %d : Y %d", i, finalTime1));
		}

	}

}
