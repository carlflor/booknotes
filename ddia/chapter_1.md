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
