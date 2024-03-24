# CODSOFT
tasklist=[]
def add_task():
    print("Please fill the below details to add a task.")
    Tasks=input("Enter the task: ")
    Submission_deadline=input("Enter the month: ")
    list1={
        "Task":Tasks,
        "Submission_Deadline":Submission_deadline
    }
    tasklist.append(list1)
    print("Task added successfully.")
    main_menu()
def view_task():
    if not tasklist:
        print("There are no tasks submitted yet.")
    else:
        print("Tasks are:")
        i=1
        for task in tasklist:
            print(i,".")
            for key,value in task.items():
                print(key,":",value)
            i=i+1
    main_menu()
def delete_completed_tasks():
    if not tasklist:
        print("There are no tasks submitted to delete from the list.")
    else:
        print("List of Tasks:")
        i=1
        for task in tasklist:
            print(i,".")
            for key,value in task.items():
                print(key,":",value)
            i=i+1
        n=int(input("enter the task number to mark as done: "))
        if n<0 or n>len(tasklist):
            print("Invalid number.")
        else:
            index=n-1
            del tasklist[index]
            print("Completed task has been successfully removed from the list.")
    main_menu()
def main_menu():
    op=int(input("================\nTo-Do-List Menu...\n1. Add task\n2. View task\n3. Delete_completed_tasks\n"
          "4. exit\nPlease choose a number from the above menu: "))
    if(op==1):
        add_task()
    elif(op==2):
        view_task()
    elif(op==3):
        delete_completed_tasks()
    elif(op==4):
        pass
    else:
        print("You have choosen wrong number...Please choose a valid number.")
        main_menu()
main_menu()
