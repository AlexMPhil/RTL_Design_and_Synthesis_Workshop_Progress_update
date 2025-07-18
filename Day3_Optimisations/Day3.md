# Day 3 - Optimisations

Looking into mult2.v file==> 3 bit input a, 4 bit output y with logic 2(a).
Multiply by 2 is same as a appended by zero, no hardware multiplier required since it is simply a shift.
* Img12 shows it requires no cells and abc shows nothing to map
* Img13 shows its just a appended by zero
* 
Looking into mult8.v file ==> 9*a = (8+1)a = 8a + a
* Img14 shows again no cells, no mapping
* Img15 shows its appended byitself (in this case)
