# GROUP COURSEWORK

## Front Page Information
- **Module Code**: `CS2PPNU`
- **Assignment Title**: _Python QR Code Generator_
- **Student Number(s)**:


- **Actual Hours Spent**: 
- **AI Tools Used**: CURSOR

---

## 1. Project Overview
This project implements a **complete QR code generation system** in Python, compliant with the _ISO/IEC 18004_ standard.

The system includes:
1. **Standard QR encoding** (Byte mode)
2. **Automatic version & ECC selection**
3. **Mask pattern evaluation**
4. **Multiple rendering styles**
5. **Interactive GUI** (`PyQt`)
6. **Testing, logging, and CI integration**

The coursework focuses on **correctness**, **clarity**, and **explainability**, rather than industrial optimisation.

---

## 2. File Structure

### Core QR Modules
- `qr_encoder.py` — **Data encoding & Reed–Solomon ECC**
- `qr_matrix.py` — **Matrix construction & data placement**
- `qr_capacity.py` — _Version capacity table_

### Enhancements
- `enhancement_a.py` — **Auto version & ECC**
- `enhancement_b.py` — _Mask evaluator_
- `enhancement_c.py` — **Educational slideshow**
- `enhancement_d.py` — _Custom renderer_
- `enhancement_e.py` — **Logging & analytics**

### GUI
- `qt_qr_gui.py` — **PyQt GUI application**
- `style.qss` — _GUI stylesheet_

### Demonstrations
- `demo_1.txt` – `demo_5.txt`
- _QR output images_
- _Analytics charts_

### Tests
- `test_project.py`
- `test_stage2.py`
- `test_enhancement_a.py` – `test_enhancement_e.py`
- `test_gui_pytest.py`

### Other Files
- `run_demos.py`
- `validate_all_tests.py`
- `qr_history.csv`
- `.gitlab-ci.yml`

---

## 3. How to Run

### 3.1 Environment Configuration
- **Python Version**: `>= 3.11`

Install dependencies:
```bash
pip install pyqt5 pillow numpy pandas matplotlib reedsolo
```

### 3.2 Launching the GUI

Run the application:

```bash
python qt_qr_gui.py
```

Main features:
- **Text input**
- _Manual / automatic_ version selection
- **ECC level** selection
- **Real-time QR preview**
- `PNG` export
- **Automatic logging**


### 3.3 Running Demonstration Scripts

Generate all coursework demos:

```bash
python run_demos.py
```

This produces:
- `demo_1.txt` – `demo_5.txt`
- QR output images
- Educational slideshow frames
- Analytics charts 

### 3.4 Running Tests and Validation

Run unit tests:

```bash
pytest
```

Run full validation:

```bash
python validate_all_tests.py
```

This generates `test_validation_report.txt`.

---

## 4. QR Encoding Pipeline

### Step 1 — Text Encoding
- Mode: **Byte mode** (`0100`)
- UTF-8 byte stream
- Character count appended

### Step 2 — Error Correction
- **Reed–Solomon ECC**
- Implemented using `reedsolo`

### Step 3 — Matrix Construction
- Matrix size determined by QR version
- Finder, timing, and format patterns placed

### Step 4 — Data Placement
- **Zig-zag** placement algorithm
- Reserved areas skipped

### Step 5 — Mask Application
- Default mask used in Stage 1
- Optimal mask selected via **Enhancement B**

### Step 6 — Format Information
- ECC level and mask ID encoded
- Written to reserved locations

---

## 5. Coursework Demonstrations

### Demo 1 — _Basic ASCII_
✓ Successful encoding
✓ Full binary and matrix log
→ File: [demo_1.txt](demo_1.txt)

### Demo 2 — _Mixed Characters_
✓ Includes punctuation
→ File: [demo_2.txt](demo_2.txt)

### Demo 3 — _UTF-8 Input_
✓ Non-ASCII bytes
→ File: [demo_3.txt](demo_3.txt)

### Demo 4 — _Unicode Input_
✓ Greek characters
→ File: [demo_4.txt](demo_4.txt)

### Demo 5 — _Capacity Overflow_  
✗ Input exceeds Version 1-L  
✓ Correctly logs capacity error  
→ File: [demo_5.txt](demo_5.txt)

### Screen recording of GUI QR generation
(gui_demo.mp4)

QR CODE PICTURE OF DEMO 2
→ File:[demo_2.png](demo_2.png)

---

## 6. Enhancements

### Enhancement A — **Auto Version & ECC**
Automatically selects the minimal supported QR version.
_Test_: `test_enhancement_a.py`

### Enhancement B — **Mask Evaluation**
Evaluates all 8 mask patterns and selects the lowest penalty score.
_Test_: `test_enhancement_b.py`

### Enhancement C — **Educational Slideshow**
Provides step-by-step QR matrix visualisation.
_Test_: `test_enhancement_c.py`

### Enhancement D — **Custom Renderer**
Supports shapes, colours, and visual styles.
_Test_: `test_enhancement_d.py`

### Enhancement E — **Logging & Analytics**
Logs all generation events to CSV and generates charts.
_Test_: `test_enhancement_e.py`

---

## 7. Testing & CI

### 7.1 Testing
Tests validate:
- Encoding correctness
- Capacity handling
- Mask scoring
- Enhancement integration
- GUI error handling

### 7.2 Continuous Integration
GitLab CI automatically runs:
- `pytest`
- Validation checks

### 7.2 Demonstrations

---

## 8. GUI Application
The GUI integrates all enhancements and provides:
- **Clean layout**
- Error prompts
- Style customisation
- **Automatic logging**

---

## 9. Analytics Output
Analytics charts display:
- Success ratio
- Error frequency
- Usage trends

---

## 10. Limitations
- Version 1 QR codes have strict capacity limits
- Custom styles may reduce scan reliability
- GUI testing is partially manual
- Performance is not optimised
- Intended for coursework use

---

## 11. References
- ISO/IEC 18004 — QR Code Specification
- Python Official Documentation
- PyQt5 Documentation
- reedsolo Library

---

## 12. Statement on AI Usage
- AI tools were used only for documentation assistance
- All code and testing were manually implemented

