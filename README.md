# Changes in this fork:

Possibility to connect to arbitrary pools. 
In the nicehash repo, the host was hardcoded to `equihash.<location>.nicehash.com`, with only the location (e.g. _eu_, _us_) configurable.

In this repo, the argument for param _-l_ takes arbitrary _host:port_ configurations.

Example usage:

`nheqminer -l yourzcashpool.com:1234 -u yourusername -p yourpassword`

This fork now also includes the changes done in fork https://github.com/sarath-hotspot/nheqminer.git, approx. doubling performance (for my configuration, may depend on the CPU model) see section _Sarath's Edits_ at the bottom of this document.

# Build instructions:

## Linux cmake (Tested on Ubuntu 14.04):
You should have **CMake** installed (2.8 minimal version), boost (install from the repositories or download boost manually build and install it manually), download the sources manually or via git. 
Under Ubuntu open a terminal and run the following commands:
  - `sudo apt-get install cmake build-essential libboost-all-dev`
  - `git clone https://github.com/d10r/nheqminer.git`
  - `cd nheqminer/nheqminer`
  - `mkdir build`
  - `cd build`
  - `cmake ..`
  - `make`

## Other options

Not tested for this fork. See https://github.com/nicehash/nheqminer.git

# Run instructions:

If run without parameters, miner will start mining with 75% of available virtual cores on NiceHash. Use parameter -h to learn about available parameters:

        -h              Print this help and quit
        -l [location]   Host
	-q [port]	Port
	-u [username]   Username
        -p [password]   Password (default: x)
        -t [num_thrds]  Number of threads (default: number of sys cores)
        -d [level]      Debug print level (0 = print all, 5 = fatal only, default: 2)
        -b [hashes]     Run in benchmark mode (default: 100 hashes)
        -a [apiport]       Local API port (default: 0 = do not bind)

<i>Note: if you have a CPU with hyper threading enabled, it may be better to use less threads then there are logical cores. Benchmark in order to find out!</i>

# Sarath's Edits

My integration of Xenoncat's code in nheqminer works only in Linux (I did not verify it in other operating systems). 

## Pointing this miner to other stratum based pools. 
### supernova
nheqminer -l zec.suprnova.cc:2142 -u username.workername -p password -t threadCount 

### zmine
nheqminer  -l zmine.io:1337 -u ZcashTransparentAddress

## Donations
If you feel this project is useful to you. Feel free to donate.

    BTC address: 1PqPwYC8u2XCQxJv6qu3HwCRdQkdsqhXRS

