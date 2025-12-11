**Intelligent Traffic Insight System – ATCC + ANPR**

This project presents a combined Automatic Traffic Counting & Classification (ATCC) system along with an Automatic Number Plate Recognition (ANPR) module. The idea was to build a compact yet realistic traffic-monitoring solution that moves smoothly from model training to deployment.

To achieve this, the heavy training tasks were handled in Google Colab (GPU), while the final interface and analytics were designed in VS Code using Streamlit.

-----------------------------------------------------------------------
📌 **Datasets Used**

Two openly accessible datasets form the backbone of the project:

**ANPR Image Dataset**:
(Large License Plate Dataset – Kaggle)

**ATCC Traffic Videos Dataset**:
(Traffic Video Dataset – Kaggle)

These datasets allowed us to test the system in conditions close to real-world scenarios.

-----------------------------------------------------------------------
🌐 **What the System Can Do**

Real-time identification of vehicles in uploaded or live videos

Automatic detection of number plates and extraction of text using OCR

Option to adjust the confidence level for detections

A complete interactive dashboard including:

Tables for vehicle counts

Multiple graphs (bar, line, pie, scatter)

Simple upload options for local videos and images

A ready-to-use SQLite storage layer for logging and later analysis

Clear separation between training workflows and deployment workflows

-----------------------------------------------------------------------
🔍 **Models & Tools Behind the System**
**Detection + OCR**

**YOLOv8n** for detecting vehicles

**YOLOv8 / custom plate model** for isolating license plates

**EasyOCR** for converting plate images into text

**Tech Environment**

Python, Streamlit, Pandas, Matplotlib, OpenCV, SQLite, Ultralytics YOLOv8, Google Colab, VS Code

(We kept our environment lightweight so it can run on mid-range systems too.)

--------------------------------------------------------------------------
🛠 **Data Flow Overview**
**ATCC Processing**

Traffic videos → YOLOv8 frame analysis → vehicle categories counted → final results saved as CSV.

**ANPR Processing**

Plate images → YOLO detection → OCR text extraction → stored into separate CSV.

These CSVs are then imported into the dashboard for consolidated analysis.

--------------------------------------------------------------------
**🧩 Running the Project in VS Code**

**1. Navigate to the folder**
cd ANPR_AND_ATCC

**2. Create a virtual environment**
python -m venv venv

**3. Activate it (on PowerShell)**
.\venv\Scripts\activate

**4. Install all project requirements**
pip install -r requirements.txt

**5. Set up the database**
python db/init_db.py

**6. Launch the Streamlit app**
python -m streamlit run streamlit_app/app.py

**7. Open this URL in your browser**
http://localhost:8501

----------------------------------------------------------------------
**Future Work & Roadmap**

**Support for multiple OCR languages:** Extend the system to recognize plates in different regional languages using PaddleOCR and additional trained models.

**Vehicle Registration API Integration:** Connect plate outputs with official/state databases to enable real-time verification and automated alerts.

**Deployment on Edge Devices:** Optimize and compress models so they can run efficiently on Raspberry Pi, Jetson Nano, and similar embedded hardware.

**Cloud Hosting & Remote Dashboards:** Move analytics and monitoring interfaces to cloud services like AWS, GCP, or Azure for broader accessibility.

**UI/UX Improvements:** Add features such as a dark theme, user login system, notification options, and a fully responsive layout for mobile devices.

**Richer Vehicle Classification:** Expand the detection categories to include buses, emergency response vehicles, e-scooters, bicycles, and other road users.

**Model Upgrades:** Explore transformer-based detection architectures to further increase accuracy and robustness.

-----------------------------------------------------------------------
**License**

This project is released under the **MIT License © 2025 Vidzai Digital.**
