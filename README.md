# Libra C++ implementation

This repo is built on top of [Libra](https://github.com/sunblaze-ucb/Libra.git)

## Prerequisites

On Debian based systems, you can run the following command:
```
./setup.sh
``` 
This script will change your default clang compiler to clang-7.

Or:
```
apt update
apt -y install cmake make git clang++-7 libgmp-dev g++ parallel
```

In other words, you'll need a C++11-compatible compiler (we use clang-7) (g++ 5, 6, or 7 will work).

Add dependant libraries:
```
git submodule init && git submodule update
```

## Building

The top-level Makefile in this directory will build everything below. Just run

```
cmake .
make -j4        # for example
```

## Testing

### SHA256
```
cd tests/SHA256
python build.py
python run.py
```

use `sudo` if necessary.

It will output prover time, verifier time and proof size of Libra PIOP for Merkle tree verification from $2^1$ leaves to $2^8$ leaves. Besides, it outputs polynomial variable number. Sum the cost of corresponding PCS to obtain overall cost for Libra SNARK.
