## sendosc

sendosc is a simple command-line tool for sending OSC packet.


This is a minimal fork/repackaging of yoggy's `sendosc` with all of its dependencies to create a statically linked version on macOS via cmake.

It probably should work on Linux as well (but not tested yet).


## Usage

```
sendosc

usage : sendosc dst_host dst_port path [[type] [param]] ...
 
   type
     i : int
     f : float
     b : boolean (true/false)
     s : string
 
   example
     ./sendosc 127.0.0.1 5678 /test1 i 123
     ./sendosc 127.0.0.1 5678 /test2 f 123.45
     ./sendosc 127.0.0.1 5678 /test3 s teststring
     ./sendosc 127.0.0.1 5678 /test4 b true
     ./sendosc 127.0.0.1 5678 /test5 s teststring i 123 f 123.4 b false
```

## How to Build

You can just run `./build.sh` or type the following:

```
mkdir build && cd build
cmake ..
make

```

You should find a static linked version of `sendosc` in the `build` directory. Install it wherever you like.


## Copyright and license

Copyright (c) 2015 yoggy

Released under the [MIT license](LICENSE.txt)
