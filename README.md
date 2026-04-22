# Library Management System

A cyber-minimalist console application developed in Java for managing library book inventories. The system utilizes object-oriented principles to execute book entity tracking, user input validation, and transaction state management.

## Features

* **Dynamic Inventory Tracking:** Custom array resizing logic (`ensureCapacity`) for unbound book entity allocation.
* **Input Validation:** Strict regex-based parsing (`^[1-9]\d*$`) for operational integrity and error prevention.
* **Formatted Output:** Integrates `text-table-formatter-1.2.4` for structured, tabular data rendering within the terminal interface.
* **Timezone-Aware Initialization:** Generates system setup timestamps localized to the `Asia/Phnom_Penh` zone.
* **Transaction Management:** Boolean state toggles restricting duplicate borrow/return actions.

## Tech Stack

* **Language:** Java 21
* **Dependencies:** `text-table-formatter-1.2.4.jar`
* **Paradigm:** Object-Oriented Programming (OOP)

## Setup and Execution

1.  Clone the repository:
    ```bash
    git clone [https://github.com/SRUN-Sochettra/Library-Management.git](https://github.com/SRUN-Sochettra/Library-Management.git)
    ```
2.  Navigate to the source directory:
    ```bash
    cd Library-Management/src
    ```
3.  Compile the source files, linking the external formatting dependency:
    ```bash
    javac -cp ".:../lib/text-table-formatter-1.2.4.jar" Main.java
    ```
    *(Note: Use `;` instead of `:` for the classpath separator on Windows environments)*
4.  Execute the application:
    ```bash
    java -cp ".:../lib/text-table-formatter-1.2.4.jar" Main
    ```

## Usage Protocol

Upon execution, initialize the library parameters (Name and Address). The system loop provides a 6-node operational interface:
1.  **Add Book:** Requires Title, Author Name, Author Year Active, and Published Year.
2.  **Show All Books:** Renders complete database via console table.
3.  **Show Available Books:** Filters and renders only currently available stock.
4.  **Borrow Book:** Queries database by ID to update availability status.
5.  **Return Book:** Queries database by ID to restore availability status.
6.  **Exit:** Terminates process.

## Author

**Srun Sochettra**
GitHub: [@SRUN-Sochettra](https://github.com/SRUN-Sochettra)
