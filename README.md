Convertly | PDF to Word Converter

A responsive web application that converts text-based PDF documents into editable Microsoft Word (.docx) files.

Built using Python, Flask, pdf2docx, HTML, CSS, and JavaScript.

Convertly offers a simple interface with drag-and-drop uploading, file validation, and automatic Word document downloads.

Features

Upload PDF files using drag and drop or file selection

Convert text-based PDFs into editable Word documents

Automatically download converted DOCX files

Modern, responsive user interface

File validation and helpful error messages

Maximum file size of 15 MB

Supports PDFs containing up to 75 pages

Rejects invalid and password-protected PDFs

Temporary file processing

Automated API tests

Technologies Used

Technology

Purpose

Python

Backend programming

Flask

Web application framework

pdf2docx

PDF to Word conversion

PyMuPDF

PDF validation

HTML5

Application structure

CSS3

Design and responsive layout

JavaScript

File uploads and frontend interaction

pytest

Automated testing

Installation and Setup Using VS Code

Follow these instructions to run the project on your computer.

Step 1: Download the Project

Click the green Code button at the top of this GitHub repository.

Select Download ZIP and extract the downloaded file.

Open Visual Studio Code and select:

File → Open Folder

Choose the extracted pdf-to-word-converter folder.

Alternatively, copy the repository's HTTPS link from the GitHub Code menu and clone it using Git.

Step 2: Install Python

Ensure Python 3.11 is installed on your computer.

Download Python from https://www.python.org/downloads/ if needed.

Open the VS Code terminal:

Terminal → New Terminal

Verify your Python installation:

py -3.11 --version

You should see a Python version displayed.

Step 3: Create a Virtual Environment

In your VS Code terminal, run:

py -3.11 -m venv .venv

This creates a separate Python environment for the project.

If Python 3.11 is not available but another supported Python version is installed, you can use:

py -m venv .venv

Step 4: Install Dependencies

Run the following command in your VS Code PowerShell terminal:

.\.venv\Scripts\python.exe -m pip install -r requirements.txt

This installs Flask, pdf2docx, PyMuPDF, and the other required packages.

Step 5: Start the Application

Run:

.\.venv\Scripts\python.exe app.py

When the Flask server starts, open your web browser and visit:

http://127.0.0.1:5000

You should now see the PDF to Word Converter interface.

To stop the server, press Ctrl+C in the terminal.

Running on macOS or Linux

Open the project folder in VS Code and execute:

python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
python app.py

Visit http://127.0.0.1:5000 in your browser.

How to Use

Open the application in your browser.

Click the upload area or drag and drop a PDF document.

Select Convert to Word.

Allow the application to process the document.

Download the generated Word file automatically.

Open the document using Microsoft Word or another DOCX-compatible editor.

For best results, use a PDF containing selectable text.

Project Structure

pdf-to-word-converter/
├── .github/
│   └── workflows/
│       └── tests.yml
├── static/
│   ├── app.js
│   └── style.css
├── templates/
│   └── index.html
├── tests/
│   └── test_app.py
├── app.py
├── requirements.txt
├── requirements-dev.txt
├── .gitignore
├── LICENSE
└── README.md

File Descriptions

app.py: Handles the Flask server, PDF validation, and conversion.

templates/index.html: Contains the application interface.

static/style.css: Controls the layout, appearance, and responsiveness.

static/app.js: Handles file selection, uploads, and downloads.

requirements.txt: Lists the required Python packages.

requirements-dev.txt: Lists additional testing dependencies.

tests/test_app.py: Contains automated tests.

.github/workflows/tests.yml: Configures GitHub Actions testing.

Testing the Application

To run the automated tests on Windows, open your VS Code terminal and execute:

.\.venv\Scripts\python.exe -m pip install -r requirements-dev.txt
.\.venv\Scripts\python.exe -m pytest -q

The tests cover the home page, API health check, invalid file uploads, and a simulated Word download.

Important: The download test uses a mocked conversion function. Test the application with a real PDF to verify the actual conversion engine.

API Endpoints

Method

Endpoint

Description

GET

/

Displays the application

GET

/health

Checks the API health

POST

/api/convert

Converts an uploaded PDF into DOCX

Limitations

Works best with text-based PDF documents.

Scanned PDFs require OCR, which is not included.

Complex formatting, tables, images, and fonts may not convert perfectly.

Maximum upload size is 15 MB.

Maximum document length is 75 pages.

Uploaded files are processed temporarily and removed after conversion.

The conversion dependency is no longer actively maintained by its original maintainer.

Additional security controls are required before deploying this as a public file-upload service.

Deployment note: GitHub Pages cannot run the Flask backend. The application requires hosting that supports Python.

Contributing

Contributions, bug reports, and suggestions are welcome.

To contribute:

Fork this repository.

Create a new branch.

Make your changes.

Test your changes.

Submit a pull request.

License

This project is licensed under the MIT License. See the LICENSE file for details.
