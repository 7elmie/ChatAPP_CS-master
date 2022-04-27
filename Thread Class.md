
# @uthor : 7elmie
# What is Thread's in Python.?
A Python thread is like a process, and may even be a process, depending on the Python thread system. 
In fact, Python threads are sometimes called “lightweight” processes. 
because threads occupy much less memory, and take less time to create than do processes.
Threads allow applications to perform multiple tasks at once. Multi-threading is important in many applications.

For an Example :

    import threading
    class mythread(threading.Thread):
    def __init__(self, i):
    threading.Thread.__init__(self)
    self.h = i
    def run(self):
    print“ Value send“, self.h
    thread1 = mythread(1)
    thread1.start()


# This module defines the following functions:

    threading.active_count()
Return the number of Thread objects currently alive. The returned count is equal to the length of the list returned by enumerate().
The function activeCount is a deprecated alias for this function.

    threading.current_thread()
Return the current Thread object, corresponding to the caller’s thread of control. If the caller’s thread of control was not created through the threading module, a dummy thread object with limited functionality is returned.
The function currentThread is a deprecated alias for this function.

    threading.excepthook(args, /)
Handle uncaught exception raised by Thread.run().
The args argument has the following attributes:

    exc_type: Exception type.

exc_value: Exception value, can be None.
exc_traceback: Exception traceback, can be None.
thread: Thread which raised the exception, can be None.
If exc_type is SystemExit, the exception is silently ignored. 
Otherwise, the exception is printed out on sys.stderr.
If this function raises an exception, sys.excepthook() is called to handle it.

    threading.excepthook() 
    Thread.run()
can be overridden.to control how uncaught exceptions raised by are handled.
Storing exc_value using a custom hook can create a reference cycle. It should be cleared explicitly to break the reference cycle when the exception is no longer needed.
Storing thread using a custom hook can resurrect it if it is set to an object which is being finalized. Avoid storing thread after the custom hook completes to avoid resurrecting objects.


#   New in version 3.8.

    threading.__excepthook__
Holds the original value of threading.excepthook(). It is saved so that the original value can be restored in case they happen to get replaced with broken or alternative objects.
#   New in version 3.10.

    threading.get_ident()
Return the ‘thread identifier’ of the current thread. This is a nonzero integer. Its value has no direct meaning; it is intended as a magic cookie to be used e.g. to index a dictionary of thread-specific data. Thread identifiers may be recycled when a thread exits and another thread is created.

#   New in version 3.3.

    threading.get_native_id()
Return the native integral Thread ID of the current thread assigned by the kernel. This is a non-negative integer. Its value may be used to uniquely identify this particular thread system-wide (until the thread terminates, after which the value may be recycled by the OS).
Availability: Windows, FreeBSD, Linux, macOS, OpenBSD, NetBSD, AIX.

#   New in version 3.8.

    threading.enumerate()
Return a list of all Thread objects currently active. The list includes daemonic threads and dummy thread objects created by current_thread(). It excludes terminated threads and threads that have not yet been started. However, the main thread is always part of the result, even when terminated.

    threading.main_thread()
Return the main Thread object. In normal conditions, the main thread is the thread from which the Python interpreter was started.

#   New in version 3.4.

    threading.settrace(func)
Set a trace function for all threads started from the threading module. The func will be passed to sys.settrace() for each thread, before its run() method is called.

    threading.gettrace()
Get the trace function as set by settrace().

#   New in version 3.10.

    threading.setprofile(func)
Set a profile function for all threads started from the threading module. The func will be passed to sys.setprofile() for each thread, before its run() method is called.

    threading.getprofile()
Get the profiler function as set by setprofile().

#   New in version 3.10.

    threading.stack_size([size])
Return the thread stack size used when creating new threads. The optional size argument specifies the stack size to be used for subsequently created threads, and must be 0 (use platform or configured default) or a positive integer value of at least 32,768 (32 KiB). If size is not specified, 0 is used. If changing the thread stack size is unsupported, a RuntimeError is raised. If the specified stack size is invalid, a ValueError is raised and the stack size is unmodified. 32 KiB is currently the minimum supported stack size value to guarantee sufficient stack space for the interpreter itself. Note that some platforms may have particular restrictions on values for the stack size, such as requiring a minimum stack size > 32 KiB or requiring allocation in multiples of the system memory page size - platform documentation should be referred to for more information (4 KiB pages are common; using multiples of 4096 for the stack size is the suggested approach in the absence of more specific information).
Availability: Windows, systems with POSIX threads.

This module also defines the following constant:
    
    threading.TIMEOUT_MAX
The maximum value allowed for the timeout parameter of blocking functions (Lock.acquire(), RLock.acquire(), Condition.wait(), etc.). Specifying a timeout greater than this value will raise an OverflowError.

#   New in version 3.2.

This module defines a number of classes, which are detailed in the sections below.
The design of this module is loosely based on Java’s threading model. 
However, where Java makes locks and condition variables basic behavior of every object, 
they are separate objects in Python. Python’s Thread class supports a subset of the behavior of Java’s 
Thread class; currently, there are no priorities, no thread groups, and threads cannot be destroyed, stopped, suspended, resumed, or interrupted. 
The static methods of Java’s Thread class, when implemented, are mapped to module-level functions.
All of the methods described below are executed atomically.

    Thread-Local Data
Thread-local data is data whose values are thread specific. To manage thread-local data, just create an instance of local (or a subclass) and store attributes on it:

    mydata = threading.local()
    mydata.x = 1
The instance’s values will be different for separate threads.

    class threading.local
A class that represents thread-local data.
For more details and extensive examples, see the documentation string of the _threading_local module.


#   Thread Objects
The Thread class represents an activity that is run in a separate thread of control. There are two ways to specify the activity: by passing a callable object to the constructor, or by overriding the run() method in a subclass. 
No other methods (except for the constructor) 
should be overridden in a subclass. 
In other words, only override the 
        
    __init__() 
and 
        
    run() 
methods of this class.
Once a thread object is created, its activity must be started by calling the thread’s start() method. 
This invokes the run() method in a separate thread of control.


class threading : 
    
    threading.Thread(group=None, target=None, name=None, args=(), kwargs={}, *, daemon=None)
This constructor should always be called with keyword arguments. 
Arguments are: group should be None; 
reserved for future extension when a ThreadGroup class is implemented.
target is the callable object to be invoked by the run() method. 
Defaults to None, meaning nothing is called.
name is the thread name. 
By default, a unique name is constructed of the form “Thread-N” where N is a small decimal number
or “Thread-N (target)” where “target” is target.__name__ if the target argument is specified.
args is the argument tuple for the target invocation. Defaults to ().
kwargs is a dictionary of keyword arguments for the target invocation. Defaults to {}.
If not None, daemon explicitly sets whether the thread is daemonic. If None (the default). 
the daemonic property is inherited from the current thread.
If the subclass overrides the constructor, it must make sure to invoke the base 
class constructor 
    
    (Thread.__init__()) before doing anything else to the thread.

#   Changed in version 3.10: 

    Use the target name if name argument is omitted.

#   Changed in version 3.3: Added the daemon argument.

    start()
Start the thread’s activity.
It must be called at most once per thread object. 
It arranges for the object’s 

    run() 
method to be invoked in a separate thread of control.
This method will raise a RuntimeError if called more than once on the same thread object.

    run()
Method representing the thread’s activity.
You may override this method in a subclass. The standard run() method invokes the callable object passed to the object’s constructor as the target argument, if any, with positional and keyword arguments taken from the args and kwargs arguments, respectively.

join(timeout=None)
Wait until the thread terminates. This blocks the calling thread until the thread whose join() method is called terminates – either normally 
or through an unhandled exception – or until the optional timeout occurs.
When the timeout argument is present and not None, it should be a floating point number specifying a timeout for the operation in seconds (or fractions thereof). 
As join() always returns None, you must call is_alive() after join() to decide whether a timeout happened – if the thread is still alive, the join() call timed out.

When the timeout argument is not present or None, the operation will block until the thread terminates.
A thread can be join()ed many times.
join() raises a RuntimeError if an attempt is made to join the current thread as that would cause a deadlock. It is also an error to join() a thread before it has been started and attempts to do so raise the same exception.

    name
A string used for identification purposes only. It has no semantics. Multiple threads may be given the same name. The initial name is set by the constructor.

    getName()
    setName()   Deprecated getter/setter API for name; 
use it directly as a property instead.

#   Deprecated since version 3.10.

    ident
The ‘thread identifier’ of this thread or None if the thread has not been started. This is a nonzero integer. 

    See the get_ident() function. 
Thread identifiers may be recycled when a thread exits and another thread is created. The identifier is available even after the thread has exited.

    native_id
The Thread ID (TID) of this thread, as assigned by the OS (kernel). 
This is a non-negative integer, or None if the thread has not been started. 
See the 

    get_native_id() function. 
This value may be used to uniquely identify this particular thread system-wide (until the thread terminates, after which the value may be recycled by the OS).
Note Similar to Process IDs, Thread IDs are only valid (guaranteed unique system-wide) from the time the thread is created until the thread has been terminated.
Availability: Requires 

    get_native_id() 
function.

#   New in version 3.8.

    is_alive()
Return whether the thread is alive.
This method returns True just before 

    the run() method 
starts until just after the 
    
    run() method terminates. 
The module function enumerate() returns a list of all alive threads.

    daemon
A boolean value indicating whether this thread is a daemon thread (True) or not (False).
This must be set before start() is called,otherwise RuntimeError is raised. 
Its initial value is inherited from the creating thread; 
the main thread is not a daemon thread and therefore 
all threads created in the main thread default to daemon = False.
The entire Python program exits when no alive non-daemon threads are left.

    isDaemon()
    setDaemon()