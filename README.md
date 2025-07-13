students = []

def add_student():
    roll = input("Enter Roll Number: ")
    name = input("Enter Name: ")
    course = input("Enter Course: ")
    marks = float(input("Enter Marks: "))
    
    student = {
        "Roll": roll,
        "Name": name,
        "Course": course,
        "Marks": marks
    }
    students.append(student)
    print("✅ Student added successfully!\n")

def view_students():
    if not students:
        print("No students found.\n")
        return
    print("\n--- All Students ---")
    for s in students:
        print(f"Roll: {s['Roll']}, Name: {s['Name']}, Course: {s['Course']}, Marks: {s['Marks']}")
    print()

def search_student():
    roll = input("Enter Roll Number to Search: ")
    found = False
    for s in students:
        if s['Roll'] == roll:
            print(f"\nStudent Found:\nName: {s['Name']}, Course: {s['Course']}, Marks: {s['Marks']}\n")
            found = True
            break
    if not found:
        print("❌ Student not found!\n")

def menu():
    while True:
        print("----- Student Management System -----")
        print("1. Add Student")
        print("2. View All Students")
        print("3. Search Student by Roll Number")
        print("4. Exit")
        choice = input("Enter your choice: ")

        if choice == '1':
            add_student()
        elif choice == '2':
            view_students()
        elif choice == '3':
            search_student()
        elif choice == '4':
            print("Exiting program. Bye!")
            break
        else:
            print("Invalid choice. Try again.\n")

# Run the menu
menu()
