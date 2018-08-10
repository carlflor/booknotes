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
There are numerous case where there is a hardware failure in datacenters. The first response to this is to add *redundancy* to individual hardware components in order to reduce the failure rate of the system.

In AWS there are time when virtual machine instances become unavailable without warning, as the platforms are designed to prioritize flexibility and elasticity over single-machine reliability. This can be handled by using software fault-tolerance techniques.

#### Software Errors
Systemic errors also happen. The bugs that cause these kinds of software faults often lie dormant for a long time until they are triggered by an unusual set of circumstances. In those circumstances, it is revealed that the software is making some kind of assumption about its environment--and while that assumption is usually true, it eventually stops being true for some reason.

Here are a number of ways to lessen this:
- Think about assumptions and interactions in the system
- Thorough testing
- Process isolation
- Allowing processes to crash and restart
- Measuring, monitoring, and analyzing system behaviour in production

#### Human Errors
As humans tend to make errors, here are some ways to avoid it:
- Design systems in a way that minimizes opportunities for error.
- Provide fully featured non-production sandbox environments where people can explore and experiment safely, using real data, without affecting real users
- Unit tests and integration tests in the entire system
- Quick and easy recovery from human errors, fast rollback of config changes, roll out new code gradually to lessen possible negative impact
- Detailed and clear monitoring, such as performance metrics and error rates. This is referred to as telemetry.

## Scalability
Scalability is the term we use to describe a system's ability to cope with increased load.

#### Describing Load
Before we determine if a system is scalable, we need to describe its load. Load can be described through *load parameters*. The best parameters depend on the architecure of your system. Here are following examples:
- Requests per second to a web-server
- Ratio of reads to writes in a database
- Number of simultaneously active users in a chat room
- Hit rate on a cache

#### Describing Performance
Once you have described the load on your system, you can investigate what happens when the load increases. You can look at it in two ways:
- When you increase a load parameter and keep the system resources (CPU, memory, network bandwidth) unchanged, how is the performance in your system affected?
- When you increase a load parameter, how much do you need to increase the resource if you want to keep performance unchanged.

#### Approaches for Coping with Load
In handling different types of load to maintain good performance, it is best to have multiple approaches depending on the requirements of the system. People often talk of a dichotomy between scaling up (more powerful machine) and scaling out (distributing load across multiple smaller machines). However, there is no scalable architecture that fits all systems.
