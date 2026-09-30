import json
import os
FILE_NAME="library.json"

def create_file():
    if not os.path.exists(FILE_NAME):
        with open(FILE_NAME,"w") as file:
            json.dump([],file)

def load_books():
    with open(FILE_NAME,"r") as file:
        return json.load(file)

def save_books(books):
    with open(FILE_NAME,"w") as file:
        json.dump(books,file,indent=4)

def add_books(books):
    print("========== ADD BOOK ==========")
    book_id=input("Enter Book ID:")

    for book in books:
        if book["id"]==book_id:
            print("Book ID already exists.")
            return

    title=input("Enter Book Title:")
    author=input("Enter Author Name:")
    category=input("Enter Category:")

    book={
        "id":book_id,
        "title":title,
        "author":author,
        "category":category,
        "status":"Available",
        "issued_to":""
    }
    books.append(book)
    save_books(books)
    print("Book added successfully!")

def view_books(books):
    print("========== ALL BOOKS ==========")

    if len(books)==0:
        print("No books available.")
        return
    for book in books:
         print("----------------------------")
         print("Book ID :",book["id"])
         print("Title :",book["title"])
         print("Author :",book["author"])
         print("Category :",book["category"])
         print("Status :",book["status"])

         if book["status"]=="Issued":
            print("Issued To :",book["issued_to"])

def search_book(books):
    print("========== SEARCH BOOK ==========")
    keyword=input("Enter book title or author:").lower()
    found=False
    for book in books:
        if(keyword in book["title"].lower() or
            keyword in book["author"].lower()):

         print("----------------------------")
         print("Book ID :",book["id"])
         print("Title :",book["title"])
         print("Author :",book["author"])
         print("Category :",book["category"])
         print("Status :",book["status"])
         found=True

    if not found:
        print("No matching book found.")

def issue_book(books):
    print("========== ISSUE BOOK ==========")
    book_id=input("Enter Book ID:")
    found=False
    for book in books:
        if book["id"]==book_id:
            if book["status"]=="Issued":
                print("This book is already issued.")
                return
            student_name=input("Enter Student Name:")
            book["status"]="Issued"
            book["issued_to"]=student_name

            save_books(books)
            print("Book issued successfully!")
            print("Book :",book["title"])
            print("Issued To :",student_name)
            return
    print("Book not found.")

def return_book(books):
    print("========== RETURN BOOK ==========")
    book_id=input("Enter Book ID: ")
    for book in books:
        if book["id"]==book_id:
            if book["status"]=="Available":
                print("This book has not been issued.")
                return
            book["status"]="Available"
            book["issued_to"]=""
            save_books(books)

            print("Book returned successfully!")
            return
    print("Book not found.")

def delete_book(books):
     print("========== DELETE BOOK ==========")
     book_id=input("Enter Book ID:")
     for book in books:
         if book["id"]==book_id:
             if book["status"]=="Issued":
                 print("Cannot delete an issued book.")
                 return
             books.remove(book)
             save_books(books)
             print("Book deleted successfully.")
             return
print("Book not found.")

def issued_book(books):
     print("========== ISSUED BOOKS ==========")
     found=False
     for book in books:
         if book["status"]=="Issued":
            print("\n----------------------------")
            print("Book ID :",book["id"])
            print("Title :",book["title"])
            print("Author :",book["author"])
            print("Issued To :",book["issued_to"])

            found=True


            if not found:
                print("No books are currently issued.")

def library_statistics(books):
    print("========== LIBRARY STATISTICS ==========")
    total=len(books)
    available=0
    issued=0
    for book in books:
        if book["status"]=="Available":
            available=available+1
        else:
            issued=issued+1

    print("Total Books :",total)
    print("Available Books :",available)
    print("Issued Books :",issued)

def main():
    create_file()
    books=load_books()
    while True:
        print("\n")
        print("====================================")
        print("       LIBRARY MANAGEMENT SYSTEM")
        print("====================================")
        print("1. Add Book")
        print("2. View All Books")
        print("3. Search Book")
        print("4. Issue Book")
        print("5. Return Book")
        print("6. Delete Book")
        print("7. View Issued Books")
        print("8. Library Statistics")
        print("9. Exit")
        print("====================================")

        choice=input("Enter your choice: ")

        if choice=="1":
            add_books(books)
        elif choice=="2":
            view_books(books)
        elif choice=="3":
            search_book(books)
        elif choice=="4":
            issue_book(books)
        elif choice=="5":
            return_book(books)
        elif choice=="6":
            delete_book(books)
        elif choice=="7":
            issued_book(books)
        elif choice=="8":
            library_statistics(books)
        elif choice=="9":
            print("Thank you for using Library Management System!")
            break
        else:
            print("Invalid choice. Please enter 1-9.")

main()
