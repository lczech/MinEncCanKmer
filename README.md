# MinEncCanKmer

Minimal encoding of canonical k-mers

## Compilation

```
gcc -O3 -D_FILE_OFFSET_BITS=64 -pthread -mbmi -o canonical fasta.c canonical.c -lm
```

## Usage


```
./canonical <fasta> <k> <b>
```

where

* `fasta` is a (multiple) fasta file
* `k` is the k-mer length, optional, default 5, maximum 31
* `b` is the number of buckets, optional, default 4

Output: distribution of k-mers to buckets


## 2-bit encoding

To switch to standard 2-bit encoding, (un)comment the following lines:

```
// process_string(seq,k,threads,t)
   process_string_std(seq,k,threads,t)
```

## General alphabets

For encoding canonical k-mers on general (non-DNA) alphabets, Python scripts are provided in the according subfolder, where `minenc.py` outputs the encoding of all k-mers for a given alphabet size, and `minenc_rc.py` encodes considering reverse complementation.

## C++ implementation

An implementation of the functionality in C++ is available in the [genesis library](https://github.com/lczech/genesis), see [here](https://github.com/lczech/genesis/blob/master/lib/genesis/sequence/kmer/canonical_encoding.hpp). The library also offers other useful functionality for working with sequences and k-mers.

## Citation

Please cite: Wittler R. General encoding of canonical k-mers. Peer Community Journal. 2023;3: e87. https://doi.org/10.24072/pcjournal.323

## License

* fasta.c and fasta.h are borrowed from [FragGeneScan-Plus](https://github.com/hallamlab/FragGeneScanPlus).
* MinEncCanKmer is licensed under the [GNU general public license](https://gitlab.ub.uni-bielefeld.de/gi/MinEncCanKmer/-/blob/main/LICENSE).
