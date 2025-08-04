# python-calculator-by-george
     self.equation=StringVar()
     self.entry_value=''
     #create an entry box:
     Entry(width=17,bg='#ccddff',font=('Arial Bold',28),textvariable=self.equation).place(x=0,y=0)
     #Create buttoms
     Button(width = 11,height = 4,text = '1', bg ="white",relief ="flat",command= lambda:self.show(1)).place(x=0,y=125)#1
     Button(width = 11,height = 4,text = '2', bg ="white",relief ="flat",command= lambda:self.show(2)).place(x=90,y=125)#2
     Button(width = 11,height = 4,text = '3', bg ="white",relief ="flat",command= lambda:self.show(3)).place(x=180,y=125)#3
     Button(width = 11,height = 4,text = '4', bg ="white",relief ="flat",command= lambda:self.show(4)).place(x=0,y=200)#4
     Button(width = 11,height = 4,text = '5', bg ="white",relief ="flat",command= lambda:self.show(5)).place(x=90,y=200)#5
     Button(width = 11,height = 4,text = '6', bg ="white",relief ="flat",command= lambda:self.show(6)).place(x=180,y=200)#6
     Button(width = 11,height = 4,text = '7', bg ="white",relief ="flat",command= lambda:self.show(7)).place(x=0,y=275)#7
     Button(width = 11,height = 4,text = '8', bg ="white",relief ="flat",command= lambda:self.show(8)).place(x=180,y=275)#8
     Button(width = 11,height = 4,text = '9', bg ="white",relief ="flat",command= lambda:self.show(9)).place(x=90,y=275)#9
     Button(width = 11,height = 4,text = '0', bg ="white",relief ="flat",command= lambda:self.show(0)).place(x=90,y=350)#0
     Button(width = 11,height = 4,text = '+', bg ="white",relief ="flat",command= lambda:self.show("+")).place(x=270,y=275)#+
     Button(width = 11,height = 4,text = '-', bg ="white",relief ="flat",command= lambda:self.show("-")).place(x=270,y=200)#-
     Button(width = 11,height = 4,text = '=', bg ="lightblue",relief ="flat",command= self.solve).place(x=270,y=350)#=
     Button(width = 11,height = 4,text = '/', bg ="white",relief ="flat",command= lambda:self.show("/")).place(x=270,y=50)#/
     Button(width = 11,height = 4,text = 'C', bg ="white",relief ="flat",command=self.clear).place(x=0,y=350)
     Button(width = 11,height = 4,text = '(', bg ="white",relief ="flat",command= lambda:self.show("(")).place(x=0,y=50)#(
     Button(width = 11,height = 4,text = ')', bg ="white",relief ="flat",command= lambda:self.show(")")).place(x=90,y=50)#)
     Button(width = 11,height = 4,text = '%', bg ="white",relief ="flat",command= lambda:self.show("%")).place(x=180,y=50)#%
     Button(width = 11,height = 4,text = 'x', bg ="white",relief ="flat",command= lambda:self.show("*")).place(x=270,y=125)#x
     Button(width = 11,height = 4,text = '.', bg ="white",relief ="flat",command= lambda:self.show(".")).place(x=180,y=350)#.

 #Function of buttoms:
def clear(self):
    self.entry_value=''
    self.equation.set(self.entry_value)


def show(self,value):
    self.entry_value+=str(value)
    self.equation.set(self.entry_value)

def solve(self):
    try:
        result = eval(self.entry_value)
        self.equation.set(result)
        self.entry_value = str(result)
        error_label.config(text="")
    except (SyntaxError, ZeroDivisionError, ValueError):
        self.equation.set("")
        self.entry_value = ""
        error_label.config(text="Error: Invalid expression")
