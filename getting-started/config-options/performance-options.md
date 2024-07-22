---
description: 'N'
---

# Performance Options





## threads

The count of threads or workers designated for downloading

```
min=0
max=system
```

0 threads: This is a special setting indicating that you want to use the main program thread for downloading as well\


### Caveats

* It's important to note that if the thread count exceeds 0 but the number of downloads for a model doesn't equal or surpass 5 downloads per thread, only the main thread will handle the downloading process.
*   Additionally, the maximum number of usable threads is determined by your system, irrespective of the configuration file settings.



    * &#x20;on Windows and Linux The number of unused threads is provided.&#x20;
    * However, on Mac, the operating system lacks this specific OS API, so the maximum is established as the total number of threads on the system



***

## download-sems

Max concurrent number of downloads per thread

If threads is the number of workers for downloading, then download-sems is the number of tasks each worker can process at a time.



## Note on values to pick

### Threads

* It's recommended to use **0 to 3 threads** for downloads.
  * **0 threads** means downloads will occur on the main program thread.
* Using a combination of console debug (or higher log levels) and download progress bars might benefit from more threads.
* However, in newer versions, the performance difference between different thread counts is usually minimal or non-existent.

### Sems

* It's recommended to limit total downloads across all threads to **around 15**
* This translates to **5 sems** if using 3 threads.

\
