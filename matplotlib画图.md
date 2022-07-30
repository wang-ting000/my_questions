> plt.ginput(n)可以获取n个鼠标点击的坐标值   
>> plt.ginput(0,0)可以一直点击鼠标左键直至点击中键结束；第二个参数0就是阻止timeout = 30的
> 显示中文：  
>> plt.rcParams['font.sans-serif']=['SimHei'] #用来正常显示中文标签
>>plt.rcParams['axes.unicode_minus']=False #用来正常显示负号

> `plt.title(r'$1/\lambda$'"=%s"%(lam_rec))`在标题显示变量以及希腊字母  
> 横纵坐标等比例的方法：
>>```python
>>ax = plt.gca()
>>ax.set_aspect(1)
>>```
