## Q Language

A dynamically typed and interpreted language for Windows

### Download
Binary for 64-bit Windows here: http://www.bcas.freeuk.com/qq.exe (0.5MB)

This is the actual interpreter, not an installer. Download by right-clicking then click the 'Save Link As' (depends on browser) and save to your machine. Maybe need to adjust AV settings to allow it to run.

### Examples

Basic ones should be listed above.

### Running the examples

    qq fib

This runs fib.q (compiles to byte-code file fib.pc first then runs). Use 'qq fib.pc' to run the precompiled byte-code file (however the byte-code compiler runs at up to 1M lines per second, so it won't save much).

### Choice of byte-code dispatcher

For native Windows, it defaults to the faster 'asm' dispatcher, which accelerates some byte-codes (with special asm handlers and persistent values in registers) to usually give some benefit.

The regular dispatcher is a simple function pointer loop; run that like this:

    qq -fn fib

### Building from source

Source codes can be seen here: [sources](../sources), in the file qq.ma (not up to date). This is an 'amalgamated' one file version, and needs to be built with my M (now Mosaic) compiler, described [here](../Mosaic).

### Version for Linux

I have supported C targets for my M language in the past, which enabled versions of my projects to be built on Linux with a C compiler. But that is not available at present (too many tricky-to-convert features of M).

Besides, in the C version, the -asm dispatcher is not supported. The -fn dispatcher will be faster because the C can be optimised, but usually not as fast as -asm even though my compiler doesn't optimise.

### About the language

Q has dynamic types, but most other aspects are static. No hot-loaded modules so needs to compile all modules into a single .pc file before it can run.

Evolved from application scripting languages which first appeared in 1980s, and now starting to converge with the companion M language, which has the same syntax.


