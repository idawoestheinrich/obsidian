## Core Concepts to Understand
#### 1. Functional Programming & Pure Functions
Phlex guarantees thread safety by enforcing functional principles. Instead of algorithms reaching out and modifying global event states, you write **pure functions** (or algorithm modules) that:
Office of Scientific and Technical Information (OSTI) (.gov)
- Take explicit, immutable inputs.
- Return explicit outputs without side effects.
- Never mutate shared memory.

#### 2. Directed Acyclic Graph (DAG) Execution
Instead of executing code linearly (event by event), Phlex builds an execution graph.
- **Nodes** are your algorithms (e.g., Pythia event generator, Geant4 transport step, digitizer).
- **Edges** represent data dependencies.
- Phlex automatically resolves dependencies and runs non-dependent tasks concurrently across CPU threads.
#### 3. Fine-Grained & Hierarchical Parallelism
Older frameworks parallelized at the _event_ level (Thread 1 does Event A, Thread 2 does Event B). Phlex supports **hierarchical execution**:

Office of Scientific and Technical Information (OSTI) (.gov)
- It can run different algorithms on the _same_ event in parallel if they don't depend on each other.
- It can process sub-event structures (like individual tracks or detector modules) independently.

### Technical Prerequisites

To be comfortable writing C++ within Phlex, focus on these building blocks:
- **Modern C++ (C++17 / C++20):**
    - Immutable references (`const &`), smart pointers (`std::shared_ptr`, `std::unique_ptr`), and `std::optional`.
    - Lambda functions and `std::function` wrappers.
    - Value semantics (copy/move operations).
        
- **Task-Based Concurrency:**
    - How task schedulers (like Intel oneTBB, which heavily influences HEP frameworks) split work into lightweight, lock-free tasks rather than heavy threads.

- **Config-Driven Frameworks:**
    - Phlex workflows are wired using declarative configuration files (defining which modules to load and how data flows between them).
        

### Step-by-Step Learning Plan
1. **Understand Data-Flow Graphs:** Draw your physics simulation pipeline as a flowchart (Inputs → Processing Steps → Outputs). Identify which steps can run at the same time.
2. **Explore the Source Code:** Check out the official repository (`Framework-R-D/phlex` on GitHub). Walk through the example user code to see how a Phlex module is structured.
3. **Write a Minimal Module:** Implement a simple algorithm module that takes a dummy data product, performs a pure transformation, and produces an output product.
4. **Inspect I/O Integration:** Look at how Phlex handles persistence (saving data), particularly its integration with **FORM** (Fine-grained Object Reading/Writing Model) and **ROOT**.