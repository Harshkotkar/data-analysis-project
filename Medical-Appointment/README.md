thj
# Medical Appointment No-Show Dataset Analysis

| Contents                           |
|------------------------------------|
| [Dataset Description](#dataset-description) |
| [Columns Description](#columns-description) |
| [EDA Questions](#eda-questions)   |
| [Data Wrangling](#data-wrangling) |
| [Data Cleaning](#data-cleaning)   |
| [Data Visualization](#data-visualization) |
| [Conclusion](#conclusion)         |
| [Built With](#built-with)         |

---

## Dataset Description
This dataset contains information from 100,000 medical appointments in Brazil and explores the factors influencing whether patients show up for their appointments. Each row includes details about the appointment and patient characteristics.  

---

## Columns Description
1. **`PatientId`**: Unique identifier for patients.  
2. **`AppointmentID`**: Unique identifier for appointments.  
3. **`Gender`**: Patient's gender (Male/Female).  
4. **`ScheduledDay`**: Date the appointment was scheduled.  
5. **`AppointmentDay`**: Date of the actual appointment.  
6. **`Age`**: Patient's age.  
7. **`Neighbourhood`**: Location of the appointment.  
8. **`Scholarship`**: Indicates if the patient is enrolled in a welfare program ([Bolsa Família](https://en.wikipedia.org/wiki/Bolsa_Fam%C3%ADlia)).  
9. **`Hipertension`**: Indicates if the patient has hypertension.  
10. **`Diabetes`**: Indicates if the patient has diabetes.  
11. **`Alcoholism`**: Indicates if the patient has alcoholism.  
12. **`Handcap`**: Indicates if the patient has a disability.  
13. **`SMS_received`**: Number of reminder SMS received by the patient.  
14. **`No-show`**: Whether the patient missed the appointment.  

---

## EDA Questions
1. How often do men visit hospitals compared to women? Who is more likely to show up?  
2. Does receiving an SMS reminder impact attendance? Is there a link between reminders and days before the appointment?  
3. Does having a scholarship affect appointment attendance? Are specific age groups influenced?  
4. Do certain diseases affect attendance? Is this influenced by gender?  

---

## Data Wrangling
The dataset is sourced from the file `noshowappointments-kagglev2-may-2016.csv` ([Kaggle](https://www.kaggle.com/datasets/joniarroba/noshowappointments)).  

---

## Data Cleaning
### Key Steps
1. Initial dataset contained 110,527 rows and 14 columns, with no missing or duplicate values.  
2. Removed less relevant columns: `PatientId` and `AppointmentId`.  
3. Converted `ScheduledDay` and `AppointmentDay` to datetime format and calculated days until the appointment.  
4. Cleaned `Handcap` column to only include `0` and `1`.  
5. Converted `Gender` to categorical type.  
6. Changed columns like `Scholarship`, `Hipertension`, `Diabetes`, `Alcoholism`, and `SMS_received` to boolean types.  
7. Parsed `No-show` column into a boolean format.  
8. Addressed inconsistencies in `Age` column.  

**Final Cleaned Dataset**: 110,521 rows and 11 columns.  

---

## Data Visualization
Visualizations were created using `Matplotlib` and `Seaborn` to uncover patterns and correlations.  

---

## Conclusion
### Q1: Gender Analysis  
- Women constitute a larger proportion of the dataset and show higher appointment attendance compared to men.  
- Overall, 79.8% of patients attended their appointments, while 20.1% missed them.  

### Q2: SMS Reminders  
- 67.8% of patients who didn’t receive SMS reminders still attended their appointments.  
- Attendance decreases as the number of days between scheduling and the appointment increases.  
- Gender does not significantly impact attendance related to SMS reminders.  

### Q3: Scholarships and Age Groups  
- Having a scholarship has little impact on attendance rates.  
- The scholarship program spans multiple age groups, including infants enrolled by their parents.  

### Q4: Chronic Diseases and Attendance  
- Most patients in the dataset do not have chronic diseases.  
- Chronic illnesses are more common among younger patients and can negatively impact attendance.  

---

## Built With
- **JupyterLab**  
- **Python 3**  
- **Pandas**  
- **NumPy**  
- **Matplotlib**  
- **Seaborn**

---
