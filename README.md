# Konga Checkout – Selenium IDE Invalid Card Test

## Overview
This project automates a checkout flow on the **Konga e-commerce platform** using Selenium IDE. The test validates how the system handles **invalid card payment attempts** during checkout. It demonstrates UI automation skills, e-commerce testing, negative scenario testing, and recognition of automation limitations around secure payment gateways.

---

## Tools & Technologies
- Selenium IDE (Firefox)
- Mozilla Firefox Browser
- GitHub

---

## Test Scenario
1. Launch Konga website  
2. Login with valid test credentials  
3. Navigate to **All Categories → Computers → Laptops → MacBooks**  
4. Add a MacBook to cart  
5. Proceed to checkout  
6. Select delivery address  
7. Click **Place Order**  
8. Select **Card Payment**  
9. Attempt to input invalid card details  
10. Verify that an appropriate payment error or failure response occurs  

---

## Test Data Notes
- All credentials and card data are **dummy values**  
- No real personal information or payment details are used  

---

## Expected Result
User should be unable to complete payment using invalid card details, and the system should display a meaningful error or failure message during the payment process.

---

## Actual Playback Behavior
During recording, Selenium IDE successfully captured all actions,

However, during playback:

- Although the iframe was selected on the test script 
- the iframe did not visibly load on the UI
- Selenium continued execution but eventually stalled at **Place Order**
- card input fields could not be interacted with
- no payment form was rendered for automation

This discrepancy occurs because secure payment iframes often expose the DOM during recording but **block automation during playback** for compliance and security reasons.

---

## Known Automation Limitation
Konga’s card payment interface loads inside a **secure PCI-DSS compliant iframe** provided by a third-party payment gateway. Selenium IDE cannot interact with cross-domain or secure iframes due to:

- Security sandboxing
- Cross-domain restrictions
- Compliance rules
- Lack of DOM exposure for automation tools

This is expected behavior and is commonly encountered when automating checkout/payment workflows in e-commerce applications.

 This is not a defect in the application. It is a technical limitation of Selenium IDE.



## Project Structure
Konga-Checkout-Selenium-Invalid-Card-Test/
├── tests/
│ └── konga_checkout.side
├── screenshots/ (optional)
└── README.md


---

## How to Execute the Test
1. Install Selenium IDE (Firefox)
2. Open Selenium IDE
3. Import `konga_checkout.side`
4. Run test using Firefox browser

---

## Key Takeaways
✔ Demonstrates functional UI automation of an e-commerce checkout  
✔ Performs negative testing using invalid payment data  
✔ Shows tester understanding of real-world payment gateway constraints  
✔ Highlights ability to scope and document automation limitations  
✔ Suitable for QA portfolios and learning assignments  


## Conclusion
This project reflects practical experience with **UI automation**, **e-commerce testing**, and navigating real-world security constraints in automated testing. It also demonstrates awareness of testing scope, negative scenarios, and best practices for documenting limitations.


