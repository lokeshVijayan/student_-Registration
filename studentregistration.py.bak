from tkinter import *
import sqlite3
import csv

window=Tk()
n=StringVar()
f=StringVar()
m=IntVar()
em=StringVar()
rm=IntVar()
rf=IntVar()
cp=StringVar()
cd=StringVar()
cm=StringVar()
conn_obj=sqlite3.connect("registration.db")
cur_obj=conn_obj.cursor()
cur_obj.execute( """ create table std13( name string,fathersname string, mobilenum integer ,
                 email string, male integer ,female integer ,python string,django string,
                 mysql string )""")
def insert():
    cur_obj.execute(" insert into std12 values(?,?,?,?,?,?,?,?,?)",
                    (n.get(),f.get(),m.get(),em.get(),rm.get(),rf.get(),cp.get(),
                     cd.get(),cm.get()))
    cur_obj.execute("commit")
    n.set('')
    f.set('')
    m.set('')
    em.set('')
    rm.set('')
    rf.set('')
    cp.set('')
    cd.set('')
    cm.set('')
def display():
    
    cur_obj.execute("select * from std12 ")
    
    rec=cur_obj.fetchall()
    
    with open('reg.csv','w',newline="") as f1: 
        writer_obj=csv.writer(f1)
        for records in rec:
            writer_obj.writerow(list(records) )                               




                                

l1=Label(window,text="STUDENT REGISTRATION FORM")
l1.pack()
L=Label(window,text="ENTER YOUR NAME:")
L.place(x=50,y=40)
e1=Entry(window,bd=5,textvariable=n)
e1.place(x=250,y=50)
l2=Label(window,text="ENTER YOUR FATHERNAME:")
l2.place(x=50,y=100)
e2=Entry(window,bd=5,textvariable=f)
e2.place(x=250,y=100)
l3=Label(window,text="ENTER YOUR MOBILENUMBER:")
l3.place(x=50,y=150)
e3=Entry(window,bd=5,textvariable=m)
e3.place(x=250,y=150)
l4=Label(window,text="ENTER YOUR EMAIL:")
l4.place(x=50,y=200)
e4=Entry(window,bd=5,textvariable=em)
e4.place(x=250,y=200)
l5=Label(window,text="ENTER YOUR GENDER:")
l5.place(x=50,y=250)
R1=Radiobutton(window,text="male",textvariable="rm",value=1)
R1.place(x=250,y=250)
R2=Radiobutton(window,text="female",textvariable="rf",value=0)
R2.place(x=350,y=250)
l6=Label(window,text="SELECT YOUR COURSE:")
l6.place(x=50,y=300)
c1=Checkbutton(window,text="python",textvariable="cp")
c1.place(x=250,y=300)
c2=Checkbutton(window,text="django",textvariable="cd")
c2.place(x=310,y=300)
c3=Checkbutton(window,text="mysql",textvariable="cm")
c3.place(x=400,y=300)
B=Button(window,text="INSERT",command=insert)
B.place(x=250,y=350)
B=Button(window,text="REGISTER",command=display)
B.place(x=350,y=350)









window.mainloop()
