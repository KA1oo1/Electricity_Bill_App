# Electricity_Bill_App

**Disclaimer**: This project is intended for educational purposes only. The creator is not responsible for any misuse. Please use it responsibly and only in authorized contexts.

---

This project is a **C-based console application** that calculates the **quarterly electricity bill** for a user based on units consumed, applying fixed and variable charges, tax, and penalty (if the due date has passed).

This is a solution to a challenge from the Android app "**Learn C Programming**". The logic was independently implemented by the author and validated against the expected outputs.  
For comparison, the solution written by the creators can be found on their github repository:  
🔗 [Official GitHub Repo](https://github.com/coding-cx/electricity_bill_calculator)

---

## Contents
- **Readme**: Containing a detailed explanation of how the bill is calculated and a **Sample Output**.
- **Code**: The main logic of the application implemented in C (see `electricity_bill`)
---

## How It Works

The program performs the following steps:

1. **Prompt the user** to enter:
   - Account number (must be a positive integer)
   - Units consumed for each of the last **three months**

2. **Calculate the total consumed units**, determine the applicable **fixed charge** and **energy charge per unit** from the following table:

   | Units       | Fixed Charge | Energy Charge/Unit |
   |-------------|--------------|---------------------|
   | 0 - 100     | $3           | $0.25               |
   | 101 - 300   | $7           | $0.50               |
   | 301 - 500   | $10          | $0.75               |
   | Above 500   | $12          | $1.00               |

3. **Add tax**:  
   - A tax of **0.5%** is calculated on the total usage bill and **rounded up**.

4. **Add penalty** (if the due date is passed):  
   - A penalty of **5%** is added to the final amount (after tax) and **rounded up**.
   - ⚠️ *Note: Due date checking is not handled in the code; penalty is applied by default for demonstration.*

5. **Display the bill**, including:
   - Account number
   - Total usage
   - Charges breakdown
   - Final amount (with and without penalty)

---

## Sample Output

```text
Welcome to Electricity Bill Application

Enter the Account number to proceed 
1234
Enter the Units Consumed in the past 3 months 
150
120
80

Total Consumed Units: 350

Charges Levied as: 
Fixed Cahrge: $10 
Energy Charge: $0.75

*******************

Account Numeber:  1234
Final Amount:  $274.00

WARNING: PAYMENT DUEDATE HAS PASSED!
Final Amount with DueDate Penalty: $288.00

*******************
```

---

## Code

The full implementation is provided in the `electricity_bill` file.

---

## Limitations

- Does not perform actual date validation for overdue payment.
- Input validation is minimal (ensures only positive values but does not handle non-numeric entries).
- Only calculates bills for a single user at a time.

---

## License

This project is open-source.

---

## Author

KA
