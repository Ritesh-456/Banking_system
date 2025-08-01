# 🏦 Banking System with Streamlit UI

A simple Object-Oriented Banking System that allows users to create and manage bank accounts via a **Streamlit web interface**. Data is securely stored in `.txt` files using JSON format. This app supports **account creation**, **deposit**, **withdrawal**, and **balance check** for multiple banks.

## 📂 Project Structure

```Bash
bank_project/
├── streamlit_app.py # Streamlit UI (Frontend)
├── main.py # CLI Version (For testing)
├── data_store/ # Stores user JSON data by bank
│ └── SBI.txt # Example file
├── bank_classes/ # Bank-wise class files
│ ├── __init__.py
│ └── sbi.py # SBI Bank class
├── requirements.txt # Python dependencies
└── README.md # Project documentation
```

---

## 🏦 Supported Banks

- SBI (State Bank of India)
- BOB (Bank of Baroda)
- PNB (Punjab National Bank)
- Canara Bank
- Union Bank

Each bank is implemented as a separate class under `bank_classes/`.

---

## 🚀 Features

| Feature        | CLI (main.py) | Streamlit (streamlit_app.py) |
| -------------- | ------------- | ---------------------------- |
| Create Account | ✅            | ✅                           |
| Login with PIN | ✅            | ✅                           |
| Deposit        | ✅            | ✅                           |
| Withdraw       | ✅            | ✅                           |
| Check Balance  | ✅            | ✅                           |

---

## 🧠 Tech Stack

- **Python 3.x**
- **Streamlit** - Frontend UI
- **JSON files** - Backend data storage
- **OOP (Object-Oriented Programming)** - For bank logic

---

## 📦 Installation

### 1. Clone the Repository

```Bash
git clone https://github.com/Ritesh-456/Banking_system.git  
cd bank-project # New Folder Name
```

### 2. Create Virtual Environment (Recommended)

```Bash
python -m venv all_modules
source all_modules/bin/activate  # Linux/macOS
all_modules\Scripts\activate     # Windows
```

### 3. Install Dependencies

```Bash
pip install -r requirements.txt
If requirements.txt is missing, use:
```

- *If `requirements.txt` is missing, use:*

```Bash
pip install streamlit
```

---

## ▶️ Run the App

### 🌐 Launch Streamlit Web Interface

```Bash
streamlit run streamlit_app.py
```

### 🧪 For Testing via CLI (main.py)

You can test the same functionality via terminal:

```Bash
python main.py
```

---

## 🛠 Sample Bank Class (bank_classes/sbi.py)

```Bash
class SBI:
    def __init__(self, data):
        self.data = data

    def match_pin(self, pin):
        return self.data["pin"] == pin

    def deposit(self, amount):
        self.data["balance"] += amount
        print("✅ Deposited successfully.")

    def withdraw(self, amount):
        if self.data["balance"] >= amount:
            self.data["balance"] -= amount
            print("✅ Withdrawal successful.")
        else:
            print("❌ Insufficient balance.")

    def check_balance(self):
        print(f"💰 Current balance: ₹{self.data['balance']}")
```

---

## 💾 Data Storage

User account data is stored in:

```bash
data_store/SBI.txt
data_store/BOB.txt
...
```
Each file contains JSON with multiple users, where each PIN is the unique key.

**Example:**

```bash
{
  "1234": {
    "bank_name": "SBI",
    "first_name": "John",
    "last_name": "Doe",
    "balance": 5000,
    "pin": "1234"
  }
}
```
---
## ☁️ Deployment
You can deploy this app on:

- Streamlit Cloud
- Render
- [Local Server]

Streamlit Cloud Deployment Steps
- Push your code to GitHub
- Go to streamlit.io/cloud
- Click New App
- Select your repo and `streamlit_app.py`
- Deploy!

---
## 🛡️ Security Notes
PINs are stored in plaintext (for learning only).

For real-world use: consider hashing, encrypting PINs, and using databases.

---
## 🧑‍💻 Author
Made by Your `github.com/Ritesh-456/`
--
## 📃 License
This project is licensed for educational purposes. And all license are belongs to  &copy;`github.com/Ritesh-456/`

--
## 📝 Note  
Your data is **temporary**. If Streamlit or project goes to sleep, all details will be **cleared**.  
To keep your data safe, it's better to **fork this project** and run it on your own device.