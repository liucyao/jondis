# Overview

Jondis is a high availability pool management class for the excellent https://github.com/andymccurdy/redis-py

# Features

* Slave discovery on startup
* On master failure, if a slave is promoted, the pool will reconfigure to connect to the new master


# Limitations

* Currently all commands are sent to the master
* No master discovery
* In certain scenarios, the pool will pick up new slaves (if it's reconfigured), but
  there's currently no periodic / automatic slave discovery
* Does not talk to sentinel
        

# Requirements

redis-py


# Usage

```python
from jondis.pool import Pool
pool = Pool(hosts=["redis01:6379","redis02:6379"])
redis = redis_lib.client.StrictRedis(connection_pool=pool)
```




