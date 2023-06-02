# Application alerts
1. Critical business task based queue size crossing threshold.
2. critical busines task related 3rd party api X failures in Y minutes/seconds.

# Infra 
1. Graphana dashbaords for timeline based trend analysis
2. infra utilisation level alerts - CPU, RAM, Disk 

# Availability
every min check these
1. health check api (all checks) pass or failed (checked once every min.)
2. in last 5min, latency breach P99(30-40 api's total hits or checking for each api separately)
3. in last 5 min, api status error rate percentage of hits receieved

# Health-check Logics
1. Activemq
    1. Able to create new connection
    2. Produce msg and time taken
    3. Consume the same and time taken
    4. connection count
2. Mongo
    1. Ping command to mongo
    2. Total connection 
    3. Active connection
3. Channel
    1. Order sync and inventory sync status 
4. Hazelcast
    1. is running
    2. Name
    3. Cluster size
5. Mysql
    1. “Select 1” query to check master and slave are up via respective session factory 
    2. totalConnections
    3. currentActiveConnections
    4. currentIdleConnections
    5. threadsAWaitingConnection
6. S3
    1. Every 60mins, put and delete UUID based time string into S3
7. Zookeeper
        1. Check  isConnected via zookeeper client
        2. Acquire a lock (use health check namespace) and release lock, capture status and time of both operation


