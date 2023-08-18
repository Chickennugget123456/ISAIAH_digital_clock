# ISAIAH_digital_clock
A clock that shows time basic digital clock
import tkinter as tk
import datetime
import time

from time import strftime
from datetime import datetime
import pytz

def update_time():
    central_time = datetime.now(pytz.timezone('US/Central'))
    current_time = central_time.strftime('%I:%M %p')

    time_label.config(text = current_time)
    time_label.after(1000, update_time) # Update every 1000ms (1 second)
  
# Create the main window
window = tk.Tk()
window.title('Simple Digital Clock')

# Create a label to display the time
time_label = tk.Label(window, font=('Helvetica', 48), bg='black', fg='white')
time_label.pack(padx=20, ipady=20)

#Start updating the time
update_time()
# Run the GUI event loop
window.mainloop
