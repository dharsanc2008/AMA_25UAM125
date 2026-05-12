## Comparison Between the Two Programs

The second program is an **enhanced version** of the first bank-account management program.
Several new features and functions were added, and the menu system was expanded.

---

# Changes Made in the Second Program

## 1. Added New Function Prototypes

### First Program

```c
unsigned int enterChoice(void);
void textFile(FILE *readPtr);
void updateRecord(FILE *fPtr);
void newRecord(FILE *fPtr);
void deleteRecord(FILE *fPtr);
```

### Second Program

```c
unsigned int enterChoice(void);
void textFile(FILE *readPtr);
void updateRecord(FILE *fPtr);
void newRecord(FILE *fPtr);
void deleteRecord(FILE *fPtr);
void viewAccount(FILE *fPtr);
void displayAllAccounts(FILE *fPtr);
void displayAccountStatistics(FILE *fPtr);
```

### Change

Three new functions were added:

* `viewAccount()` → View details of a single account
* `displayAllAccounts()` → Display all stored accounts
* `displayAccountStatistics()` → Show statistics like total balance and average balance

---

# 2. Menu Expanded

### First Program Menu

```c
1 - store formatted text file
2 - update an account
3 - add a new account
4 - delete an account
5 - end program
```

### Second Program Menu

```c
1 - store formatted text file
2 - update an account
3 - add a new account
4 - delete an account
5 - view account details
6 - display all accounts
7 - display account statistics
8 - end program
```

### Change

New menu options added:

| New Option | Purpose                    |
| ---------- | -------------------------- |
| 5          | View one account           |
| 6          | Display all accounts       |
| 7          | Display account statistics |
| 8          | Exit program               |

The exit option changed from `5` to `8`.

---

# 3. Main Loop Condition Changed

### First Program

```c
while ((choice = enterChoice()) != 5)
```

### Second Program

```c
while ((choice = enterChoice()) != 8)
```

### Change

Because new menu options were added, the exit choice changed from `5` to `8`.

---

# 4. New Cases Added in switch Statement

### Added Cases

```c
case 5:
    viewAccount(cfPtr);
    break;

case 6:
    displayAllAccounts(cfPtr);
    break;

case 7:
    displayAccountStatistics(cfPtr);
    break;
```

### Change

The program can now:

* Search and display one account
* Display every account
* Show banking statistics

---

# 5. New Function: `viewAccount()`

### Purpose

Allows the user to view a specific account using the account number.

### Features

* Reads one record from the file
* Displays account details
* Shows error if account does not exist

### Output Example

```text
Acct Last Name      First Name   Balance
1     Smith         John          500.00
```

---

# 6. New Function: `displayAllAccounts()`

### Purpose

Displays every valid account stored in the file.

### Features

* Uses `rewind()` to start from beginning
* Reads all records using `fread()`
* Skips empty accounts
* Counts total displayed accounts

### Additional Improvement

A formatted table and separator line were added.

---

# 7. New Function: `displayAccountStatistics()`

### Purpose

Shows summary statistics of all accounts.

### Features

Calculates:

* Total number of accounts
* Total balance
* Average balance

### Example Output

```text
========== ACCOUNT STATISTICS ==========
Total Accounts: 5
Total Balance: $2500.00
Average Balance: $500.00
========================================
```

---

# 8. Better User Interaction

The second program is more user-friendly because:

* Users can directly view account information
* Users can see all records without generating a text file
* Users can monitor banking statistics

---

# 9. Minor Comment Change

### First Program

```c
// write updated record over old record in file
```

### Second Program

```c
// write updated record over old record in filez
```

### Change

Typographical error added accidentally (`filez`).

---

# 10. Overall Improvement

| Feature              | First Program | Second Program |
| -------------------- | ------------- | -------------- |
| Create text file     | Yes           | Yes            |
| Update account       | Yes           | Yes            |
| Add account          | Yes           | Yes            |
| Delete account       | Yes           | Yes            |
| View single account  | No            | Yes            |
| Display all accounts | No            | Yes            |
| Show statistics      | No            | Yes            |
| Better reporting     | Limited       | Improved       |

---

# Final Conclusion

The second program is an upgraded and more complete banking management system.

### Main Enhancements

* Added account viewing feature
* Added display-all-accounts feature
* Added statistical analysis
* Improved menu system
* Better reporting and usability

The core file handling logic remains the same, but the second version provides more functionality and better user interaction.
