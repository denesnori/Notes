### datetime library
```
from datetime import datetime
```

- get the current date and time
```
from datetime import datetime

print datetime.now()
# 2017-10-28 12:11:35.005907
```

- format the date and time

```
from datetime import datetime
now = datetime.now()

year = now.year
month = now.month
day = now.day
hour = now.hour
minute = now.minute
second = now.second

print '%s %s %s' % (now.year, now.month, now.day)
```
