pony_assert: C FFI to the rescue of pony testers
-----------

# The problem 

pony programs cannot crash at runtime by construction
(so long as they don't allocate too much memory).

So if your program stays inside pony code and never calls out
to the C FFI, it can only crash if it runs out of memory.

For production this is great. 

But... what if we are testing? What if we are doing 
feather-weight testing via assertions? These
are critical software engineering practices.

For testing, pony's lack of built in ability to
halt processing is inappropriate.

That is, we want a _fail-stop model_ in most testing situations.

If an assertion is violated, we _want_ to crash 
the program immediately, so we are are informed 
that we have found a bug in our logic! Not in 10 minutes, not
"eventually" at some point in the future 
(what the standard library `pony_test` does). 

We want to crash _now_!

What can we do?

# The solution

assert.pony is a lightweight assertion 
facility for testing pony code that 
uses to the C FFI to immediately
crash your program if an asserted invariant
is violated.


---
Author: Jason E. Aten, Ph.D.

LICENSE: MIT
