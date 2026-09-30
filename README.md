# Book-managment-system
Library Management System My python projects Library Management System A lightweight, Command Line Interface (CLI) Library Management System built with Python. This application allows librarians or administrators to manage book inventories, track issued books, and view system statistics without the need for a complex database setup, utilizing a local JSON file for persistent data storage.

Features Add Books: Add new books to the inventory with a unique ID, title, author, and category.

View All Books: Display a complete list of all books currently in the library system.

Search Books: Find specific books using keywords matching the title or author.

Issue Books: Assign available books to students and update their status to "Issued".

Return Books: Process returned books and update their status back to "Available".

Delete Books: Remove books from the system (prevents deletion if the book is currently issued).

View Issued Books: Display a filtered list of all books currently checked out by students.

Library Statistics: Generate a quick dashboard showing the total number of books, available books, and issued books.

Persistent Storage: All data is automatically saved to a library.json file, ensuring no data is lost between sessions.

Prerequisites Python 3.x installed on your machine.

Standard Python libraries (only json and os are required, which come pre-installed).

Installation and Usage Download the Script: Save the provided Python code as library_management.py.

Run the Script: Open your terminal or command prompt and execute the following command:

Bash python library_management.py First Run: The script will automatically create a library.json file in the same directory to store the library data.

Navigation: Use the number keys (1-9) to navigate the interactive menu and perform library operations.

Data Structure The data is stored in library.json as a list of dictionary objects. Each book follows this schema:

JSON { "id": "101", "title": "The Great Gatsby", "author": "F. Scott Fitzgerald", "category": "Fiction", "status": "Available", "issued_to": "" }
