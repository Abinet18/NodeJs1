# NodeJs1

Q1. Why do we sometimes want to use SetImmediate instead of SetTimeOut
A. SetTimeout registers a function in the timer phase of an event loop thus it can run before I/O event callbacks.
   SetImmediate registers a function in the check phase of the event loop which happens after I/O event callbacks.
   Thus when we want I/O callbacks to be processed before our function we use SetImmediate.
Q2. Explain the difference between process.nextTick and setImmediate
    process.nextTick adds the call back to the nextTick queue which is not part of the event loop. Callbacks in the nextTick queue are processed before any callback in the event queue (timers or I/O callbacks). SetImmediate adds the callback in the check phase of the event loop which is processed after timers or I/O callbacks.
Q3.Name 10 global modules avaialable in NodeJs environment
    global
    http
    module
    path
    net
    https
    require
    stream
    domain
    zlib
