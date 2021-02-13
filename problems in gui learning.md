## gui窗口不能在pycharm/spyder中显示的解决方法

 在**代码文件**中运行gui程序的时候，必须要在末尾加上如下代码：
 

```python
tk.mainloop()
```
说明来自[RealPython教程](https://realpython.com/python-gui-tkinter/#building-your-first-python-gui-application-with-tkinter)

## 笔记：widgets

>**Label**	显示文本
>> 修改样式:  
>>>label = tk.Label(
>>>text="Hello, Tkinter",  
>>>foreground="white",  # Set the text color to white  
>>>background="black"  # Set the background color to black)
>>[htmlcolors](https://htmlcolorcodes.com/color-names/)


>**Button**	可显示文字并且触发动作


>**Entry**	允许输入一行文字
>>entry.delete()，删除的是列表  
>>entry.insert(),加入位置信息和内容  
>>entry.get()，获取一行的内容


>**Text**	允许输入多行文字
>>text.get("<line>.<char>"),换行符也在其中，删除时应当注意  
>>text.delete()    
>>text.insert()


>**Frame**	用于将相关小部件分组或在小部件之间提供填充的矩形区域  
>>border_effects = {  
>>"flat": tk.FLAT,  
>>"sunken": tk.SUNKEN,  
>>"raised": tk.RAISED,  
>>"groove": tk.GROOVE,  
>>"ridge": tk.RIDGE,  
>>}  
>>window = tk.Tk()  
>>for relief_name, relief in border_effects.items():  
>>frame = tk.Frame(master=window, relief=relief, borderwidth=5)  
>>frame.pack(side=tk.LEFT)  
>>label = tk.Label(master=frame, text=relief_name)  
>>label.pack()



## 笔记:Geometry Manager
>.pack()
>>fill=tk.X,tk.Y,tk.BOTH
>>side=tk.TOPtk.LEFT,tk.RIGHT,tk.BOTTOM
>.place()
>>原点在左上角
>>x=,y=
>.grid
>>row=,colum=
>>sticky=n,s,e,w

## 笔记:event handler
>window.mainloop()检测是否有event 的发生，而发生后执行的函数称为event handler  
>event_list保存event objects
>>import tkinter as tk  
>>Create a window object
>>window = tk.Tk()

>>Create an event handler
>>def handle_keypress(event):  
>>"""Print the character associated to the key pressed"""
 >>print(event.char)

>>Run the event loop
>>window.mainloop()


>**使用.bind()将handler_keypress和key press event 绑定**  
>>window.bind("<Key>", handle_keypress)  
>>[event types](https://web.archive.org/web/20190512164300/http://infohost.nmt.edu/tcc/help/pubs/tkinter/web/event-types.html)

    import tkinter as tk
    window = tk.Tk()
    def handle_click(event):
        print('the button was clicked')

    button = tk.Button(text='click me')
    button.pack()
    button.bind("<Button-1>",handle_click)
    window.mainloop()

>**使用.command()**
>>获取Label的text
>>>text = label["text"]
>>重新赋予Label一个text：
>>>label["text"] = "Good bye"
```
import tkinter as tk

window = tk.Tk()

def increase():
    value = int(lbl_value["text"])
    lbl_value["text"] = f"{value + 1}"

def decrease():
    value = int(lbl_value["text"])
    lbl_value["text"] = f"{value - 1}"



window.rowconfigure(0, minsize=50, weight=1)
window.columnconfigure([0, 1, 2], minsize=50, weight=1)

btn_decrease = tk.Button(master=window, text="-",command=decrease)
btn_decrease.grid(row=0, column=0, sticky="nsew")

lbl_value = tk.Label(master=window, text="0")
lbl_value.grid(row=0, column=1)

btn_increase = tk.Button(master=window, text="+",command=increase)
btn_increase.grid(row=0, column=2, sticky="nsew")

window.mainloop()
```

## 笔记：更多的widgets
>Checkbutton()
>Radiobutton()
>combobox

 
