Web Application Outage Postmortem
Issue Summary:

Duration: June 12, 2024, 09:00 AM - 11:30 AM (EAT)
Impact: Intermittent downtime experienced in the web application service, affecting approximately 20% of users.
Root Cause: Overloaded database server due to connection pool exhaustion.

What Really Happened?

Our database server, let's call it "Dave," was working diligently. But on June 12th, Dave was swamped. User traffic spiked, and the connection pool (the number of simultaneous connections the database can handle) maxed out. With nowhere to go, new requests had to wait their turn, leading to intermittent downtime for about 20% of our users.

The Technical Bit: Simplified

User Traffic Surge: More users logged in than usual.
Connection Pool Maxed Out: The database server can only handle a certain number of connections at once.
Wait Your Turn: Excess connections were put on hold, causing delays and downtime.

The Aftermath

After identifying the root cause, we:
Increased the Connection Pool Size: More connections at once without crashing.
Optimised Queries: Reduced the load on the database by making queries more efficient.
Implemented Load Balancing: Distributed the traffic to multiple servers to prevent overload.
