> plt.ginput(n)可以获取n个鼠标点击的坐标值   
>> plt.ginput(0,0)可以一直点击鼠标左键直至点击中键结束；第二个参数0就是阻止timeout = 30的
> 显示中文：  
>> plt.rcParams['font.sans-serif']=['SimHei'] #用来正常显示中文标签
>>plt.rcParams['axes.unicode_minus']=False #用来正常显示负号
