MCQ’S APPLICATION PROJECT

Project coding:






from tkinter import *


import tkinter as tk


from tkinter import messagebox



from functools import partial




root = tk.Tk()
root.title('Login')
root.geometry('200x200')
root.configure(background='LightBlue')



def main(value):
    root.destroy()

    main = tk.Tk()
    main.title('Mcqs Application!')
    main.geometry('1000x450')
    main.configure(background='MediumSeaGreen')

    v = tk.IntVar()
    v1 = tk.IntVar()
    v2 = tk.IntVar()
    v3 = tk.IntVar()
    v4 = tk.IntVar()
    v5 = tk.IntVar()
    v6 = tk.IntVar()
    v7 = tk.IntVar()
    v8 = tk.IntVar()

    def result(score,name):
        main.destroy()
        r1 = tk.Tk()
        r1.title('Result')
        r1.geometry('425x200')
        r1.configure(background='#DEBA5D')
        lblHeading = Label(text='------RESULT------',font=("Helvetica", 16),bg='#DEBA5D')
        lblHeading.grid(row=1,column=1,padx=(40,10))
        lbluName = Label(text='User Name:',bg='#DEBA5D',fg='Maroon',font=("Helvetica", 12))
        lbluName.grid(row=2,column=0)
        lblName = Label(text=name, bg='#DEBA5D',font=("Arial", 10))
        lblName.grid(row=2, column=2)
        lbluName = Label(text='Total Marks:', bg='#DEBA5D', fg='Maroon',font=("Helvetica", 12))
        lbluName.grid(row=3, column=0)
        lblName = Label(text='9', bg='#DEBA5D', font=("Arial", 10))
        lblName.grid(row=3, column=2)
        lbluName = Label(text='Your Score:', bg='#DEBA5D', fg='Maroon',font=("Helvetica", 12))
        lbluName.grid(row=4, column=0)
        lblName = Label(text=str(score), bg='#DEBA5D', font=("Arial", 10))
        lblName.grid(row=4, column=2)
        lbluName = Label(text='Percentage:', bg='#DEBA5D', fg='Maroon',font=("Helvetica", 12))
        lbluName.grid(row=5, column=0)

        percentage = (score/9)*100
        status = ""
        color = ""

        lblName = Label(text=str(round(percentage,2)), bg='#DEBA5D', font=("Arial", 10))
        lblName.grid(row=5, column=2)

        if percentage>=50:
            status = "Pass"
            color = "green"
        else:
            status = "Fail"
            color = "red"

        lbluName = Label(text='Status:', bg='#DEBA5D', fg='Maroon',font=("Helvetica", 12))
        lbluName.grid(row=6, column=0)
        lblName = Label(text=status, bg='#DEBA5D', font=("Arial", 10),fg=color)
        lblName.grid(row=6, column=2)

        r1.mainloop()


    questions = {
        "q1": "Which is the hardware part?",
        "q2": "Which type is dot-matrix?",
        "q3": "CPU is an example of ?",
        "q4": "Which one is called as 4 bit combination?",
        "q5": "Which is the best units of data an external storage device?",
        "q6": "Which of the following have the fastest access time ?",
        "q7": "Which of the following is a programming language?",
        "q8": "What kind of number system is often used in a typical 32 bits computer?",
        "q9": "Which of the following is not an output device ?"
    }

    answers = {
        "q1": ["Firmware  oomponents", "Physical components", "Logical components", "all of the above"],
        "q2": ["Printer", "Disk", "Tape", "Bus"],
        "q3": ["Software", "A program", "An output unit", "Hardware"],
        "q4": ["Byte", "Nibble", "Gega Byte", "Mega byte"],
        "q5": ["Bits", "Bytes", "Hertz", "Clock cycle"],
        "q6": ["Semiconductor Memories", "Magnetic disks", "Magnetic tapes", "Compact disks"],
        "q7": ["Lotus", "Pascal", "Ms-Excel", "Netscape"],
        "q8": ["2", "10", "16", "32"],
        "q9": ["Scanner", "Printer", "Flat screen", "Touch screen"]
    }

    correct = {
        "q1": 2,
        "q2": 1,
        "q3": 4,
        "q4": 2,
        "q5": 2,
        "q6": 1,
        "q7": 2,
        "q8": 1,
        "q9": 4
    }

    def click():
        total = 0
        if v.get() == correct['q1']:
            total += 1
        if v1.get() == correct['q2']:
            total += 1
        if v2.get() == correct['q3']:
            total += 1
        if v3.get() == correct['q4']:
            total += 1
        if v4.get() == correct['q5']:
            total += 1
        if v5.get() == correct['q6']:
            total += 1
        if v6.get() == correct['q7']:
            total += 1
        if v7.get() == correct['q8']:
            total += 1
        if v8.get() == correct['q9']:
            total += 1
        return total

    label1 = Label(main, text="MCQS SYSTEM", font=("Helvetica", 16), fg="Black", bg='MediumSeaGreen')
    label1.grid(row=0, column=2)

    label1 = Label(main, text=questions['q1'], bg='MediumSeaGreen')
    label1.grid(row=1, column=1)

    # defines Button 1 and places it using grid
    button1 = Radiobutton(main, text=answers["q1"][0], variable=v, value=1, bg='MediumSeaGreen')
    button1.grid(row=2, column=1)

    button2 = Radiobutton(main, text=answers["q1"][1], variable=v, value=2, bg='MediumSeaGreen')
    button2.grid(row=3, column=1)

    button3 = Radiobutton(main, text=answers["q1"][2], variable=v, value=3, bg='MediumSeaGreen')
    button3.grid(row=4, column=1)

    button4 = Radiobutton(main, text=answers["q1"][3], variable=v, value=4, bg='MediumSeaGreen')
    button4.grid(row=5, column=1)

    label2 = Label(main, text=questions['q2'], bg='MediumSeaGreen')
    label2.grid(row=1, column=2)

    # defines Button 1 and places it using grid
    button12 = Radiobutton(main, text=answers["q2"][0], variable=v1, value=1, bg='MediumSeaGreen')
    button12.grid(row=2, column=2)

    button22 = Radiobutton(main, text=answers["q2"][1], variable=v1, value=2, bg='MediumSeaGreen')
    button22.grid(row=3, column=2)

    button32 = Radiobutton(main, text=answers["q2"][2], variable=v1, value=3, bg='MediumSeaGreen')
    button32.grid(row=4, column=2)

    button42 = Radiobutton(main, text=answers["q2"][3], variable=v1, value=4, bg='MediumSeaGreen')
    button42.grid(row=5, column=2)

    label3 = Label(main, text=questions['q3'], bg='MediumSeaGreen')
    label3.grid(row=1, column=3)

    # defines Button 1 and places it using grid
    button13 = Radiobutton(main, text=answers["q3"][0], variable=v2, value=1, bg='MediumSeaGreen')
    button13.grid(row=2, column=3)

    button23 = Radiobutton(main, text=answers["q3"][1], variable=v2, value=2, bg='MediumSeaGreen')
    button23.grid(row=3, column=3)

    button33 = Radiobutton(main, text=answers["q3"][2], variable=v2, value=3, bg='MediumSeaGreen')
    button33.grid(row=4, column=3)

    button43 = Radiobutton(main, text=answers["q3"][3], variable=v2, value=4, bg='MediumSeaGreen')
    button43.grid(row=5, column=3)

    label4 = Label(main, text=questions['q4'], bg='MediumSeaGreen')
    label4.grid(row=6, column=1)

    # defines Button 1 and places it using grid
    button14 = Radiobutton(main, text=answers["q4"][0], variable=v3, value=1, bg='MediumSeaGreen')
    button14.grid(row=7, column=1)

    button24 = Radiobutton(main, text=answers["q4"][1], variable=v3, value=2, bg='MediumSeaGreen')
    button24.grid(row=8, column=1)

    button34 = Radiobutton(main, text=answers["q4"][2], variable=v3, value=3, bg='MediumSeaGreen')
    button34.grid(row=9, column=1)

    button44 = Radiobutton(main, text=answers["q4"][3], variable=v3, value=4, bg='MediumSeaGreen')
    button44.grid(row=10, column=1)

    label5 = Label(main, text=questions['q5'], bg='MediumSeaGreen')
    label5.grid(row=6, column=2)

    # defines Button 1 and places it using grid
    button15 = Radiobutton(main, text=answers["q5"][0], variable=v4, value=1, bg='MediumSeaGreen')
    button15.grid(row=7, column=2)

    button25 = Radiobutton(main, text=answers["q5"][1], variable=v4, value=2, bg='MediumSeaGreen')
    button25.grid(row=8, column=2)

    button35 = Radiobutton(main, text=answers["q5"][2], variable=v4, value=3, bg='MediumSeaGreen')
    button35.grid(row=9, column=2)

    button45 = Radiobutton(main, text=answers["q5"][3], variable=v4, value=4, bg='MediumSeaGreen')
    button45.grid(row=10, column=2)

    label6 = Label(main, text=questions['q6'], bg='MediumSeaGreen')
    label6.grid(row=6, column=3)

    # defines Button 1 and places it using grid
    button16 = Radiobutton(main, text=answers["q6"][0], variable=v5, value=1, bg='MediumSeaGreen')
    button16.grid(row=7, column=3)

    button26 = Radiobutton(main, text=answers["q6"][1], variable=v5, value=2, bg='MediumSeaGreen')
    button26.grid(row=8, column=3)

    button36 = Radiobutton(main, text=answers["q6"][2], variable=v5, value=3, bg='MediumSeaGreen')
    button36.grid(row=9, column=3)

    button46 = Radiobutton(main, text=answers["q6"][3], variable=v5, value=4, bg='MediumSeaGreen')
    button46.grid(row=10, column=3)

    label7 = Label(main, text=questions['q7'], bg='MediumSeaGreen')
    label7.grid(row=11, column=1)

    # defines Button 1 and places it using grid
    button17 = Radiobutton(main, text=answers["q7"][0], variable=v6, value=1, bg='MediumSeaGreen')
    button17.grid(row=12, column=1)

    button27 = Radiobutton(main, text=answers["q7"][1], variable=v6, value=2, bg='MediumSeaGreen')
    button27.grid(row=13, column=1)

    button37 = Radiobutton(main, text=answers["q7"][2], variable=v6, value=3, bg='MediumSeaGreen')
    button37.grid(row=14, column=1)

    button47 = Radiobutton(main, text=answers["q7"][3], variable=v6, value=4, bg='MediumSeaGreen')
    button47.grid(row=15, column=1)

    label8 = Label(main, text=questions['q8'], bg='MediumSeaGreen')
    label8.grid(row=11, column=2)

    # defines Button 1 and places it using grid
    button18 = Radiobutton(main, text=answers["q8"][0], variable=v7, value=1, bg='MediumSeaGreen')
    button18.grid(row=12, column=2)

    button28 = Radiobutton(main, text=answers["q8"][1], variable=v7, value=2, bg='MediumSeaGreen')
    button28.grid(row=13, column=2)

    button38 = Radiobutton(main, text=answers["q8"][2], variable=v7, value=3, bg='MediumSeaGreen')
    button38.grid(row=14, column=2)

    button48 = Radiobutton(main, text=answers["q8"][3], variable=v7, value=4, bg='MediumSeaGreen')
    button48.grid(row=15, column=2)

    label49 = Label(main, text=questions['q9'], bg='MediumSeaGreen')
    label49.grid(row=11, column=3)

    # defines Button 1 and places it using grid
    button19 = Radiobutton(main, text=answers["q9"][0], variable=v8, value=1, bg='MediumSeaGreen')
    button19.grid(row=12, column=3)

    button29 = Radiobutton(main, text=answers["q9"][1], variable=v8, value=2, bg='MediumSeaGreen')
    button29.grid(row=13, column=3)

    button39 = Radiobutton(main, text=answers["q9"][2], variable=v8, value=3, bg='MediumSeaGreen')
    button39.grid(row=14, column=3)

    button49 = Radiobutton(main, text=answers["q9"][3], variable=v8, value=4, bg='MediumSeaGreen')
    button49.grid(row=15, column=3)

    button = Button(main, text='Submit', command=lambda: result(click(),value), height=1, width=50, bg='DodgerBlue', fg='white')
    button.grid(row=16, column=2)

    main.mainloop()

label1 = Label(text='', bg='LightBlue')
label1.grid(row=1, column=1)

label2 = Label(text='', bg='LightBlue')
label2.grid(row=2, column=1)

label3 = Label(text='', bg='LightBlue')
label3.grid(row=3, column=1)

label4 = Label(text='Enter Your Name: ', bg='LightBlue')
label4.grid(row=6, column=1, padx=(1, 1))

textbox = Entry(root, width=30)
textbox.grid(row=7, column=1, padx=(10, 10))

label5 = Label(text='', bg='LightBlue')
label5.grid(row=8, column=1)

label6 = Label(text='', bg='LightBlue')
label6.grid(row=9, column=1)

label7 = Label(text='', bg='LightBlue')
label7.grid(row=10, column=1)

button = Button(root, text='Start Quiz', fg='white', bg='SeaGreen', command= lambda: main(textbox.get()))
button.grid(row=8, column=1, padx=(10, 10))

root.mainloop()
