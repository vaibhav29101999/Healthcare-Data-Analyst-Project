# 🏥 Healthcare Data Analyst Project

## 📌 Project Objective

To analyze patient, appointment, prescription, and billing data from a multi-department hospital to identify operational inefficiencies, patient behavior trends, and actionable opportunities for improving patient scheduling, doctor performance management, and resource allocation.

## 📊 Dataset Overview

The project uses anonymized hospital records containing:

- **Patients**: Registration details, demographics, registration dates
- **Appointments**: Appointment dates, departments, doctors, patient IDs, status (Completed/No-Show)
- **Prescriptions**: Prescription date, patient ID, medicine details, prescribing doctor
- **Billing**: Patient charges, payment status, appointment linkage
  
## 📈 Key Analyses Performed

- 📌 **Appointment No-Show Rate** analysis overall, by department, and by patient
- 📌 **Doctor Performance**: Total appointments handled and no-show rates per doctor
- 📌 **Prescription Trends**: Most prescribed medicines and seasonal trends
- 📌 **Average Waiting Time**: From registration to first appointment, overall and per department
- 📌 **Department-Wise Appointment Frequency**: Monthly, quarterly, and yearly trends
- 📌 **Peak Appointment Days and Time Slots**: To optimize scheduling and staffing
- 📌 **Operational Efficiency Metrics**: Average patient load per department, no-show patterns

## 🗄️ SQL Queries Used

### 📌 No-Show Rate (Overall)
```sql
SELECT 
  (SUM(CASE WHEN Status = 'No-Show' THEN 1 ELSE 0 END) * 100.0) / COUNT(*) AS No_Show_Rate
FROM appointments;
