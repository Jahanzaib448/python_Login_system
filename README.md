# 🧑‍💻 User Registration & Login System (Using While Loop)

This is a simple **Python project** that allows a user to **register** and then **log in** using a username and password.  
The program is built using **while loops** and **if-else conditions**, making it perfect for Python beginners learning control flow.

---

## 🚀 Features

✅ Register a new user with a username and password  
✅ Prevent duplicate usernames during registration  
✅ Login system with **3 attempts limit**  
✅ Case-insensitive usernames (Ali, ALI, ali — all treated the same)  
✅ Clean and user-friendly console interface  

---

## 🧠 How the Code Works

1. The program starts by displaying a welcome message.  
2. It enters a `while` loop for **user registration**:
   - User enters a username and password.
   - Username is converted to lowercase using `.lower()` so it’s case-insensitive.
   - If the username already exists, it asks the user to try again.
   - If registration succeeds, the loop breaks.
3. After registration, the program asks the user to **log in**:
   - The user gets **3 login attempts**.
   - Each time, the username and password are verified against the stored data.
   - On success → displays a welcome message.
   - On failure → reduces attempts and shows remaining tries.
4. If all attempts fail, it shows a “Too many failed attempts” message.

---

## 🧩 Code Example

```python
users = {} 

print("========== Welcome to Login System ==========\n")

while True:
    print("📝 REGISTER YOUR ACCOUNT")
    username = input("Enter a username: ").lower()
    password = input("Enter a password: ")

    if username in users:
        print("⚠️ Username already exists! Try again.\n")
    else:
        users[username] = password
        print(f"✅ Registration successful! Welcome, {username}.\n")
        break 

print("========== Please Login ==========\n")
attempts = 3

while attempts > 0:
    username = input("Enter your username: ").lower()
    password = input("Enter your password: ")

    if username in users and users[username] == password:
        print(f"\n✅ Login successful! Welcome back, {username} 🙌")
        break
    else:
        attempts -= 1
        print(f"❌ Invalid username or password. Attempts left: {attempts}\n")

if attempts == 0:
    print("\n🚫 Too many failed login attempts! Try again later.")
# python_Login_system
python Login system using while Loop 
