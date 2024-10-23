# OCR


# OCR Project - README

## Project Overview
This project demonstrates the use of Optical Character Recognition (OCR) to extract text from images and convert it into machine-readable text. The project utilizes **Tesseract OCR**, **Pillow**, and **Levenshtein** for text recognition and post-processing, while **FPDF** is used to generate PDFs from the recognized text.

## Key Features
- Image preprocessing for enhanced OCR accuracy
- Text recognition using Tesseract OCR
- Error correction using Levenshtein distance
- Conversion of recognized text into searchable PDFs using FPDF
- Jupyter Notebook support for easy testing and demonstration

## Dependencies
To run this project, the following dependencies need to be installed:

1. **Pillow**: For image manipulation and preprocessing
   - Install via pip: `pip install Pillow`

2. **Tesseract OCR**: The core OCR engine used for text recognition
   - Install Tesseract: [Tesseract Installation Guide](https://github.com/tesseract-ocr/tesseract)
   - After installation, add Tesseract to your system's PATH environment.

3. **FPDF**: For generating PDF documents from recognized text
   - Install via pip: `pip install fpdf`

4. **Levenshtein**: For post-processing, error correction, and improving recognition accuracy.
   - Install via pip: `pip install python-Levenshtein`

## Installation

### 1. Clone the repository:
```bash
git clone https://github.com/yourusername/ocr-project.git
cd ocr-project
```

### 2. Install Python dependencies:
```bash
pip install -r requirements.txt
```

### 3. Install Tesseract OCR:
Refer to the [Tesseract Installation Guide](https://github.com/tesseract-ocr/tesseract) to install Tesseract on your system.

### 4. Verify Tesseract Installation:
Run the following command to ensure Tesseract is correctly installed:
```bash
tesseract --version
```

## Usage

### 1. Preprocess Image:
Use Pillow to preprocess the image (e.g., converting to grayscale, resizing, or thresholding). This step helps in improving OCR accuracy.

### 2. Run OCR:
Use Tesseract OCR to extract text from the preprocessed image.
```python
from PIL import Image
import pytesseract

# Load and preprocess the image
img = Image.open('sample.jpg')
text = pytesseract.image_to_string(img)

print(text)
```

### 3. Error Correction (Levenshtein):
After extracting the text, use Levenshtein distance to correct any OCR errors.

### 4. Generate PDF:
Use FPDF to create a searchable PDF from the recognized text.

```python
from fpdf import FPDF

pdf = FPDF()
pdf.add_page()
pdf.set_font("Arial", size=12)
pdf.multi_cell(200, 10, txt=text)
pdf.output("output.pdf")
```

## Testing and Validation
Run the provided Jupyter Notebook to see the full OCR pipeline in action, from image preprocessing to PDF generation.

## Contribution
Feel free to submit issues or pull requests to improve this project.

## License
This project is licensed under the MIT License.
