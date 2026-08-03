```C++
void Helpers::SplitCanvas(TCanvas*& c,
                          vector<int> active_channels,
                          vector<int> plot_active_channels) {
    // cross check if user input exists in data
    filterChannelUserInput(plot_active_channels, active_channels);
 
    if (plot_active_channels.empty()) {
        c->Divide(
            TMath::Min(static_cast<double>(active_channels.size()), 4.),
            TMath::Max(TMath::Ceil(static_cast<double>(active_channels.size()) / 4.), 1.),
            0, 0);
    }
    else if (static_cast<int>(plot_active_channels.size()) > 1) {
        c->Divide(
            TMath::Min(static_cast<double>(plot_active_channels.size()), 4.),
            TMath::Max(ceil(static_cast<double>(plot_active_channels.size()) / 4.), 1.),
            0, 0);
    }
}
```
### 🔍 What this does conceptually

- A **ROOT `TCanvas`** is like a single figure in matplotlib.
- You can **split** it into multiple “pads” (subplots).
- This function decides _how many subplots to make_, depending on how many channels (detector readouts) you want to show.
- So: If `plot_active_channels` is empty, it uses `active_channels`.
-  Otherwise, it uses the user’s chosen subset.

Then it divides the canvas into a grid with:
- Up to **4 columns**
- Enough rows to fit all channels
E.g.  
If there are 10 channels → 4 columns × 3 rows (to fit all).

### 🧩 How it works
`TCanvas::Divide(nx, ny)`  
→ splits the figure into an `nx`×`ny` grid.
They use some math:
```cpp
TMath::Min(size, 4.)   # Max 4 columns TMath::Ceil(size / 4.) # Enough rows to fit all
```
The result looks like this:

| Channels | Grid created      |
| -------- | ----------------- |
| 1–4      | 1 row × N columns |
| 5–8      | 2 rows × 4 cols   |
| 9–12     | 3 rows × 4 cols   |
| etc.     | ...               |
So the plots tile neatly.
In Python it could look like this:
```python
import math
import matplotlib.pyplot as plt

def split_canvas(active_channels, plot_active_channels):
    if not plot_active_channels:
        n = len(active_channels)
    else:
        n = len(plot_active_channels)

    cols = min(n, 4)
    rows = max(math.ceil(n / 4), 1)
    fig, axes = plt.subplots(rows, cols, figsize=(6*cols, 4*rows))
    return fig, axes

```
That’s almost exactly what this C++ code does, but with `plt.subplots` instead of `c->Divide()`.