# DASK_MASTER

This repository aims at accumulating and making notes relatet to usage and practical implementation of dask.


Important links for fundamentals:
1.)https://blog.dask.org/2017/01/24/dask-custom


An array with size = (20000,20000)

*  What happens if the dask chunks=(20000,20000)?
    * Will the computation run in 4 seconds?
    * How much memory will be used?
    
   ans : computation runs in same nearly same or more amount  than numpy as initiation dask add overhead and we did not use advantage of parallel computing. Same memory will be used.
   
   
* What happens if the dask chunks=(25,25)?
    * What happens to CPU and memory?
    
    The user cpu time will increase a lot due to overhead of dask, thats because a lot of small chunks will now be needed to run in parallel. Memory usage will be less but cpu overhead will be high. How dask works is it makes things run in parallel, every call for a chunk have overhead, more call means more overhead that's problem with lots of chunk. So selecting a right size of chunk is impotant.
