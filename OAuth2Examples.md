from tkinter import *
from tkinter import messagebox
from PIL import Image, ImageTk  # Importing PIL for better image support

class Dashboard1:
    def __init__(self, window):
        self.window = window
        self.window.title('DTRLM-Dashboard') 
        self.window.geometry('1366x768')
        self.window.state('zoomed')
        self.window.config(background='#eff5f6')
                
        # Header
        self.header = Frame(self.window, bg='#009df4')
        self.header.place(x=300, y=0, width=1070, height=60)
        self.logout_text = Button(self.header, text='Logout', bg='#32cf8e', font=("", 13, "bold"), bd=0, fg='white', cursor='hand2', activebackground='#32cf8e')
        self.logout_text.place(x=950, y=15)
        
        # Sidebar
        self.sidebar = Frame(self.window, bg='#ffffff')
        self.sidebar.place(x=0, y=0, width=300, height=750) 
        
        # Body
        self.heading = Label(self.window, text='DTRLM-Centreline', font=("", 13, "bold"), fg='#0064d3', bg='#eff5f6')
        self.heading.place(x=325, y=70)
        
        # Body Frame 1
        self.bodyFrame1 = Frame(self.window, bg='#ffffff')
        self.bodyFrame1.place(x=328, y=110, width=1040, height=640)
        # Dashboard
        self.dashboard_text = Button(self.sidebar, text='1. Track Alignment and Geometry', bg='#ffffff', font=("", 10, "bold"), bd=0, cursor='hand2', activebackground='#ffffff')
        self.dashboard_text.place(x=10, y=189)
        self.dashboard_text = Button(self.sidebar, text='1.1 Centreline', bg='#ffffff', font=("", 10, "bold"), bd=0, cursor='hand2', activebackground='#ffffff')
        self.dashboard_text.place(x=50, y=229)
         # Track Alignment Content
        self.alignment_info = Label(self.window, text="Track Centreline", font=("", 12, "bold"), fg='#0064d3', bg='#eff5f6')
        self.alignment_info.place(x=1100, y=100)
        
        self.alignment_content = Label(self.window, text="Track Centreline refers to the straightness or curvature of the track. The alignment of the track affects the comfort of passengers, the stability of freight, and the wear and tear on rolling stock and infrastructure. There are three main types of alignment: straight, curved, and transition curves.", font=("", 10), justify=LEFT, wraplength=250, fg='#000000', bg='#eff5f6')
        self.alignment_content.place(x=1100, y=130)
        # Length Dropdown
        self.length_label = Label(self.bodyFrame1, text="Length:", font=("", 10, "bold"), bg='#ffffff')
        self.length_label.place(x=10, y=10)

        self.length_var = StringVar()
        self.length_var.set("Select")
        self.length_dropdown = OptionMenu(self.bodyFrame1, self.length_var, "CM", "MM")
        self.length_dropdown.place(x=80, y=10)

        # Length Entry
        self.length_entry = Entry(self.bodyFrame1, font=("", 10))
        self.length_entry.place(x=240, y=10)

        # Width Dropdown
        self.width_label = Label(self.bodyFrame1, text="Width:", font=("", 10, "bold"), bg='#ffffff')
        self.width_label.place(x=10, y=50)

        self.width_var = StringVar()
        self.width_var.set("Select")
        self.width_dropdown = OptionMenu(self.bodyFrame1, self.width_var, "CM", "MM")
        self.width_dropdown.place(x=80, y=50)

        # Width Entry
        self.width_entry = Entry(self.bodyFrame1, font=("", 10))
        self.width_entry.place(x=240, y=50)

        # Latitude Dropdown
        self.latitude_label = Label(self.bodyFrame1, text="Latitude:", font=("", 10, "bold"), bg='#ffffff')
        self.latitude_label.place(x=10, y=90)

        self.latitude_var = StringVar()
        self.latitude_var.set("Select")
        self.latitude_dropdown = OptionMenu(self.bodyFrame1, self.latitude_var, "DD", "DMS", "DMM")
        self.latitude_dropdown.place(x=80, y=90)

        # Latitude Entry
        self.latitude_entry = Entry(self.bodyFrame1, font=("", 10))
        self.latitude_entry.place(x=240, y=90)

        # Longitude Dropdown
        self.longitude_label = Label(self.bodyFrame1, text="Longitude:", font=("", 10, "bold"), bg='#ffffff')
        self.longitude_label.place(x=10, y=130)

        self.longitude_var = StringVar()
        self.longitude_var.set("Select")
        self.longitude_dropdown = OptionMenu(self.bodyFrame1, self.longitude_var, "DD", "DMS", "DMM")
        self.longitude_dropdown.place(x=80, y=130)

        # Longitude Entry
        self.longitude_entry = Entry(self.bodyFrame1, font=("", 10))
        self.longitude_entry.place(x=240, y=130)


        # Load Image and Display it in Dashboard1
        image_path = "C:/Users/jampana.jyothi21/OneDrive/Pictures/Screenshots/Screenshot 2024-04-22 123158.png"
        self.img = Image.open(image_path)
        self.tk_img = ImageTk.PhotoImage(self.img)
        self.image_label = Label(self.bodyFrame1, image=self.tk_img)
        self.image_label.place(x=300, y=300)  # Change x, y based on your needs
        
        # Adding the rest of the widgets...
        # Example of a Next Button
        next_button = Button(self.bodyFrame1, text='NEXT', bg='#32cf8e', font=("", 13, "bold"), bd=0, fg='white', cursor='hand2', activebackground='#32cf8e', command=self.go_to_Dashboard2)
        next_button.place(x=50, y=200)
        
    def go_to_Dashboard2(self):
        self.window.destroy()
        win = Tk()
        Dashboard2(win)
        win.mainloop()

# Placeholder for Dashboard2 and Dashboard3 classes with minimal content

class Dashboard2:
    def __init__(self, window):
        self.window = window
        self.window.title('DTRLM-Dashboard') 
        self.window.geometry('1366x768')
        self.window.state('zoomed')
        self.window.config(background='#eff5f6')
        
        # Header
        self.header = Frame(self.window, bg='#009df4')
        self.header.place(x=300, y=0, width=1070, height=60)
        
        # SideBar
        self.sidebar = Frame(self.window, bg='#ffffff')
        self.sidebar.place(x=0, y=0, width=300, height=750) 

        # Body
        self.heading = Label(self.window, text='DTRLM-Centreline', font=("", 13, "bold"), fg='#0064d3', bg='#eff5f6')
        self.heading.place(x=325, y=70)

        # Body Frame 1
        self.bodyFrame1 = Frame(self.window, bg='#ffffff')
        self.bodyFrame1.place(x=328, y=110, width=1040, height=640)
        
        # Dashboard
        self.dashboard_text = Button(self.sidebar, text='1. Track Alignment and Geometry', bg='#ffffff', font=("", 10, "bold"), bd=0, cursor='hand2', activebackground='#ffffff')
        self.dashboard_text.place(x=10, y=189)
        self.dashboard_text = Button(self.sidebar, text='1.1 Centreline', bg='#ffffff', font=("", 10, "bold"), bd=0, cursor='hand2', activebackground='#ffffff')
        self.dashboard_text.place(x=50, y=229)
         # Track Alignment Content
        self.alignment_info = Label(self.window, text="Track Centreline", font=("", 12, "bold"), fg='#0064d3', bg='#eff5f6')
        self.alignment_info.place(x=1100, y=100)
        
        self.alignment_content = Label(self.window, text="Track Centreline refers to the straightness or curvature of the track. The alignment of the track affects the comfort of passengers, the stability of freight, and the wear and tear on rolling stock and infrastructure. There are three main types of alignment: straight, curved, and transition curves.", font=("", 10), justify=LEFT, wraplength=250, fg='#000000', bg='#eff5f6')
        self.alignment_content.place(x=1100, y=130)
       # Length Dropdown
        self.length_label = Label(self.bodyFrame1, text="Length:", font=("", 10, "bold"), bg='#ffffff')
        self.length_label.place(x=10, y=10)

        self.length_var = StringVar()
        self.length_var.set("Select")
        self.length_dropdown = OptionMenu(self.bodyFrame1, self.length_var, "CM", "MM", command=self.update_length_entry)
        self.length_dropdown.place(x=80, y=10)

        # Length Entry
        self.length_entry = Entry(self.bodyFrame1, font=("", 10))
        self.length_entry.place(x=240, y=10)

        # Width Dropdown
        self.width_label = Label(self.bodyFrame1, text="Width:", font=("", 10, "bold"), bg='#ffffff')
        self.width_label.place(x=10, y=50)

        self.width_var = StringVar()
        self.width_var.set("Select")
        self.width_dropdown = OptionMenu(self.bodyFrame1, self.width_var, "CM", "MM", command=self.update_width_entry)
        self.width_dropdown.place(x=80, y=50)

        # Width Entry
        self.width_entry = Entry(self.bodyFrame1, font=("", 10))
        self.width_entry.place(x=240, y=50)

        # Latitude Dropdown
        self.latitude_label = Label(self.bodyFrame1, text="Latitude:", font=("", 10, "bold"), bg='#ffffff')
        self.latitude_label.place(x=10, y=90)

        self.latitude_var = StringVar()
        self.latitude_var.set("Select")
        self.latitude_dropdown = OptionMenu(self.bodyFrame1, self.latitude_var, "DD", "DMS", "DMM", command=self.update_latitude_entry)
        self.latitude_dropdown.place(x=80, y=90)

        # Latitude Entry
        self.latitude_entry = Entry(self.bodyFrame1, font=("", 10))
        self.latitude_entry.place(x=240, y=90)

        # Longitude Dropdown
        self.longitude_label = Label(self.bodyFrame1, text="Longitude:", font=("", 10, "bold"), bg='#ffffff')
        self.longitude_label.place(x=10, y=130)

        self.longitude_var = StringVar()
        self.longitude_var.set("Select")
        self.longitude_dropdown = OptionMenu(self.bodyFrame1, self.longitude_var, "DD", "DMS", "DMM", command=self.update_longitude_entry)
        self.longitude_dropdown.place(x=80, y=130)

        # Longitude Entry
        self.longitude_entry = Entry(self.bodyFrame1, font=("", 10))
        self.longitude_entry.place(x=240, y=130)

        
        # Previous Button
        previous_button = Button(self.bodyFrame1, text='Previous', bg='#32cf8e', font=("", 13, "bold"), bd=0, fg='white', cursor='hand2', activebackground='#32cf8e', command=self.go_to_Dashboard1)
        previous_button.place(x=50, y=200)
        
        # Submit Button
        submit_button = Button(self.bodyFrame1, text="Submit", bg='#32cf8e', font=("", 13, "bold"), bd=0, fg='white', cursor='hand2', activebackground='#32cf8e', command=self.go_to_Dashboard3)
        submit_button.place(x=250, y=200)

    def update_length_entry(self, value):
        if value != "Select":
            self.length_entry.delete(0, END)
            self.length_entry.insert(0, value)

    def update_width_entry(self, value):
        if value != "Select":
            self.width_entry.delete(0, END)
            self.width_entry.insert(0, value)

    def update_latitude_entry(self, value):
        if value != "Select":
            self.latitude_entry.delete(0, END)
            self.latitude_entry.insert(0, value)

    def update_longitude_entry(self, value):
        if value != "Select":
            self.longitude_entry.delete(0, END)
            self.longitude_entry.insert(0, value)

    def go_to_Dashboard1(self):
        self.window.destroy()
        win = Tk()
        Dashboard1(win)
        win.mainloop()

    def go_to_Dashboard3(self):
        self.window.destroy()
        win = Tk()
        Dashboard3(win)
        win.mainloop()


class Dashboard3:
    def __init__(self, window):
        self.window = window
        self.window.title('DTRLM-Dashboard') 
        self.window.geometry('1366x768')
        self.window.state('zoomed')
        self.window.config(background='#eff5f6')
        
        # Header
        self.header = Frame(self.window, bg='#009df4')
        self.header.place(x=300, y=0, width=1070, height=60)
        
        # SideBar
        self.sidebar = Frame(self.window, bg='#ffffff')
        self.sidebar.place(x=0, y=0, width=300, height=750) 

        # Body
        self.heading = Label(self.window, text='DTRLM-Centreline', font=("", 13, "bold"), fg='#0064d3', bg='#eff5f6')
        self.heading.place(x=325, y=70)
          
        # Body Frame 1
        self.bodyFrame1 = Frame(self.window, bg='#ffffff')
        self.bodyFrame1.place(x=328, y=110, width=1040, height=640)
        
        # Dashboard
        self.dashboard_text = Button(self.sidebar, text='1. Track Alignment and Geometry', bg='#ffffff', font=("", 10, "bold"), bd=0, cursor='hand2', activebackground='#ffffff')
        self.dashboard_text.place(x=10, y=189)
        self.dashboard_text = Button(self.sidebar, text='1.1 Centreline', bg='#ffffff', font=("", 10, "bold"), bd=0, cursor='hand2', activebackground='#ffffff')
        self.dashboard_text.place(x=50, y=229)
        
        # Success message
        self.success_label = Label(self.bodyFrame1, text='Success!! Your Request in Track Alignment and Geometry\nis Submitted Successfully.', font=("", 12, "bold"), fg='#006400', bg='#ffffff')
        self.success_label.place(relx=0.5, rely=0.5, anchor=CENTER)
        ++++
    def go_to_Dashboard1(self):
        self.window.destroy()
        win = Tk()
        Dashboard1(win)
        win.mainloop()


if __name__ == "__main__":
    root = Tk()
    Dashboard1(root)
    root.mainloop()

