## Schema
Metadata 

Here is a list of each metadata field, with explanations:

- Patientid (internal identifier, just for this dataset)

- offset (number of days since the start of symptoms or hospitalization for each image, this is very important to have when there are multiple images for the same patient to track progression while being imaged. If a report says "after a few days" let's assume 5 days.)

- sex (M, F, or blank)

- age (age of the patient in years)

- finding (which pneumonia)

- survival (did they survive? Y or N)

- intubated (Yes (Y) if the patient was intubated (or ventilated) at any point during this illness or No (N) or blank if unknown.)
- went_icu (Yes (Y) if the patient was in the ICU (intensive care unit) or CCU (critical care unit) at any point during this illness or No (N) or blank if unknown.)
- needed_supplemental_O2 (Yes (Y) if the patient required supplemental oxygen at any point during this illness or No (N) or blank if unknown )

- extubated (Yes (Y) if the patient was successfully extubated or No (N) or blank if unknown)

- temperature (Temperature of the patient in Celsius at the time of the image)

- pO2 saturation (partial pressure of oxygen saturation in % at the time of the image)

- wbc count (white blood cell count in units of 10^3/uL at the time of the image)
- neutrophil count (neutrophil cell count in units of 10^3/uL at the time of the image)

- lymphocyte count (lymphocyte cell count in units of 10^3/uL at the time of the image)

- view (Posteroanterior (PA), Anteroposterior (AP), AP Supine (APS), or Lateral (L) for X-rays; Axial or Coronal for CT scans)

- modality (CT, X-ray, or something else)

- date (date the image was acquired)

- location (hospital name, city, state, country) importance from right to left.)

- folder

- doi (DOI of the research article)

- rl (URL of the paper or website where the image came from)
license
- clinical notes (about the radiograph in particular, not just the patient)
- other notes (e.g. credit)