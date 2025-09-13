**CHANGES TO IMPLEMENT**


## General
- **Remove all hardcoding step-by-step.**
- **Make all settings configurable** via the `.env` file.



## System Admin: New App Features
- **.env File Editing**



## Patient View Enhancements

**Login:**

- Identify user type: _Patient_ or _Doctor_.
- Allow language selection: **English** or **French**.
    - If French is selected, display all labels and AI-generated content in French.


**Step 2 (1A): Patient Registration**

- *Skip Options*: Allow skipping non-mandatory fields (e.g., income group, profession, blood group, medical records, travel history on pages 2 \& 3).
- *Mandatory Fields*: Age, Gender.
- Move _Page 4 content_ (med history, family history, recent \& relevant medical reports) to follow Page 2.
- **Recent \& Relevant Medical Reports:**
    - Add “Do you have anything to upload? (Yes/No)”


**Step 3 (1B): Vital Signs \& Report Upload**

- **Dynamic Vital Ranges:** Tooltips should auto-update based on age, gender, take weight, and height and impact vitals basis this.
- **Report Upload UI**:
    - Display if upload is ‘Yes’ in Step 2.
    - UI should resemble ChatGPT: upload image from camera, select report type (radio buttons), add optional prompt, and click “Process” for AI insights and file storage.
    - Include validation info on supported file types and size, shown sequentially like ChatGPT.
    - **Supported Report Types:** tongue, skin, throat, lab test, lab report, imaging/scans, pathology, signaling.
    - **AI Calls:** Configure in `.env` file.
    - Show/hide report upload section based on upload selection in Step 2.
    -  ( wait )


**Step 4 (1C): Medical Records \& Reports**

- **Medical Records \& Contact Info (Page 1):** Not required.
- **Medical Reports Section:** Merge into Step 3.
- If "Diabetes" (etc.) is **No** in Step 1, skip Page 3 of Step 4.
- **Skip Logic**: Do not show whether findings are critical/concerning to the patient.


**Step 5 (2A, 2B, 2C): Describe Your Symptoms**

- Do **not** show critical/verbiage labels or any medical diagnosis.
- Hide AI insights from the patient.
- On free-form entry, simply submit the collected data.
- Remove clinical summary, assessment, findings, and reasoning from patient’s view.

**Step 7 (3A): Differential Diagnosis**

- Do **not** display ICD codes; jump directly to differential questions.
- Omit elimination history when starting Q\&A.
- Add “Skip” option to bypass remaining differential questions.
- Move directly to “Generate Tests.”
- In test information, do **not** display clinical reasoning or expected findings.
show msg to patient that report is getting reviewed


this should go to remote panel with  entire clinical summary, diff questions, final icd codes with reasoning, suggested tests

after approval , 

**Report Generation**

- Before download, collect contact number and email and referring doctor details .
- Add them to the report and send download link via email/SMS to the referring doctor.




report generation should go to doc...pls wait msg

approve - gives to user , reject , feedback 