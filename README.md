# PII Redaction Library 🔒

[![PyPI Version](https://img.shields.io/pypi/v/pii-redactor)](https://pypi.org/project/pii-redactor/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python Version](https://img.shields.io/pypi/pyversions/pii-redactor)](https://pypi.org/project/pii-redactor/)

Advanced Personally Identifiable Information (PII) detection and redaction library with multi-format support.

![PII Redaction Demo](https://via.placeholder.com/800x400.png?text=PII+Redaction+Demo)

## Features ✨
- 📄 Multi-format support: Text, DOCX, PDF
- 🌍 Localization: English & Spanish (extensible)
- 🔄 Redaction reversal via JSON logs
- 🛡️ Detects:
  - Emails • Phones • SSNs • Credit Cards
  - Names • Organizations • Custom patterns
- 🧩 Configurable regex patterns via YAML
- 📊 Built-in validation for credit cards & SSNs

## Installation 💻
```bash
pip install pii-redactor
python -m spacy download en_core_web_sm
python -m spacy download es_core_news_sm



Usage 🚀
Command Line Interface
# Basic redaction
pii-redact input.txt output.txt

# Spanish localization
pii-redact documento.docx redactado.docx --locale es_ES

# Custom config
pii-redact sensitive.pdf redacted.pdf --config custom_config.yml

# Redaction reversal
pii-redact redacted.txt original.txt --reverse redacted.log.json
Python API
from pii_redactor import PIIRedactor

redactor = PIIRedactor(locale='es_ES')
result = redactor.process_file("input.docx", "output.docx")

print(f"Redacted {len(result['emails'])} emails")
print(f"Detected {len(result['names'])} names")


Configuration ⚙️
Create custom_config.yml:

yaml
patterns:
  employee_id: '\bEMP-\d{5}\b'
locales:
  en_US:
    honorifics: ['Dr.', 'Madam']
    patterns:
      custom_phone: '\d{3}-\d{3}-\d{4}'


Supported Locales 🌐
Locale	Entities Detected	spaCy Model
en_US	Names, Orgs, US PII	en_core_web_sm
es_ES	Spanish names, DNI, IBAN	es_core_news_sm


Contributing 🤝
Fork the repository

Create your feature branch (git checkout -b feature/amazing-feature)

Commit changes (git commit -m 'Add amazing feature')

Push to branch (git push origin feature/amazing-feature)

Open a Pull Request

License 📄
This project is licensed under the MIT License - see LICENSE for details.

Acknowledgments
Built with ❤️ using spaCy

PDF handling by pdfplumber

Inspired by GDPR/CCPA compliance needs



---

### **LICENSE** (MIT)
```text
MIT License

Copyright (c) 2023 [Your Name or Organization]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
Deployment Steps
Save these files in your project root:

README.md

LICENSE

Commit and push:

bash
git add README.md LICENSE
git commit -m "Add documentation and license"
git push origin main
Your GitHub repository will now show:

Professional README rendering

License visible in repo header

Clear usage instructions for visitors