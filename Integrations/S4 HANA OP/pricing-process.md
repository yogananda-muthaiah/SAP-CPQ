# Overview of Pricing Procedure in S/4HANA

In S/4HANA, the pricing procedure is a systematic configuration that determines how prices, surcharges, discounts, taxes, and other values are calculated in sales/purchasing documents. The process is controlled by a set of elements: Condition Types, Access Sequences, Condition Tables, Calculation Schema (Pricing Procedure), and Condition Records.

---

## Key Components & Their Configuration Flow

### A. Condition Types
These define what the system calculates (price, discount, tax, etc.) and how.

- **Examples:** PR00 (base price), K007 (customer discount).
- **Tx Code:** V/06

### B. Condition Tables
Store key fields that form the basis for pricing conditions (e.g., Material, Customer, Sales Org).

- **Tx Codes:** V/03 (Create), V/04 (Change), V/05 (Display)

### C. Access Sequences
A search strategy that defines in which order the system looks up the condition tables for the applicable record. Each access step points to a specific condition table—the search goes from most specific to most general.

- **Tx Code:** V/07

**How to check:**
1. Enter V/07.
2. View the access sequence.
3. Double-click to see which condition tables and fields are used.

**SPRO Path:** Sales and Distribution → Basic Functions → Pricing Control → Define Access Sequences

**Example:** An access sequence might first check for a customer/material-specific price; if none exists, then just material.

### D. Calculation Schema / Pricing Procedure
The calculation schema (pricing procedure) organizes the sequence of condition types and calculations to be performed.

**It controls:**
- Sequence of calculations (steps)
- Whether a value is mandatory, statistical, etc.
- Subtotals, alternate calculations, etc.

- **Tx Code:** V/08

**How to check:**
1. Enter V/08.
2. Select a pricing procedure.
3. Display/modify its sequence, steps, condition types, routines, etc.

### E. Pricing Procedure Determination
The system determines the applicable pricing procedure by combining:
- Customer Pricing Procedure
- Document Pricing Procedure
- Sales Area

### F. Condition Records
Define the actual prices, discounts, or surcharges at runtime. Stored per condition type based on table fields' combination (e.g., price for a customer/material).

- **Tx Codes:** VK11 (create), VK12 (change), VK13 (display)

---

## Custom Pricing Routines

### Purpose
For advanced pricing logic, routines are written in ABAP and linked at specific points in the procedure (requirements, alternative calculations).

### Typical Use
- Requirements (when to apply a condition)
- Alternative Condition Base Value
- Alternative Calculation Type

### Creation Flow
1. Create the routine using transaction VOFM.
2. Assign the routine number in the pricing procedure (V/08) or access sequence as appropriate.
3. Activate and test.

**Checking in Document:** In sales orders (VA02/VA03), under "Conditions," the routine used is visible, and custom logic effect can be analyzed.

## Step-by-Step Example Workflow

### 1. Check or Define Condition Tables
Use V/03–V/05 to list or create tables for required keys (e.g., Sales Org/Customer/Material).

### 2. Define/Check Access Sequence
Use V/07 to create or examine the search strategy and which tables/fields are checked.

### 3. Condition Types
Use V/06 to view/create condition types and assign access sequences to these.

### 4. Define Pricing Procedure (Calculation Schema)
Use V/08 to assemble the condition types in the desired order; set markers for mandatory/statistical/subtotals; assign routines if needed.

### 5. Pricing Procedure Determination
Assign the procedure using SPRO or by maintaining the sales org, doc pricing procedure, and customer pricing procedure.

### 6. Create Condition Records
Use VK11 to enter actual valid-to/from pricing data for the defined keys.

### 7. Test/Check in Document
Create/display a sales order (VA01/VA02/VA03), navigate to the “Conditions” tab, and click "Analysis" for a step-by-step breakdown of which records and logic were applied.

---

This structured approach ensures a clear and coherent overview of the pricing procedure in S/4HANA, including the key components and their configuration flow.
# Transaction Codes for Day-to-Day Checks

| Function              | Transaction Code  | Description                           |
|-----------------------|-------------------|---------------------------------------|
| Condition Table       | V/03, V/04, V/05  | Create/Change/Display                 |
| Condition Type        | V/06              | Create/Change/Display                 |
| Access Sequence       | V/07              | Create/Change/Display                 |
| Pricing Procedure     | V/08              | Create/Change/Display                 |
| Condition Record      | VK11, VK12, VK13  | Create/Change/Display                 |
| Pricing Routine       | VOFM              | Maintain custom ABAP routines         |
| Analyze Pricing in Doc| VA02/VA03         | Sales Order, “Conditions” tab, “Analysis” |


Transaction Table Reference:

Tables like T683, T685, T682, T681 (Pricing Procedure, Condition Type, Access Sequence, Condition Table) are helpful for backend reviews.

# Summary Table: Standard T-codes and Uses

| Task                              | T-code       |
|-----------------------------------|--------------|
| Create/Check Condition Types      | V/06         |
| Create/Check Access Sequence      | V/07         |
| Create/Check Condition Tables     | V/03–V/05    |
| Pricing Procedure Maintenance     | V/08         |
| Maintain Condition Records        | VK11–VK13    |
| Custom Routine Maintenance        | VOFM         |
| Analyze in Sales/Purchasing       | VA02/VA03    |
| IMG Complete Pricing Control      | SPRO         |
