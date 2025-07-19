#  Model Counting Competition Submission of Ganak + Approxmc 2025
Scripts and binary. The binary shows all SHA1 hashes so you can rebuild it to
exactly the same behaviour.

## SHA hashes:
```plain
c o Ganak SHA1: 61286bc663e22987dfff25b4c01b1b4cff5beff3
c o Arjun SHA1: 39ef145587c791ac101c8b3b503aa62b5b756d76
c o SBVA SHA1: 0faa08cf3cc26ed855831c9dc16a3489c9ae010f
c o CMS SHA1: 6c866e338b3221c6ed036273268037f96397b092
c o ApproxMC SHA1: fb5dfbe46293e956cec7e963d9b649d0437160c1
c o BreakID SHA1: dee9744b7041cec373aa0489128b06a40fce43a1

CadiBack:
c o Version 0.2.1 9c42e308406e76a5e8ea224d65e971f4208c9c36

CadiCal:
c o CaDiCaL 2.0.0 0e8be0642ebf3e872a9df806fc0c1c1d8fa90084
```

All of the above is available online, in public repositories, at the time, and
before the time of the competition, under `meelgroup` or `msoos`
organizations/users on GitHub. CMS refers to CryptoMiniSat.

Static binary compiled with `gcc (GCC) 15.1.1 20250425`

## How to rebuild
Clone all above repositories in their respective directories (i.e. cadical,
cadiback, sbva, breakid, approxmc, arjun, ganak), then make sure that a
`build` subdirectory exists for all except `cadical` and `cadiback`. Then
go to the `build` subdirectory for each, and execute: `ln -s ../scripts/*.sh .`
or `ln -s ../scripts/build_scripts/*.sh .` to get the build scripts into the
`build` subdirectory for each. Then go into `ganak/build` and call
`./rebuild_static_all_release.sh`.

I have the GMP library recompiled to build both C++ and static libraries:
```bash
#!/bin/bash
make clean
CC=gcc-14 CXX=g++-14 ./configure --enable-shared --enable-static --enable-cxx
make clean
CC=gcc-14 CXX=g++-14 make -j14
sudo CC=gcc-14 CXX=g++-14 make -j14 install
```

And I have mpfr compiled for static libraries, and location to GMP:
```bash
#!/bin/bash
make clean
CC=gcc-14 CXX=g++-14 ./configure --enable-shared --enable-static --with-gmp=/usr/local
make clean
CC=gcc-14 CXX=g++-14 make -j14
sudo CC=gcc-14 CXX=g++-14 make -j14 install
```

## Thanks
Many thanks are printed while running the binary. Authors' names, papers, etc.
Each repository also has its own set of thanks and authors and papers. Science
is a mountain, and this tool is built on a mountain of work and papers and
books etc. It's a huge mountain, a beautiful montain, the best mountain.
