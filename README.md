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

### Step 3 — Matrix Construction  
Matrix size: 21 × 21 (Version 1)  
Includes:  
Finder patterns  
Timing patterns  
Format info reserved areas  
Dark module  
Data region  

### Step 4 — Zig-Zag Data Placement  

### Step 5 — Mask Application  
Default: Mask 0  
(Other masks available via Enhancement B)  
Step 6 — Format Information Encoding  
ECC level + mask bits encoded and written to proper locations.  

## 5.Coursework Demos (demo_1.txt – demo_5.txt)   
The project includes all required demonstration logs.  
### Demo 1 — “known”
✓ Successfully encoded  
✓ 152-bit binary stream  
✓ 19 data codewords + 7 ECC  
✓ Includes full ASCII matrix  
→ File: demo_1.txt  

### Demo 2 — “We’ve succeeded!”  
✓ Encodes mixed ASCII including punctuation  
✓ Fits in Version 1-L  
→ File: demo_2.txt  

### Demo 3 — “~¡256_-_aA&ñ”  
✓ Includes extended UTF-8 characters  
✓ Encodes successfully  
→ File: demo_3.txt  

### Demo 4 — “From α to ɷ...”  
✓ Contains Greek letters  
✓ Encoded and matrix printed  
→ File: demo_4.txt  

### Demo 5 — “Sugarplum_Fairy_Nightmare”  
✗ Length = 25 bytes  
✗ Version 1-L maximum = 19 bytes  
→ Correctly raises capacity error  
→ File: demo_5.txt  

## 6.Enhancements A–E (All Implemented)  
### Enhancement A — Auto Version & ECC
File: `enhancement_a.py`  
Automatically selects minimal Version supporting the input  
Supports Version 1 & 2  
Auto ECC selection  
Outputs images such as:  
`option_a_final_test.png`   
`option_a_v2_test.png`  
Test: `test_enhancement_a.py`  

### Enhancement B — Mask Evaluator   
File: `enhancement_b.py`  
Computes penalty scores for all 8 masks  
Returns the best mask ID  
Compatible with any QRMatrix instance  
Test: `test_enhancement_b.py`  

### Enhancement C — Educational Slideshow  
File: `enhancement_c.py`  
Produces step-by-step educational frames  
Visualizes matrix evolution  
Tkinter UI with Next/Prev navigation  
Can export frames  
Excellent for teaching QR internals  
Test: `test_enhancement_c.py`  

### Enhancement D — Custom Renderer  
File: `enhancement_d.py`  
Renders QR with custom:  
Shapes (square / circle)  
Colors (fg/bg)  
Scaling   
Produces stylized results (corporate, aesthetic, dark mode)  
Test: `test_enhancement_d.py`  

### Enhancement E — Logging & Analytics
File:` enhancement_e.py`  
Logs all generation events to CSV  
Fields include:  
`Timestamp, Text, Version, ECC_Level, Mask, Style, Warning, Success`    
Generates analytics chart (e.g., succss ratio over time)  
Example output: `option_e_chart.png`  
Test: `test_enhancement_e.py` & `test_stage2.py`  

## 7.Testing & CI  
### 7.1 Unit Tests  
Test suites cover:  
Binary encoding correctness  
Input overflow handling  
Matrix dimension + finder pattern correctness  
Auto version/ECC selection  
Mask evaluation scoring  
Logger field validation  
GUI exceptions and fallback behaviour  
Main tests:  
`test_project.py`  
`test_stage2.py`  
`test_enhancement_a.py`  
`test_enhancement_b.py`  
`test_enhancement_c.py`  
`test_enhancement_d.py`  
`test_enhancement_e.py`  

### 7.2 CI Pipeline
The .gitlab-ci.yml file runs:
`pytest`  
Linting (optional)  
Build & test automation  

## 8.GUI (PyQt5 Application)  
Main features:  
Clean interface styled with QSS  
Text input, Version/ECC selectors  
Real-time QR rendering  
PNG export  
Error messages (overflow, invalid input)  
Automatic history logging  
File: `qt_qr_gui.py`  

## 9.Analytics Example (Enhancement E)
Example chart (`option_e_chart.png`):  
X-axis: date or timestamp  
Y-axis: success ratio  
Useful for monitoring usage trends and failures  

## 10.Limitations & Safety Notes  
1.QR Codes can embed malicious URLs — users must generate responsibly  
2.Low-contrast custom styles may reduce scan reliability  
3.Version 1 has strict size limitations  
4.Unicode consumes multiple bytes; capacity overflow possible  
5.System intended for teaching, not industrial deployment  

## 11.References  
ISO/IEC 18004:2006 — QR Code Specification  
Thonky.com — QR Code Tutorial  
reedsolo Library Documentation  
PyQt5, Pillow, NumPy, Pandas, Matplotlib  
GitLab CI Documentation  

## 12.Statement on AI Usage
1.All code and technical design decisions were independently implemented and manually verified.  
2.No AI-generated code was directly submitted.   

