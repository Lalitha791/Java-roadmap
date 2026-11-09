sum += arr[i];                 // Sum
count++;                       // Counter
arr[i] == 0                    // Condition
arr[arr.length - 1]            // Last element
arr[arr.length - 1]++;         // Update last element


                                                                                        cloning array 
import java.util.Arrays;                                                               int[] copy = arr.clone();

Arrays.toString(arr);       // Print
Arrays.sort(arr);           // Sort
Arrays.equals(a, b);        // Compare
Arrays.copyOf(arr, 5);      // Copy
Arrays.fill(arr, 0);        // Fill
Arrays.binarySearch(arr, 5);// Search sorted array




In Java, arrays are a way to store multiple values of the same type in a single structure. Unlike other data structures, arrays have a fixed size once created. Elements can be assigned to an array or retrieved from it using an index. Java arrays use zero-based indexing: the first element's index is 0, the second element's index is 1, etc.

Here is the standard syntax for initializing an array:

type[] variableName = new type[size];

/ Declare array with explicit size (size is 2)
int[] twoInts = new int[2];

