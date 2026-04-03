 

# 📌 Project: To-Do List CLI Application

A simple command-line To-Do List app that helps users:

* Add tasks
* View tasks
* Delete tasks
* Mark tasks as completed

---

# 💻 `main.py`

```python id="tdl001"
# To-Do List CLI Application

tasks = []

def show_tasks():
    if not tasks:
        print("\nNo tasks found!\n")
        return

    print("\nYour Tasks:")
    for i, task in enumerate(tasks, start=1):
        status = "✔" if task["done"] else "❌"
        print(f"{i}. {task['name']} [{status}]")
    print()

def add_task():
    task_name = input("Enter task: ")
    tasks.append({"name": task_name, "done": False})
    print("Task added successfully!\n")

def delete_task():
    show_tasks()
    try:
        index = int(input("Enter task number to delete: "))
        if 1 <= index <= len(tasks):
            removed = tasks.pop(index - 1)
            print(f"Deleted task: {removed['name']}\n")
        else:
            print("Invalid task number!\n")
    except ValueError:
        print("Please enter a valid number!\n")

def mark_done():
    show_tasks()
    try:
        index = int(input("Enter task number to mark as done: "))
        if 1 <= index <= len(tasks):
            tasks[index - 1]["done"] = True
            print("Task marked as completed!\n")
        else:
            print("Invalid task number!\n")
    except ValueError:
        print("Please enter a valid number!\n")

def menu():
    while True:
        print("===== TO-DO LIST APP =====")
        print("1. View Tasks")
        print("2. Add Task")
        print("3. Delete Task")
        print("4. Mark Task as Done")
        print("5. Exit")

        choice = input("Enter choice: ")

        if choice == "1":
            show_tasks()
        elif choice == "2":
            add_task()
        elif choice == "3":
            delete_task()
        elif choice == "4":
            mark_done()
        elif choice == "5":
            print("Goodbye!")
            break
        else:
            print("Invalid choice!\n")

menu()
```

---

# 📄 `README.md`

```markdown id="tdl002"
# 📝 To-Do List CLI Application

## 📌 Overview
This is a simple **Python command-line To-Do List application** that helps users manage daily tasks efficiently. Users can add, view, delete, and mark tasks as completed.

---

## 🚀 Features
- Add new tasks  
- View all tasks  
- Delete tasks by number  
- Mark tasks as completed  
- Simple and interactive CLI menu  

---

## 🛠️ Technologies Used
- Python 3.x  

---

## 📂 Project Structure
```

to-do-list/
│
├── main.py       # Main application file
└── README.md     # Documentation

````

---

## ▶️ How to Run

### 1. Download or Clone the project
```bash
git clone https://github.com/your-username/to-do-list.git
````

### 2. Go to project folder

```bash
cd to-do-list
```

### 3. Run the program

```bash
python main.py
```

---

## 💡 Example Usage

```
===== TO-DO LIST APP =====
1. View Tasks
2. Add Task
3. Delete Task
4. Mark Task as Done
5. Exit
```

---

## 🧠 Concepts Used

* Lists
* Dictionaries
* Functions
* Loops
* Conditionals
* Exception Handling

---

## 📈 Future Improvements

* Save tasks to a file (JSON/CSV)
* Add due dates
* Add priority levels
* GUI version using Tkinter
* Task search feature

---
 
