# final-project

import tkinter as tk
from tkinter import *
from tkinter import messagebox
from tkinter import ttk
from tkinter import filedialog
import csv
import matplotlib.pyplot as plt
import pandas as pd

turn = 1 #מגדיר של מי התור
counter = 1 #ממספר את התור עד ל10
scoreplayer1 = 0
scoreplayer2 = 0

list = []
for i in range(18, 50):
    list.append(i)


# game code
def tictactoe():
    window = Tk()
    window.config(bg="#49A")
    window.geometry("700x300")
    window.title("                                            Shenkar championship tic-tac-toe ")

    lbl = Label(window, text=p1.get() + ": X", bg="#49A", fg="white", font=('DAVID 18 bold'))
    lbl.grid(row=1, column=0)
    lbl = Label(window, text=p2.get() + ": O", bg="#49A", fg="white", font=('DAVID 18 bold'))
    lbl.grid(row=2, column=0)
    lbl = Label(window, text="                                              ", bg="#49A", fg="white",
                font=('DAVID 10 bold'))
    lbl.grid(column=1)

    def push1(): #נקבל טקסט של הכפתור
        global turn
        if btn1["text"] == " ":
            if turn == 1:
                turn = 2
                btn1["text"] = "X"
            elif turn == 2:
                turn = 1
                btn1["text"] = "O"
            check()

    def push2():
        global turn
        if btn2["text"] == " ":
            if turn == 1:
                turn = 2
                btn2["text"] = "X"
            elif turn == 2:
                turn = 1
                btn2["text"] = "O"
            check()

    def push3():
        global turn
        if btn3["text"] == " ":
            if turn == 1:
                turn = 2
                btn3["text"] = "X"
            elif turn == 2:
                turn = 1
                btn3["text"] = "O"
            check()

    def push4():
        global turn
        if btn4["text"] == " ":
            if turn == 1:
                turn = 2
                btn4["text"] = "X"
            elif turn == 2:
                turn = 1
                btn4["text"] = "O"
            check()

    def push5():
        global turn
        if btn5["text"] == " ":
            if turn == 1:
                turn = 2
                btn5["text"] = "X"
            elif turn == 2:
                turn = 1
                btn5["text"] = "O"
            check()

    def push6():
        global turn
        if btn6["text"] == " ":
            if turn == 1:
                turn = 2
                btn6["text"] = "X"
            elif turn == 2:
                turn = 1
                btn6["text"] = "O"
            check()

    def push7():
        global turn
        if btn7["text"] == " ":
            if turn == 1:
                turn = 2
                btn7["text"] = "X"
            elif turn == 2:
                turn = 1
                btn7["text"] = "O"
            check()

    def push8():
        global turn
        if btn8["text"] == " ":
            if turn == 1:
                turn = 2
                btn8["text"] = "X"
            elif turn == 2:
                turn = 1
                btn8["text"] = "O"
            check()

    def push9():
        global turn
        if btn9["text"] == " ":
            if turn == 1:
                turn = 2
                btn9["text"] = "X"
            elif turn == 2:
                turn = 1
                btn9["text"] = "O"
            check()

    def check(): #בודק האם המשחק הוכרע
        global counter
        b1 = btn1["text"]
        b2 = btn2["text"]
        b3 = btn3["text"]
        b4 = btn4["text"]
        b5 = btn5["text"]
        b6 = btn6["text"]
        b7 = btn7["text"]
        b8 = btn8["text"]
        b9 = btn9["text"]
        counter = counter + 1
        if b1 == b2 and b1 == b3 and b1 == "O" or b1 == b2 and b1 == b3 and b1 == "X":
            win(btn1["text"])
        if b4 == b5 and b4 == b6 and b4 == "O" or b4 == b5 and b4 == b6 and b4 == "X":
            win(btn4["text"])
        if b7 == b8 and b7 == b9 and b7 == "O" or b7 == b8 and b7 == b9 and b7 == "X":
            win(btn7["text"])
        if b1 == b4 and b1 == b7 and b1 == "O" or b1 == b4 and b1 == b7 and b1 == "X":
            win(btn1["text"])
        if b2 == b5 and b2 == b8 and b2 == "O" or b2 == b5 and b2 == b8 and b2 == "X":
            win(btn2["text"])
        if b3 == b6 and b3 == b9 and b3 == "O" or b3 == b6 and b3 == b9 and b3 == "X":
            win(btn3["text"])
        if b1 == b5 and b1 == b9 and b1 == "O" or b1 == b5 and b1 == b9 and b1 == "X":
            win(btn1["text"])
        if b7 == b5 and b7 == b3 and b7 == "O" or b7 == b5 and b7 == b3 and b7 == "X":
            win(btn7["text"])
        if counter == 10:
            window.destroy()
            messagebox.showinfo("Tie", "I'ts a tie, game over ")
            file()
            lastpage()

    def win(player):
        window.destroy()
        if player == "X":
            ans = "we got a winner, " + p1.get() + " won"
        else:
            ans = "we got a winner, " + p2.get() + " won"
        messagebox.showinfo("Game over!", ans)
        global scoreplayer1
        global scoreplayer2
        if player == "X":
            scoreplayer1 = 1
            scoreplayer2 = 0
        elif player == "O":
            scoreplayer1 = 0
            scoreplayer2 = 1

        file()
        lastpage()

    btn1 = Button(window, text=" ", bg="white", fg="black", borderwidth=4, width=4, height=2, font=('david', '22'),
                  command=push1)
    btn1.grid(column=2, row=1)
    btn2 = Button(window, text=" ", bg="white", fg="black", borderwidth=4, width=4, height=2, font=('david', '22'),
                  command=push2)
    btn2.grid(column=3, row=1)
    btn3 = Button(window, text=" ", bg="white", fg="black", borderwidth=4, width=4, height=2, font=('david', '22'),
                  command=push3)
    btn3.grid(column=4, row=1)
    btn4 = Button(window, text=" ", bg="white", fg="black", borderwidth=4, width=4, height=2, font=('david', '22'),
                  command=push4)
    btn4.grid(column=2, row=2)
    btn5 = Button(window, text=" ", bg="white", fg="black", borderwidth=4, width=4, height=2, font=('david', '22'),
                  command=push5)
    btn5.grid(column=3, row=2)
    btn6 = Button(window, text=" ", bg="white", fg="black", borderwidth=4, width=4, height=2, font=('david', '22'),
                  command=push6)
    btn6.grid(column=4, row=2)
    btn7 = Button(window, text=" ", bg="white", fg="black", borderwidth=4, width=4, height=2, font=('david', '22'),
                  command=push7)
    btn7.grid(column=2, row=3)
    btn8 = Button(window, text=" ", bg="white", fg="black", borderwidth=4, width=4, height=2, font=('david', '22'),
                  command=push8)
    btn8.grid(column=3, row=3)
    btn9 = Button(window, text=" ", bg="white", fg="black", borderwidth=4, width=4, height=2, font=('david', '22'),
                  command=push9)
    btn9.grid(column=4, row=3)

    # file code
    def file():
        with open('Shenkar-TTT.csv', 'a', newline='') as file:
            writer = csv.writer(file)
            num_rows = 0
            for row in open("Shenkar-TTT.csv"):
                num_rows += 1
            if num_rows == 0:
                writer.writerow(["Player Name", "Age", "Gender", "Departmnet", "Points"])

            writer.writerow([p1.get(), a1.get(), gender1.get(), dp1.get(), scoreplayer1])
            writer.writerow([p2.get(), a2.get(), gender2.get(), dp2.get(), scoreplayer2])

    window.mainloop()


def Scoreoaed_table():
    fig, ax = plt.subplots() #טבלה שיודעת לקבל מס' פלוטים ולהוציא לטבלה מסודרת
    # hide axes
    ax.set_title('Championship scoreboard', color='black', pad=10)
    # plt.suptitle('Championship scoreboard')
    fig.patch.set_visible(False)
    ax.axis('off')
    ax.axis('tight')
    df = pd.read_csv('Shenkar-TTT.csv')
    df2 = df.groupby(['Departmnet']).sum().sort_values('Points', ascending=False)
    df2 = df2.drop('Gender', axis=1)
    df2 = df2.drop('Age', axis=1)
    ax.table(cellText=df2.values, rowColours=["lightblue"] * 11,
             colColours=["lightblue"] * 11, loc='upper center',
             colLabels=df2.columns, rowLabels=df2.index, cellLoc="center", colWidths=([0.12, 0.12]))
    fig.tight_layout()
    plt.show()


def plot_by_dep():
    df = pd.read_csv('Shenkar-TTT.csv')
    df2 = df.groupby(['Departmnet']).sum()
    df2 = df2.drop('Gender', axis=1)
    df2 = df2.drop('Age', axis=1)
    plt.style.use('fast')
    df2.plot(kind='bar',title='amount of wins by department')
    plt.xticks(rotation=30, size=8)
    plt.grid(True, linestyle='solid', linewidth=0.4)
    plt.show()


def plot_by_gen():
    df = pd.read_csv('Shenkar-TTT.csv')
    df.loc[df['Gender'] == 1, 'Gender'] = 'Female'
    df.loc[df['Gender'] == 2, 'Gender'] = 'Male'
    df3 = df.groupby(['Gender']).mean()
    df3 = df3.drop('Age', axis=1)
    plt.style.use('fast')
    df3.plot(kind='bar', figsize=(9, 3.5), width=0.2, title='distribution by percentage of wins by gender')
    plt.grid(True, linestyle='solid', linewidth=0.4)
    plt.xticks(rotation=30, size=8)
    plt.show()


def plot_by_age():
    df = pd.read_csv('Shenkar-TTT.csv')
    df.loc[df['Gender'] == 1, 'Gender'] = 'Female'
    df.loc[df['Gender'] == 2, 'Gender'] = 'Male'
    df2 = df.groupby(['Age']).sum()
    plt.style.use('fast')
    df2.plot(kind='line', figsize=(14, 4), title='distribution by age')
    plt.ylabel("Number of wins")
    plt.title("Distribution of victories by age")
    plt.grid(True, linestyle='solid', linewidth=0.4)
    plt.show()


def convertToExcel():
    df = pd.read_csv('Shenkar-TTT.csv')
    df.loc[df['Gender'] == 1, 'Gender'] = 'Female'
    df.loc[df['Gender'] == 2, 'Gender'] = 'Male'
    df.loc[df['Points'] == 1, 'Points'] = 'Won'
    df.loc[df['Points'] == 0, 'Points'] = 'Did not win'
    export_file_path = filedialog.asksaveasfilename(defaultextension='.xlsx')
    df.to_excel(export_file_path, index=None, header=True)


# last page
def lastpage():
    global turn
    global counter
    global scoreplayer1
    global scoreplayer2
    turn = 1
    counter = 1
    scoreplayer1 = 0
    scoreplayer2 = 0

    def quit1():
        last.destroy()

    def playagain():
        quit1()
        registration()

    last = Tk()
    last.config(bg="#49A")
    last.title("Shenkar championship tic-tac-toe ")
    lbl = Label(last, text="Scoreboard and statistical distributions", fg='white', bg="#49A",
                font=('DAVID 13 bold underline'))
    lbl.grid(row=0, column=3)
    lbl = Label(last, text=" ", bg="#49A", fg="white", font=('DAVID 10 bold')).grid(row=1, column=3)
    bt1 = tk.Button(last, text='Scoreboard', bg='dark grey', fg='white', command=Scoreoaed_table).grid(row=2, column=3)
    lbl = Label(last, text=" ", bg="#49A", fg="white", font=('DAVID 10 bold')).grid(row=3, column=3)
    bt2 = tk.Button(last, text='Amount of wins by department', bg='dark grey', fg='white', command=plot_by_dep).grid(
        row=4, column=3)
    lbl = Label(last, text=" ", bg="#49A", fg="white", font=('DAVID 10 bold')).grid(row=5, column=3)
    bt3 = tk.Button(last, text='Distribution of victories by age', bg='dark grey', fg='white',
                    command=plot_by_age).grid(row=6, column=3)
    lbl = Label(last, text=" ", bg="#49A", fg="white", font=('DAVID 10 bold')).grid(row=7, column=3)
    bt4 = tk.Button(last, text='Distribution by percentage of wins by gender', bg='dark grey', fg='white',
                    command=plot_by_gen).grid(row=8, column=3)
    lbl = Label(last, text=" ", bg="#49A", fg="white", font=('DAVID 10 bold')).grid(row=9, column=3)
    bt5 = tk.Button(last, text='Play again', bg='green', fg='white', command=playagain, ).grid(row=10, column=2)
    bt6 = tk.Button(last, text='Exit game', bg='red', fg='white', command=quit1).grid(row=10, column=4)
    lbl = Label(last, text=" ", bg="#49A", fg="white", font=('DAVID 10 bold')).grid(row=12, column=3)
    lbl = Label(last, text=" ", bg="#49A", fg="white", font=('DAVID 10 bold')).grid(row=13, column=3)
    bt7 = tk.Button(last, text='Export To Excel', bg='dark grey', fg='white', command=convertToExcel).grid(row=14,
                                                                                                            column=3)


# registration code
def registration():
    global gender1
    global gender2
    global p1
    global p2
    global g1
    global g2
    global a1
    global a2
    global dp1
    global dp2
    root = Tk()
    gender1 = tk.StringVar(root)
    gender2 = tk.StringVar(root)

    # func that check if the registraion is fill up correctly
    def startgame():
        Letter_char = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's',
                       't', 'u', 'v', 'w', 'x', 'y', 'z', ' ']
        g1 = gender1.get()
        g2 = gender2.get()
        if len(p1.get()) != 0 and len(p2.get()) != 0:
            if len(p1.get()) < 15 and len(p2.get()) < 15:
                pp1 = p1.get().replace(" ", "").isalpha()
                pp2 = p2.get().replace(" ", "").isalpha()
                if pp1 and pp2:
                    if g1 == "1" or g1 == "2" and g2 == "1" or g2 == "2":
                        if dp1.get() != dp2.get():
                            root.withdraw()
                            tictactoe()
        messagebox.showinfo("Fill",
                            "You didn't fill everything out correctly, please check: \n1)Did You filled every part? \n2)Name can't be longer then 15 and only letters.\n3)You can't play against student from the same department. ")

    root.title("                                                                    SHENKAR TIC-TAC-TOE CHAMPIONSHIP")

    root.geometry("700x400")
    root.config(bg="#49A")

    lbl = Label(root, text="SHENKAR TIC-TAC-TOE CHAMPIONSHIP - SIGN UP", fg="alice blue", bg="#49A",
                font=('DAVID 13 bold underline'))
    lbl.grid(row=0, column=1)
    tk.Label(root, text="", bg="#49A").grid(row=1, column=0)
    tk.Label(root, text="Player 1", fg="alice blue", bg="#49A",
             font=('DAVID 12 bold underline')).grid(row=2, column=1)
    tk.Label(root, text="", bg="#49A").grid(row=3, column=0)

    tk.Label(root, text="Please Enter Student Name", fg="white", bg="#49A").grid(row=4, column=0)
    p1 = tk.Entry(root)
    p1.grid(row=4, column=1)

    tk.Label(root, text="Please Enter Student age", fg="white", bg="#49A").grid(row=5, column=0)
    a1 = ttk.Combobox(root, values=list, state="readonly")
    a1.current(0)
    a1.grid(row=5, column=1)

    tk.Label(root, text="Gender?", fg="white", bg="#49A").grid(row=6, column=0)
    rad1 = Radiobutton(root, text='Female', bg="#49A", value=1, variable=gender1).grid(row=6, column=1)
    rad2 = Radiobutton(root, text='Male', bg="#49A", value=2, variable=gender1).grid(row=6, column=2)

    tk.Label(root, text="Choose department:", fg="white", bg="#49A").grid(row=7, column=0)
    dp1 = ttk.Combobox(root, state="readonly")
    dp1['values'] = ("Fashion Design", "Industrial Design", "Jewelry Design", "Electrical Engineering","Software Engineering", "Industrial Engineering")
    dp1.current(0)
    dp1.grid(row=7, column=1)
    tk.Label(root, text="", bg="#49A").grid(row=8, column=0)
    tk.Label(root, text="Player 2", fg="alice blue", bg="#49A",
             font=('DAVID 12  bold underline')).grid(row=9, column=1)
    tk.Label(root, text="                                              ", bg="#49A", fg="white",
             font=('DAVID 10 bold')).grid(row=10, column=3)
    tk.Label(root, text="Please Enter second Student name", fg="white", bg="#49A").grid(row=11, column=0)
    p2 = tk.Entry(root)
    p2.grid(row=11, column=1)

    tk.Label(root, text="Please Enter second Student age", fg="white", bg="#49A").grid(row=12, column=0)
    a2 = ttk.Combobox(root, values=list, state="readonly")
    a2.current(0)
    a2.grid(row=12, column=1)

    tk.Label(root, text="Gender?", fg="white", bg="#49A").grid(row=13, column=0)
    rad3 = Radiobutton(root, text='Female', bg="#49A", value=1, variable=gender2).grid(row=13, column=1)
    rad4 = Radiobutton(root, text='Male', bg="#49A", value=2, variable=gender2).grid(row=13, column=2)

    tk.Label(root, text="Choose department:", fg="white", bg="#49A").grid(row=14, column=0)
    dp2 = ttk.Combobox(root, state="readonly")
    dp2['values'] = ("Fashion Design", "Industrial Design", "Jewelry Design", "Electrical Engineering","Software Engineering", "Industrial Engineering")
    dp2.current(0)
    dp2.grid(row=14, column=1)
    tk.Label(root, text="", bg="#49A").grid(row=15, column=0)
    bt = tk.Button(root, text='Start Game!', bg="green", fg="white", command=startgame).grid(row=16, column=1)

    root.mainloop()


registration()
