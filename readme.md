- Install Rtools and msys
- Download and extract a copy of boost in `c:/msys/home/boost_1_57_0`
- Create or edit `c:/msys/etc/fstab` to mount `c:/Rtools/gcc-4.6.3 /mingw`
- Extract QuantLib-1.5.tar.gz
- To configure run: `CPPFLAGS="-I/home/boost_1_57_0" CXXFLAGS="-g0" ./configure`
- To build (box with 8 cores) run: `make -j9`
- Add `-m64` to CXXFLAGS to build x64 library
- Example of my RQuantLib `Makevars.win` file:

```Make
QUANTLIB_ROOT="C:/Users/Jeroen/Desktop/quantlib"
BOOSTLIB="C:/msys/home/boost_1_57_0"

PKG_CPPFLAGS=-I$(QUANTLIB_ROOT)/include -I../inst/include -I. -I$(BOOSTLIB)
PKG_CXXFLAGS= -fpermissive 
PKG_LIBS=-L$(QUANTLIB_ROOT)/lib${R_ARCH} -lQuantLib
```

- The static libraries are too big for github (even with -g0), that is why they are zipped.
- Hopefully future versions of RQuantLib will use boost from the BH package.