# 第八週

* PC

```
// This file is part of www.nand2tetris.org
// and the book "The Elements of Computing Systems"
// by Nisan and Schocken, MIT Press.
// File name: projects/03/a/PC.hdl

/**
 * A 16-bit counter with load and reset control bits.
 * if      (reset[t] == 1) out[t+1] = 0
 * else if (load[t] == 1)  out[t+1] = in[t]
 * else if (inc[t] == 1)   out[t+1] = out[t] + 1  (integer addition)
 * else                    out[t+1] = out[t]
 */

CHIP PC {
    IN in[16],load,inc,reset;
    OUT out[16];

    PARTS:
    // Put your code here:
    Inc16(in=pc,out=i);
    Mux16(a=pc,b=i,sel=inc,out=x);
    Mux16(a=x,b=in,sel=load,out=y);
    Mux16(a=y,b=false,sel=reset,out=z);
    Register(in=z,load=true,out=pc,out=out);
}
```
![](https://github.com/qweasd049564/co109a/blob/master/homework/IMG_0226.JPG)
