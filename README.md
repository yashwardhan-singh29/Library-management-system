# Library Management System

This is my first semester python project. It is a library program where you can see all the books, add a new book, issue a book and return a book, and everything is done with a menu.

I made it using only basic python, so there are no functions and no modules in it.

## What it does

- Shows a menu again and again until you choose Exit
- Displays all the books with their ID, title, author and status (Available or Issued)
- You can add a new book, it is always added as Available
- You can issue a book using its ID, and it is marked Issued
- You can return a book using its ID, and it is marked Available again
- If you try to issue a book that is already issued, or return a book that was not issued, it shows a message
- If the book ID is not in the library it says "Book ID not found"
- If you type a wrong number in the menu it shows a message and asks again

## How to run

1. Open the notebook in jupyter (or vscode)
2. Run the cell, it has the list of books and the menu together
3. Type your choice in the box and press enter
4. Choose 5 to exit

If you change the starting books, run the cell again. This also puts the library back to how it was at the start.

## Menu

```
LIBRARY MANAGEMENT SYSTEM
1) Display All Books
2) Add a Book
3) Issue a Book
4) Return a Book
5) Exit
```

1) Display All Books - prints every book with its ID, title, author and status.

2) Add a Book - type the book ID, title and author. The book is added at the end of the list with the status Available.

3) Issue a Book - type the ID of the book. If it is Available it becomes Issued. If it is already Issued a message is shown.

4) Return a Book - type the ID of the book. If it is Issued it becomes Available. If it was not issued a message is shown.

5) Exit - ends the program

## Books at the start

| ID | Title | Author | Status |
| --- | --- | --- | --- |
| 101 | To Kill a Mockingbird | Harper Lee | Available |
| 102 | 1984 | George Orwell | Available |
| 103 | The Great Gatsby | F. Scott Fitzgerald | Issued |

## Example run

```
Enter choice (1-5): 3
Enter Book ID to issue: 101
Issued To Kill a Mockingbird successfully.
Enter choice (1-5): 3
Enter Book ID to issue: 101
To Kill a Mockingbird is already issued.
Enter choice (1-5): 1
LIBRARY BOOKS
ID: 101 | Title: To Kill a Mockingbird | Author: Harper Lee | Status: Issued
ID: 102 | Title: 1984 | Author: George Orwell | Status: Available
ID: 103 | Title: The Great Gatsby | Author: F. Scott Fitzgerald | Status: Issued
```

## What I used

lists (nested lists), while and for loops, if/elif/else, break, input(), int(), str(), append(), f-strings and string joining with +

The whole library is a list, and each book is a small list inside it, like this:

```python
library = [[101, "To Kill a Mockingbird", "Harper Lee", "Available"],
           [102, "1984", "George Orwell", "Available"]]
```

In every book, index 0 is the ID, 1 is the title, 2 is the author and 3 is the status. To issue or return a book, the program goes through the library with a for loop, finds the book with the same ID and changes its status. A variable called found keeps track of whether the ID was there or not.

## Problems / things to add later

- If you type letters instead of a number for the book ID (in options 2, 3 and 4), the program crashes with a ValueError, because int() is used without checking the input first. Only the menu choice is safe from this, because it is compared as text
- The same ID can be added twice, because there is no check for duplicate IDs. Then only the first book with that ID can be issued or returned
- An empty title or author is accepted
- The books are lost if you restart the notebook because nothing is saved in a file
- There is no way to remove a book or search for a book by title
- There is no record of who has taken a book or the due date
- The menu is printed again without a blank line, so the output looks crowded after a few steps
- Can use functions to make the code shorter (issue and return have almost the same code) once we learn them
