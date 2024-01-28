# Performance Options

## threads

The count of threads or workers designated for downloading

```
min=0
max=system
```

0 threads: This is a special setting indicating that you want to use the main program thread for downloading as well\


### Caveats

* It's important to note that if the thread count exceeds 0 but the number of downloads for a model doesn't surpass a minimum per thread, only the main thread will handle the downloading process.
*   Additionally, the maximum number of usable threads is determined by your system, irrespective of the configuration file settings.



    * This is linked to the handling of unused threads on Windows and Linux. However, on Mac, the operating system lacks this specific OS API, so the maximum is established as the total number of threads on the system



## download-sems

Max concurrent number of downloads per thread

If threads is the number of workers for downloading, then download-sems is the number of tasks each worker can process at a time.\
\
