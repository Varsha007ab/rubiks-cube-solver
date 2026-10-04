# 🧩 Rubik's Cube Vision Solver

> A computer-vision based Rubik's Cube solver that detects sticker colors from images and generates a solution sequence automatically.

**Team 5 — Manasvi · Pragya · Varsha**

---

## ✨ Overview

This project combines **computer vision, image processing, color classification, cube-state validation, and automated Rubik's Cube solving**.

The system accepts images of the six cube faces, detects the 3×3 sticker grid, classifies sticker colors using HSV-based color references, validates the resulting cube state, converts it into standard cube notation, and generates a sequence of moves using the Kociemba solver.

### Pipeline

```text
Six Cube Face Images
        ↓
OpenCV Image Processing
        ↓
3 × 3 Sticker Grid Detection
        ↓
HSV Color Classification
        ↓
Confidence + Cube Validation
        ↓
Kociemba Cube Notation
        ↓
Automated Solution
        ↓
Step-by-Step Moves
```

---

## 🚀 Features

- 📷 Image-based Rubik's Cube face detection
- 🎨 HSV-based sticker color classification
- 🔎 Automatic 3×3 grid sampling
- 📊 Confidence scoring for detected stickers
- ✅ Cube-state validation
- 🔄 Conversion to Kociemba face notation
- 🧠 Automated cube solving
- 📝 Step-by-step explanation of every generated move
- 🐞 Debug images showing detected grids and colors

---

## 🛠️ Technologies

| Technology | Purpose |
|---|---|
| Python | Core implementation |
| OpenCV | Image processing and visualization |
| NumPy | Numerical/image operations |
| Kociemba | Rubik's Cube solving |
| Google Colab | Original execution environment |

---

## 📁 Project Structure

```text
rubiks-cube-solver/
│
├── src/
│   └── rubiks_cube_solver.py
│
├── docs/
│   └── PROJECT_REPORT.docx
│
├── presentation/
│   └── TEAM5_PRESENTATION.pptx
│
├── assets/
│   └── README.md
│
├── notebooks/
│   └── README.md
│
├── README.md
├── requirements.txt
├── IMPLEMENTATION_NOTE.md
├── LICENSE
└── .gitignore
```

---

## ⚙️ Installation

Clone the repository:

```bash
git clone https://github.com/Varshaa007ab/rubiks-cube-solver.git
cd rubiks-cube-solver
```

Install dependencies:

```bash
pip install -r requirements.txt
```

### Dependencies

```text
opencv-python-headless
numpy
kociemba
```

---

## ▶️ Running the Project

The original implementation is designed for **Google Colab** and uses Colab's file-upload interface.

Open the Python file in Google Colab or adapt the upload section for a local environment.

The program expects six images corresponding to:

```text
U.jpg
R.jpg
F.jpg
D.jpg
L.jpg
B.jpg
```

The program detects the stickers, validates the cube configuration, creates the solver input string, and prints the solution.

---

## 📸 Input Requirements

For reliable detection:

- Keep the cube centered in the image.
- Keep one face approximately straight toward the camera.
- Use bright, even lighting.
- Avoid strong shadows and reflections.
- Make sure all nine stickers are visible.
- Upload all six faces using the expected face names.

The implementation also creates annotated/debug images that can be inspected to understand how the computer vision stage classified each sticker.

---

## 🧠 How the Computer Vision Works

### 1. Grid detection

The image is sampled around a dynamically calculated 3×3 grid.

### 2. HSV classification

Each sticker region is converted to HSV and compared against reference HSV values for:

```text
White
Yellow
Red
Orange
Green
Blue
```

### 3. Face mapping

The center sticker of each face is used to determine which detected color corresponds to the standard cube face notation.

### 4. Validation

The program checks that:

- Each cube color occurs nine times.
- The six center stickers correspond to different faces.

### 5. Solving

The validated cube state is converted to the solver's facelet notation and passed to the Kociemba solver.

---

## 🧪 Example Output

The program prints information similar to:

```text
Detected face stickers:

Kociemba cube string:
...

Solution moves:
R U R' F2 ...

Step-by-step:
1. R -> Turn R face clockwise
2. U -> Turn U face clockwise
3. R' -> Turn R face counterclockwise
...
```

---

## 🐞 Debug Output

The program creates a `debug_output` directory containing:

```text
U_annotated.png
U_preview.png
R_annotated.png
R_preview.png
...
```

These files help inspect whether the sticker grid and color classification are working correctly.

---

## 📚 DSA Context

The accompanying project report and presentation discuss the Rubik's Cube as a state-space search problem and cover:

- Cube state representation
- Graph search
- IDA*
- Heuristic functions
- Recursion / DFS
- Move generation
- Complexity analysis
- Alternative search approaches

The report describes a 54-sticker representation and discusses IDA* as the primary algorithmic approach.

> **Implementation note:** the Python implementation included in this repository uses the `kociemba` package for the final solving stage. The accompanying academic report/presentation discuss IDA* as the DSA approach. See `IMPLEMENTATION_NOTE.md` for this distinction.

---

## 📖 Documentation

- **[Project Report](docs/PROJECT_REPORT.docx)**
- **[Team Presentation](presentation/TEAM5_PRESENTATION.pptx)**
- **[Implementation Note](IMPLEMENTATION_NOTE.md)**

---

## 🔮 Future Improvements

Potential extensions include:

- Real-time webcam cube detection
- Interactive 3D cube visualization
- Web-based user interface
- Automatic camera guidance
- Stronger color calibration
- More robust perspective correction
- Pattern-database based solving
- Local implementation of IDA*
- Support for larger cube variants

---

## 👩‍💻 Team

**Team 5**

- Manasvi
- Pragya
- Varsha

---

## 📄 License

This project is intended for educational and academic use.
