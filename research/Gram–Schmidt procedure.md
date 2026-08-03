The [**Gram–Schmidt procedure**](https://en.wikipedia.org/wiki/Gram–Schmidt_process) is originally a **linear algebra algorithm**: it takes a set of (possibly non-orthogonal) vectors and turns them into an **orthonormal basis**.

In the context of **particle physics and event reconstruction**, when people mention “Gram–Schmidt,” they usually mean they are applying this idea of **orthogonalization** to help reconstruct particle kinematics.
In many reconstruction problems (tracking, jet reconstruction, background suppression, etc.), you deal with vectors in momentum space or feature space that are:
- **Correlated** (e.g. overlapping measurements, jet constituents, calorimeter clusters)
- **Not orthogonal** (so they “double count” information)

The Gram–Schmidt process can be used to:
1. **Make basis vectors orthogonal** → ensures that each reconstructed component (track, shower, or feature) contributes independently.
2. **Stabilize numerical algorithms** → orthogonal bases prevent numerical instabilities when solving equations in fitting and unfolding.
3. **Separate signal from noise** → in high-dimensional feature spaces, orthogonalization helps decorrelate observables so classifiers (like BDTs or NNs) behave more robustly.