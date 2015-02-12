- Installed Rtools, msys
- Extracted a copy of boost in /home/boost_1_57_0
- In msys in /etc/fstab, mount c:/Rtools/gcc-4.6.3 to /mingw
- Extract QuantLib-1.5.tar.gz
- To configure run: CPPFLAGS="-I/home/boost_1_57_0" CXXFLAGS="-g0" ./configure
- To build (box with 8 cores) run: make -j9
- Add -m64 to CXXFLAGS to build x64 library
- Example of my Makevars.win file in RQuantLib:

```Make
# Makevars.win 
QUANTLIB_ROOT="C:/Users/Jeroen/Desktop/quantlib"
BOOSTLIB="C:/msys/home/boost_1_57_0"
PKG_CXXFLAGS=-I$(QUANTLIB_ROOT)/include -I../inst/include -I. -I$(BOOSTLIB) $(SHLIB_OPENMP_CFLAGS) -fpermissive 
PKG_LIBS=-L$(QUANTLIB_ROOT)/lib${R_ARCH} -lQuantLib $(SHLIB_OPENMP_CFLAGS) 
```

- The static libraries are too big for github (even with -g0), that is why they are zipped.