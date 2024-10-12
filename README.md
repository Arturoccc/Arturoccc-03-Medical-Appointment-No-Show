# Medical Appointment No Show Dataset Analysis

## Contents
- [Dataset Description](#dataset-description)
- [Columns Description](#columns-description)
- [EDA Questions](#eda-questions)
- [Data Wrangling](#data-wrangling)
- [Data Cleaning](#data-cleaning)
- [Data Visualization](#data-visualization)
- [Conclusion](#conclusion)
- [Built with](#built-with)

## Dataset Description:
A person makes a doctor appointment, receives all the instructions and no-show. Who to blame? This dataset collects information from 100k medical appointments in Brazil and is focused on the question of whether or not patients show up for their appointment. A number of characteristics about the patient are included in each row.

## Columns Description:
1. `PatientId`: Identification of a patient.
2. `AppointmentID`: Identification of each appointment.
3. `Gender`: Male or Female.
4. `AppointmentDay`: The day of the actual appointment, when they have to visit the doctor.
5. `ScheduledDay`: The day someone called or registered the appointment, this is before the appointment of course.
6. `Age`: How old is the patient.
7. `Neighbourhood`: Where the appointment takes place.
8. `Scholarship`: True or False. Observation, this is a broad topic, consider reading this article [here](https://en.wikipedia.org/wiki/Bolsa_Fam%C3%ADlia).
9. `Hipertension`: True or False.
10. `Diabetes`: True or False.
11. `Alcoholism`: True or False.
12. `Handcap`: True or False.
13. `SMS_received`: 1 or more messages sent to the patient.
14. `No-show`: True or False.

## EDA Questions:
- Q1: How often do men go to hospitals compared to women? Which of them is more likely to show up?
- Q2: Does receiving an SMS as a reminder affect whether or not a patient may show up? Is it correlated with the number of days before the appointment?
- Q3: Does having a scholarship affect showing up on a hospital appointment? What are the age groups affected by this?
- Q4: Does having certain diseases affect whether or not a patient may show up to their appointment? Is it affected by gender?

## Data Wrangling:
Our data can be found on `noshowappointments-kagglev2-may-2016.csv` file provided on this repository, downloaded from [Kaggle](https://www.kaggle.com).

## Data Cleaning:
### Exploration Summary
1. Our dataset consists of 110,527 rows with 14 columns, and has no NaNs nor duplicated values.
2. `PatientId` and `AppointmentID` columns wouldn't be helpful during analysis.
3. `ScheduledDay` and `AppointmentDay` need to be casted to date data type.
4. We may append a new column for days until appointment.
5. `Gender` needs to be casted into a category type.
6. `Scholarship`, `Hipertension`, `Diabetes`, `Alcoholism` and `SMS_received` better be boolean data type.
7. `No-show` column needs to be parsed and casted to boolean type.
8. `Handcap` column needs to be cleaned to have only `0` and `1` values.
9. `Age` column has inconsistent unique values that need to be handled.

We ended up with a dataframe of 110,521 rows and 11 columns after completing the cleaning process.

## Data Visualization:
Using `Matplotlib` and `Seaborn`, we made several meaningful visuals and charts to help us gain informative insights regarding any correlation between attributes in our dataset, that will be discussed in the next section.

## Conclusion:

### Q1: How often do men go to hospitals compared to women? Which of them is more likely to show up?
- Nearly half of our dataset consists of women with wider age distribution and some outliers, all of which achieve a rate higher than men.
- It is obvious that 79.8% of our patients did show up on their appointments and only 20.1% of them did not.
- Women do show up on their appointments more often than men do, but this may be affected by the percentage of women in this dataset.

### Q2: Does receiving an SMS as a reminder affect whether or not a patient may show up? Is it correlated with the number of days before the appointment?
- 67.8% of our patients did not receive any SMS reminder of their appointments, yet they showed up on their appointments.
- It is clear that there is a positive correlation between the number of due days and whether a patient shows up or not.
- Patients with appointments from 0 to 30 days tend to show up more regularly, while patients with a higher number of days tend not to show up.
- Gender does not affect the number of due days and showing up at an appointment that much.

### Q3: Does having a scholarship affect showing up on a hospital appointment? What are the age groups affected by this?
- Having a scholarship does not affect showing up to a doctor appointment that much.
- Huge age group is enrolled in that scholarship and also enroll their babies on.

### Q4: Does having certain diseases affect whether or not a patient may show up to their appointment? Is it affected by gender?
- We can conclude that the vast majority of our dataset does not have chronic diseases, yet, they are present in so many young people.
- Having a chronic disease may affect your showing up at a hospital's appointment.

## Built with:
- JupyterLab
- Python3
- Pandas
- Numpy
- Matplotlib
- Seaborn
# Medical Appointment No-Show Analysis
