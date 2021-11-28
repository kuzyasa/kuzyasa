from tkinter import *
from tkinter import messagebox
from tkinter import Tk, Frame, Menu
import os
import sqlite3
import tkinter as tk
from tkinter import ttk
from PIL import ImageTk
import tkinter as tk
from PIL import ImageGrab
from tkinter import Button
from tkinter import filedialog
from tkinter.filedialog import *
import tkinter.filedialog as fd

root = Tk()
root.geometry("400x300+400+200")
root.title("Авторизация")
root.iconbitmap("user.ico")
root.configure(bg='OliveDrab')



def show():
    if Entry2.cget('show') == '':
        Entry2.config(show='*')
        c2.config(text='Показать')
    else:
        Entry2.config(show='')
        c2.config(text='Скрыть')

def reg():
    if Entry1.get()=='katya' and Entry2.get()=='1234':
        messagebox.showinfo("Логин","Добро Пожаловать " + Entry1.get())
        Button1.place_forget()
        Button3.place_forget()
        Button4.place_forget()
        Label1.place_forget()
        Label2.place_forget()
        Label3.place_forget()
        Entry1.place_forget()
        Entry2.place_forget()
        c2.place_forget()
        root.configure(bg='white')
        root.iconbitmap("menu.ico")
        okno1()
    

    elif Entry1.get()=='' and Entry2.get()=='':
        messagebox.showinfo("Логин","Заполните данные")
    else:
        messagebox.showerror("Пароль","Неверный логин или пароль")

def avtor():
    messagebox.showinfo("Автор","Кузьминых Н.П")
def intu():
    messagebox.showinfo("Инструкция","Для работы программы необходимо открывать нужные пользователю таблицы и выполнять различные действия.")
def spravka():
    messagebox.showinfo("Справка","Программа должна облегчить работу с базами данными")
def exit():
    if messagebox.askokcancel("Выход", "Выйти из программы?"):
                root.destroy()

def win():
    root.attributes('-fullscreen', False)
def full():
    root.attributes('-fullscreen', True)
    
def okno1():
    global Button11,Button22,Button33,Button44,Button55,Button66,Button77,Button88,toolbar1,label5,label6,label7,Button99,Button00
    root.geometry("1000x600+0+0")
    root.title("Таблицы")
    root.resizable(False, False)
    #image8 = ImageTk.PhotoImage(file="jok.jpg")
    root.iconbitmap("menu.ico")
    toolbar1=Frame(root,bg="#d7d8e0")

    image = ImageTk.PhotoImage(file="table.png")
    image2 = ImageTk.PhotoImage(file="table.png")
    image3 = ImageTk.PhotoImage(file="table.png")
    image4 = ImageTk.PhotoImage(file="table.png")
    image5 = ImageTk.PhotoImage(file="avtor.png")
    image6 = ImageTk.PhotoImage(file="int.png")
    image7 = ImageTk.PhotoImage(file="sprav.png")
    image8 = ImageTk.PhotoImage(file="arm3.jpg")
    image9 = ImageTk.PhotoImage(file="exit.png")
    image10 = ImageTk.PhotoImage(file="full.png")
    image11 = ImageTk.PhotoImage(file="win.png")
    label5 = Label(text = "БАЗА ДАННЫХ",font=("Arial",30,'bold'))
    label6 = Label(text = "ПО УЧЕТУ ВОЕННООБЯЗАННЫХ",font=("Arial",30,'bold'))
    label7 = Label(image=image8)
    Button11 = Button(toolbar1,text = "Журналы",image=image,compound=TOP,
                     font=("Arial",11,'bold'),background="#d7d8e0",borderwidth=0,command=okno2)
    Button11.pack(side=LEFT)
    
    Button22 = Button(toolbar1,text = "Болезни",image=image2,compound=TOP,
                     font=("Arial",11,'bold'),background="#d7d8e0",borderwidth=0,command=okno3)
    Button22.pack(side=LEFT)
    
    Button33 = Button(toolbar1,text = "Родители",image=image3,compound=TOP,
                     font=("Arial",11,'bold'),background="#d7d8e0",borderwidth=0,command=okno4)
    Button33.pack(side=LEFT)

    Button44 = Button(toolbar1,text = "Места",image=image4,compound=TOP,
                     font=("Arial",11,'bold'),background="#d7d8e0",borderwidth=0,command=okno5)
    Button44.pack(side=LEFT)
    
    Button55 = Button(toolbar1,text = "Автор",image=image5,compound=TOP,
                     font=("Arial",11,'bold'),background="#d7d8e0",borderwidth=0,command=avtor)
    Button55.pack(side=LEFT)

    Button66 = Button(toolbar1,text = "Инструкция",image=image6,compound=TOP,
                     font=("Arial",11,'bold'),background="#d7d8e0",borderwidth=0,command=intu)
    Button66.pack(side=LEFT)
    
    Button77 = Button(toolbar1,text = "Справка",image=image7
                      ,compound=TOP,
                     font=("Arial",11,'bold'),background="#d7d8e0",borderwidth=0,command=spravka)
    Button77.pack(side=LEFT)
    Button00 = Button(toolbar1,text = "Полный экран",image=image10
                      ,compound=TOP,
                     font=("Arial",11,'bold'),background="#d7d8e0",borderwidth=0,command=full)
    Button00.pack(side=LEFT)
    Button99 = Button(toolbar1,text = "В окне",image=image11
                      ,compound=TOP,
                     font=("Arial",11,'bold'),background="#d7d8e0",borderwidth=0,command=win)
    Button99.pack(side=LEFT)
    Button88 = Button(toolbar1,text = "Выход",image=image9
                      ,compound=TOP,
                     font=("Arial",11,'bold'),background="#d7d8e0",borderwidth=0,command=exit)
    Button88.pack(side=LEFT)

    
    toolbar1.pack(side=TOP,fill=X)
    label5.pack()
    label6.pack()
    label7.pack()
    root.mainloop()

    
def back2():
    Button10.pack_forget()
    Button20.pack_forget()
    Button30.pack_forget()
    Button40.pack_forget()
    Button41.pack_forget()
    Button42.pack_forget()
    Button43.pack_forget()
    Button44.pack_forget()
    Button45.pack_forget()
    Button51.pack_forget()
    Button50.pack_forget()
    toolbar2.pack_forget()
    tree1.pack_forget()
    
    
def back3():
    Button60.pack_forget()
    Button70.pack_forget()
    Button80.pack_forget()
    Button90.pack_forget()
    Button101.pack_forget()
    Button102.pack_forget()
    Button100.pack_forget()
    toolbar3.pack_forget()
    tree2.pack_forget()

def back4():
    Button110.pack_forget()
    Button120.pack_forget()
    Button130.pack_forget()
    Button140.pack_forget()
    Button141.pack_forget()
    Button151.pack_forget()
    Button152.pack_forget()
    Button150.pack_forget()
    toolbar4.pack_forget()
    tree3.pack_forget()

def back5():
    Button160.pack_forget()
    Button170.pack_forget()
    Button180.pack_forget()
    Button190.pack_forget()
    Button191.pack_forget()
    Button202.pack_forget()
    Button201.pack_forget()
    Button200.pack_forget()
    toolbar5.pack_forget()
    tree4.pack_forget()
    
    
def save():
    conn = sqlite3.connect("baza.db")
    cur = conn.cursor()
    cur.execute("SELECT * FROM journal")
    rows = cur.fetchall()
    file = open('baza.txt', 'w', encoding='utf-8')
    for row in rows:
        file.write(str(row))
            


    conn.close()

             
def bazaa():
    global row
    for record in tree1.get_children():
        tree1.delete(record)
    conn = sqlite3.connect("baza.db")
    cur = conn.cursor()
    cur.execute("SELECT * FROM journal")
    rows = cur.fetchall()
    for row in rows:
        tree1.insert("", tk.END, values=row)

    conn.close()

def bazaa2():
    for record in tree2.get_children():
        tree2.delete(record)
    conn = sqlite3.connect("baza.db")
    cur = conn.cursor()
    cur.execute("SELECT * FROM bolezni")
    rows = cur.fetchall()
    for row in rows:
        #print(row) # it print all records in the database
        tree2.insert("", tk.END, values=row)
    conn.close()

def bazaa3():
    for record in tree3.get_children():
        tree3.delete(record)
    conn = sqlite3.connect("baza.db")
    cur = conn.cursor()
    cur.execute("SELECT * FROM roditel")
    rows = cur.fetchall()
    for row in rows:
        #print(row) # it print all records in the database
        tree3.insert("", tk.END, values=row)
    conn.close()

def bazaa4():
    for record in tree4.get_children():
        tree4.delete(record)
    conn = sqlite3.connect("baza.db")
    cur = conn.cursor()
    cur.execute("SELECT * FROM mesto")
    rows = cur.fetchall()
    for row in rows:
        #print(row) # it print all records in the database
        tree4.insert("", tk.END, values=row)
    conn.close()
    


def delete():

    conn = sqlite3.connect("baza.db")
    c = conn.cursor()
    for selection_item in tree1.selection():
        c.execute('''DELETE FROM journal WHERE id_priz=?''', (tree1.set(selection_item, '#1'),))
        tree1.delete(selection_item)
    conn.commit()
    conn.close()

def delete2():

    conn = sqlite3.connect("baza.db")
    c = conn.cursor()
    for selection_item in tree2.selection():
        c.execute('''DELETE FROM bolezni WHERE id_bol=?''', (tree2.set(selection_item, '#1'),))
        tree2.delete(selection_item)
    conn.commit()
    conn.close()
    
def delete3():

    conn = sqlite3.connect("baza.db")
    c = conn.cursor()
    for selection_item in tree3.selection():
        c.execute('''DELETE FROM roditel WHERE id_rod=?''', (tree3.set(selection_item, '#1'),))
        tree3.delete(selection_item)
    conn.commit()
    conn.close()
def delete4():

    conn = sqlite3.connect("baza.db")
    c = conn.cursor()
    for selection_item in tree4.selection():
        c.execute('''DELETE FROM mesto WHERE id_mesto=?''', (tree4.set(selection_item, '#1'),))
        tree4.delete(selection_item)
    conn.commit()
    conn.close()


def okno_add():
    global entry_fio,entry_fio2,combobox,entry_vozrast,entry_vozrast2,entry_vozrast3,entry_vozrast4
    dob = Toplevel()
    dob.title('Добавление')
    dob.geometry('400x420+400+150')
    dob.resizable(False, False)
    label_fio = tk.Label(dob,text='ID')
    label_fio.place(x=50, y=20)
    label_fio2 = tk.Label(dob,text='Ф.И.О:')
    label_fio2.place(x=50, y=50)
    label_select = tk.Label(dob,text='Звание')
    label_select.place(x=50, y=80)
    label_sum = tk.Label(dob,text='Возраст')
    label_sum.place(x=50, y=110)
    label_sum2 = tk.Label(dob,text='Болезнь')
    label_sum2.place(x=50, y=140)
    label_sum3 = tk.Label(dob,text='Родитель')
    label_sum3.place(x=50, y=170)
    label_sum4 = tk.Label(dob,text='Место')
    label_sum4.place(x=50, y=200)

    entry_fio = ttk.Entry(dob)
    entry_fio.place(x=200, y=20)
    
    entry_fio2 = ttk.Entry(dob)
    entry_fio2.place(x=200, y=50)

    entry_vozrast = ttk.Entry(dob)
    entry_vozrast.place(x=200, y=110)
    entry_vozrast2 = ttk.Entry(dob)
    entry_vozrast2.place(x=200, y=140)
    entry_vozrast3 = ttk.Entry(dob)
    entry_vozrast3.place(x=200, y=170)
    entry_vozrast4 = ttk.Entry(dob)
    entry_vozrast4.place(x=200, y=200)
        
    combobox = ttk.Combobox(dob,values=[u'Рядовой', u'Ефрейтор', u'Капитан', u'Сержант', u'Прапорщик'])
    combobox.current(0)
    combobox.place(x=200, y=80)

    btn_cancel = ttk.Button(dob, text='Закрыть',command=dob.destroy)
    btn_cancel.place(x=300, y=370)

    btn_ok = ttk.Button(dob,text='Добавить',command=add)
    btn_ok.place(x=220, y=370)
def okno_add2():
    global entry_fio,entry_fio2
    dob = Toplevel()
    dob.title('Добавление')
    dob.geometry('400x420+400+300')
    dob.resizable(False, False)
    label_fio = tk.Label(dob,text='ID')
    label_fio.place(x=50, y=20)
    label_fio2 = tk.Label(dob,text='Название')
    label_fio2.place(x=50, y=50)


    entry_fio = ttk.Entry(dob)
    entry_fio.place(x=200, y=20)
    
    entry_fio2 = ttk.Entry(dob)
    entry_fio2.place(x=200, y=50)


    btn_cancel = ttk.Button(dob, text='Закрыть',command=dob.destroy)
    btn_cancel.place(x=300, y=370)

    btn_ok = ttk.Button(dob,text='Добавить',command=add2)
    btn_ok.place(x=220, y=370)
def okno_add3():
    global entry_fio,entry_fio2,entry_fio3
    dob = Toplevel()
    dob.title('Добавление')
    dob.geometry('400x420+400+300')
    dob.resizable(False, False)
    label_fio = tk.Label(dob,text='ID')
    label_fio.place(x=50, y=20)
    label_fio2 = tk.Label(dob,text='Ф.И.О')
    label_fio2.place(x=50, y=50)
    label_fio3 = tk.Label(dob,text='Телефон')
    label_fio3.place(x=50, y=80)


    entry_fio = ttk.Entry(dob)
    entry_fio.place(x=200, y=20)
    
    entry_fio2 = ttk.Entry(dob)
    entry_fio2.place(x=200, y=50)

    entry_fio3 = ttk.Entry(dob)
    entry_fio3.place(x=200, y=80)


    btn_cancel = ttk.Button(dob, text='Закрыть',command=dob.destroy)
    btn_cancel.place(x=300, y=370)

    btn_ok = ttk.Button(dob,text='Добавить',command=add3)
    btn_ok.place(x=220, y=370)

def okno_add4():
    global entry_fio,entry_fio2,entry_fio3
    dob = Toplevel()
    dob.title('Добавление')
    dob.geometry('400x420+400+300')
    dob.resizable(False, False)
    label_fio = tk.Label(dob,text='ID')
    label_fio.place(x=50, y=20)
    label_fio2 = tk.Label(dob,text='Город службы')
    label_fio2.place(x=50, y=50)
    label_fio3 = tk.Label(dob,text='Город проживания')
    label_fio3.place(x=50, y=80)


    entry_fio = ttk.Entry(dob)
    entry_fio.place(x=200, y=20)
    
    entry_fio2 = ttk.Entry(dob)
    entry_fio2.place(x=200, y=50)

    entry_fio3 = ttk.Entry(dob)
    entry_fio3.place(x=200, y=80)


    btn_cancel = ttk.Button(dob, text='Закрыть',command=dob.destroy)
    btn_cancel.place(x=300, y=370)

    btn_ok = ttk.Button(dob,text='Добавить',command=add4)
    btn_ok.place(x=220, y=370)
    
def okno_update():
    global entry_fio,entry_fio2,combobox,entry_vozrast,entry_vozrast2,entry_vozrast3,entry_vozrast4
    dob = Toplevel()
    dob.title('Редактирование')
    dob.geometry('400x420+400+300')
    dob.resizable(False, False)
    label_fio = tk.Label(dob,text='ID')
    label_fio.place(x=50, y=20)
    label_fio2 = tk.Label(dob,text='Ф.И.О:')
    label_fio2.place(x=50, y=50)
    label_select = tk.Label(dob,text='Звание')
    label_select.place(x=50, y=80)
    label_sum = tk.Label(dob,text='Возраст')
    label_sum.place(x=50, y=110)
    label_sum2 = tk.Label(dob,text='Болезнь')
    label_sum2.place(x=50, y=140)
    label_sum3 = tk.Label(dob,text='Родитель')
    label_sum3.place(x=50, y=170)
    label_sum4 = tk.Label(dob,text='Место')
    label_sum4.place(x=50, y=200)

    entry_fio = ttk.Entry(dob)
    entry_fio.place(x=200, y=20)
    
    entry_fio2 = ttk.Entry(dob)
    entry_fio2.place(x=200, y=50)

    entry_vozrast = ttk.Entry(dob)
    entry_vozrast.place(x=200, y=110)
    entry_vozrast2 = ttk.Entry(dob)
    entry_vozrast2.place(x=200, y=140)
    entry_vozrast3 = ttk.Entry(dob)
    entry_vozrast3.place(x=200, y=170)
    entry_vozrast4 = ttk.Entry(dob)
    entry_vozrast4.place(x=200, y=200)
        
    combobox = ttk.Combobox(dob,values=[u'Рядовой', u'Ефрейтор', u'Капитан', u'Сержант', u'Прапорщик'])
    combobox.current(0)
    combobox.place(x=200, y=80)

    btn_cancel = ttk.Button(dob, text='Закрыть',command=dob.destroy)
    btn_cancel.place(x=300, y=370)

    btn_ok = ttk.Button(dob,text='Редактировать',command=update)
    btn_ok.place(x=220, y=370)
    select()

def okno_update2():
    global entry_fio,entry_fio2
    dob = Toplevel()
    dob.title('Редактирование')
    dob.geometry('400x420+400+300')
    dob.resizable(False, False)
    label_fio = tk.Label(dob,text='ID')
    label_fio.place(x=50, y=20)
    label_fio2 = tk.Label(dob,text='Название')
    label_fio2.place(x=50, y=50)


    entry_fio = ttk.Entry(dob)
    entry_fio.place(x=200, y=20)
    
    entry_fio2 = ttk.Entry(dob)
    entry_fio2.place(x=200, y=50)


    btn_cancel = ttk.Button(dob, text='Закрыть',command=dob.destroy)
    btn_cancel.place(x=300, y=370)

    btn_ok = ttk.Button(dob,text='Редактировать',command=update2)
    btn_ok.place(x=220, y=370)
    select2()

def okno_update3():
    global entry_fio,entry_fio2,entry_fio3
    dob = Toplevel()
    dob.title('Редактирование')
    dob.geometry('400x420+400+300')
    dob.resizable(False, False)
    label_fio = tk.Label(dob,text='ID')
    label_fio.place(x=50, y=20)
    label_fio2 = tk.Label(dob,text='Ф.И.О')
    label_fio2.place(x=50, y=50)
    label_fio3 = tk.Label(dob,text='Телефон')
    label_fio3.place(x=50, y=80)


    entry_fio = ttk.Entry(dob)
    entry_fio.place(x=200, y=20)
    
    entry_fio2 = ttk.Entry(dob)
    entry_fio2.place(x=200, y=50)

    entry_fio3 = ttk.Entry(dob)
    entry_fio3.place(x=200, y=80)


    btn_cancel = ttk.Button(dob, text='Закрыть',command=dob.destroy)
    btn_cancel.place(x=300, y=370)

    btn_ok = ttk.Button(dob,text='Редактировать',command=update3)
    btn_ok.place(x=220, y=370)
    select3()

def okno_update4():
    global entry_fio,entry_fio2,entry_fio3
    dob = Toplevel()
    dob.title('Редактирование')
    dob.geometry('400x420+400+300')
    dob.resizable(False, False)
    label_fio = tk.Label(dob,text='ID')
    label_fio.place(x=50, y=20)
    label_fio2 = tk.Label(dob,text='Город службы')
    label_fio2.place(x=50, y=50)
    label_fio3 = tk.Label(dob,text='Город проживания')
    label_fio3.place(x=50, y=80)


    entry_fio = ttk.Entry(dob)
    entry_fio.place(x=200, y=20)
    
    entry_fio2 = ttk.Entry(dob)
    entry_fio2.place(x=200, y=50)

    entry_fio3 = ttk.Entry(dob)
    entry_fio3.place(x=200, y=80)


    btn_cancel = ttk.Button(dob, text='Закрыть',command=dob.destroy)
    btn_cancel.place(x=300, y=370)

    btn_ok = ttk.Button(dob,text='Редактировать',command=update4)
    btn_ok.place(x=220, y=370)
    select4()
 
def add():
    global entry_fio,entry_fio2,combobox,entry_vozrast,entry_vozrast2,entry_vozrast3,entry_vozrast4
    conn = sqlite3.connect("baza.db")
    c = conn.cursor()

    c.execute("INSERT or IGNORE into journal VALUES (:id_priz, :fio, :zvanie, :vozrast, :id_bol, :id_rod, :id_mesto )",

        {
            'id_priz': entry_fio.get(),
            'fio': entry_fio2.get(),
            'zvanie': combobox.get(),
            'vozrast': entry_vozrast.get(),
            'id_bol': entry_vozrast2.get(),
            'id_rod': entry_vozrast3.get(),
            'id_mesto': entry_vozrast4.get(),
        })
    
    conn.commit()
    conn.close()

    entry_fio.delete(0,END)
    entry_fio2.delete(0,END)
    combobox.delete(0,END)
    entry_vozrast.delete(0,END)
    entry_vozrast2.delete(0,END)
    entry_vozrast3.delete(0,END)
    entry_vozrast4.delete(0,END)

    tree1.delete(*tree1.get_children())
    bazaa()

def add2():
    global entry_fio,entry_fio2
    conn = sqlite3.connect("baza.db")
    c = conn.cursor()

    c.execute("INSERT or IGNORE into bolezni VALUES (:id_bol, :nazvania)",

        {
            'id_bol': entry_fio.get(),
            'nazvania': entry_fio2.get(),
        })
    
    conn.commit()
    conn.close()

    entry_fio.delete(0,END)
    entry_fio2.delete(0,END)


    tree2.delete(*tree2.get_children())
    bazaa2()

def add3():
    global entry_fio,entry_fio2,entry_fio3
    conn = sqlite3.connect("baza.db")
    c = conn.cursor()

    c.execute("INSERT or IGNORE into roditel VALUES (:id_rod, :fio, :telefon)",

        {
            'id_rod': entry_fio.get(),
            'fio': entry_fio2.get(),
            'telefon': entry_fio3.get(),

        })
    
    conn.commit()
    conn.close()

    entry_fio.delete(0,END)
    entry_fio2.delete(0,END)
    entry_fio3.delete(0,END)

    tree3.delete(*tree3.get_children())
    bazaa3()

def add4():
    global entry_fio,entry_fio2,entry_fio3
    conn = sqlite3.connect("baza.db")
    c = conn.cursor()

    c.execute("INSERT or IGNORE into mesto VALUES (:id_mesto, :gorod_sluj, :gorod_proj)",

        {
            'id_mesto': entry_fio.get(),
            'gorod_sluj': entry_fio2.get(),
            'gorod_proj': entry_fio3.get(),

        })
    
    conn.commit()
    conn.close()

    entry_fio.delete(0,END)
    entry_fio2.delete(0,END)
    entry_fio3.delete(0,END)

    tree4.delete(*tree4.get_children())
    bazaa4()
def update():
    selected = tree1.focus()
    tree1.item(selected, text="",values=(entry_fio.get(),entry_fio2.get(),combobox.get(),entry_vozrast.get(),entry_vozrast2.get(),entry_vozrast3.get(),entry_vozrast4.get(),))

    conn = sqlite3.connect("baza.db")
    c = conn.cursor()


    c.execute("""UPDATE journal SET
        fio = :fi,
        zvanie = :zva,
        vozrast = :voz,
        id_bol = :bol,
        id_rod = :rod,
        id_mesto = :mesto

        WHERE id_priz = :priz""",
        {
            'fi':entry_fio2.get(),
            'zva':combobox.get(),
            'voz':entry_vozrast.get(),
            'bol':entry_vozrast2.get(),
            'rod':entry_vozrast3.get(),
            'mesto':entry_vozrast4.get(),
            'priz':entry_fio.get(),
        })
    conn.commit()   
    conn.close()
def update2():
    selected = tree2.focus()
    tree2.item(selected, text="",values=(entry_fio.get(),entry_fio2.get()))

    conn = sqlite3.connect("baza.db")
    c = conn.cursor()


    c.execute("""UPDATE bolezni SET
        nazvania = :naz


        WHERE id_bol = :bol""",
        {
            'naz':entry_fio2.get(),
            'bol':entry_fio.get(),
        })
    conn.commit()   
    conn.close()

def update3():
    selected = tree3.focus()
    tree3.item(selected, text="",values=(entry_fio.get(),entry_fio2.get(),entry_fio3.get()))

    conn = sqlite3.connect("baza.db")
    c = conn.cursor()


    c.execute("""UPDATE roditel SET
        fio = :fi,
        telefon = :tel
        

        WHERE id_rod = :rod""",
        {
            'fi':entry_fio2.get(),
            'tel':entry_fio3.get(),
            'rod':entry_fio.get(),
        })
    conn.commit()   
    conn.close()
def update4():
    selected = tree4.focus()
    tree4.item(selected, text="",values=(entry_fio.get(),entry_fio2.get(),entry_fio3.get()))

    conn = sqlite3.connect("baza.db")
    c = conn.cursor()

   
    c.execute("""UPDATE mesto SET
        gorod_sluj = :sluj,
        gorod_proj = :proj

        WHERE id_mesto = :mesto""",
        {
            'sluj':entry_fio2.get(),
            'proj':entry_fio3.get(),
            'mesto':entry_fio.get(),
            
        })
    conn.commit()   
    conn.close()
def select():
    global entry_fio,entry_fio2,combobox,entry_vozrast,entry_vozrast2,entry_vozrast3,entry_vozrast4
    entry_fio.delete(0,END)
    entry_fio2.delete(0,END)
    combobox.delete(0,END)
    entry_vozrast.delete(0,END)
    entry_vozrast2.delete(0,END)
    entry_vozrast3.delete(0,END)
    entry_vozrast4.delete(0,END)

    selected = tree1.focus()
    values = tree1.item(selected,'values')

    entry_fio.insert(0,values[0])
    entry_fio2.insert(0,values[1])
    combobox.insert(0,values[2])
    entry_vozrast.insert(0,values[3])
    entry_vozrast2.insert(0,values[4])
    entry_vozrast3.insert(0,values[5])
    entry_vozrast4.insert(0,values[6])

def select2():
    global entry_fio,entry_fio2
    entry_fio.delete(0,END)
    entry_fio2.delete(0,END)


    selected = tree2.focus()
    values = tree2.item(selected,'values')

    entry_fio.insert(0,values[0])
    entry_fio2.insert(0,values[1])

def select3():
    global entry_fio,entry_fio2,entry_fio3
    entry_fio.delete(0,END)
    entry_fio2.delete(0,END)
    entry_fio3.delete(0,END)


    selected = tree3.focus()
    values = tree3.item(selected,'values')

    entry_fio.insert(0,values[0])
    entry_fio2.insert(0,values[1])
    entry_fio3.insert(0,values[2])

def select4():
    global entry_fio,entry_fio2,entry_fio3
    entry_fio.delete(0,END)
    entry_fio2.delete(0,END)
    entry_fio3.delete(0,END)


    selected = tree4.focus()
    values = tree4.item(selected,'values')

    entry_fio.insert(0,values[0])
    entry_fio2.insert(0,values[1])
    entry_fio3.insert(0,values[2])
def search_records():
 
    lookup_record = entry_search.get()

    search.destroy()

    for record in tree1.get_children():
        tree1.delete(record)

    conn = sqlite3.connect("baza.db")
    c = conn.cursor()
    c.execute("SELECT * FROM journal WHERE vozrast = ?",(lookup_record,))
    rows = c.fetchall()
    for row in rows:
        tree1.insert("", tk.END, values=row)

    conn.commit()
    conn.close()
     
def okno_search():
    global entry_search,search
    search = Toplevel()
    search.title('Поиск')
    search.geometry('400x200+400+150')
    search.resizable(False, False)
    search.configure(bg='OliveDrab')

    label2= LabelFrame(search,text='Возраст',bg='OliveDrab',fg='white',font='Arial 20')
    label2.pack(padx=10, pady=10)
    entry_search = Entry(label2)
    entry_search.pack(padx=20, pady=20)
    btn_ok = ttk.Button(search,text='Найти',command=search_records)
    btn_ok.pack(padx=20, pady=20)

def search_records2():
    lookup_record = entry_search.get()
    for record in tree1.get_children():
        tree1.delete(record)

    conn = sqlite3.connect("baza.db")
    c = conn.cursor()
    lookup_record = (lookup_record + '%',)
    c.execute("SELECT * FROM journal WHERE fio like ?",lookup_record,)
                                         
    rows = c.fetchall()
    for row in rows:
        tree1.insert("", tk.END, values=row)
    search.destroy()
    conn.commit()
    conn.close()
     
def okno_search2():
    global entry_search,entry_search2,search,lookup_record
    search = Toplevel()
    search.title('Поиск')
    search.geometry('400x200+400+150')
    search.resizable(False, False)
    search.configure(bg='OliveDrab')

    label2= LabelFrame(search,text='Первая буква имени',bg='OliveDrab',fg='white',font='Arial 20')
    label2.pack(padx=10, pady=10)
    entry_search = Entry(label2)
    entry_search.pack(padx=20, pady=20)
    btn_ok = ttk.Button(search,text='Найти',command=search_records2)
    btn_ok.pack(padx=0, pady=0)
def search_records3():
    
    for record in tree1.get_children():
        tree1.delete(record)

        
    lookup_record = entry_search.get()
    lookup_record2 = entry_search2.get()
    conn = sqlite3.connect("baza.db")
    c = conn.cursor()
    lookup_record = (lookup_record + '%')
    #lookup_record2 = (lookup_record2 + '%')
    result = "SELECT * FROM journal WHERE fio like ? AND vozrast = ?"
    c.execute(result,(lookup_record,lookup_record2))

    rows = c.fetchall()
 
    for row in rows:
        tree1.insert("", tk.END, values=row)
    search.destroy()
    conn.commit()
    conn.close()
    
def okno_search3():
    global entry_search,entry_search2,search,lookup_record
    search = Toplevel()
    search.title('Поиск')
    search.geometry('400x250+400+150')
    search.resizable(False, False)
    search.configure(bg='OliveDrab')

    label2= LabelFrame(search,bg="OliveDrab",text='Первая буква имени',fg='white',font='Arial 15')
    label2.pack(padx=10, pady=10)
    label3= LabelFrame(search,bg="OliveDrab",text='Возраст',fg='white',font='Arial 15')
    label3.pack(padx=10, pady=10)
    entry_search = Entry(label2)
    entry_search.pack(padx=20, pady=20)
    entry_search2 = Entry(label3)
    entry_search2.pack(padx=20, pady=20)
    btn_ok = ttk.Button(search,text='Найти',command=search_records3)
    btn_ok.pack(padx=0, pady=0)



    
def search_records4():
    
    for record in tree1.get_children():
        tree1.delete(record)

        
    lookup_record = entry_search.get()
    lookup_record2 = entry_search2.get()
    conn = sqlite3.connect("baza.db")
    c = conn.cursor()
    #lookup_record = (lookup_record + '%')
    #lookup_record2 = (lookup_record2 + '%')
    result = "SELECT * FROM journal WHERE id_priz BETWEEN ? AND ?"
    c.execute(result,(lookup_record,lookup_record2))

    rows = c.fetchall()
 
    for row in rows:
        tree1.insert("", tk.END, values=row)
        
    search.destroy()
    conn.commit()
    conn.close()


def okno_search4():
    global entry_search,entry_search2,search,lookup_record
    search = Toplevel()
    search.title('Поиск')
    search.geometry('400x250+400+150')
    search.resizable(False, False)
    search.configure(bg='OliveDrab')

    label2= LabelFrame(search,bg="OliveDrab",text='От',fg='white',font='Arial 15')
    label2.pack(padx=10, pady=10)
    label3= LabelFrame(search,bg="OliveDrab",text='До',fg='white',font='Arial 15')
    label3.pack(padx=10, pady=10)
    entry_search = Entry(label2)
    entry_search.pack(padx=20, pady=20)
    entry_search2 = Entry(label3)
    entry_search2.pack(padx=20, pady=20)
    btn_ok = ttk.Button(search,text='Найти',command=search_records4)
    btn_ok.pack(padx=0, pady=0)

def search_records5():
    
    for record in tree2.get_children():
        tree2.delete(record)

        
    lookup_record = entry_search.get()
    #lookup_record2 = entry_search2.get()
    conn = sqlite3.connect("baza.db")
    c = conn.cursor()
    lookup_record = (lookup_record + '%')
    #lookup_record2 = (lookup_record2 + '%')
    result = "SELECT * FROM bolezni WHERE nazvania like ?"
    c.execute(result,(lookup_record,))

    rows = c.fetchall()
 
    for row in rows:
        tree2.insert("", tk.END, values=row)
        
    search.destroy()
    conn.commit()
    conn.close()
def okno_search5():
    
    global entry_search,entry_search2,search,lookup_record
    search = Toplevel()
    search.title('Поиск')
    search.geometry('400x250+400+150')
    search.resizable(False, False)
    search.configure(bg='SpringGreen')

    label2= LabelFrame(search,bg="SpringGreen",text='Первая буква болезни')
    label2.pack(padx=10, pady=10)
    entry_search = Entry(label2)
    entry_search.pack(padx=20, pady=20)

    btn_ok = ttk.Button(search,text='Найти',command=search_records5)
    btn_ok.pack(padx=0, pady=0)


def search_records6():
    
    for record in tree3.get_children():
        tree3.delete(record)

        
    lookup_record = entry_search.get()
    #lookup_record2 = entry_search2.get()
    conn = sqlite3.connect("baza.db")
    c = conn.cursor()
    lookup_record = (lookup_record + '%')
    #lookup_record2 = (lookup_record2 + '%')
    result = "SELECT * FROM roditel WHERE fio like ?"
    c.execute(result,(lookup_record,))

    rows = c.fetchall()
 
    for row in rows:
        tree3.insert("", tk.END, values=row)
        
    search.destroy()
    conn.commit()
    conn.close()
def okno_search6():
    
    global entry_search,entry_search2,search,lookup_record
    search = Toplevel()
    search.title('Поиск')
    search.geometry('400x250+400+150')
    search.resizable(False, False)
    search.configure(bg='SpringGreen')

    label2= LabelFrame(search,bg="SpringGreen",text='Первая буква родителя')
    label2.pack(padx=10, pady=10)
    entry_search = Entry(label2)
    entry_search.pack(padx=20, pady=20)

    btn_ok = ttk.Button(search,text='Найти',command=search_records6)
    btn_ok.pack(padx=0, pady=0)

def search_records7():
    
    for record in tree3.get_children():
        tree3.delete(record)

        
    lookup_record = entry_search.get()
    #lookup_record2 = entry_search2.get()
    conn = sqlite3.connect("baza.db")
    c = conn.cursor()
    lookup_record = ('%' + lookup_record)
    #lookup_record2 = (lookup_record2 + '%')
    result = "SELECT * FROM roditel WHERE telefon like ?"
    c.execute(result,(lookup_record,))

    rows = c.fetchall()
 
    for row in rows:
        tree3.insert("", tk.END, values=row)
        
    search.destroy()
    conn.commit()
    conn.close()
def okno_search7():
    
    global entry_search,entry_search2,search,lookup_record
    search = Toplevel()
    search.title('Поиск')
    search.geometry('400x250+400+150')
    search.resizable(False, False)
    search.configure(bg='SpringGreen')

    label2= LabelFrame(search,bg="SpringGreen",text='Последняя цифра телефона')
    label2.pack(padx=10, pady=10)
    entry_search = Entry(label2)
    entry_search.pack(padx=20, pady=20)

    btn_ok = ttk.Button(search,text='Найти',command=search_records7)
    btn_ok.pack(padx=0, pady=0)
    
def search_records8():
    
    for record in tree4.get_children():
        tree4.delete(record)

        
    lookup_record = entry_search.get()
    #lookup_record2 = entry_search2.get()
    conn = sqlite3.connect("baza.db")
    c = conn.cursor()
    lookup_record = (lookup_record + '%')
    #lookup_record2 = (lookup_record2 + '%')
    result = "SELECT * FROM mesto WHERE gorod_sluj like ?"
    c.execute(result,(lookup_record,))

    rows = c.fetchall()
 
    for row in rows:
        tree4.insert("", tk.END, values=row)
        
    search.destroy()
    conn.commit()
    conn.close()
def okno_search8():
    
    global entry_search,entry_search2,search,lookup_record
    search = Toplevel()
    search.title('Поиск')
    search.geometry('400x250+400+150')
    search.resizable(False, False)
    search.configure(bg='SpringGreen')

    label2= LabelFrame(search,bg="SpringGreen",text='Первая буква города службы')
    label2.pack(padx=10, pady=10)
    entry_search = Entry(label2)
    entry_search.pack(padx=20, pady=20)

    btn_ok = ttk.Button(search,text='Найти',command=search_records8)
    btn_ok.pack(padx=0, pady=0)

def pej() ->None:
        x = root.winfo_x()
        y = root.winfo_y()
        
        height = root.winfo_height()
        width = root.winfo_width()

        image = ImageGrab.grab((x+50,y,x+width,y+height))
        image.save("screen.bmp","BMP")
        os.startfile("screen.bmp","print")

        
def okno2():
    global Button10,Button20,Button30,Button40,Button41,Button42,Button43,Button44,Button45,Button50,Button51,toolbar2,tree1,txt,file_name
    Button11.pack_forget()
    Button22.pack_forget()
    Button33.pack_forget()
    Button44.pack_forget()
    Button55.pack_forget()
    Button66.pack_forget()
    Button77.pack_forget()
    Button88.pack_forget()
    Button99.pack_forget()
    Button00.pack_forget()
    label5.pack_forget()
    label6.pack_forget()
    label7.pack_forget()
    
    toolbar1.pack_forget()
    root.geometry("1000x600+0+0")
    root.title("Журналы")
    root.resizable(False, False)
    root.iconbitmap("jou.ico")
    toolbar2=Frame(root,bg="#d7d8e0")
    toolbar2.pack(side=TOP,fill=X)
    image = ImageTk.PhotoImage(file="add.png")
    image2 = ImageTk.PhotoImage(file="edit.png")
    image3 = ImageTk.PhotoImage(file="delete.png")
    image4 = ImageTk.PhotoImage(file="find.png")
    image5 = ImageTk.PhotoImage(file="back.png")
    image6 = ImageTk.PhotoImage(file="upload.png")
    image7 = ImageTk.PhotoImage(file="find.png")
    image8 = ImageTk.PhotoImage(file="find.png")
    image9 = ImageTk.PhotoImage(file="pej.png")
    image10 = ImageTk.PhotoImage(file="save.png")
    Button10 = tk.Button(toolbar2,text = "Добавить",image=image,compound=TOP,font=("Calibri",11,'bold'),background="#d7d8e0",borderwidth=0,command=okno_add)
    Button10.pack(side=LEFT)
    Button20 = Button(toolbar2,text = "Изменить",image=image2,compound=TOP,font=("Calibri",11,'bold'),background="#d7d8e0",borderwidth=0,command=okno_update)
    Button20.pack(side=LEFT)
    Button30 = Button(toolbar2,text = "Удалить",image=image3,compound=TOP,font=("Calibri",11,'bold'),background="#d7d8e0",borderwidth=0,command=delete)
    Button30.pack(side=LEFT)
    Button40 = Button(toolbar2,text = "Поиск-1",image=image4,compound=TOP,font=("Calibri",11,'bold'),background="#d7d8e0",borderwidth=0,command=okno_search)
    Button40.pack(side=LEFT)
    Button41 = Button(toolbar2,text = "Поиск-2",image=image7,compound=TOP,font=("Calibri",11,'bold'),background="#d7d8e0",borderwidth=0,command=okno_search2)
    Button41.pack(side=LEFT)
    Button42 = Button(toolbar2,text = "Поиск-3",image=image8,compound=TOP,font=("Calibri",11,'bold'),background="#d7d8e0",borderwidth=0,command=okno_search3)
    Button42.pack(side=LEFT)
    Button43 = Button(toolbar2,text = "Поиск-4",image=image8,compound=TOP,font=("Calibri",11,'bold'),background="#d7d8e0",borderwidth=0,command=okno_search4)
    Button43.pack(side=LEFT)
    Button44 = Button(toolbar2,text = "Печать",image=image9,compound=TOP,font=("Calibri",11,'bold'),background="#d7d8e0",borderwidth=0,command=pej)
    Button44.pack(side=LEFT)
    Button45 = Button(toolbar2,text = "Сохранить",image=image10,compound=TOP,font=("Calibri",11,'bold'),background="#d7d8e0",borderwidth=0,command=save)
    Button45.pack(side=LEFT)
    Button51 = Button(toolbar2,text = "Обновить",image=image6,compound=TOP,font=("Calibri",11,'bold'),background="#d7d8e0",borderwidth=0,command=bazaa)
    Button51.pack(side=LEFT)
    Button50 = Button(toolbar2,text = "Обратно",image=image5,compound=TOP,font=("Calibri",11,'bold'),background="#d7d8e0",borderwidth=0,command=lambda:[back2(),okno1()])
    Button50.pack(side=LEFT)

    

    style = ttk.Style()
    style.theme_use("alt")
    style.configure("Treeview",
                    background="PaleGoldenrod",
                    foreground="black",
                    rowheight=30,
                    fieldbackground="silver",
                    font="Arial 12"
                    )
    style.configure("Treeview.Heading",
                    font="Arial 10 bold"
                    )
    
    tree1 = ttk.Treeview(columns=('id_priz', 'fio', 'zvanie', 'vozrast', 'id_bol', 'id_rod', 'id_mesto'), height=30, show='headings')
    tree1.column('id_priz', width=30, anchor=CENTER)
    tree1.column('fio', width=365, anchor=CENTER)
    tree1.column('zvanie', width=100, anchor=CENTER)
    tree1.column('vozrast', width=100, anchor=CENTER)
    tree1.column('id_bol', width=140, anchor=CENTER)
    tree1.column('id_rod', width=100, anchor=CENTER)
    tree1.column('id_mesto', width=150, anchor=CENTER)

    tree1.heading('id_priz', text='Код')
    tree1.heading('fio', text='Ф.И.О')
    tree1.heading('zvanie', text='Звание')
    tree1.heading('vozrast', text='Возраст')
    tree1.heading('id_bol', text='Болезнь')
    tree1.heading('id_rod', text='Родитель')
    tree1.heading('id_mesto', text='Место')
    
    tree1.pack(side=TOP)
    
    bazaa()
    root.mainloop()





def okno3():
    global Button60,Button70,Button80,Button90,Button100,Button101,Button102,toolbar3,tree2
    Button11.pack_forget()
    Button22.pack_forget()
    Button33.pack_forget()
    Button44.pack_forget()
    Button55.pack_forget()
    Button66.pack_forget()
    Button77.pack_forget()
    Button99.pack_forget()
    Button00.pack_forget()
    Button88.pack_forget()
    label5.pack_forget()
    label6.pack_forget()
    label7.pack_forget()
    toolbar1.pack_forget()
    
    root.geometry("1000x600+0+0")
    root.title("Болезни")
    root.iconbitmap("bol.ico")
    toolbar3=Frame(bg="#d7d8e0")
    
    image = ImageTk.PhotoImage(file="add.png")
    image2 = ImageTk.PhotoImage(file="edit.png")
    image3 = ImageTk.PhotoImage(file="delete.png")
    image4 = ImageTk.PhotoImage(file="find.png")
    image5 = ImageTk.PhotoImage(file="back.png")
    image6 = ImageTk.PhotoImage(file="upload.png")
    image7 = ImageTk.PhotoImage(file="pej.png")
    Button60 = Button(toolbar3,text = "Добавить",image=image,compound=TOP,font=("Calibri",11,'bold'),background="#d7d8e0",borderwidth=0,command=okno_add2)
    Button60.pack(side=LEFT)
    Button70 = Button(toolbar3,text = "Изменить",image=image2,compound=TOP,font=("Calibri",11,'bold'),background="#d7d8e0",borderwidth=0,command=okno_update2)
    Button70.pack(side=LEFT)
    Button80 = Button(toolbar3,text = "Удалить",image=image3,compound=TOP,font=("Calibri",11,'bold'),background="#d7d8e0",borderwidth=0,command=delete2)
    Button80.pack(side=LEFT)
    Button90 = Button(toolbar3,text = "Поиск-1",image=image4,compound=TOP,font=("Calibri",11,'bold'),background="#d7d8e0",borderwidth=0,command=okno_search5)
    Button90.pack(side=LEFT)
    Button101 = Button(toolbar3,text = "Обновить",image=image6,compound=TOP,font=("Calibri",11,'bold'),background="#d7d8e0",borderwidth=0,command=bazaa2)
    Button101.pack(side=LEFT)
    Button102 = Button(toolbar3,text = "Печать",image=image7,compound=TOP,font=("Calibri",11,'bold'),background="#d7d8e0",borderwidth=0,command=pej)
    Button102.pack(side=LEFT)
    Button100 = Button(toolbar3,text = "Назад",image=image5,compound=TOP,font=("Calibri",11,'bold'),background="#d7d8e0",borderwidth=0,command=lambda:[back3(),okno1()])
    Button100.pack(side=LEFT)
    toolbar3.pack(side=TOP,fill=X)
    
    style = ttk.Style()
    style.theme_use("alt")
    style.configure("Treeview",
                    background="PaleGoldenrod",
                    foreground="black",
                    rowheight=30,
                    fieldbackground="silver",
                    font="Arial 12"
                    )
    style.configure("Treeview.Heading",
                    font="Arial 10 bold"
                    )
    tree2 = ttk.Treeview(columns=('id_bol', 'nazvania'), height=30, show='headings')
    tree2.column('id_bol', width=235, anchor=CENTER)
    tree2.column('nazvania', width=750, anchor=CENTER)


    tree2.heading('id_bol', text='Код')
    tree2.heading('nazvania', text='Название')

    tree2.pack(side=TOP)
    bazaa2()
    root.mainloop()


def okno4():
    global Button110,Button120,Button130,Button140,Button141,Button150,Button151,Button152,toolbar4,tree3
    Button11.pack_forget()
    Button22.pack_forget()
    Button33.pack_forget()
    Button44.pack_forget()
    Button55.pack_forget()
    Button66.pack_forget()
    Button77.pack_forget()
    Button88.pack_forget()
    Button99.pack_forget()
    Button00.pack_forget()
    label5.pack_forget()
    label6.pack_forget()
    label7.pack_forget()
    toolbar1.pack_forget()
    
    root.geometry("1000x600+0+0")
    root.title("Родители")
    root.resizable(False, False)
    root.iconbitmap("rod.ico")
    toolbar4=Frame(bg="#d7d8e0")
    
    image = ImageTk.PhotoImage(file="add.png")
    image2 = ImageTk.PhotoImage(file="edit.png")
    image3 = ImageTk.PhotoImage(file="delete.png")
    image4 = ImageTk.PhotoImage(file="find.png")
    image5 = ImageTk.PhotoImage(file="back.png")
    image6 = ImageTk.PhotoImage(file="upload.png")
    image7 = ImageTk.PhotoImage(file="pej.png")
    Button110 = Button(toolbar4,text = "Добавить",image=image,compound=TOP,font=("Calibri",11,'bold'),background="#d7d8e0",borderwidth=0,command=okno_add3)
    Button110.pack(side=LEFT)
    Button120 = Button(toolbar4,text = "Изменить",image=image2,compound=TOP,font=("Calibri",11,'bold'),background="#d7d8e0",borderwidth=0,command=okno_update3)
    Button120.pack(side=LEFT)
    Button130 = Button(toolbar4,text = "Удалить",image=image3,compound=TOP,font=("Calibri",11,'bold'),background="#d7d8e0",borderwidth=0,command=delete3)
    Button130.pack(side=LEFT)
    Button140 = Button(toolbar4,text = "Поиск-1",image=image4,compound=TOP,font=("Calibri",11,'bold'),background="#d7d8e0",borderwidth=0,command=okno_search6)
    Button140.pack(side=LEFT)
    Button141 = Button(toolbar4,text = "Поиск-2",image=image4,compound=TOP,font=("Calibri",11,'bold'),background="#d7d8e0",borderwidth=0,command=okno_search7)
    Button141.pack(side=LEFT)
    Button151 = Button(toolbar4,text = "Обновить",image=image6,compound=TOP,font=("Calibri",11,'bold'),background="#d7d8e0",borderwidth=0,command=bazaa3)
    Button151.pack(side=LEFT)
    Button152 = Button(toolbar4,text = "Печать",image=image7,compound=TOP,font=("Calibri",11,'bold'),background="#d7d8e0",borderwidth=0,command=pej)
    Button152.pack(side=LEFT)
    Button150 = Button(toolbar4,text = "Назад",image=image5,compound=TOP,font=("Calibri",11,'bold'),background="#d7d8e0",borderwidth=0,command=lambda:[back4(),okno1()])
    Button150.pack(side=LEFT)
    toolbar4.pack(side=TOP,fill=X)
    style = ttk.Style()
    style.theme_use("alt")
    style.configure("Treeview",
                    background="PaleGoldenrod",
                    foreground="black",
                    rowheight=30,
                    fieldbackground="silver",
                    font="Arial 12"
                    )
    style.configure("Treeview.Heading",
                    font="Arial 10 bold"
                    )
    tree3 = ttk.Treeview(columns=('id_rod', 'fio', 'telefon'), height=30, show='headings')

    tree3.column('id_rod', width=343, anchor=CENTER)
    tree3.column('fio', width=300, anchor=CENTER)
    tree3.column('telefon', width=343, anchor=CENTER)


    tree3.heading('id_rod', text='Код')
    tree3.heading('fio', text='Ф.И.О')
    tree3.heading('telefon', text='Телефон')

    tree3.pack(side=TOP)
    
    
    bazaa3()
    
    root.mainloop()


def okno5():
    global Button160,Button170,Button180,Button190,Button191,Button200,Button201,Button202,toolbar5,tree4
    Button11.pack_forget()
    Button22.pack_forget()
    Button33.pack_forget()
    Button44.pack_forget()
    Button55.pack_forget()
    Button66.pack_forget()
    Button77.pack_forget()
    Button88.pack_forget()
    Button99.pack_forget()
    Button00.pack_forget()
    label5.pack_forget()
    label6.pack_forget()
    label7.pack_forget()
    toolbar1.pack_forget()
    root.geometry("1000x600+0+0")
    root.title("Места")
    root.resizable(False, False)
    root.iconbitmap("mesto.ico")
    toolbar5=Frame(root,bg="#d7d8e0")
    
    image = ImageTk.PhotoImage(file="add.png")
    image2 = ImageTk.PhotoImage(file="edit.png")
    image3 = ImageTk.PhotoImage(file="delete.png")
    image4 = ImageTk.PhotoImage(file="find.png")
    image5 = ImageTk.PhotoImage(file="back.png")
    image6 = ImageTk.PhotoImage(file="upload.png")
    image7 = ImageTk.PhotoImage(file="pej.png")
    Button160 = Button(toolbar5,text = "Добавить",image=image,compound=TOP,font=("Calibri",11,'bold'),background="#d7d8e0",borderwidth=0,command=okno_add4)
    Button160.pack(side=LEFT)
    Button170 = Button(toolbar5,text = "Изменить",image=image2,compound=TOP,font=("Calibri",11,'bold'),background="#d7d8e0",borderwidth=0,command=okno_update4)
    Button170.pack(side=LEFT)
    Button180 = Button(toolbar5,text = "Удалить",image=image3,compound=TOP,font=("Calibri",11,'bold'),background="#d7d8e0",borderwidth=0,command=delete4)
    Button180.pack(side=LEFT)
    Button190 = Button(toolbar5,text = "Поиск-1",image=image4,compound=TOP,font=("Calibri",11,'bold'),background="#d7d8e0",borderwidth=0,command=okno_search8)
    Button190.pack(side=LEFT)
    Button191 = Button(toolbar5,text = "Поиск-2",image=image4,compound=TOP,font=("Calibri",11,'bold'),background="#d7d8e0",borderwidth=0)
    Button191.pack(side=LEFT)
    Button201 = Button(toolbar5,text = "Обновить",image=image6,compound=TOP,font=("Calibri",11,'bold'),background="#d7d8e0",borderwidth=0,command=bazaa4)
    Button201.pack(side=LEFT)
    Button202 = Button(toolbar5,text = "Печать",image=image7,compound=TOP,font=("Calibri",11,'bold'),background="#d7d8e0",borderwidth=0,command=pej)
    Button202.pack(side=LEFT)
    Button200 = Button(toolbar5,text = "Назад",image=image5,compound=TOP,font=("Calibri",11,'bold'),background="#d7d8e0",borderwidth=0,command=lambda:[back5(),okno1()])
    Button200.pack(side=LEFT)
    toolbar5.pack(side=TOP,fill=X)
    style = ttk.Style()
    style.theme_use("alt")
    style.configure("Treeview",
                    background="PaleGoldenrod",
                    foreground="black",
                    rowheight=30,
                    fieldbackground="silver",
                    font="Arial 12"
                    )
    style.configure("Treeview.Heading",
                    font="Arial 10 bold"
                    )
    tree4 = ttk.Treeview(root,columns=('id_mesto', 'gorod_sluj', 'gorod_proj'), height=30, show='headings')

    tree4.column('id_mesto', width=343, anchor=CENTER)
    tree4.column('gorod_sluj', width=300, anchor=CENTER)
    tree4.column('gorod_proj', width=343, anchor=CENTER)


    tree4.heading('id_mesto', text='Код')
    tree4.heading('gorod_sluj', text='Город службы')
    tree4.heading('gorod_proj', text='Город проживания')

    tree4.pack(side=TOP)
    bazaa4()
    root.mainloop()
   

image = ImageTk.PhotoImage(file="pre.png")
image2 = ImageTk.PhotoImage(file="table2.png")
image3 = ImageTk.PhotoImage(file="passo.png")
image4 = ImageTk.PhotoImage(file="avto2.png")

Label1 = Label(width = 70, height = 1, border=5, relief="groove", fg='white' ,bg='OliveDrab',text = "Авторизация",font=("Arial",15,'bold'))
Label1.place(x = -220, y = 10)
Label2 = Label(width = 70, height = 1, fg='white' ,bg='OliveDrab',text = "Введите логин:",font=("Arial",13,'bold'))
Label2.place(x = -145, y = 75)
Label3 = Label(width = 70, height = 1, fg='white' ,bg='OliveDrab',text = "Введите пароль:",font=("Arial",13,'bold'))
Label3.place(x = -145, y = 155)
Button1 = Button(text= "Войти", image=image, width = 100,bg='OliveDrab',fg='white',compound=LEFT,height = 30,border=0,font=("Times New Roman",12,'bold'),command=reg)
Button1.place(x = 145, y =240)

Button3 = Button(image=image3, width = 50,bg='OliveDrab',height = 50,border=0,font=("Arial",12,'bold'))
Button3.place(x = 60, y =175)
Button4 = Button(image=image4, width = 50,bg='OliveDrab',height = 50,border=0,font=("Arial",12,'bold'))
Button4.place(x = 60, y =99)
Entry1 = Entry(bg='OliveDrab',fg='white',border=5,relief="ridge",font=("Arial",12,'bold'))
Entry1.place(x=110, y=110)
Entry2 = Entry(bg='OliveDrab',fg='white',border=5,relief="ridge",font=("Arial",12,'bold'),show='*')
Entry2.place(x=110, y=190)
c2 = Checkbutton(root,text="Показать",bg='OliveDrab',border=0,fg='white',font=("Arial",10,'bold'),command=show)
c2.place(x=310,y=195)



