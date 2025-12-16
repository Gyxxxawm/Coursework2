# GROUP COURSEWORK

## Front Page Information
- **Module Code**: `CS2PPNU`
- **Assignment Title**: _Python QR Code Generator_
- **Student Number(s)**: _To be filled_
- **Actual Hours Spent**: _Approx. XX hours_
- **AI Tools Used**: **ChatGPT** _(documentation support only)_

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



## 11.References  
ISO/IEC 18004:2006 — QR Code Specification  
Thonky.com — QR Code Tutorial  
reedsolo Library Documentation  
PyQt5, Pillow, NumPy, Pandas, Matplotlib  
GitLab CI Documentation  

## 12.Statement on AI Usage
1.All code and technical design decisions were independently implemented and manually verified.  
2.No AI-generated code was directly submitted.   

