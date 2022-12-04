# DATA Dictionary:

## admission_sample.csv


### Clean process:

1. filter out the "ELECTIVE" in NEXT_ADMISSION_TYPE, to make sure all of the next admission is emergency admission

2. filter out newborn and death in ADMISSION_TYPE

3. some other format cleaning

### Columns:
For some normal variables, please check the sample data, here list the modified ones.

- Direct tnformation for next admission

NEXT_ADMITTIME: ADMITTIME of the next admission
NEXT_ADMISSION_TYPE: ADMISSION_TYPE of the next admission 
NEXT_ADMISSION_LOCATION: ADMISSION_LOCATION of the next admission
NEXT_DISCHARGE_LOCATION: DISCHARGE_LOCATION of the next admission

- Calculated information for next admission

DAYS_NEXT_ADMIT: Number of days between next admission time and this dicharge time
OUTPUT_LABEL: if DAYS_NEXT_ADMIT < 30, return 1; else return 0

- Calculated information for this admission

DURATION: Days in (DISCHTIME - ADMITTIME); indicate the number of days patient in the hosipital this admission


## notes_sample.csv

Nothing change

## combine_sample.csv

Left join (admission, notes) by 'SUBJECT_ID'&'HADM_ID'

Columns:

- SUBJECT_ID
- HADM_ID
- ADMITTIME
- DISCHTIME
- DAYS_NEXT_ADMIT
- NEXT_ADMITTIME
- ADMISSION_TYPE
- DEATHTIME
- OUTPUT_LABEL
- DURATION
- NEXT_ADMISSION_TYPE
- NEXT_ADMISSION_LOCATION
- NEXT_DISCHARGE_LOCATION

- SUBJECT_ID
- HADM_ID
- CHARTDATE
- TEXT
- CATEGORY

