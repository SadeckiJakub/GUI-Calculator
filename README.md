from tkinter import *

root = Tk()
root.title('GUI Calculator')
root.config(bg='white')

displayStr = StringVar()
displayStr.set('0')
display = Entry(root, bd=4, width=16, font=('Calibri Light','24'), textvariable=displayStr, justify=RIGHT)
display.grid(row=0,columnspan=4)
result=''

def Click(character):
    global displayStr, result
    result = result + str(character)
    displayStr.set(result)

def Equal():
    global displayStr, result
    result1 = str(eval(result))
    displayStr.set(result1)
    result=displayStr.get()

def Clear():
    global displayStr, result
    displayStr.set('0')
    result =''

def MinusPlus():
    global displayStr, result
    a = displayStr.get()
    result1 = -float(a)
    displayStr.set(result1)
    result=displayStr.get()

def Percent():
    global displayStr, result
    b = displayStr.get()
    result1 = float(b) / 100
    displayStr.set(result1)
    result=displayStr.get()

number7 = Button(root, text='7', font=('Calibri Light','16'),bg='grey66',command=lambda:Click(7), height=2, width=6)
number7.grid(row=2,column=0)

number8 = Button(root, text='8', font=('Calibri Light','16'),bg='grey66',command=lambda:Click(8), height=2, width=6)
number8.grid(row=2,column=1)

number9 = Button(root, text='9', font=('Calibri Light','16'),bg='grey66',command=lambda:Click(9), height=2, width=6)
number9.grid(row=2,column=2)

number4 = Button(root, text='4', font=('Calibri Light','16'),bg='grey66',command=lambda:Click(4), height=2, width=6)
number4.grid(row=3,column=0)

number5 = Button(root, text='5', font=('Calibri Light','16'),bg='grey66',command=lambda:Click(5), height=2, width=6)
number5.grid(row=3,column=1)

number6 = Button(root, text='6', font=('Calibri Light','16'),bg='grey66',command=lambda:Click(6), height=2, width=6)
number6.grid(row=3,column=2)

number1 = Button(root, text='1', font=('Calibri Light','16'),bg='grey66',command=lambda:Click(1), height=2, width=6)
number1.grid(row=4,column=0)

number2 = Button(root, text='2', font=('Calibri Light','16'),bg='grey66',command=lambda:Click(2), height=2, width=6)
number2.grid(row=4,column=1)

number3 = Button(root, text='3', font=('Calibri Light','16'),bg='grey66',command=lambda:Click(3), height=2, width=6)
number3.grid(row=4,column=2)

number0 = Button(root, text='0', font=('Calibri Light','16'),bg='grey66',command=lambda:Click(0), height=2, width=13)
number0.grid(row=5,columnspan=2)

clear = Button(root, text='C', font=('Calibri Light','16'),bg='grey88',command=Clear, height=2, width=6)
clear.grid(row=1,column=0)

dot = Button(root, text='.', font=('Calibri Light','16'),bg='grey66',command=lambda:Click('.'), height=2, width=6)
dot.grid(row=5,column=2)

equal = Button(root, text='=', font=('Calibri Light','16'),bg='dark orange',command=Equal, height=2, width=6)
equal.grid(row=5,column=3)

minusplus = Button(root, text='+/-', font=('Calibri Light','16'),bg='grey88',command=MinusPlus, height=2, width=6)
minusplus.grid(row=1,column=1)

percent = Button(root, text='%', font=('Calibri Light','16'),bg='grey88',command=Percent, height=2, width=6)
percent.grid(row=1,column=2)

add = Button(root, text='+', font=('Calibri Light','16'),bg='dark orange',command=lambda:Click('+'), height=2, width=6)
add.grid(row=4,column=3)

subtract = Button(root, text='-', font=('Calibri Light','16'),bg='dark orange',command=lambda:Click('-'), height=2, width=6)
subtract.grid(row=3,column=3)

multiply = Button(root, text='*', font=('Calibri Light','16'),bg='dark orange',command=lambda:Click('*'), height=2, width=6)
multiply.grid(row=2,column=3)

divide = Button(root, text='/', font=('Calibri Light','16'),bg='dark orange',command=lambda:Click('/'), height=2, width=6)
divide.grid(row=1,column=3)

root.mainloop()



