# Recycling Machine Application - Use Case Diagram

## Overview

This Use Case Diagram illustrates the functional processes of the **Recycling Machine Application**, which automates bottle and can returns, refunds, and receipt generation. It also handles error detection and daily reporting, ensuring smooth operation for both customers and operators.

---

## Actors

1. **Customer** – Returns recyclable items, requests receipts, and receives refunds.
2. **Operator** – Manages deposit values, daily reports, and resolves technical issues.
3. **System** – Performs automated recognition, refund, and reporting operations within the machine.

---

## Major Use Cases

### Customer Actions

* **Return Bottle / Return Can** – Customers insert bottles or cans for recycling.

  * *Includes:* Recognize Item
* **Receive Refund** – Customers are refunded based on returned items.

  * *Extends:* Alarm Refund Jammed (if refund system malfunctions)
* **Request Receipt** – Customers request a printed receipt.

  * *Includes:* Print Receipt
  * *Extends:* Receipt Roll Empty (if no paper available)

---

### System Operations

* **Recognize Item** – Identifies the type of item (bottle or can) for processing.

  * *Includes:* Record Transaction
  * *Extends:* Alarm Unrecognized or Blocked Items (if item type is invalid)
* **Record Transaction** – Logs each recycling operation for reporting and tracking.

---

### Operator Functions

* **Update Deposit Values** – Adjusts refund or deposit values for items.
* **View Daily Count** – Displays total items processed per day.
* **Generate Daily Report** – Summarizes daily operations.

  * *Includes:* Record Transaction
* **Resolve Technical Issue** – Addresses any system alarms or malfunctions triggered during operation.

---

### Error and Alarm Handling

* **Alarm Unrecognized or Blocked Items** – Triggered when an item is unreadable or blocked.
* **Alarm Refund Jammed** – Triggered when the refund mechanism fails.
* **Receipt Roll Empty** – Triggered when the receipt printer runs out of paper.
* **Trigger Alarm** – Activated by any system malfunction.

  * Leads to **Resolve Technical Issue** handled by the Operator.

---

## Notes

* **«include»** relationships indicate required steps in a process (e.g., recognizing an item before issuing a refund).
* **«extend»** relationships show optional or exception-based scenarios (e.g., refund jam or unrecognized items).
* The system ensures continuous monitoring and automatic alerts for smooth machine operation.

---

## Purpose

This UML serves as a visual guide for:

* Understanding user and system interactions.
* Identifying core and exceptional workflows in the recycling process.
* Supporting developers and analysts in designing system logic and fault handling.
