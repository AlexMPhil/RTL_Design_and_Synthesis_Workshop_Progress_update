# Day 3 - GLS, Synthesis Simulation Mismatch, Blocking and Non-blcoking statements

GLS or Gate Level Synthesis refers to the running of testbench with netlist as design under test (DUT). The testbench remians the stimulus injection. 
Netlist is the same as RTL code logically therefore the testbench remains the same.

Why GLS? 
* To verify the logical correctness of a design after synthesis
* To ensure timing of design is met (if Gate level models are delay annotated then we can use GLS for timing validation)

Synthesis Simulation Mismatch
Why does SS Mismatch happen?
* Missing sensitivity list => A simulator works based on activity ie: output changes when there is change in input. Therefore importan inputs that have change must be mentioned in sensitivity list of module. An alternate option is to put a '*' in it that is a substitute for all rleevant sensitive variables.
* Blocking vs Non-Blocking Assignments
  * Blocking (=) => statements are executed in order it is written, therefore there is consecutive statement evaluation. Here, we need to be extremely aware of th statement, where a variablles musgt be declared and ready before any processign with it.
  * Non Blocking (<=) => statements are executed parallely. easily allows for sequential circuit coding.
* Non Standard Verilog Coding 
