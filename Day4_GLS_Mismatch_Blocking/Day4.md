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

* Img 35 shows the codes of the files we will be working with=> ternary_operator_mux.v, bad_mux.v, good_mux.v. Ternary operator is of the format '<cond>?<T>:<F>'.
* Img36 shows the gtkwave output of ternary_operator_mux.v
* Img37 is the yosys show output of the same, showing it is a mux. It doesnt seem to form nand, clkinv and oai along with it as shown in the lecture which could be attributed to updated library.

UNFORTUNATELY FOR SOME REASON, WHEN I DO THE GLS STEPS AS SHOWIN IN LECTURE AFTER THIS PINT I DO NOT GET THE '_ 6 _, _ 7 _' AS SHOWN (FOR THIS PARTICULAR VERILOG FILE)

* Img38 shows the gtkwave output of bad_mux.v and it shows how because of missing sensitivity list, when sel is low, there is no output change happening and fails to respons like a proper mux. The I0 activities are not sensed when select is low.

* Img39 shows gtkwave output of succesful GLS of bad_mux.v, where we can see that y follows i0 when select is low and follows i1 when select is high. Therefore by observing Img38 and Img39 we are able to see the Synthesis Simulation Mismatch

* 

