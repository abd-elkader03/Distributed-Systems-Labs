\# Lab 4 - Reflection Report

\# Student: Mohamed Ahmed Abd-elkader SE3



\## 1. Which parts show the benefits of microservices over a monolith?



\-Independent deployment: product-service and order-service are deployed

&#x20; separately.



\-Independent scaling: If order-service gets more traffic, we can scale it

&#x20; independently without scaling product-service.



\-Technology flexibility: Each service has its own requirements.txt



\- Fault isolation: When product-service failed order-service returned a

&#x20; 503 error instead of completely crashing.



\## 2. New complexities introduced by splitting into two services?



\- Network dependency: order-service now depends on network calls to

&#x20; product-service. Network calls can fail or be slow unlike in-process calls.



\- Distributed failure handling: We needed to add timeout and retry logic to handle failures gracefully.





\## 3. What would break if network latency increased or one service became slow?



\- order-service has a 2-second timeout. If product-service response takes

&#x20; longer than 2 seconds, the request will fail.



\- The retry mechanism (2 retries with 1 second delay) means a slow

&#x20; product-service could cause order-service to take up to 6 seconds to respond.



\- A circuit breaker pattern would help prevent this by stopping calls to

&#x20; a failing service early.



\## 4. Which 12-factor app principles are visible?



\- Factor 3 - Config: PRODUCT\_SERVICE\_URL is read from environment

&#x20; variables, not hardcoded in the source code.



\- Factor 6 - Processes: Both services are stateless processes.

&#x20; They store no state locally



\- Factor 7 - Port binding: Each service binds to its own port and is self-contained.



\- Factor 9 - Disposability: Both services start quickly and can be

&#x20; stopped and restarted cleanly





\## Conclusion

This lab demonstrated how microservices provide flexibility and fault isolation

at the cost of added network complexity.

