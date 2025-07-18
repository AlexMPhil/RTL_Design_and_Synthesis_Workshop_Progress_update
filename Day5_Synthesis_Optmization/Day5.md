# Day 5 - Optimization in Synthesis

## If-else

We have a priority based ladder, and the hardware implementation is a series of multiplexers where one output becomes of the inputs of the next.

### Danger with if? (Inferred Latch)

Incomplete if statements by bad coding logic results in inferre latches. This happens when there no true else result and results in a latch.

## Case
Also considered like a mux in hardware

### Danger with case?

* Incomplete Case => This will also lead to inferred latches. This happens when we do not tell what happens in some cases you don care about. This can be avoided by default case addition.
* Partial assignment => Controlling two variables in some cases and only one variable in some cases. This can be solved by assigning all outputs of case
* Comparing if-else ladder and case, if-else has designated priority, but there isnt such a priority order in case. Bad case statements can have multiple matches. Therfore we should avoid overlapping case.
