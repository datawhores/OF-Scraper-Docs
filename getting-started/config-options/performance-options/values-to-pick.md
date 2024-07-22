# Values to Pick

## Note on values to pick

### Threads

* It's recommended to use **0 to 3 threads** for downloads.
  * **0 threads** means downloads will occur on the main program thread.
* Using a combination of console debug (or higher log levels) and download progress bars might benefit from more threads.
* However, in newer versions, the performance difference between different thread counts is usually minimal or non-existent.

### Sems

* It's recommended to limit total downloads across all threads to **around 15**
* This translates to **5 sems** if using 3 threads.
