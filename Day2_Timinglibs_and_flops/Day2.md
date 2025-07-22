# Day 2 - Timing Libs, Synthesis and Flops

## Flops

Why flops? ==> to avoid glitches in combinational/sequential circuits by shielding unnecessary transition via restricting output change to clock edge.
### Coding styles
* Async reset => irrespective of clock and the rst needs to be mentioned in sensitivity list of the module.
* Sync reset => wait for clock

back to flops lab
![Img02](../Day2_Timinglibs_and_flops/img02.png)
* Img02 is of async reset where q is only changing on clock because of d
![Img03](../Day2_Timinglibs_and_flops/img03.png)
* Img03 also contributes.
![Img04](../Day2_Timinglibs_and_flops/img04.png)
* Img04 is of async set where q doesnt wait for clock
![Img05](../Day2_Timinglibs_and_flops/img05.png)
* Img05 is for sync reset where we wait for clock edge and for q to go low
![Img06](../Day2_Timinglibs_and_flops/img06.png)
* Img06 is the yosys synth of dff_asyncres
![Img07](../Day2_Timinglibs_and_flops/img07.png)
* Img07 is the out of dfflibmap for the same
![Img08](../Day2_Timinglibs_and_flops/img08.png)
* Img08 is the out of abc and show. We see that to link active high reset and active low reset, we have clock inverter in show.
![Img09](../Day2_Timinglibs_and_flops/img09.png)
* Img09 is the out of abc and show of set flop
![Img10](../Day2_Timinglibs_and_flops/img10.png)
* Img10 is the out of abc and show of asyncres.v
![Img11](../Day2_Timinglibs_and_flops/img11.png)
* Img11 is the out of abc and show of syncres.v. Here we see there is no set and reset pin.


