# Day 3 - Optimisations

Looking into mult2.v file==> 3 bit input a, 4 bit output y with logic 2(a).
Multiply by 2 is same as a appended by zero, no hardware multiplier required since it is simply a shift.
* Img12 shows it requires no cells and abc shows nothing to map
* Img13 shows its just a appended by zero
  
Looking into mult8.v file ==> 9*a = (8+1)a = 8a + a
* Img14 shows again no cells, no mapping
* Img15 shows its appended byitself (in this case)

State optimisation means optmiisation of unused states, making more condensed state machines
* Cloning of logic is done when we do physical aware synthesis => Distant flops have routing delay that can be avoided by splitting flops into 2 have two paths of intermediate delay rather than one path of large delay
* Retiming=> considers combination logic delay between flops and elements, shifting logic and spreading it evenly ie partitioning logic

## Combination Logic Optimisation
Img 16 opt_check.v seems to be muz that simplifies as and gate of a and b
Similarly opt_check2.v seems to be a mux that simplifies to be or gate between a and b

Img 17 shows the purge in opt_check before abc
Img18 confirms the purge optimization as it shows the module as an and gate
Img 19 shows opt_check 2 becomes or gate as opposed to the lecture telling it should be a nand realisation of the same (most likely due to updation of standard cell library?)

Img20 shows that opt_check3 is another ternary operator based mux module where logic ssentailly boils down to 3 input and of a,b and c., which is proven in after purge show as in img 21

Img 22 shows the same for opt_check4


