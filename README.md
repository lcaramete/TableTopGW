# TableTopGW – Gravitational Waveform Simulator

## 📖 Introduction
**TableTopGW** is an educational and outreach tool that demonstrates the generation of **gravitational-wave–like signals** using a simple **tabletop experiment** combined with Python software.

The system provides:
- A hands-on analogy to **spacetime curvature**.
- Visualization of **binary inspiral dynamics**.
- Simulation of **gravitational waveforms** using the quadrupole formalism.


## 🛠 System Components

### Physical Setup
- Circular **metal frame** (~150 cm diameter).
- **Elastic fabric** stretched over the frame.
- **Heavy central sphere** → simulates a massive astrophysical object (black hole/neutron star).
- **Lighter sphere** → spirals inward, mimicking inspiraling binaries.
- **Webcam** → records sphere motion from above or below.

### Software
- **TableTopGW Python package**
  - Image processing (motion tracking from video).
  - Orbital separation calculation.
  - Gravitational waveform generation.

🔗 Software and datasets are available on GitHub:  
[https://github.com/lcaramete/TableTopGW](https://github.com/lcaramete/TableTopGW)


## ⚙️ Installation

### Requirements
- **Python 3.x**
- Standard Python packages (see `requirements.txt`).

### Setup
```bash
git clone https://github.com/lcaramete/TableTopGW.git
cd TableTopGW
pip install -r requirements.txt
````


## 🧪 Performing the Experiment

### Preparing the Fabric

1. Stretch the **elastic fabric** tightly over the circular frame.
2. Secure it with clips.

### Adding Objects

1. Place the **heavy sphere** at the center (massive compact object).
2. Release the **lighter sphere** (orbiting body).

### Recording Motion

1. Position the **webcam** above or below the setup.
2. Record the full inspiral motion.


## 💻 Software Usage

### Image Processing

* Video is converted into **grayscale frames**.
* **Central mass location** chosen manually in the first frame.
* **Mobile sphere position** extracted by comparing consecutive frames.

Steps:

1. Calculate row/column pixel sums.
2. Compute differences between frames.
3. Identify maximum differences → sphere coordinates.
4. Repeat across all frames.

**Output**: lists of `x, y` positions of the mobile sphere.

### Orbital Separation

Distance between central object and mobile sphere:

```
d = sqrt((x2 - x1)^2 + (y2 - y1)^2)
```

**Output**: time series of orbital separation values.

### Gravitational Wave Generation

* Based on **quadrupole formalism**:

  * Plus polarization `h+(t)`
  * Cross polarization `h×(t)`
  * Combined waveform `h(t)`
* **Outputs**:

  * Raw waveform
  * Interpolated waveform


## ▶️ Example Run

```bash
python main.py --input Example_Data/sample_video.mp4
```

This will:

* Process the recorded video.
* Extract orbital separation.
* Generate gravitational waveforms.


## ⚠️ Limitations

* Elastic fabric is a **2D analogy** of 4D spacetime.
* Only the lighter ball moves (unlike real binaries).
* Inspiral driven by **friction and gravity**, not real gravitational radiation.
* Best results when the **heavy sphere is centered**.


## 🔧 Troubleshooting

* **No sphere detected?** → check grayscale conversion & lighting.
* **Noisy waveform?** → ensure heavy sphere is centered.
* **Weak spiral motion?** → adjust fabric tension or sphere mass.


## 🎓 Educational Use

The TableTopGW system demonstrates:

* **Spacetime curvature** caused by mass.
* **Orbital decay** due to energy loss.
* **Gravitational waves** from binary systems.

It is ideal for **students, educators, and outreach events**.


## 📂 Resources

* Software: [https://github.com/lcaramete/TableTopGW](https://github.com/lcaramete/TableTopGW)
* Example Data: [Example_Data Repository](https://github.com/lcaramete/TableTopGW/tree/main/Example_Data)


## 📜 Citation

Caramete, L.-I., Caramete, A., Işfan, M.-C., Pislan, F.-C., Popescu, T., Băsceanu, V., & Nicolin-Zaczek, A., Tabletop gravitational waves waveform simulator, Institute of Space Science INFLPR subsidiary, University of Bucharest, National Institute of Materials Physics.

