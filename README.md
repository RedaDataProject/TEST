#  Swag Labs – End-to-End QA Testing (Manual & Automated with Selenium in Python)

This repository contains a complete QA testing approach for the [Swag Labs](https://www.saucedemo.com/) demo e-commerce application. It includes a structured test plan, detailed test cases, execution results, automated test scripts, bug reports, and key QA insights.

---

##  Project Description

**Project Name:** Swag Labs QA Testing  
**Target Application:** [https://www.saucedemo.com/](https://www.saucedemo.com/)  
**Tools & Technologies:** Selenium WebDriver (Python), Jira, Bugzilla  
**Testing Types:**  
- Functional Testing  
- Usability Testing  
- Basic Performance Checks  
- Automation (Selenium)

---

##  Scope of Testing

This QA process covers:  
- Core user flows: login, product selection, cart, checkout  
- Sidebar and navigation interactions  
- Reset App State behavior  
- Validation of app response to missing user inputs

---

##  Testing Methods

- Manual test cases following QA best practices  
- Automated test scripts developed using Selenium  
- Bug documentation aligned with industry standards  
- Reports generated from real execution results  

---

##  Key Findings

- **Navigation Bug:** Clicking on the Swag Labs header doesn't redirect users.  
- **Sidebar Bugs:** "Reset App State" and logout confirmation are malfunctioning.  
- **Checkout Flaws:** Orders can be submitted without selecting products.  
- **Missing Validations:** No quantity control and no error shown when placing empty orders.

---

##  Recommendations

1. **Fix Critical Functional Bugs** in navigation and checkout flows  
2. **Improve Error Messages** during key actions like cart/checkout/logout  
3. **Add Confirmation Steps** for logout and reset operations  
4. **Expand Automation Coverage** to include edge cases and negative flows  
5. **Perform Regression Testing** after fixing known issues

---

## Files Included

- `SWAGsystem_Anushiga.xlsx`: Manual test cases, execution results, and bug summaries  
- `Automated test script_Anushiga.docx`: Selenium automation script + setup instructions  
- `Summary_Report.xlsx`: Overview of testing efforts and outcomes

---

## Example Automated Script

```python
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.chrome.service import Service as ChromeService
from webdriver_manager.chrome import ChromeDriverManager
import time

driver = webdriver.Chrome(service=ChromeService(ChromeDriverManager().install()))
driver.get("https://www.saucedemo.com/")
driver.maximize_window()

# Login
driver.find_element(By.ID, "user-name").send_keys("standard_user")
driver.find_element(By.ID, "password").send_keys("secret_sauce")
driver.find_element(By.ID, "login-button").click()

# Reset App State
driver.find_element(By.ID, "react-burger-menu-btn").click()
time.sleep(1)
driver.find_element(By.ID, "reset_sidebar_link").click()

# Verify state reset
# (You can update this block depending on the element being tested)
print("Reset action performed successfully.")
driver.quit()
