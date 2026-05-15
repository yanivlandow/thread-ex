Task 3
The output is less than 20,000 due to a race condition. The bar++ operation is not atomic, so both threads access and modify the variable at the same time, causing some increments to be lost or overwritten.

Task 4
Adding the synchronized keyword to the method locks the entire method. This prevents the threads from interfering with each other, so the result is exactly 20,000.

Task 5
Using synchronized(this) only locks the critical section (the specific block of code) instead of the whole method. The result is still 20,000, but it is better practice because it improves performance in larger methods by reducing unnecessary waiting.

Task 6
The code runs very fast because there are no locks (synchronized) slowing it down. However, because 10 threads are running concurrently without synchronization, there is a massive race condition and the final output is completely wrong.

Task 7
The final output is exactly correct (100,000,000) because the synchronized(this) block ensures thread safety. However, the execution time is significantly longer because the threads constantly have to wait for the lock to be released before they can increment the variable.
