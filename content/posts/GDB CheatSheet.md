---
tags: [BOF]
title: GDB Cheatsheet
created: '2020-05-31T13:18:44.243Z'
modified: '2020-08-18T13:56:57.064Z'
---


- Data:
    - `disas main` to disassemble function
    - `x/50wx $esp` e**x**amine 50 **w**ords in **h**ex starting from **esp**
    - `x/50i $eip` examine 50 instructions from eip
    - `x anything` examine address and show it’s contents
    - `info variables varname` will show any variable address (for global!)
    - `info functions` to list all functions
    - `info frame` shows the saved RTN address under "saved eip"
    - `info proc map` shows memory map
    - `ctx` shows general info about everything *(works in gef only)*

- Flow
    - `b *address` or `b *function<+number>`
    - `j *address` *to jump*
    - `si` **s**tep **i**nstruction
    - `ni` step instruction and stepover functions

- Hook Stops
we use these to execute certain commands everytime our program flow stops (ex: breakpoints, steps)
    - to define a hook stop we run the following:
```
define hook-stop
>info registers
>x/24wx $esp
>x/2i $eip
>end
```
