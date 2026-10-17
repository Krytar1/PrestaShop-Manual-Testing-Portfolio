# Manual Testing Portfolio: PrestaShop E-commerce Platform

This repository contains functional manual test cases designed and executed for an e-commerce platform based on **PrestaShop** (`https://dev-mystore-testlab.coderslab.pl/index.php`). 

The goal of this project is to demonstrate my practical software testing skills, including test case design, requirement analysis, business logic verification, and clear documentation practices aligned with **ISTQB standards**.

---

## 🛠️ Project Scope & Tested Functionalities

The test suite covers critical user paths (happy paths) and negative scenarios within the e-commerce system:
1. **Cart Management:** Verifying the correctness of adding available items to the shopping cart, total price calculations, and item counts.
2. **Stock Constraints (Negative Path):** Ensuring that out-of-stock items cannot be added to the cart and verifying the availability of back-in-stock notification forms.
3. **Localization & UI:** Testing the currency switching functionality (EUR to USD) and verifying dynamic price conversion across the storefront.
4. **Account Management:** Validating the complete user registration flow, account creation, and newsletter subscription integration.

---

## 📂 Test Cases

### TC-001: Add Available Item to Shopping Cart
**Author:** Krystyna Tarczynska  

* **Preconditions:**
  * The website https://dev-mystore-testlab.coderslab.pl/index.php is opened.
  * The user is in a guest session (not logged in).

| # | Test Steps | Test Data | Expected Results |
|---|---|---|---|
| 1 | Click on any available product from the homepage. | E.g., "Hummingbird printed t-shirt" | The product details page opens successfully. |
| 2 | Click the **"Add to cart"** button. | Default quantity (1) | A popup window appears with the message "Product successfully added to your shopping cart". |
| 3 | Verify the information in the popup window. | N/A | The popup displays the correct product name, total price, and total number of pieces. |

* **Postconditions:** The item is correctly added to the cart, and the cart badge updates with the correct amount and total price.

---

### TC-002: Attempt to Add an Out-of-Stock Item to the Shopping Cart
**Author:** Krystyna Tarczynska  

* **Preconditions:**
  * The website https://adidas.gr is opened.
  * An item with at least one out-of-stock size is identified in advance.

| # | Test Steps | Test Data | Expected Results |
|---|---|---|---|
| 1 | Search for the specific out-of-stock item using the search bar. | "Tiro 25 Competition Training Jersey Kids" | The product details page opens successfully. |
| 2 | Select a size that is currently out of stock. | Size: 176 | The selected size is visually highlighted as unavailable. The "Add to Cart" button becomes disabled or disappears. |
| 3 | Verify the presence of the stock notification option. | N/A | A "Notify Me" button appears, allowing the user to subscribe for an email alert when the size is back in stock. |

* **Postconditions:** The unavailable item cannot be added to the shopping cart, and the back-in-stock subscription form is fully visible.

---

### TC-003: Change Currency from Euro (EUR) to US Dollar (USD)
**Author:** Krystyna Tarczynska  

* **Preconditions:**
  * The website https://dev-mystore-testlab.coderslab.pl/index.php is opened.
  * The default currency is set to Euro (EUR / €).

| # | Test Steps | Test Data | Expected Results |
|---|---|---|---|
| 1 | Click on the currency dropdown menu in the top header. | N/A | The dropdown menu expands, displaying available currencies: EUR € and USD \$. |
| 2 | Select **"USD \$"** from the list. | N/A | The page reloads or updates dynamically. The selected currency changes to USD \$. |
| 3 | Verify the product prices displayed on the homepage. | N/A | All product prices are successfully converted and displayed with the "\$" symbol. |

* **Postconditions:** The store currency is successfully set to US Dollar (USD) for the duration of the user session.

---

### TC-004: User Account Creation and Newsletter Subscription
**Author:** Krystyna Tarczynska  

* **Preconditions:**
  * The website https://dev-mystore-testlab.coderslab.pl/index.php is opened.
  * The user is not logged in and does not have an account.

| # | Test Steps | Test Data | Expected Results |
|---|---|---|---|
| 1 | Click the **"Sign in"** link in the top header. | N/A | The sign-in page opens successfully. |
| 2 | Click the **"No account? Create one here"** link. | N/A | The registration form page is displayed. |
| 3 | Fill out the form with valid data, check the terms and conditions box, and check the newsletter subscription box. | **First name:** Anna<br>**Last name:** Xyz-Abc<br>**Email:** qaz@wp.pl<br>**Password:** 123!@#qaZ | The fields are filled successfully, and the checkboxes are ticked. |
| 4 | Click the **"Save"** button. | N/A | The account is created successfully. The user is automatically logged in, and the name "Anna" is visible in the top header. |

* **Postconditions:** The new user account is active and authenticated, and the email address is subscribed to the newsletter.

