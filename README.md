# calculator-
import tkinter as tk 
-Logic- 
expression 
= 
|||| 
def press(val): 
global expression 
if val == =": 
try: 
result = str(eval(expression)) 
display.config(text=result) 
expression = result 
except: 
display.config(text="Error") 
expression 
= 
elif val == "C": 
expression 
= 
|||| 
display.config(text="0") 
elif val == "<": 
expression = expression[:-1] 
display.config(text=expression if expression else 
"0") 
else: 
expression += str(val) 
display.config(text=expression) 
-Window - 
root = tk.Tk() 
root.title("Calculator") 
root.resizable(False, False) root.configure(bg="#f0f0f0") 
-Display- 
display = tk.Label( 
root, 
text="0", 
anchor="e", 
font=("Courier", 28), 
bg="white", 
fg="#222", relief="flat", 
bd=0, 
) 
padx=12, 
pady=16, 
width=14 
display.grid(row=0, column=0, columnspan=4, padx=12, pady=(12, 4), sticky="ew") 
Button layout — 
buttons = 
["C", "", "%", "/"], 
["7", "8", "9", "*"], 
["4", "5", "6", "-"], 
] 
["1", "2", "3", "+"], 
["O", ".", "", "="], 
for r, row in enumerate(buttons): 
for c, label in enumerate(row): 
if label 
== 
continue # skip empty cell 
is_op = label in ("+", "-", "*", "/", "%", "=", "C", "") bg = "#d6d6d6" if is_op else "white" 
fg = "#c0392b" if label == "=" else "#333" if label in ("C", ""): 
fg = "#555" 
span = 2 if label == "0" else 1 
btn = tk.Button( 
root, 
text=label, 
font=("Courier", 18), 
bg=bg, 
fg=fg, 
activebackground="#bbb" if is_op else "#e8e8e8", 
relief="flat", 
bd=0, 
cursor="hand2", 
) 
command-lambda v=label: press(v) 
btn.grid( 
row=r + 1, 
column=c, 
columnspan=span, 
padx=5, 
pady=5, 
ipadx=10, 
ipady=12, 
sticky="new" 
) 
Make grid responsive 
for i in range(5): 
root.grid_columnconfigure(i, weight=1) 
root.mainloop() 
