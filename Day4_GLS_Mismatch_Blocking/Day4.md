# Day 3 - GLS, Synthesis Simulation Mismatch, Blocking and Non-blcoking statements

GLS or Gate Level Synthesis refers to the running of testbench with netlist as design under test (DUT). The testbench remians the stimulus injection. 
Netlist is the same as RTL code logically therefore the testbench remains the same.

Why GLS? 
* To verify the logical correctness of a design after synthesis
* To ensure timing of design is met (if Gate level models are delay annotated then we can use GLS for timing validation)

Synthesis Simulation Mismatch
