import webbrowser
import tkinter # imports main library
from random import randint # For random functions
window = tkinter.Tk() #so that there's less confusing brackets
defin = ""
glossary2d =[]

def MakeList():

    with open('Glossary.txt') as f:
        for line in f:
            #print(line)
            parts = line.split(",")
            #print(parts)
            glossary2d.append(parts)

def search(event):
    global defin
    defin=""
    search_for = Myentry.get()
    print(search_for)
    for i in glossary2d:
        if search_for.lower() in i[0].lower():
            print(*i)
            defin+=i[0]
            defin+=" - "
            defin+=i[1]
            defin+="\n"
            definition.configure(text=defin)
    window.clipboard_clear()
    window.clipboard_append(defin)

def reporter():

    webbrowser.open_new(f"https://docs.google.com/forms/d/e/1FAIpQLSfWt4FCjmHGKY94KOMENRJrMU4mTorrEM1_VaA16lq17Y5ldQ/viewform?usp=pp_url&entry.317166398={defin}")
    # https://docs.google.com/forms/d/e/1FAIpQLSfWt4FCjmHGKY94KOMENRJrMU4mTorrEM1_VaA16lq17Y5ldQ/viewform?usp=pp_url&entry.317166398=MYQU
    print(defin)

def ran_def():
    global defin
    defin=""
    i=glossary2d[randint(0,len(glossary2d))]
    defin+=i[0]
    defin+=" - "
    defin+=i[1]
    defin+="\n"
    definition.configure(text=defin)
    window.clipboard_clear()
    window.clipboard_append(defin)

MakeList()

window.title('CS Glossary')
window.geometry("650x300") #Width x Height
MyTitle = tkinter.Label(window, text="Glossary",font="Helvetica 16 bold")
MyTitle.pack()
subtitle = tkinter.Label(window, text="Answers automatically copied to clipboard. Press return to search",font="Helvetica 12",wraplength=600)
subtitle.pack()

Error_Button = tkinter.Button(window, text="Random Definition", command=ran_def)
Error_Button.pack()

Myentry = tkinter.Entry(window, font="Helvetica 16")
Myentry.bind("<Return>", search)
Myentry.pack()

definition = tkinter.Label(window, font="Helvetica 16", wraplength=600, justify="left")
definition.pack(anchor="w")

Error_Button = tkinter.Button(window, text="Report Error", command=reporter)
Error_Button.pack()

window.mainloop()
