import tkinter as tk
from tkinter import messagebox

def add_task():
    task = entry.get()
    if task:
        task_list.insert(tk.END, task)
        entry.delete(0, tk.END)
    else:
        messagebox.showwarning("Warning", "Please enter a task.")

def remove_task():
    selected_task = task_list.curselection()
    if selected_task:
        task_list.delete(selected_task)

def clear_entry(event):
    entry.delete(0, tk.END)

def toggle_complete():
    selected_task = task_list.curselection()
    if selected_task:
        task = task_list.get(selected_task)
        if task.endswith(" [Done]"):
            task_list.delete(selected_task)
        else:
            task_list.delete(selected_task)
            task_list.insert(tk.END, task + " [Done]")

root = tk.Tk()
root.title("Colorful To-Do List")

entry = tk.Entry(root, width=40)
entry.insert(0, "Add a task")
entry.pack(pady=10)
entry.bind("<FocusIn>", clear_entry)

add_button = tk.Button(root, text="Add Task", command=add_task)
add_button.pack()

remove_button = tk.Button(root, text="Remove Task", command=remove_task)
remove_button.pack()

complete_button = tk.Button(root, text="Mark Complete", command=toggle_complete)
complete_button.pack()

task_list = tk.Listbox(root, width=40, selectmode=tk.SINGLE)
task_list.pack()

root.mainloop()
