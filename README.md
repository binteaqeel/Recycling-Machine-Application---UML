# Batch Payroll Application - Use Case Diagram

## Overview

This UML Use Case Diagram represents the functional flow of a **Batch Payroll Application** that automates employee payment processing. It illustrates interactions between the **Employee**, **Bank**, **Paymaster**, and **Union** with various payroll-related operations.

---

## Actors

1. **Employee** – Submits work-related data and receives payments.
2. **Bank** – Handles direct deposits and financial transactions.
3. **Paymaster** – Oversees paycheck generation and payment approval.
4. **Union** – Manages deductions, dues, and service charges for its members.

---

## Major Use Cases

### Employee Actions

* **Submit Time Card** – Employees record their worked hours.

  * *Extends:* Apply Overtime Rule
* **Submit Sales Receipt** – Records sales for commission-based employees.

  * *Extends:* Ignore Commission if No Sales Receipt
* **Receive Pay** – Employees obtain their payment.

  * *Extends:* Reject if Payment Missing or Invalid Time Card
* **Calculate Pay** – Determines employee pay based on time cards and sales.

  * *Includes:* Apply Deductions, Apply Commission Rules

---

### Payroll Processing

* **Generate Payments** – Initiates the payment process for all employees.

  * *Includes:* Mail Paycheck, Deliver Paycheck, Direct Deposit
  * *Extends:* Switch to Paycheck if Bank Transfer Fails
  * *Extends:* Hold for Pickup if Address Missing

---

### Deductions and Rules

* **Apply Deductions** – Calculates applicable deductions.

  * *Includes:* Deduct Weekly Dues, Add Service Charges
  * *Extends:* Continue Without Charges (if not applicable)
* **Apply Commission Rules** – Applies commission structures based on sales.

  * *Extends:* Skip Deductions for Non-Union Members

---

## Payment Methods

* **Mail Paycheck** – Physical check is mailed.
* **Deliver Paycheck** – Paymaster handles in-person paycheck delivery.
* **Direct Deposit** – Funds transferred directly to the employee’s bank account.

---

## Notes

* The diagram emphasizes the use of **«include»** for mandatory relationships and **«extend»** for optional or conditional scenarios.
* It ensures that missing data (e.g., invalid time card, missing address, or failed transfer) is handled gracefully.
* The union’s interaction highlights deduction and membership-specific rules integrated into payroll processing.

---

## Purpose

This model serves as a blueprint for developers and analysts to understand:

* The logical flow of payroll operations.
* The dependencies among various payment-related processes.
* How exceptions and alternate flows are managed within the system.
