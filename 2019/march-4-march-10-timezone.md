# March 4 - March 10 \[timezone\]

## Review

{% embed url="https://making.pusher.com/ephemeral-port-exhaustion-and-how-to-avoid-it/" %}



## Tips and sharing

A little more explanation about the tricky points of python timezone:

```text
# in env.sh
export TIME_ZONE='Asia/Taipei'
# in other logic
TIME_ZONE = os.getenv('TIME_ZONE') 
CURRENT_TZ = pytz.timezone(TIME_ZONE)
```

If checking the CURRENT\_TZ, can see something like this:

![](../.gitbook/assets/image%20%286%29.png)

The explanation is:

> A pytz timezone class does not represent a single offset from UTC, it represents a geographical area which, over the course of history, has probably gone through several different UTC offsets. The oldest offset for a given zone, representing the offset from before time zones were standardized \(in the late 1800s, most places\) is usually called "LMT" \(Local Mean Time\), and it is often offset from UTC by an odd number of minutes.

To create datetime with timezone, can do this:

```text
from datetime import datetime
import pytz

my_datetime = datetime(2015, 6, 11, 13, 30)
my_tz = pytz.timezone('America/Chicago')    
good_dt = my_tz.localize(my_datetime)

print(good_dt) # 2015-06-11 13:30:00-05:00
```

