C++ with multithreading to maximize packet throughput.

### Explanation
- Create a packet pool of 1024 pre-initialized DHCP discovery packets to avoid constant re-allocation.
- Each packet gets a randomized MAC address and transaction ID.
- Spawning twice as many threads as CPU cores, with each thread sending a continuous stream of DHVP discover packets via UDP broadcast.
- After every 1000 packets, code refreshes MAC address and transaction ID to ensure variety.
- To minimize contention, each thread maintains its own packet counter and only periodically updates the global counter.
- Display thread shows real-time statistics every second, total packets sent, current rate, and average rate since start.