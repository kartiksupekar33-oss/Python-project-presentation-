# Python-project-presentation-
Student Mark Management System

class Student: def init(self, roll_no, name): self.roll_no = roll_no self.name = name self.marks = {}

def add_mark(self, subject, mark):
    self.marks[subject] = mark

def get_total(self):
    return sum(self.marks.values())

def get_percentage(self):
    if self.marks:
        return self.get_total() / len(self.marks)
    return 0

def display(self):
    print(f"\nRoll No: {self.roll_no}")
    print(f"Name: {self.name}")
    print("Marks:")
    for subject, mark in self.marks.items():
        print(f"  {subject}: {mark}")
    print(f"Total: {self.get_total()}")
    print(f"Percentage: {self.get_percentage():.2f}%")

class StudentManagementSystem: def init(self): self.students = {}

def add_student(self, roll_no, name):
    if roll_no in self.students:
        print("Student already exists!")
        return
    self.students[roll_no] = Student(roll_no, name)
    print("Student added successfully!")

def add_mark(self, roll_no, subject, mark):
    if roll_no not in self.students:
        print("Student not found!")
        return
    self.students[roll_no].add_mark(subject, mark)
    print("Mark added successfully!")

def display_student(self, roll_no):
    if roll_no not in self.students:
        print("Student not found!")
        return
    self.students[roll_no].display()

def display_all_students(self):
    if not self.students:
        print("No students available!")
        return
    for student in self.students.values():
        student.display()

def main(): sms = StudentManagementSystem()

while True:
    print("\n===== Student Mark Management System =====")
    print("1. Add Student")
    print("2. Add Mark")
    print("3. Display Student")
    print("4. Display All Students")
    print("5. Exit")

    choice = input("Enter your choice: ")

    if choice == "1":
        roll = input("Enter roll number: ")
        name = input("Enter name: ")
        sms.add_student(roll, name)

    elif choice == "2":
        roll = input("Enter roll number: ")
        subject = input("Enter subject: ")
        mark = int(input("Enter mark: "))
        sms.add_mark(roll, subject, mark)

    elif choice == "3":
        roll = input("Enter roll number: ")
        sms.display_student(roll)

    elif choice == "4":
        sms.display_all_students()

    elif choice == "5":
        print("Exiting...")
        break

    else:
        print("Invalid choice! Please try again.")

if name == "main": main()
