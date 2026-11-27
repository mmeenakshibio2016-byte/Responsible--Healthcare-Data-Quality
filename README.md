# Responsible--Healthcare-Data-Quality
Privacy-aware healthcare data preparation and reproducible validation using Python
## Objective
Prepare healthcare data responsibly while identifying clinical data-quality risks.

## Files
- `source_healthcare_patients_sample.csv` — preserved input copy
- `cleaned_healthcare_data.csv` — conservative cleaning output
- `healthcare_data_quality.ipynb` — reproducible validation notebook
- `data_dictionary.xlsx` — field definitions, classifications, and risks
- `exception_log.csv` — validation exceptions and review notes

## Initial profile
- 10 rows, 10 columns
- 0 missing cells
- 0 exact duplicate rows
- 0 duplicate PatientID values
- No obvious direct identifiers (name, phone, address, DOB) in the supplied columns

## Privacy caveat
The absence of obvious direct identifiers does not establish formal de-identification. PatientID may be linkable, and combinations of demographic and clinical attributes may create re-identification risk. Verify data provenance, linkage keys, consent/authority, and public-release approval with the data owner.

## Cleaning policy
Only leading/trailing whitespace in text fields is normalized. No clinical values are imputed, fabricated, or silently changed. No rows are automatically deleted. Unusual values are logged for review. The broad checks in the notebook are structural screening rules, not clinical reference ranges or medical advice.

## Run
Install dependencies:
```bash
pip install pandas numpy openpyxl jupyter
```
Open `healthcare_data_quality.ipynb` in VS Code or Jupyter. Keep `source_healthcare_patients_sample.csv` in the same folder.

## Public submission warning
Do not publish real patient data or potentially linkable records in a public repository. Obtain explicit authorization or replace the source file with a synthetic/de-identified approved sample before making the repository public.
## Responsible Data Handling and Limitations

- The supplied sample contains 10 records and 10 fields.
- No missing cells, exact duplicate rows, or duplicate PatientID values were detected in the initial profile.
- These checks do not establish that the data is clinically accurate or formally de-identified.
- PatientID and combinations of demographic and clinical attributes may create re-identification risks.
- Validation rules are intended for structural data-quality screening, not clinical diagnosis or treatment decisions.
- Missing clinical values must not be fabricated or automatically imputed.
- Medication dosage appropriateness cannot be established without medication-specific clinical context.
- Cholesterol values should not be clinically interpreted without confirmed units and measurement context.
- Public demonstration files should contain independently generated synthetic data only.
