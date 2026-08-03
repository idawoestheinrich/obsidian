TGraph objects
A [TGraph](https://root.cern.ch/doc/master/classTGraph.html "A TGraph is an object made of two arrays X and Y with npoints each.") is an object made of two arrays X and Y with npoints each.

A **`TGraph`** in ROOT refers to a **graph of points (xᵢ, yᵢ)** — essentially a _scatter plot_ or _curve_ defined by arrays of x-values and y-values.

It is one of ROOT’s core classes for representing **arbitrary sets of points**, especially when the x-axis is _not evenly spaced_.

# 📘 What is `TGraph`?
A **TGraph** object stores two parallel arrays:
- `x[i]` — x-coordinates
- `y[i]` — y-coordinates
Each pair `(x[i], y[i])` defines a point.
Unlike [[TH1F Class Reference|TH1F]] (histograms), a `TGraph`:
 - does **not** impose bins
- does **not** histogram data
- simply draws the points (optionally connected with lines)