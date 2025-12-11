# GROUP COURSEWORK

## Front Page Information
Module Code: CS2PPNU  
Assignment Title: Python Application Group Project  
Student Number(s):   
Actual Hours Spent:   
AI Tools Used: CURSOR  

## 1.Project Overview 
This project implements a complete Python application system for text-to-QR code conversion, featuring:  
1.Standard QR code encoding (Version 1-L)  
2.Full data bit generation, Reed-Solomon error correction, matrix layout, and mask application   
3.Advanced enhancements (automated version selection, optimal mask selection, educational slides, style rendering, and log analysis)   
4.GUI (PyQt)   
5.Demo presentation, unit testing, and CI integration.   
6.The system is modular and well-structured, with all QR code generation steps compliant with industry standards.  

## 2.File Structure  

### Core Modules
- `qr_encoder.py` — Encoding + ECC  
- `qr_matrix.py` — Matrix construction  
- `qr_capacity.py` — Version capacities  

### Enhancements
- `enhancement_a.py` — Auto version/ECC  
- `enhancement_b.py` — Mask evaluator  
- `enhancement_c.py` — Slideshow  
- `enhancement_d.py` — Custom renderer  
- `enhancement_e.py` — Logger & analytics  

### GUI
- `qt_qr_gui.py` — PyQt GUI  
- `style.qss` — GUI theme  

### Demos
- `demo_1.txt` – `demo_5.txt`  
- QR style images  
- Analytics chart  

### Tests
- `test_project.py`  
- `test_stage2.py`  
- `test_enhancement_*.py`

### Other
- `qr_history.csv`  
- `.gitlab-ci.yml`  
- `README.md`  
- `__pycache__/`  

## 3.How to Run  

### 3.1 Environment configuration  
Python 3.11.7  
`pip install pyqt5 pillow numpy pandas matplotlib reedsolo`  

### 3.2 Launching the GUI  
`qt_qr_gui.py`  
Features include:  
1.Text input  
2.Version selection (including Auto)  
3.ECC selection  
4.QR generation + image preview  
5.Save QR as PNG  
6.Logging of each generation event  

### 3.3 Running Demonstration Scripts  
`run_demos.py`  
This produces:  
1.All five coursework-required demo logs  
2.Rendered QR images  
3.Slideshow samples  
4.Analytics charts

### 3.4 Running Unit Tests  
`test_project.py`  

## 4.QR Encoding Pipeline  
### Step 1 — Text → Binary (Byte Mode)  
Mode indicator: 0100  
Length (8 bits)  
Byte-encoded UTF-8 stream  
Final padded bit length: 152 bits for Version 1-L  

### Step 2 — Error Correction (Reed–Solomon)  
Data codewords: 19  
ECC codewords: 7  
RS parameters use reedsolo library  


