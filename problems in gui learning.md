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
