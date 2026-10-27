# Hospital Billing and Patient Classification

## 1. Problem Statement

Develop a Python program to calculate hospital bills based on consultation, diagnostic, and treatment charges. Apply concessions based on patient conditions, validate billing details, calculate the final amount, and classify patients according to the payment policy.

## 2. Algorithm

1. Start the program.
2. Input the patient's name and patient type.
3. Input consultation, diagnostic, and treatment charges.
4. Check whether all charges are valid and non-negative.
5. Calculate the total bill by adding all charges.
6. If the patient is a senior citizen, apply a 10% concession.
7. If the total bill is above ₹10,000, apply an additional 5% concession.
8. Calculate the final bill after concessions.
9. Classify the payment:
   - Below ₹5,000 – Low Payment
   - ₹5,000 to ₹10,000 – Medium Payment
   - Above ₹10,000 – High Payment
10. Display the total bill, concession, final bill, and patient classification.
11. Stop the program.
``` mermaid
## 3. Flowchart in Steps

START

Input patient details and charges

Are all charges valid?

Yes ↓

No →

Display error

Calculate total bill

Apply applicable concessions

Calculate final bill

Classify payment amount

Display bill and classification

STOP
```
## 4. Python Source Code

```
# Hospital Billing and Patient Classificationname = input("Enter patient name: ")patient_type = input("Enter patient type (senior/regular): ").lower()consultation = float(input("Enter consultation charges: "))diagnostic = float(input("Enter diagnostic charges: "))treatment = float(input("Enter treatment charges: "))if consultation < 0 or diagnostic < 0 or treatment < 0:    print("Invalid charges. Charges cannot be negative.")elif patient_type not in ["senior", "regular"]:    print("Invalid patient type.")else:    total = consultation + diagnostic + treatment    concession = 0    if patient_type == "senior":        concession += total * 0.10    if total > 10000:        concession += total * 0.05    final_bill = total - concession    if final_bill < 5000:        category = "Low Payment"    elif final_bill <= 10000:        category = "Medium Payment"    else:        category = "High Payment"    print("\n--- Hospital Bill ---")
```

## 5. Sample Input

```
Enter patient name: Ravi
Enter patient type (senior/regular): senior
Enter consultation charges: 1000
Enter diagnostic charges: 3000
Enter treatment charges: 8000
```

## 6. Sample Output

```
--- Hospital Bill ---
Patient Name: Ravi
Total Bill: Rs. 12000.0
Concession: Rs. 1800.0
Final Bill: Rs. 10200.0
Patient Classification: High Payment
```

## 7. Explanation of Output

- Total bill = ₹1,000 + ₹3,000 + ₹8,000 = ₹12,000.
- Senior citizen concession = 10% of ₹12,000 = ₹1,200.
- Additional concession = 5% of ₹12,000 = ₹600.
- Total concession = ₹1,200 + ₹600 = ₹1,800.
- Final bill = ₹12,000 − ₹1,800 = ₹10,200.
- Since the final bill is above ₹10,000, the classification is High Payment.

Note: The concession rates and payment categories are example rules for this programming assignment. They can be changed to match your teacher's specified policy.
