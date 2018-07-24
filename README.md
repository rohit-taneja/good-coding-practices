# **Good coding practices**

## *General*
----
* #### [Limit Scope of variables](https://www.refactoring.com/catalog/reduceScopeOfVariable.html)
* #### Follow naming conventions
* #### Think about access specifiers (private/public)
* #### Try to define variables/function etc in alphabetical order
* #### Don't call a method until unless it is required i.e scope of calling a method matters
* #### Try not to call a method multiple times in a single API call. Try to pass data between functions
* #### Fetch only data that is necessary. Don't get all details if not required
* #### Similarly, Send only data that is necessary. Don't send all details if not required
* #### Use bulk get and post function calls. Save latency. Make chunks
* #### Create a master data and pass it around functions to save API calls
* #### There should not be unused function arguments
* #### Boolean switch arguments should not be present in function definition. This violates [Single Respnsibility Principle](https://en.wikipedia.org/wiki/Single_responsibility_principle)
* #### Try to follow [REST](http://www.restapitutorial.com/)
* #### Don't call common methods if not all of it is required. Break that method
* #### Use round for floats
* #### Check for variable types int and string , don't compare both. Instead convert both to string and then compare
* #### Normalize case of string, either upper or lower.
* #### Try to model the solution by thinking which Data Structure will be effective. Yes, they are useful.
* #### Add Auth where required
* #### We should not give a user's data to another user
* #### Validate data, strip, int, str, valid json etc
* #### Validate max size in bulk requests
* #### Have retrials for failure cases. Retry should be idempotent
* #### Check for IDE warnings/errors
* #### Check that the code is running
* #### Don't change function contract without refactoring it's usages
* #### No INFO logs if not required. Use debug logs for debugging
* #### Add error logs where required
* #### For bulk APIs instead of looping and fetching a single entity, fetch entity in bulk
* #### Have one source of truth, don't duplicate
* #### Don't create multiple ways of doing a same thing."There should be one-- and preferably only one --obvious way to do it." (see Zen of Python) 
* #### Check for I/O Blocking calls, should be either done in async or thread
* #### Variable/Function names should be self explanatory
* #### Environment level constants should be in config
* #### Environment independent constants should be in constants file
* #### Follow [DRY](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself)
* #### Try to write [Pure functions](https://en.wikipedia.org/wiki/Pure_function)
* #### If any block of code is used >=2 times, try to make it a function . DRY
* #### Enums are used instead of constants whereever applicable
* #### No negatively named boolean variables
* #### Catch clauses are fine grained and catch specific exceptions
* #### Exceptions are not eaten if caught, unless explicitly documented otherwise
* #### APIs and other public contracts check input values and fail fast
* #### Floating point numbers are not compared for equality. Use Decimal instead
* #### Loops have a set length and correct termination conditions. No Infinite While or For Loops
* #### Order/index of a collection is not modified when it is being looped over
* #### Methods return early without compromising code readability
* #### Invalid parameter values handled such that exceptions are not thrown
* #### No sensitive information is logged or visible in a stacktrace
* #### There are no usages of 'magic numbers’
* #### Know your Variables which are immutable
* #### Arrays are checked for out of bound conditions
* #### Comments exist and describe rationale or reasons for decisions in code
* #### A class/module should have only one reason to change. [Single Respnsibility Principle](https://en.wikipedia.org/wiki/Single_responsibility_principle)
* #### Where third-party utilities are used, are returning errors being caught?
* #### Remove any commented out lines.
* #### Function length: For a method above 50 lines, it should be cut into smaller pieces.
* #### Number of method arguments: For the methods and functions, do they have 3 or fewer arguments? Greater than 3 is probably a sign that it could be grouped in a different way.
* #### Some endpoints should be idempotent (Should not do anything if called twice)
* #### Make parallel request for fast processing
* #### Naming a new function → Check if it is defined before or not 
* #### Don’t make/calculate X if x is getting used multiple times, instead declare it
* #### Reduce the scope of Action by adding Checks. Like action on a particular status
* #### Use single resource pool per application
* #### Use not (!) to your advantage by not writing many ==
* #### Use code [linting](https://en.wikipedia.org/wiki/Lint_(software)) tool.
* #### Reformat code
* #### Use [dead code](https://en.wikipedia.org/wiki/Dead_code) detectot tools
* #### Always check for division by 0. i.e your divisor should never have value=0



## *Managing resources acquired*
----
* #### Add strict tiemouts for every resource that you are using. [Circuit breaker pattern](https://martinfowler.com/bliki/CircuitBreaker.html)
* #### Don't forget to free the resource. Clear resource in finally statement if necessary
* #### Release resource as soon as they are not required
* #### Reuse reource, don't just create new ones every time
* #### Refresh resources over time, they tend to hog on to memory with time
* #### Know your resource usage limits. The min and the max
* #### Have alerts in place for resource shortage. We can have multiple alerts
* #### If possible dedicate/limit resource tied to a process

## *Caching*
----
* #### Add caching whereever applicable.
* #### Don't forget to define action points to invalidate cache (on upates/delete and in some cases inserts)
* #### Use memoization whereever applicable for CPU intensive functions
* #### Model your data precisely. hashmap, string, boolean etc
* #### Think of what should happen if the same function get called with same input

## *Production Bug*
----
* #### Try to look for patterns in the faulty set
* #### If problem is still there, stop/fix it immediately. Look for what damage has been done. Look for how to minimize the damage. Look for other problems that might arise due to this. Fix the damage. Think about where we lacked. Make sure that this doesn't happen in future.
* #### If nothing works, just Restart the server, restart everything :P


## *Third Party Integration*
----
* #### Test the PROD APIs before releasing
* #### Always deal with domain names and not IPs
* #### Use HTTPS
* #### Have an AUTH
* #### Check for IP filtering
* #### Have sandbox server to test
* #### Prod and Stag AUTH should be different
* #### API contract for PROD and Stag should be same. i.e they must run on the same code
* #### Have API retries on failures
* #### Deine mechanism after final failure occurs
* #### Use statuscake/pingdom to get health checkups for 3rd party API downtime

## *Database*
----
* #### Create index for keys in where query
* #### Create index for keys in order by
* #### Decrease the span of the query filtering or sql query by adding a indexed field conditions like if you know that your results are after a certain date and date field is indexed then add that date filter to the query

## *Logs*
----
* #### Use [log rotation](https://en.wikipedia.org/wiki/Log_rotation)
* #### Delete/Backup old files
* #### Decide [rotating policy](https://www.techrepublic.com/article/manage-linux-log-files-with-logrotate/) : by date or by size or a mix of both

## *Subversion control*
----
* #### Don't commit config file

## *Security*
----

## *Scripts*
----

## * Encoding/Decoding/Marshalling/De-Marshalling*
----

## *New feature release*
----
* #### Check for old code compatability
