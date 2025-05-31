# 🛒 SuperMarket Billing System - Python  

## 🔍 Project Overview

This Python-based SuperMarket Billing System simulates a real-world retail billing process.
It allows cashiers to:

- Add multiple products to a cart

- Apply automated discounts based on purchase amount

- Generate itemized receipts in TXT & PDF formats

- Validate user inputs (mobile number, product names)

**Goal:** Demonstrate Python skills in file handling, loops, conditionals, and user interaction while solving a practical problem.

## ✨ Features

✅ Interactive Console Interface

- Guides users step-by-step (name, mobile, product selection).

- Case-insensitive product search (e.g., "Apple" = "apple").

✅ Dynamic Discounts

 Total Purchase |	Discount 
----------------|-----------
≤ ₹500	        | 10% 
≤ ₹1000	        | 15% 
≤ ₹1500	        | 20%
| > ₹1500	        | 30%      |

✅ Receipt Generation

- Text (.txt): [Simple formatted bill.](./demo-thumbnail.png.jpg)

- PDF (.pdf): [Professional layout with borders.](./sample-bill.pdf)

✅ Input Validation

- Ensures:

    - Non-empty customer names.

    - 10-digit mobile numbers (using Regex).

    - Valid product names.

✅ Multi-Transaction Support

- Processes multiple customers in one session.

## 🛠️ Installation

Clone the repository:

```bash
git clone https://github.com/your-username/supermarket-billing.git
cd supermarket-billing
Install dependencies (only fpdf needed):
```
```bash
pip install fpdf
```
## 🚀 Usage

Run the script:

```bash
python supermarket_billing.py
```
2. Follow prompts:

    - Enter customer details (name, mobile).

    - Add products (e.g., "apple", "milk") and quantities.

    - Choose to save receipts as TXT/PDF.

3. Example Workflow:

```plaintext
Insert a Name: John Doe  
Enter Mob No.: 9876543210  
Product name: apple  
Quantity: 2  
Want to add more items? (yes/no): no  
Do you want to save the bill? (yes/no): yes  
Do you want to save the bill as a PDF? (yes/no): yes
```  
## 🧩 Code Structure

```python
# 1. PRODUCT DATABASE
Products = {
    "apple": 30,
    "banana": 20,
    # ... (10+ items)
}

# 2. INPUT VALIDATION
while not name:  # Ensures non-empty name
while not re.fullmatch(r"\d{10}", mob):  # Validates mobile

# 3. DISCOUNT LOGIC
if amount <= 500: discount = 0.10
elif amount <= 1000: discount = 0.15
# ...

# 4. RECEIPT GENERATION (TXT/PDF)
with open(filename, "w") as file:
    file.write(bill_content)
pdf = FPDF()  # PDF formatting

```
## 📸 Sample Outputs
Text Receipt

~~~plaintext
--- Supermarket Bill ---  
Name        : John Doe  
Mobile No.  : 9876543210  

--- Subtotal ---  
Item Name    Quantity  Price  Total  
----------------------------------  
apple        2         30     60.00  
bread        1         40     40.00  
----------------------------------  
Total Payable: ₹90.00 (Saved: ₹10.00)
~~~ 
PDF Receipt

[(See /docs/sample_receipt.pdf for a formatted example.)](./sample-bill.pdf)

## 🔮 Future Improvements

- GUI Version: Add Tkinter/PyQt interface.

- Inventory Management: Track stock levels.

- Barcode Scanner: Integrate with pyzbar for quick input.

## 🤝 Contributing

1. Fork the repository.

2. Create a branch (git checkout -b feature/new-discounts).

3. Commit changes (git commit -m "Add new feature").

4. Push to the branch (git push origin feature/new-discounts).

5. Open a Pull Request.

## 📜 License
This project is licensed under the MIT License.

[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](./LICENSE)  
Copyright © 2025 [Sagarkumar49](https://github.com/Sagarkumar49)

## 🌟 Show Support

If you find this useful, give it a ⭐ on GitHub!
