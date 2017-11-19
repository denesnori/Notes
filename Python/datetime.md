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
#### ```datetime.strptime(string, formatter)```

**strptime** -> **St**ring **P**arse **Time**

Reference:
-[strptime, stackoverflow](https://stackoverflow.com/questions/44596077/datetime-strptime-in-python)

### ```datetime.strftime(...)```

**strftime** -> **St**ring **F**ormat **Time**

### calendar module
- calendar and additional methods

Generarate plain text calendars:
```
class calendar.TextCalendar([firstweekday])
```

```
import calendar
print calendar.TextCalendar(firstweekday = 6).formatyear(2018)
```
Reference:
-[](https://docs.python.org/2/library/calendar.html#calendar.setfirstweekday)
