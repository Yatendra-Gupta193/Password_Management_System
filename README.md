# Password Management System (Java CLI)  
 
A Java command-line password management system that lets a user:
- Log in using a **master password**
- Generate strong passwords
- Add / update / delete stored credentials
- Display saved passwords
- Show “unsafe” passwords by comparing stored passwords against `hackedPassword.txt`
- Create / view / delete memos stored in `Memo.txt`

## Features
- Password generator (includes letters, digits, and symbols)
- Password validation (length + digit count + special characters + uppercase + lowercase)            
- File persistence:
  - `passwordDB.txt` for saved passwords
  - `Memo.txt` for memos
  - `hackedPassword.txt` for unsafe-password comparison

## Project Structure
- `PMS/src/Main.java` — application entry point (login + main menu)
- `PMS/src/PasswordManagement.java` — linked-list based CRUD for passwords + persistence to `passwordDB.txt`
- `PMS/src/MemoManagement.java` — memo list + persistence to `Memo.txt`
- `PMS/src/PasswordGenerator.java` — password generation logic
- `PMS/src/NodePassword.java` — node structure for the password linked list

## How to Run
### Run using existing compiled classes
From the repository root:
```bat
cd d:/Password-Management-System-main
java -cp PMS/out/production/PMS Main
```

### (Optional) Compile first
```bat
cd d:/Password-Management-System-main
javac PMS/src/*.java
java -cp PMS/src Main
```

> Note: Using `PMS/out/production/PMS` is the most reliable with the current project state.

## Master Password
In `PMS/src/Main.java`, the login check is hardcoded as:
- **master password:** `admin`

## Menu Options
After login, the program shows:
- `[1] Generate Password`
- `[2] Update Password`
- `[3] Delete Password`
- `[4] Saved Passwords`
- `[5] Unsafe Passwords list`
- `[6] Create Memo`
- `[7] Delete Memo`
- `[8] View Memos`
- `[0] Exit System`

## Data Files Used
Ensure these files exist in the working directory (`d:/Password-Management-System-`) when running:
- `passwordDB.txt`
- `Memo.txt`
- `hackedPassword.txt`

If they are missing, the app may print messages like **“File not found”**.

## Notes / Known Issues
- The memo loader prints `Memo File Not Found !` if `Memo.txt` is missing.
- Input handling in `Main.java` mixes multiple `Scanner` instances; depending on the runtime inputs, it may throw `NoSuchElementException`.
