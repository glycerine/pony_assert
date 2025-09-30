pony_assert: C FFI to the rescue of pony testers
-----------

# The problem 

pony programs cannot crash at runtime by construction.

If they stay inside pony code and never call out
to the C FFI, they are guarateed to never crash by design.

But what if we are testing or doing feather-weight testing via assertions?

If an assertion is violated, we _want_ to crash 
the program immediately, so we are are informed 
that we have found a bug! Not in 10 minutes, not
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
