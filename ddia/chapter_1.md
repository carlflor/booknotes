### Chapter 1
# Reliable, Scalable, and Maintainable Applications

**Reliability**  
Tolerating hardware and software faults. The system should continue to work *correctly* even in the face of *adversity*

**Scalability**   
Measuring load and performance. Latency percentiles, throughput  
To have a reasonable way to handle as the system *grows* (data volume, traffic volume, complexity)

**Maintainability**  
Operability, simplicity & evolvability  
Over time, many different people will work on the system, and they should be able to work *productively*.


## Data Intensive Applications
Many applications today are data-intesive than compute-intesive. Bigger problems are amount of data, complexity of data, and the speed at which it is changing.

#### Building Blocks:
- Databases - Store data to access/find later on
- Caches - Remember the result of an expensive operation for faster reads
- Search Indexes - Search/filter data by keyword
- Stream Processing - Send a message to another process to be handled asynchronously
- Batch Processing - Periodically crunch a large amount of accumulated data

## Reliability
Systems should be fault-tolerant and resilient as faults in systems are impossible to fully obliterate. Here are some faults that are common in building systems but can be avoided.

#### Hardware Faults
There are numerous case where there is a hardware failure in datacenters. The first response to this is to add *redundancy* to individual hardware components
#### Software Errors
#### Human Errors
