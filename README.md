
# Cafe Management System

This project is a comprehensive CLI (Command Line Interface) application designed to manage a database of customers, products, and cafe orders. The application provides functionalities for adding, updating, and viewing data, as well as exporting data to Excel files. The project is built using Python and MySQL, and it leverages the pandas library for data manipulation and export.

## Features
#### 1. Customer Management
- **Add Customer:** Easily add new customers to the system, including details such as name and phone number.
- **Update Customer:** Update existing customer information, such as name and contact details.
- **View Customer Data:** View a list of all customers stored in the system, along with their details.
#### 2. Product Management
- **Add Product:** Add new products to the cafe's menu, specifying details such as product type, name, and price.
- **Update Product:** Modify existing product information, including product type, name, and price.
- **View Product Data:** Display a list of all products available in the cafe, along with their details.
#### 3. Order Management
- **Place Orders:** Allow staff to place orders for customers, selecting products from the menu and specifying quantities.
- **View Order History:** View a history of all orders placed, including details such as order date, time, customer information, and product details.
- **Export Order Data:** Export order data to Excel files for further analysis or reporting purposes.
#### 4. Database Integration
- **MySQL Database:** Utilize a MySQL database backend for storing and managing customer, product, and order data.
- **Database Connectivity:** Establish a connection to the MySQL database to retrieve and update information as needed.

## Workflow
#### Main Menu

Users are presented with several options:
- New Order
- Update/Cancel Order
- Setting
- View/Export Data

Users can select an option by entering the corresponding number.

#### New Order
If the user selects "New Order", the script proceeds with the following steps:
- **Generate New Order ID:** Determine the next order ID.
- **Capture Customer Details:** Handle both new and existing customers.
- **Select Product:** List available product types and products for selection.
- **Input Order Details:** Capture the quantity and confirm the order.
- **Save Order:** Insert the order details into the database.
#### Update/Cancel Order
If the user selects "Update/Cancel Order", the script allows the user to:
- **Update Order:** Modify product details and quantity.
- **Cancel Order:** Change the order status to "Order Cancelled" and record the reason.
#### Setting
If the user selects "Setting", the script allows the user to:
- **Add Customer:** Users can input customer details like name and phone number, which are then inserted into the database.
- **Update Customer:** Existing customer information can be modified by providing the customer ID and entering the new details, with the system updating the database accordingly.
- **Add Product:** Users can add new products by entering details such as type, name, and price, which are then inserted into the database.
- **Update Product:** Existing product details can be updated by specifying the product ID and providing the new information, with the system updating the database accordingly.
- **Create Table in Database:** Users can create new tables in the database, including those for customers, products, and orders, with confirmation prompts ensuring deliberate creation.
- **Custom SQL Query:** User can execute custom SQL queries for any changes in the database.
#### View/Export Data
If the user selects "View/Export Data", the script allows the user to:
- **View Customer Data:** View and export customer data.
- **View Product Data:** View and export product data.
- **View Cancel Cafe Order Data:** View and export canceled cafe order data.
- **View Cafe Order Data:** View and export delivered cafe order data.
- **View Custom Data:** Execute custom SQL queries, view results, and export data to Excel.

## Installation
To set up and run the Cafe Management System on your local machine, follow these steps:

#### 1. Install Python:

If you haven't already installed Python, you can download and install it from the [official Python website](https://www.python.org). Make sure to select the appropriate version for your operating system.

#### 2. Install MySQL Server:

You need to have MySQL Server installed on your system. You can download and install MySQL Server from the [official MySQL website](https://dev.mysql.com/downloads/mysql/).
    
#### 3. Install Required Python Packages:

Open your terminal or command prompt and run the following commands to install the required Python packages:

```bash
  pip install mysql-connector-python pandas openpyxl
```

#### 4. Set Up MySQL Database:

Start MySQL Server if it's not already running.
Create a new database and table for the Cafe Management System. You can do this using a MySQL client or command line.
- Create Database
```bash
CREATE DATABASE cafe_management_system;
```
- Create table for Customer
```
CREATE TABLE customer (
    Customer_ID INT,
    Customer_Name VARCHAR(40),
    Phone_No BIGINT
);
```
- Create table for Product
```
CREATE TABLE product (
    Product_ID INT,
    Product_Type VARCHAR(40),
    Product_Name VARCHAR(40),
    Product_Price INT
);
```
- Create table for Cafe Order
```
CREATE TABLE cafe_order (
    Order_ID INT,
    Order_Date DATE,
    Order_Time TIME,
    Customer_ID INT,
    Customer_Name VARCHAR(40),
    Phone_No BIGINT,
    Product_ID INT,
    Product_Type VARCHAR(40),
    Product_Name VARCHAR(40),
    Product_Price INT,
    Quantity INT,
    Total_Amount INT,
    Payment_Method VARCHAR(20),
    Order_Status VARCHAR(20),
    Remarks VARCHAR(200)
);
```
- If you want to add some product in Product Table use this query
```
INSERT INTO product (Product_ID, Product_Type, Product_Name, Product_Price) VALUES (1, 'Italian Style Coffee', 'Irish Coffee', 99), (2, 'Italian Style Coffee', 'Cappuccino', 69), (3, 'Italian Style Coffee', 'Espresso', 49), (4, 'Indian Style Coffee', 'Plain Coffee', 40), (5, 'Indian Style Coffee', 'Chocolate Coffee', 50), (6, 'Indian Style Coffee', 'Cold Coffee', 50), (7, 'Mocktails', 'Watermelon', 79), (8, 'Mocktails', 'Green Apple', 79), (9, 'Mocktails', 'Orange Mojito Mint', 79), (10, 'Cold Drinks', 'Red Bull Energy Drink', 99), (11, 'Cold Drinks', 'Coke, Sprite, Fanta 750ml', 40), (12, 'Cold Drinks', 'Coke, Sprite, Fanta 250ml', 20), (13, 'Cold Drinks', 'Water Bottle 1 Ltr', 20), (14, 'Cold Drinks', 'Water Bottle 500ml', 10), (15, 'Ice-cream', 'Vanilla', 25), (16, 'Ice-cream', 'Belgian Chocolate', 45), (17, 'Ice-cream', 'American Nuts', 40), (18, 'Indian Style Coffee', 'Tea', 20), (19, 'Indian Style Coffee', 'Special Tea', 30);
```

#### 5. Clone the Project Repository:

Clone the Cafe Management System project repository from GitHub (if available) or download the source code files:

```
git clone <repository_url>
```
#### 6. Configure Database Connection:

Open the Python script file (e.g., cafe_management_system.py) and locate the database connection settings. Update the following parameters according to your MySQL Server configuration:

- **host:** Hostname or IP address of your MySQL Server.
- **user:** MySQL username.
- **password:** MySQL password.
- **database:** Name of the database you created for the Cafe Management System (e.g., cafe_management_system).

```
mydb = connect(
    host="your_host",
    user="your_user",
    password="your_password",
    database="your_database"
)
```
#### 7. Run the Application:

Navigate to the project directory containing the Python script file (cafe_management_system.py) using the terminal or command prompt. Then, execute the following command to run the application:

```
python cafe_management_system.py
```
#### 8. Follow On-Screen Instructions:

Once the application is running, you'll be presented with a menu with different options. Follow the on-screen instructions to navigate through the application, add customers, products, etc.

#### Additional Notes:
With these installation steps, you should be able to set up and run the Cafe Management System project on your system. If you encounter any issues during the installation or execution process, feel free to ask for further assistance!

### Usage

- Upon running the application, you will be presented with a menu-driven interface.
- Use the menu options to navigate through different functionalities such as customer management, product management, and order management.
- Follow the on-screen instructions to perform various tasks such as adding customers, updating products, placing orders, and exporting data.
- Make sure your MySQL Server is running while using the application to ensure database connectivity.
## Contributing

Contributions to the Cafe Management System project are welcome! If you find any issues or have suggestions for improvements, feel free to open an issue or submit a pull request on GitHub.

## Acknowledgements

- This project was inspired by the need for a robust and user-friendly solution to manage cafe operations efficiently.
- We would like to thank the open-source community for their valuable contributions to the libraries and tools used in this project.
## 🔗 Links
[![portfolio](https://img.shields.io/badge/my_portfolio-000?style=for-the-badge&logo=ko-fi&logoColor=white)](https://sumankr07.github.io/my_portfolio/)
[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/sumankr07/)

