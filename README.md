# 🧪 File-Based Testing Framework with Python

A comprehensive Python testing framework that allows you to define test cases in simple text files and run them through both command-line interface and a beautiful web dashboard.

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/downloads/release/python-380/)
[![Flask](https://img.shields.io/badge/Flask-3.0.0-green.svg)](https://pypi.org/project/Flask/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
![Status](https://img.shields.io/badge/Status-Active-success.svg)

## 📋 Table of Contents


[🎯 Overview](#-overview)  
[✨ Features](#-features)  
[🛠️ Technology Stack](#️-technology-stack)  
[📦 Installation](#-installation)  
[🚀 Usage](#-usage)  
  - [Command Line Interface](#command-line-interface)
  - [Web Interface](#web-interface)  
[📝 Test File Format](#-test-file-format)  
[💡 Examples](#-examples)  
[📁 Project Structure](#-project-structure)  
[📸 Screenshots](#-screenshots)  
[🤝 Contributing](#-contributing)  
[📄 License](#-license)  
[🙏 Acknowledgments](#-acknowledgments)  



[🔴 Overview](#-overview)  
🟠 [Features](#-features)  
🟡 [Technology Stack](#️-technology-stack)  
[🟡 Technology Stack](#-technology-stack)  
🟢 [Installation](#-installation)  
🔵 [Usage](#-usage)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;▶️ [Command Line Interface](#command-line-interface)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;▶️ [Web Interface](#web-interface)  
🟣 [Test File Format](#-test-file-format)  
🟤 [Examples](#-examples)  
⚫ [Project Structure](#-project-structure)  
⚪ [Screenshots](#-screenshots)  
🔴 [Contributing](#-contributing)  
🟠 [License](#-license)  
🟡 [Acknowledgments](#-acknowledgments)  

## 🎯 Overview

This project provides a simple yet powerful way to create and execute automated tests. Instead of writing complex test code, you can define your test cases in easy-to-read `.test` files with a straightforward format. The framework supports multiple test types including math expressions, Python code, JSON validation, and string matching.

Perfect for:
- **QA Engineers** who need quick test execution
- **Developers** wanting simple integration tests
- **Teams** requiring shareable test definitions
- **Educators** teaching software testing concepts

## ✨ Features

### Core Features
- 📝 **Simple Test Definition** - Write tests in plain text files
- 🖥️ **Dual Interface** - Command-line tool and web dashboard
- 🎨 **Beautiful Web UI** - Modern, responsive design with real-time results
- 📊 **Multiple Test Types** - Exact match, contains, regex, JSON comparison
- 🏷️ **Tag System** - Organize and filter tests by tags
- ⚡ **Fast Execution** - Run single tests or entire test suites
- 📈 **Detailed Reporting** - See pass/fail status with execution times
- 🔄 **Universal Handler** - Automatically detects and runs different input types

### Test Types Supported
- ✅ **Math Expressions** - `2+2`, `5*3`, `10/3`
- ✅ **Python Code** - `print('Hello')`, list operations, boolean logic
- ✅ **JSON Validation** - Compare JSON objects and arrays
- ✅ **String Matching** - Exact, contains, and regex patterns

## 🛠️ Technology Stack

### Backend
- **Python 3.8+** - Core language
- **Flask 3.0.0** - Web framework
- **subprocess** - Command execution
- **argparse** - CLI argument parsing

### Frontend
- **HTML5** - Structure
- **CSS3** - Styling with gradients and animations
- **JavaScript (ES6+)** - Interactive functionality
- **Fetch API** - Asynchronous requests

### Testing
- **Custom Framework** - Purpose-built test parser and runner
- **Multiple Assertion Types** - Flexible comparison methods

## 📦 Installation

### Prerequisites
- Python 3.8 or higher
- pip (Python package manager)

### Steps

1. **Clone the repository**
```bash
git clone https://github.com/qa-elevated-solutions/file-based-testing-with-python.git
cd file-based-testing-with-python
```

2. **Install dependencies**
```bash
pip install -r requirements.txt
```

3. **Verify installation**
```bash
python test_framework.py --help
```

## 🚀 Usage

### Command Line Interface

#### Run all tests in current directory
```bash
python test_framework.py . -c "python run_test.py {input}"
```

#### Run specific test file
```bash
python test_framework.py samples/sample_math.test -c "python run_test.py {input}"
```

#### Filter by tags
```bash
python test_framework.py . -c "python run_test.py {input}" -t "math,basic"
```

#### Verbose output
```bash
python test_framework.py . -c "python run_test.py {input}" -v
```

#### Custom file pattern
```bash
python test_framework.py . -c "python run_test.py {input}" -p "*.test"
```

### Web Interface

1. **Start the Flask server**
```bash
python app.py
```

2. **Open your browser**
```
http://localhost:5000
```

3. **Select or upload test files**
   - Use the "Select Test File" tab to choose from existing tests in `samples/`
   - Or use "Upload New File" to test ad-hoc files

4. **Configure command template** (default: `python run_test.py {input}`)

5. **Click "Run Tests"** to see results in real-time

## 📝 Test File Format

Test files use a simple, readable format:

```
### TEST: Test Name
DESCRIPTION: What this test does
TYPE: exact
TAGS: category1, category2
INPUT: your input data here
EXPECTED: expected output here
```

### Field Descriptions

| Field | Required | Description |
|-------|----------|-------------|
| `TEST:` | ✅ Yes | Test case name |
| `DESCRIPTION:` | ❌ No | Brief description of the test |
| `TYPE:` | ❌ No | Comparison type: `exact`, `contains`, `regex`, `json` (default: `exact`) |
| `TAGS:` | ❌ No | Comma-separated tags for filtering |
| `INPUT:` | ✅ Yes | Input data to test |
| `EXPECTED:` | ✅ Yes | Expected output |

### Test Types

- **exact** - Output must match exactly
- **contains** - Output must contain the expected text
- **regex** - Output must match the regular expression
- **json** - Output must match as JSON (structure and values)

## 💡 Examples

### Example 1: Math Tests

```
### TEST: Addition Test
DESCRIPTION: Test basic addition
TYPE: exact
TAGS: math, basic
INPUT: 2+2
EXPECTED: 4

### TEST: Division Test
DESCRIPTION: Test division with decimal
TYPE: contains
TAGS: math, decimal
INPUT: 10/3
EXPECTED: 3.3
```

### Example 2: Python Code Tests

```
### TEST: Python Hello World
DESCRIPTION: Test print statement
TYPE: exact
TAGS: python, basic
INPUT: print('Hello World')
EXPECTED: Hello World

### TEST: List Length
DESCRIPTION: Test list operations
TYPE: exact
TAGS: python, list
INPUT: print(len([1, 2, 3, 4, 5]))
EXPECTED: 5
```

### Example 3: JSON Tests

```
### TEST: JSON Object Test
DESCRIPTION: Validate JSON structure
TYPE: json
TAGS: json, data
INPUT: {"name": "test", "value": 123}
EXPECTED: {"name": "test", "value": 123}

### TEST: JSON Array Test
DESCRIPTION: Validate JSON array
TYPE: json
TAGS: json, array
INPUT: [1, 2, 3, 4, 5]
EXPECTED: [1, 2, 3, 4, 5]
```

### Example 4: String Tests

```
### TEST: Contains Test
DESCRIPTION: Test partial match
TYPE: contains
TAGS: string, partial
INPUT: The quick brown fox jumps over the lazy dog
EXPECTED: quick brown fox

### TEST: Regex Test
DESCRIPTION: Test pattern matching
TYPE: regex
TAGS: string, regex
INPUT: test@example.com
EXPECTED: \w+@\w+\.\w+
```

## 📁 Project Structure

```
file-based-testing-with-python/
├── app.py                      # Flask web application
├── test_framework.py           # Core testing framework
├── run_test.py                 # Universal test input handler
├── requirements.txt            # Python dependencies
├── README.md                   # Documentation (you are here)
├── LICENSE                     # MIT License
├── .gitignore                  # Git ignore rules
├── samples/                    # Sample test files
│   ├── sample_math.test
│   ├── sample_python.test
│   ├── sample_strings.test
│   └── all.test
└── screenshots/                # UI screenshots
    └── result_01.png
    ├── result_02.png
    ├── result_03.png
    ├── result_04.png
    └── ui_01.png
```

## 📸 Screenshots

### Web Dashboard
![Dashboard](https://github.com/user-attachments/assets/7bc6e1c4-8e6a-4414-a7d7-6bab3209d8b5)
*Main Dashboard*

![Dashboard](https://github.com/user-attachments/assets/184408d0-9500-4195-b455-30377911234d)
*Test Result 1: all.test*

![Dashboard](https://github.com/user-attachments/assets/4ad97cba-26e7-4ac6-b2e7-79a4f9c70092)
*Test Result 2: sample_math.test*

![Dashboard](https://github.com/user-attachments/assets/e3105358-1def-463b-a741-4ce54073494e)
*Test Result 3: sample_python.test*

![Dashboard](https://github.com/user-attachments/assets/d14861e6-3f59-4d43-8b69-0d1763b676a1)
*Test Result 4: sample_strings.test*

### Command Line Output
```
Found 4 test file(s)
Running 19 test(s)...
======================================================================
TEST RESULTS
======================================================================

✓ PASS Addition Test
✓ PASS Multiplication Test
✓ PASS Division Test
✓ PASS Python Hello World
✓ PASS JSON Test

======================================================================
Total: 19 | Passed: 19 | Failed: 0
======================================================================
```

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Fork the repository**
2. **Create a feature branch** (`git checkout -b feature/AmazingFeature`)
3. **Commit your changes** (`git commit -m 'Add some AmazingFeature'`)
4. **Push to the branch** (`git push origin feature/AmazingFeature`)
5. **Open a Pull Request**

### Areas for Contribution
- 🐛 Bug fixes and improvements
- 📚 Documentation enhancements
- ✨ New test types and features
- 🎨 UI/UX improvements
- 🧪 Additional test examples
- 🌐 Internationalisation

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Inspired by modern testing frameworks like pytest and unittest
- Built with ❤️ for the QA and development community

## 📞 Contact

- GitHub: [@leonardushutabarat](https://github.com/leonardushutabarat)
- Repository: [https://github.com/leonardushutabarat/File-Based-Testing](https://github.com/leonardushutabarat/File-Based-Testing)

---

**⭐ Star this repository if you find it helpful!**
