# AutomatedPayment-RPA 

## Overview

This UiPath project automates a payment process where a user is prompted to enter an initial balance and a payment value. The system ensures that both inputs are valid double values. The process includes validation, fund checking, and the option to continue or stop at various stages, ultimately leading to an end state.

---

## Process Description

### Get Initial Balance
- The user is asked to enter an initial balance.
- The input is validated to ensure it is a valid double value.
- If invalid, the process stops and moves to the **Final State** (end).

### Get Payment Value
- The user is asked to enter a payment value.
- The input is validated to ensure it is a valid double value.
- If invalid, the process stops and moves to the **Final State** (end).

### Check Funds
- If the payment value exceeds the initial balance, a **"Not enough funds"** message is displayed, and the process moves to the **Deny Payment** state.
- The user can choose to:
  - **Continue (yes):** Returns to the **Get Payment Value** step.
  - **Stop (no):** Moves to the **Final State** (end).

### Make Payment
- If the payment value is less than or equal to the initial balance:
  - The payment is processed and the remaining balance is calculated.
  - The user is asked if they want to continue:
    - **Yes:** Returns to the **Get Payment Value** step.
    - **No:** Moves to the **Final State** (end).

---

## States

- **Entry:** Starting point for each major step (Get Initial Balance, Get Payment Value, Deny Payment, Make Payment).
- **Final State:** End point of the process when the user chooses to stop or invalid input is detected.

---
## Workflow Logic

```plaintext
[Start]
   ↓
[Get Initial Balance]
   └─ Invalid → [Final State]
   ↓
[Get Payment Value]
   └─ Invalid → [Final State]
   ↓
Payment ≤ Balance? ── No ──→ [Deny Payment]
                          └─ Continue? ─ No → [Final State]
                                       └─ Yes → [Get Payment Value]
   ↓
[Make Payment]
   ↓
Continue? ─ No → [Final State]
          └ Yes → [Get Payment Value]
```
![Workflow](https://github.com/rewaaalaa7/AutomatedPayment-RPA/blob/main/State-Machine.jpg)

## Prerequisites

- UiPath Studio installed.
- Basic understanding of UiPath workflows and activities.

---

## Setup Instructions

1. Clone the repository to your local machine.
2. Open the project in UiPath Studio.
3. Configure any necessary variables (e.g., initial balance, payment value) in the workflow.
4. Run the project to test the automated payment process.

---

## Usage

- Execute the workflow to start the payment process.
- Follow the prompts to enter the initial balance and payment value.
- Respond to continuation prompts (yes/no) as needed.
- The process will end when invalid input is detected or the user chooses to stop.

---
## Output
![output1](https://github.com/rewaaalaa7/AutomatedPayment-RPA/blob/main/output1.jpg)
![output2](https://github.com/rewaaalaa7/AutomatedPayment-RPA/blob/main/output2.jpg)
![output3](https://github.com/rewaaalaa7/AutomatedPayment-RPA/blob/main/outptu3.jpg)
![output4](https://github.com/rewaaalaa7/AutomatedPayment-RPA/blob/main/output4.jpg)
---

## 🪪 License

This project is licensed under the **MIT License** – see the `LICENSE.md` file for details.
