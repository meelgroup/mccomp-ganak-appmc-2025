#  Model Counting Competition Submission of Ganak + Approxmc 2025
Scripts and binary. The binary shows all SHA1 hashes so you can rebuild it to
exactly the same behaviour.

## SHA hashes:
```plain
c o Ganak SHA1: 53074d2e7ecd1509928b3682c43de7b755967956
c o Arjun SHA1: 8d0d3a245eb8fbacc83ed071ebd546bfa8d88d28
c o SBVA SHA1: 18d080e656305261c696370f02251e57835db73a
c o CMS SHA1: 70aaf201570a3991e19d5e96118b8046139c0ff0
c o ApproxMC SHA1: d145397d06584990a25f653c30ffbb29e4e1ff79
c o BreakID SHA1: 229da25440fb86dc2f9e0bc2d3f11490076dc9c1

CadiBack:
c o Version 0.2.1 bd1aa18a5f4d028e3075b50aa1051d883f386a0c

CadiCal:
c o CaDiCaL 2.0.0 d3a78bc5ba014771e975d1ccf2a00e239048068d
```

All of the above is available online, in public repositories, at the time, and
before the time of the competition, under `meelgroup` or `msoos`
organizations/users on GitHub. CMS refers to CryptoMiniSat.

## How to rebuild
Clone all above repositories in their respective directories (i.e. cadical,
cadiback, sbva, breakid, approxmc, arjun, ganak), then make sure that a
`build` subdirectory exists for all except `cadical` and `cadiback`. Then
go to the `build` subdirectory for each, and execute: `ln -s ../scripts/*.sh .`
or `ln -s ../scripts/build_scripts/*.sh .` to get the build scripts into the
`build` subdirectory for each. Then go into `ganak/build` and call
`./rebuild_static_all_release.sh`.

I have the GMP library recompiled to SandyBridge, because we used to have
issues with that. So this binary may be a bit slower than if you had compiled
GMP on your own machine. Basically, you have to configure GMP as:
```bash
CFLAGS="-march=sandybridge" ./configure --enable-cxx --enable-shared --enable-static
```


## Thanks
Many thanks are printed while running the binary. Authors' names, papers, etc.
Each repository also has its own set of thanks and authors and papers. Science
is a mountain, and this tool is built on a mountain of work and papers and
books etc. It's a huge mountain, a beautiful montain, the best mountain.
