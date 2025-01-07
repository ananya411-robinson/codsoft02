# codsoft02
#to do list
def displaytask(tasks):#this function is created to display task 
    """Display all tasks."""
    if not tasks:
        print("YOUR TODO LIST IS EMPTY!")
    else:
        print("\nTODO LIST:")
def addtask(tasks):#function used for adding tasks 
    """Add a new task."""
    task = input("ENTER TASK :) : ")
    if task:
        tasks.append(task)#this will auto save task in task 
        print("TASK ADDDED: ",task)
    else:
        print("Task cannot be empty!")#if no tasks are these then it will show this message 

def deletetask(tasks):#used for deleting task 
    """Delete a task by its number."""
    displaytask(tasks)# here exceptional handelling is used 
    try:
        task_num = int(input("Enter the task number to delete: "))
        if 1 <= task_num <= len(tasks):
            removedtask = tasks.pop(task_num - 1)
            print("task removed",removedtask)
        else:
            print("Invalid task number!")
    except ValueError:
        print("Please enter a valid number!")

def main():
    print("**Welcome to the To-Do List **")
    tasks = []

    while True:
        print("\nOptions:")
        print("1. View tasks")
        print("2. Add a task")
        print("3. Delete a task")
        print("4. Exit")

        choice = input("Choose an option (1-4): ")
        if choice == "1":
            displaytask(tasks)
        elif choice == "2":
            addtask(tasks)
        elif choice == "3":
            deletetask(tasks)
        elif choice == "4":
            print("Goodbye will see you again!")
            break
        else:
            print("Invalid choice! Please try again.")

if __name__ == "__main__":
    main()
