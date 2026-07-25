# Food Ordering System

A simple desktop Point-of-Sale (POS) application for a fast-food style menu, built in **Java Swing** as a **BlueJ** project. It supports admin login, placing/listing orders, processing cash payments with change calculation, and viewing a sales report — all through a series of dialog-based panels.

## Features

- **Password-protected login** — a fixed admin password gates access to the system (3 attempts allowed before the app exits).
- **Fixed menu** — 15 hardcoded menu items (burgers, fries, sundaes, and drinks) with preset prices.
- **Order Meal** — pick an item by its Meal ID and quantity to add it to the current order.
- **List Orders** — view all items in the current order, the running total, and remove an order by its ID.
- **Process Payment** — enter cash received; change is calculated automatically. Confirming the payment records a sales entry and clears the current order.
- **Sales Report** — view a table of all completed transactions (amount, cash given, change) with a running total.
- **Exit** — cleanly closes the program from the main menu.

## Tech Stack

- **Language:** Java (Swing / AWT for the GUI)
- **IDE / Project format:** [BlueJ](https://www.bluej.org/) (`package.bluej`)
- **UI:** `JOptionPane` dialogs hosting custom `JPanel` forms, Nimbus look-and-feel (falls back to default if unavailable)

## Project Structure

```
Test/
├── OrderingSystem.java      # Main class — login loop, menu loop, and all business logic
├── Meal.java                 # Meal, Password, Order, and SalesReport data classes
├── MenuPanel.java             # Main menu dropdown (Order Meal / List Orders / Process Payment / Sales Report / Exit)
├── OrderMealPanel.java        # Panel for browsing the menu and placing an order
├── OrdersList.java             # Panel listing current orders and removing an order by ID
├── ProcessPaymentPanel.java    # Panel for entering cash and viewing calculated change
├── SalesReportPanel.java       # Panel displaying completed sales transactions
├── PasswordPanel.java          # Login dialog panel
├── package.bluej                # BlueJ project metadata
└── README.TXT                   # Original blank BlueJ template README
```

> Note: `Password`, `Order`, and `SalesReport` are all defined inside `Meal.java` alongside the `Meal` class rather than in their own files.

## Getting Started

### Prerequisites
- Java JDK 8 or later
- (Optional) [BlueJ](https://www.bluej.org/) IDE, since this project includes BlueJ project files

### Run with BlueJ
1. Open BlueJ.
2. **Project → Open...** and select the `Test` folder (contains `package.bluej`).
3. Right-click the `OrderingSystem` class and choose **void main(String[] args)**.

### Run from the command line
```bash
cd Test
javac *.java
java OrderingSystem
```

## Usage

1. **Login** — enter the admin password when prompted.
   - Default password: `admin`
   - You have 3 attempts; the program exits after 3 failed tries.
2. **Main Menu** — choose one of:
   - **Order Meal** — enter a Meal ID (shown in the menu table) and quantity, then confirm to add it to the order.
   - **List Orders** — review current orders and the total amount; enter an Order ID and click the button to remove that order.
   - **Process Payment** — enter the cash received; the change is calculated automatically. Confirm to save the transaction and clear the order.
   - **Sales Report** — view all completed transactions and the total revenue.
   - **Exit Program** — closes the application.

