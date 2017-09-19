# Leak report

The memory errors are ocurring due to line 41 allocating space to the variable result, without ever freeing the space afterwords. By not freeing the space afterwords, a memory leak is created that will cause the computer to continuously allocate space that isn't freed each time the program is run. This will eventually slow the computer down.

To fix this, I added an if statement on lines 72 - 74 that first checks if cleaned actually exists (because if it doesn't exist, no memory will be allocated, and thus freeing memory that doesn't exist will create an error). After checking that cleaned exists, the if loop frees the memory that has been allocated. 

Everything now works...I hope. 
