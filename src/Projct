# Library Management System using OOP

# -----------------------
# Class: Book
# -----------------------
class Book:
    def __init__(self, book_name, author):
        self.book_name = book_name
        self.author = author
        self.is_borrowed = False  # attribute to check if book is borrowed

    def borrow(self):
        if not self.is_borrowed:
            self.is_borrowed = True
            print(f"{self.book_name} has been borrowed.")
        else:
            print(f"{self.book_name} is already borrowed.")

    def return_book(self):
        self.is_borrowed = False
        print(f"{self.book_name} has been returned.")


# -----------------------
# Class: Member (Parent)
# -----------------------
class Member:
    def __init__(self, name, contact):
        self.name = name
        self.__contact = contact   # encapsulated private attribute

    # Getter
    def get_contact(self):
        return self.__contact   # # Read value 

    # Setter
    def set_contact(self, new_contact):
        self.__contact = new_contact    # Write value 

    # Polymorphic Method 

    # (polymorphism: the same method name (calculate_fine) behaves differently depending on the object type)
    def calculate_fine(self, days):
        return days * 0.0   # base Member has no fine


# -----------------------
# Child Class: TeacherMember
# -----------------------
class TeacherMember(Member):
    def calculate_fine(self, days):
        return days * 0.2   # fine for teacher


# -----------------------
# Child Class: StudentMember
# -----------------------
class StudentMember(TeacherMember):  # Inherits from TeacherMember
    def calculate_fine(self, days):
        return days * 0.5   # fine for student


# -----------------------
# Class: Library
# -----------------------
class Library:
    def __init__(self):
        self.books = []
        self.members = []

    def add_book(self, book):
        self.books.append(book)

    def add_member(self, member):
        self.members.append(member)

    def show_books(self):
        for book in self.books:
            status = "Borrowed" if book.is_borrowed else "Available"
            print(f"{book.book_name} by {book.author} - {status}")

    def show_members(self):
        for member in self.members:
            print(f"Member: {member.name}, Contact: {member.get_contact()}")
            


# -----------------------
# Example Usage
# -----------------------
# Create Books
book1 = Book("Python Basics", "EN.Omyma")
book2 = Book("Programming Basics", "Ahmed Omar")

# Create Members
student1 = StudentMember("Tota", "010125236")
teacher1 = TeacherMember("Dr. Omar", "01225784256344")

# Create Library and add books + members
lib = Library()
lib.add_book(book1)
lib.add_book(book2)
lib.add_member(student1)
lib.add_member(teacher1)

# Borrow a book
book1.borrow()

# Show library books and members
lib.show_books()
lib.show_members()

# Calculate fines
print(f"{student1.name}'s fine for 4 days: {student1.calculate_fine(4)}")
print(f"{teacher1.name}'s fine for 4 days: {teacher1.calculate_fine(4)}")




