## gui窗口不能在pycharm/spyder中显示的解决方法

 在**代码文件**中运行gui程序的时候，必须要在末尾加上如下代码：
 

```python
tk.mainloop()
```
说明来自[RealPython教程](https://realpython.com/python-gui-tkinter/#building-your-first-python-gui-application-with-tkinter)

## 笔记：widgets

Label	显示文本
Button	可显示文字并且触发动作
Entry	允许输入一行文字
Text	允许输入多行文字
Frame	用于将相关小部件分组或在小部件之间提供填充的矩形区域
