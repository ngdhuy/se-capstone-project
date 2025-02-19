# Requirement analyst

## 1 - Functional requirement

### 1.1 - E-Commerce website

* The homepage will be show the special production with: 
    * Top 4 hot products.
    * Top 4 best seller products.
* The menu will show categories of product.
* For each categories, the system will show list of product which belong to the category.
* Product information will be show at the product detail page.
* The user can be sign-up or sign-in account in the system.
* To buy product, user must register account.
* After login with Customer account, the user can choose the production to shopping cart.
* The customer can manage the shopping cart with the items which are not checkout. (Option, the customer can be payment online with payment gateway).
* The customer can checkout the current shopping cart.
* The customer can be check status of their orders.

### 1.2 - Admin Dashboard

* after login with admin role or employee role, the system will show the dashboard with the chart which visualize the summary current report about selling in the system.

#### 1.2.1 - Employee role

* Manage category information. 
* Manage production information.
* Manage the orders

#### 1.2.2 - Admin role

* Manage user-account. 
* Manage the system-configuration.

## 2 - Non-functional requirement

* Maximum loading time is 3 second.
* The system must security with authentication and authorization.

## 3 - User-role

List of user-role
* **Admin**: is the system manager. They only control user account and system-configuration.
* **Employee**: is the employee of the company. They will control production information, process orders, ...
* **Customer**: is the online buyer. They have information and account in the system with role Customer. They can use customer-account to buy the product on the online system.
* **Guest**: is the anonymous user. They have only to view the product information in the system. They can register Customer account.