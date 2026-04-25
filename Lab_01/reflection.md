Lab 1 – Reflection

\# Student: Mohamed Ahmed Abd-elkader SE3


This lab measures the Round-Trip Latency of a TCP connection between a client
and server running on the same machine (loopback). The server echoes back any
message it receives, and the client measures the time for each round-trip.



* Local TCP latency was extremely low (under 1 ms typically)
* There was some variance due to OS scheduling and system load
* The distribution was roughly normal with a slight right tail (occasional spikes)
* P99 was noticeably higher than the mean, showing tail latency behavior



Latency measurement is a fundamental skill in distributed systems. Even small
differences in latency (a few ms) can have a large impact at scale when
millions of requests are made per second.

