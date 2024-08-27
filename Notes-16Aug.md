## 10 Load Balancing Algorithms :

1. **Round Robin**
   - Sends each request to the next server in line, looping back to the first server after reaching the last one.

2. **Least Connections**
   - Sends requests to the server with the fewest active connections.

3. **Weighted Round Robin**
   - Assigns more requests to servers with higher capacities based on their weights.

4. **Weighted Least Connections**
   - Combines Least Connections and Weighted Round Robin, sending requests to the server with the best ratio of active connections to capacity.

5. **IP Hash**
   - Uses the IP address of the client to decide which server to send the request to, keeping the same client connected to the same server.

6. **Least Response Time**
   - Sends requests to the server with the quickest response time and the fewest active connections.

7. **Random**
   - Sends requests to a randomly chosen server.

8. **Least Bandwidth**
   - Sends requests to the server using the least amount of bandwidth.

### Additional Algorithms

9. **Geolocation-Based**
   - Sends requests to the server closest to the client's geographical location to reduce latency.

10. **Resource-Based**
    - Sends requests to the server with the most available resources (CPU, memory, etc.).



