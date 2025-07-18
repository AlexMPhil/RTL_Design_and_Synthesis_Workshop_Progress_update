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

## Labs

* Img44 shows the codes of incomplete if 1 and 2. 1 shows no else which results in output latching to i0. 2 has an else if but no defnite else.
* Img45 shows the gtkwave output of incomp_if which clearly shows the value of y latching onto some value at any moment, often from the past.
* Img46 shows the output of yosys show for the same, and again we see clearly we have a Dlatch instead of a mux

* Img47 shows the output of gtkwave of incomp_if2.v. When i0 and i2 are low, output is constant. When i2 is high, y follows i3. There is clear latching action
* Img48 shows the output of yosys show and it consists of mux and nor gate and latch.
