**Role:**
Act as a Senior Data Engineer and Project Management expert. Your task is to write a robust Python script using `pandas` and `openpyxl` to generate a professional, corruption-free Excel Dashboard file named `SMU_Manager_Cockpit.xlsx`.

**Context:**
I am a manager of an SMU (Specialized Maintenance Unit) dealing with Radar/CNS repairs. I need a single Excel file to track daily operational repairs and long-term Government of India (GoI) style projects/tenders.

**Requirements for the Python Script:**

1.  **Libraries:** Use `pandas` for data structure and `openpyxl` for formatting, conditional formatting, and data validation.

2.  **Structure (Create 3 Sheets):**
    * **Sheet 1: "Dashboard"** (Summary view with calculated KPIs).
    * **Sheet 2: "Routine_Ops"** (Day-to-day repair tracking).
    * **Sheet 3: "Project_Lifecycle"** (GoI Tender/Project tracking).

3.  **Data Population (Crucial):**
    * **In "Routine_Ops", populate the following specific data rows exactly:**
        * Row 1: ID=43, Point="Finalization of policy for routine optimization", Action="Policy under process", Owner="GM(CNS-Sur)", Status="Completed", Remarks="Policy already approved".
        * Row 2: ID=44, Point="In-house repair capabilities ADS-B/ERA", Action="Coordination with CNSP1", Owner="GM(CMC)", Status="In Progress", Remarks="Need ASMGCS test jig; RASS tool missing".
        * Row 3: ID=45, Point="Factory Training Policy", Action="Send proposal to GM(CMC)", Owner="In-Charge SMU", Status="Blocked", Remarks="Matter taken up with CNSOM; no policy finalized".
        * Row 4: ID=46, Point="Dedicated Vehicles Policy", Action="Proposal to be initiated", Owner="GM(CMC)", Status="Open", Remarks="E-file to CMC".
        * Row 5: ID=47, Point="Test System Facility ASMGCS", Action="Initiate proposal", Owner="In-Charge ASMGCS", Status="In Progress", Remarks="Procurement under process".
        * Row 6: ID=48, Point="In-House ITC for RADARs", Action="Initiate proposal", Owner="GM(CMC)", Status="Open", Remarks="Coordination done; proposal pending".
        * Row 7: ID=49, Point="Broadband & firewall at field stations", Action="Initiate proposal", Owner="GM(CMC)", Status="Completed", Remarks="Firewall setup by ASMGCS".
        * Row 8: ID=50, Point="Spares packing & insurance guidelines", Action="Issue guidelines", Owner="GM(CMC)", Status="In Progress", Remarks="Drafting circular based on SMU proposal".
        * Row 9: ID=51, Point="SMU Rep in CNS/ATM Spec Committee", Action="Put up proposal", Owner="GM(CMC)", Status="Open", Remarks="Focus on ITWP & Automation tracking".

4.  **Column Structure & Logic:**
    * **Routine_Ops Columns:** [ID, Action Point, Owner, Open Date, Due Date, Status, Priority, Evidence Link, Remarks].
        * *Formula:* Add a column via Python logic for "Days Open" (`=TODAY() - Open Date`).
    * **Project_Lifecycle Columns (GoI Stages):** [Project ID, Title, Current Stage, AA (Admin Approval) Date, ES (Fin Concurrence) Date, Tender Pub Date, Tech Eval Date, LOA Date, Completion Date, Status, Owner].

5.  **Formatting & Visualization (The "Managerial" Look):**
    * Convert all data ranges to **Excel Tables** (TableStyleMedium9).
    * **Header Row:** Bold, Dark Blue fill, White text.
    * **Conditional Formatting:**
        * In `Routine_Ops`, if Status is "Blocked" or "Overdue", turn the row Light Red.
        * In `Project_Lifecycle`, highlight the "Current Stage" cell in Yellow.
    * **Data Validation:**
        * Add Dropdowns for Status: ["Open", "In Progress", "Blocked", "Completed"].
        * Add Dropdowns for Priority: ["Routine", "High", "Critical"].

6.  **Dashboard Sheet (Sheet 1):**
    * Do not put raw data here.
    * Create a "Heads Up" summary area (Cells A1:B10) showing counts:
        * Total Open Tasks.
        * Tasks flagged "Critical".
        * Projects in "Tender Pub" stage.

7.  **Execution:**
    * Write the complete script.
    * Ensure the script handles the 'close' and 'save' operations safely to prevent XML corruption.
