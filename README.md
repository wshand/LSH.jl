# LSH.jl
Implementations of different locality-sensitive hash functions in Julia.

## TODO
- Replace the current MIPS hash implementation with the one specified in `A. Shrivastava and P. Li. Improved asymmetric locality sensitive hashing (alsh) for maximum inner product search (mips)`.
- Add some other hash functions:
  - Fast MinHash for Jaccard similarity hashing ([ref. 1 (Anshu's thesis)](https://www.cs.rice.edu/~as143/Doc/Anshumali_Shrivastava.pdf), [ref. 2 (ICML '17)](https://arxiv.org/pdf/1703.04664.pdf))
  - Winner-take-all hashing ([ref](http://auai.org/uai2018/proceedings/papers/321.pdf))
  - SSH ("Sketch, Shingle, and Hash") for time series ([ref](http://proceedings.mlr.press/v55/luo16.pdf))
- Implement a `LSHTable` type. This will wrap around an `LSHFunction` and allow users to search for hash collisions.
- Following the previous item, implement a `LSHTableCollection` (or similarly-named) type. `LSHTableCollection` will wrap around multiple `LSHTable`s. For a given query, if any one of the tables experiences a collision, then that collision will be added to the results.

### Long-term
- Add GPU support with `CuArrays.jl`.