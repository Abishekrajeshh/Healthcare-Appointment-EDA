# Healthcare Appointment No-Show Prediction

This project aims to analyze a dataset of healthcare appointments to understand the factors contributing to patient no-shows and build a predictive model. Understanding these factors can help healthcare providers optimize scheduling and reduce missed appointments, thereby improving efficiency and patient care.

## Dataset

The dataset contains information about over 110,000 medical appointments in Brazil, including characteristics such as patient demographics, health conditions, scheduling details, and whether the patient showed up for their appointment.

**Key Features:**
* `PatientID`: Unique identifier for each patient.
* `AppointmentID`: Unique identifier for each appointment.
* `Gender`: Male or Female.
* `ScheduledDay`: The day the appointment was scheduled.
* `AppointmentDay`: The actual day of the appointment.
* `Age`: Patient's age.
* `Neighbourhood`: The location of the hospital.
* `Scholarship`: Indicates if the patient is enrolled in the Bolsa Família welfare program.
* `Hypertension`: Indicates if the patient has hypertension.
* `Diabetes`: Indicates if the patient has diabetes.
* `Alcoholism`: Indicates if the patient has alcoholism.
* `Handicap`: Indicates if the patient has a disability.
* `SMSReceived`: Indicates if the patient received an SMS reminder.
* `NoShow`: Target variable, 'No' (patient showed up) or 'Yes' (patient did not show up).

## Project Structure

* `Healthcaredata.ipynb`: Jupyter Notebook containing the full data analysis, preprocessing, and model development.
* `data.csv`: The raw dataset used for this analysis.

## Key Findings (Preliminary - Based on EDA)

* **Imbalanced Target Variable:** Approximately 80% of appointments result in a 'No' (patient showed up), while about 20% are 'Yes' (no-show). This imbalance is crucial to consider during model training and evaluation.
* **No Sunday Appointments:** There are no appointments scheduled on Sundays, and very few on Saturdays, indicating weekends are less active for appointments.
* **No Missing Data:** The dataset is complete with no missing values, which simplifies the initial data cleaning process.
* **Age Distribution:** Patient ages range from -1 to 115. The notebook groups ages into bins for better analysis.
* **Column Renaming:** Columns were renamed for consistency and easier understanding (e.g., 'Hipertension' to 'Hypertension', 'No-show' to 'NoShow').
* **Irrelevant Columns Dropped:** 'PatientID', 'AppointmentID', and 'Neighbourhood' were dropped as they were deemed unnecessary for the initial analysis.

## How to Run the Notebook

1.  **Clone the Repository:**
    ```bash
    git clone <repository-url>
    cd <repository-name>
    ```
2.  **Create a Virtual Environment (Recommended):**
    ```bash
    python -m venv .venv
    source .venv/bin/activate  # On Windows: .venv\Scripts\activate
    ```
3.  **Install Dependencies:**
    ```bash
    pip install pandas numpy datetime matplotlib seaborn
    ```
    *(Note: `datetime` and `time` are standard Python libraries and usually don't require `pip install`.)*
4.  **Open and Run the Notebook:**
    ```bash
    jupyter notebook Healthcaredata.ipynb
    ```
    Follow the instructions within the notebook cells to execute the analysis.

## Future Work and Improvements

* **Predictive Modeling:** Implement various machine learning classification models to predict `NoShow` based on the engineered features.
* **Hyperparameter Tuning:** Optimize model performance using techniques like GridSearchCV or RandomizedSearchCV.
* **Deep Dive into Feature Interactions:** Further investigate how combinations of features impact no-show rates.
* **Deployment:** Consider deploying the trained model as a web service for real-time predictions.
