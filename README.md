# Image_Sharpening
 
> **SP13 · Signal Processing Project · IIT Madras BS Electronic Systems**
> Roll No: `23F3000611`
 
An interactive, browser-based lab for spatial-domain image filtering. Upload any image and apply **Mean**, **Gaussian**, and **Laplacian** filters in real time — no installation, no server, no dependencies.
 
---
 
## ✨ Features
 
- **Mean (Box) Filter** — configurable kernel size from 3×3 to 11×11
- **Gaussian Filter** — tunable kernel size + standard deviation σ (0.5 – 5.0)
- **Laplacian Edge Detection** — 4-connected kernel with auto-normalised display
- **Laplacian Unsharp Masking** — live strength slider (α = 0.5 – 5.0), updates instantly
- **Comparison Panel** — side-by-side Gaussian vs. Enhanced view with avg pixel-diff metric
- **Zero dependencies** — pure HTML5 + CSS + vanilla JavaScript, runs entirely in the browser
- **Mobile responsive** — works on phones and tablets too
---
 
## 🚀 Quick Start
 
### Open directly
 
```bash
# Just open the file in your browser
open index.html
```
 
No build step. No `npm install`. No server needed.
 
---
 
**Using VS Code:**
Install the [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) extension, right-click `index.html` → *Open with Live Server*.
 
---
 
## 🎛️ How to Use
 
1. **Upload an image** — click *Choose File* or drag & drop a PNG/JPEG onto the upload area. The image is automatically converted to grayscale.
2. **Set parameters** — adjust *Kernel Size* (3–11) and *Gaussian σ* (0.5–5.0) using the sliders.
3. **Click *Apply Filters*** — all five output panels (Original, Mean, Gaussian, Laplacian Edge, Laplacian Enhanced) render simultaneously.
4. **Tune enhancement live** — drag the *Laplacian Enhancement Strength* slider; the Enhanced panel and comparison update in real time without re-clicking Apply.
5. **Compare** — the bottom panel shows Gaussian Blur vs. Laplacian Enhanced side-by-side with an average pixel-difference readout.
---
 
## 🧮 Signal Processing Details
 
| Filter | Formula | Kernel |
|--------|---------|--------|
| **Mean** | `g(x,y) = (1/k²) Σ f(x+dx, y+dy)` | k×k box |
| **Gaussian** | `h(x,y) = exp(-(x²+y²)/2σ²)` (normalised) | k×k Gaussian |
| **Laplacian** | `∇²f ≈ f*K` where `K = [[0,1,0],[1,-4,1],[0,1,0]]` | 3×3 |
| **Unsharp Mask** | `Enhanced = Original + α × (Original − Gaussian)` | — |
 
Boundary handling: **clamped (replicate) padding** — out-of-bounds indices snap to the nearest valid pixel.
 
---
 
## ⚙️ Browser Compatibility
 
| Browser | Supported |
|---------|-----------|
| Chrome 90+ | ✅ |
| Firefox 88+ | ✅ |
| Edge 90+ | ✅ |
| Safari 14+ | ✅ |
| Mobile Chrome / Safari | ✅ |
 
---
 
## ⚡ Performance Notes
 
- All processing runs on the **browser main thread** using `Float32Array` typed arrays.
- Images up to ~**2 MP** process in under 500 ms on typical hardware.
- For larger images, a future version will use **Web Workers** and **separable 1-D Gaussian convolution** (O(2kN) vs current O(k²N)).
---
 
## 📄 License
 
MIT — free to use, modify, and distribute.
 
---
