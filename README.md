# Operating-System
Description of the variables and semaphores used are
We will intiliaze 3 binary semaphores mutex(1) wrt(1) and turn(1) and one integer variable readcount(0) 
• Semaphore
– turn – turn semaphore is used to coordinate access to the shared resource, ensuring that threads wait for their turn in a fair manner.
– mutex – mutual exclusion semaphore for updating readcount variable
– wrt - mutual exclusion semaphore for writers
– User by first or last reader enters or exists
• Initially
– mutex = 1, wrt = 1,turn=1.
– readcount = 0 // how many are reading
In this solution to make it starve free I have used the semaphore turn which is initialized to 1 initially for example if there are already 10 readers reading and
a writer arrives it will set turn to 0 but will not be able to write since wrt=0(readcount>0) but now if any other reader arrives it will not be able to read since 
turn=0 it will have to wait for all the readers to leave then after writer will leave setting turn=1 .
