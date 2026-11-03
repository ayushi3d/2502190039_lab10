# Robotics Equipment Maintenance Log

**A Python-Based Robotics Equipment Maintenance and Downtime Tracking System**

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Course](https://img.shields.io/badge/Course-CS--1281-orange)
![Status](https://img.shields.io/badge/Status-Completed-success)

##Project Credits

**Developed by:** Ayushi Srivastava,2502190039
**PEER NAME : SHREEYA ROUTRAY,2502190005
**Registration Number:** 2502190039  
**Branch:** Mechanical and Smart Manufacturing  
**Course:** CS-1281 – Python Programming Lab  
**Semester:** B.Tech 3rd Semester  
**Institution:** Veer Surendra Sai University of Technology (VSSUT), Burla  

**Work Order:** 09 – The Data Layer  
**Final Submission:** Work Order 10 – Ship It  

**Project Guide:** Lt. Birendra Kumar Barik

## 1. Project Overview

Robotics Equipment Maintenance Log is a Python-based application developed to validate robotics equipment maintenance records, track equipment failures, calculate downtime, and identify equipment requiring maintenance attention.

The system processes maintenance records from a text file, rejects invalid entries, performs equipment-wise analysis, and generates dated maintenance reports.

## 2. Problem Statement

Robotics laboratories use several types of equipment that may experience repeated failures and unexpected downtime. Manually maintaining these records makes it difficult to identify frequently failing equipment and monitor maintenance requirements.

This project provides a simple automated solution for maintaining and analysing robotics equipment maintenance records.

## 3. Target Users

- Robotics laboratory technicians
- Robotics project teams
- Equipment maintenance personnel
- Engineering students

## 4. Technologies Used

- Python 3
- File Handling
- Functions and Modules
- Lists and Dictionaries
- Exception Handling
- `Counter` from `collections`
- `datetime`
- `os` module

No external Python libraries are required.

## 5. Project Structure

```text
Robotics-Equipment-Maintenance-Log/
│
├── main.py
├── datalayer.py
├── test_hardening.py
├── README.md
├── lab_record.md
│
├── data/
│   └── sample.txt
│
└── reports/
    └── report_YYYY-MM-DD_HHMMSS.txt
```

## 6. Input Data Format

The system accepts pipe-separated text records containing five fields:

`Equipment_ID|Equipment_Name|Date|Issue|Downtime_Hours`

**Example:**

```text
RB01|DC_Motor|2026-09-01|Overheating|2
RB02|Sensor|2026-09-02|No_Reading|1
RB03|Battery|2026-09-03|Low_Voltage|3
```

**Validation rules:**
- Exactly five fields are required.
- Date must follow `YYYY-MM-DD`.
- Equipment ID, equipment name and issue cannot be empty.
- Downtime must be numeric, finite and between 0 and 100 hours.

## 7. Main Features

1. **Record Validation:** Checks maintenance records and identifies invalid entries.
2. **Failure Tracking:** Counts failures for each equipment category.
3. **Downtime Calculation:** Calculates cumulative downtime for each equipment category.
4. **Maintenance Decision:** Identifies equipment requiring attention.
5. **Error Logging:** Stores rejected records with line numbers and reasons.
6. **Report Generation:** Creates dated maintenance reports automatically.

## 8. Maintenance Decision Logic

Equipment is identified as requiring maintenance attention if:

- It has at least 3 recorded failures, OR
- Its cumulative downtime is at least 5 hours.

The decision is generated using the `identify_attention()` function in `datalayer.py`.

## 9. How to Run the Project

**Requirement:** Python 3.8 or later.

No additional package installation is needed.

Open the terminal in the project directory and execute:

```bash
python main.py
```

To execute the hardening tests:

```bash
python test_hardening.py
```

## 10. Sample Results

The included sample dataset contains 18 maintenance records.

| Result | Value |
|---|---:|
| Total input records | 18 |
| Valid records | 16 |
| Rejected records | 2 |
| Total downtime | 30.50 hours |

### Equipment-wise Analysis

| Equipment | Failures | Downtime |
|---|---:|---:|
| Battery | 3 | 6.00 hours |
| DC_Motor | 3 | 6.00 hours |
| Sensor | 2 | 2.00 hours |
| Wheel | 2 | 3.00 hours |
| Servo | 2 | 6.00 hours |
| Encoder | 2 | 3.50 hours |
| Driver | 1 | 3.00 hours |
| IR_Sensor | 1 | 1.00 hour |

### Equipment Requiring Attention

- Battery
- DC_Motor
- Servo

### Rejected Records

- Line 17: Missing downtime field.
- Line 18: Downtime exceeds the permitted 100-hour limit.

## 11. Error Handling and Hardening

The project was tested against four important situations:

| Test Case | Expected Behaviour |
|---|---|
| Malformed record | Reject the record and continue processing |
| Missing input file | Display a clear error message |
| Empty input file | Return an empty summary without crashing |
| Out-of-range downtime | Reject unrealistic downtime values |

All four hardening tests passed during testing.

## 12. Known Limitations

- Supports only pipe-separated text input.
- Uses a fixed downtime limit of 100 hours.
- Maintenance attention is based on fixed thresholds.
- Does not predict future equipment failures.
- Does not maintain a permanent database.

## 13. Future Scope

- Integration of graphical reports and visual analytics.
- Equipment-wise maintenance history tracking.
- Predictive maintenance using Machine Learning.
- Integration with databases.
- Automated maintenance alerts and notifications.

## 14. Conclusion

The Robotics Equipment Maintenance Log successfully demonstrates how Python can be used to automate equipment maintenance record validation, failure tracking, downtime analysis and report generation.

The project applies fundamental Python concepts such as functions, dictionaries, file handling, modules, exception handling and data validation to a practical robotics laboratory problem.


