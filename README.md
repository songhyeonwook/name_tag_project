# Nametag Generator Web App

This repository contains a simple Streamlit web application that helps
you generate nametag slides (either PPTX or PDF) from an Excel or CSV
file containing your attendee list.  The app reads the file, filters
rows for people who are marked as either **attendee** or **applicant**,
and produces a page for each person with their department and name
combined into a single line (for example, `경영지원부 홍길동`).  All
pages are compiled into one downloadable file.

## How it works

1. Upload your Excel or CSV file using the file‑uploader.
2. Select the columns that represent **Department**, **Name** and
   **Status**.  You can customise the accepted status values if your
   file uses Korean labels like “참석자” or “신청자”.  Only rows
   matching the selected statuses will be included.
3. Choose whether you want a PowerPoint deck (`.pptx`) or a PDF file.
4. Click **Generate Nametags** to build the combined file.  You’ll
   receive a download link when the generation is complete.

The application uses `pandas` to process spreadsheets, `python‑pptx`
to build slides and `reportlab` to generate PDF pages.  Each page
contains a single line centred both horizontally and vertically on the
page.  You can adjust the font size and family inside
`app.py` if you wish.

## Setup & running locally

To run the app on your own machine you’ll need Python 3.8 or later.
Install the dependencies listed in `requirements.txt` and then launch
the Streamlit app:

```bash
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
streamlit run app.py
```

Your browser will open at `http://localhost:8501`, where you can use
the application.

## Files

* `app.py` – the Streamlit application.
* `requirements.txt` – Python dependencies.
* `README.md` – this documentation.