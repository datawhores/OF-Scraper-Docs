# Performance Options

## thread\_count

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

If threads is the number of workers for downloading, then download-sems is the number of tasks each worker can process at a time

***

## download\_limit

Maximum download speed per second for  each thread

**Accepts**&#x20;

* human readable inputs&#x20;
* int representing the number of bytes per second

\
