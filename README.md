Group Members:            
              1)Samiya Saeed


              
              2)Maheera Afif




              
              3)Maryam Arshad

Problem 2: ISP Network Failover
Scenario:
ConnectSphere ISP operates across three cities: City A (core), City B, and City C. Customers in City B lose Internet connectivity whenever the primary link between City A and City B fails. The ISP requires an automatic failover solution that redirects traffic through a backup path without any manual intervention.
Objective:
Design and implement a resilient ISP network using static routing with floating static routes to ensure automatic failover within 60 seconds of a link failure.
Network Design:
Three Cisco routers are arranged in a triangle topology. City A is the core router connecting to both City B and City C. The primary path is the direct link from City A to City B. The backup path routes traffic from City A through City C to City B, and is only used when the primary link fails.
Technical Implementation:
Floating static routes are used to achieve automatic failover. The primary route is assigned Administrative Distance (AD) of 1, making it always preferred. The backup route is assigned AD of 10, meaning it only activates when the primary route disappears from the routing table due to a link failure. This allows the router to automatically switch to the backup path without any manual configuration.
Testing:
Failover is tested by shutting down the primary link using the shutdown command on City A's interface. The show ip route command confirms the backup route is now active. A continuous ping from CustomerA to CustomerB verifies that end-to-end connectivity is maintained throughout the failure and recovery.
Tools Used:

GNS3 for network simulation
Cisco c3725 IOS images
VPCS for customer PC simulation
Cisco IOS CLI for configuration
