
# @Author : 7elmie

# Overview

The time class of python datetime module represents a time quantity.
The time class can have a tzinfo representing the timezone for which the time is specified. If tzinfo is None then the time object is a “naive” object. If tzinfo is not None then the time object is an “aware” object.
The date class does not possess attributes related to time.  Similarly the time class does not have date information. A datetime class has both attributes pertaining to date and time. Remember, a date object and a time object can be made into a time object by calling the combine method of the datetime class.

# Creation of time objects:

Calling the constructor of the time class can create the time objects.
Time Constructor:
time(hour=0, minute=0, second=0, microsecond=0, tzinfo=None, *, fold=0)

# Parmeters:

## Time constructor accepts following parameters

    - hour
    - minute
    - second
    - microsecond
    - tzinfo
    - *
    - fold

All the above parameters are optional parameters.
The tzinfo is an object of a class derived from tzinfo which represents the timezone. Generally the timezone concrete class of datetime module is used to represent a timezone. Specialized timezone classes can be designed as per the needs by deriving from the tzinfo class.
The fold parameter specifies whether there was any fold in time. A fold in time means a reverse back of the clock time. In countries following Daylight Saving time during the end of summer clocks are reversed back by 1 hour. This reverse back is a fold in time.
* means a splat operator. Using a splat operator a tuple can be unpacked and a time object can be constructed out of the values from the tuple.
The time objects can be created, by calling the constructor of time class without providing any parameters. A time object  without any parameters will have its hour, minute, second and microsecond initialized to zero.

# Example 1 – Create a time object without any parameters and modify it:
    import datetime
# Create a time with all time components as 0
    t1 = datetime.time()
    print(t1)
# Create a new time object with hour as 23 that is 11 PM
    t2 = t1.replace(23)
    print(t2)
# Create a new time object with hour as 23 and minute as 30 that is 11.30 PM
    t3 = t2.replace(minute=30)
    print(t3)
    Output:
    00:00:00
    23:00:00
    23:30:00

# Example 2 – Create a time object with tzinfo:
    import datetime
# Create a time instance for 1 PM 15 Minutes 16 Seconds 17 Microseconds
    timeInstance = datetime.time(1,15,16,17)
    print(timeInstance)
# Create a timezone instance using timedelta

    pstTimeDelta = datetime.timedelta(hours=-8)

    pstTZObject  = datetime.timezone(pstTimeDelta, name="PST")
# convert the naive object into an aware object by specifying a timezone instance

    timeInstance1   = timeInstance.replace(tzinfo=pstTZObject)
    print(timeInstance1)

    Output:
    01:15:16.000017
    01:15:16.000017-08:00

# Example 3 – Create a time object using python’s splat operator:
    import datetime
# All the time parameters for creating a time instance as a tuple
# 11PM, 59 Minutes, 59 Seconds, 999999 microseconds

    timeTuple = (11,59,59,9999)
# Use the splat operator to unpack the time elements and create a time instance
    timeInstance = datetime.time(*timeTuple)
# print the time instance constructed by using splat operator
    print(timeInstance)
    Output:
    11:59:59.999999