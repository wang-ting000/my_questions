1. **迭代器协议**  

* 对象需要提供next方法，它要么返回迭代中的下一项，要么就引起一个StopIteration异常，以终止迭代  
* 可迭代对象：实现了__iter__方法；迭代器对象：还实现了__next__()方法 
* Python的内置工具(如`for循环，sum，min，max函数`等)使用迭代器协议访问对象  

2. **生成器**  

* 优点：`有延迟操作，在需要的时候才会输出结果，对于大数据量的运算有优势(节约内存)`
* 提供生成器的方式：  

     * **生成器函数**:常规函数定义，使用**yield**函数返回结果，一次返回一个结果，下次继续执行  

        ```python
        def gensquares(N):
            for i in range(N):
                yield i**2
        
        for item in gensquares(4):
            print(item,)
    
        ```
     * **生成器表达式**:类似于列表推导，但是返回按需产生结果的一个对象  
     *列表推导式*  
     
     ```python
     squares=[i**2 for i in range(4)]
     ```
     *生成器表达式*  
     
     ```python
     squares=(i**2 for i in range(4))
     next(squares)
     list(squares)
     ```
     
* **注意事项：生成器只能迭代一次**  

3. **拷贝**  

* `浅拷贝`:只拷贝父对象，不拷贝子对象  `c=copy.copy(a)`
* `深拷贝`:拷贝对象及其子对象  `d=copy.deepcopy(a)`
* `指针引用`:赋值 b=a

4. **JSON**  

* `JSON(JavaScript Object Notation) 是一种轻量级的数据交换格式，易于人阅读和编写`  


* `json.dumps`:将python对象编码成JSON字符串  


* `json.loads`:将已编码的 JSON 字符串解码为 Python 对象  

5. **itertools**  

* 无穷迭代器  

    * `itertolls.count`:是一个计数器,可以指定起始位置和步长
            ```python
            x=itertools.count(start=20,step=-1)
            print(list(itertools.islice(x,1,100,1)))
            ```
    * `itertools.cycle`:循环指定的列表和迭代式
            ```python
            x=itertools.cycle('wangting')
            print(list(itertools.islice(x,0,30,1)))
            ```
    * `itertools.repeat`:生成一个拥有指定数目元素的迭代器
            ```python
            x=itertools.repeat('k',3)
            print(list(x))
            ```
            
* 根据最短输入序列长度停止的迭代器  
     
    * `itertools.accumulate`:累加  
            ```python
            x=itertools.accumulate(range(10))
            print(list(x))
            ```
    * `itertools.chain`:连接多个列表或迭代器
            ```python
            x=itertools.chain([1,2,3],[2,3,4])
            print(list(x))
            ```
    * `itertools.compress`:按真值表筛选元素
            ```python
            x=itertools.compress(range(3),(True,False,False))
            print(list(x)) 
     * `itertools.dropwhile`:按照真值函数丢弃掉列表和迭代器前面的元素  
            ```python
            x=itertools.dropwhile(lambda e:e<5,range(10))
            print(list(x))
            ```
     * `itertools.filterfalse`:保留对应真值为False的元素  
            ```python
            x = itertools.filterfalse(lambda e: e < 5, (1, 5, 3, 6, 9, 4))
            ```
     * `itertools.groupby`:按照分组函数的值对元素进行分组  
            ```python
               x = itertools.groupby(range(10), lambda x: x < 5 or x > 8)                                                                                                 
               for condition, numbers in x:                                                  
               print(condition, list(numbers))                                                                                                        
            ```  
      * `itertools.islice`:切片
      * `itertools.starmap`:类似于map
            ```python
            x = itertools.starmap(str.islower, 'aBCDefGhI')
            ```
      * `itertools.takewhile`:与dropwhile相反
            ```python
            x = itertools.takewhile(lambda e: e < 5, range(10))
            ```
      * `itertools.tee`:将一个迭代器拆成多个
      
            ```python
            x = itertools.tee(range(10), 4)
            ```
      * `itertools.zip_longest`:类似于zip，不过已较长的列表和迭代器的长度为准
            ```python
            类似于zip，不过已较长的列表和迭代器的长度为准
            ```
      
* 排列组合迭代器

    * `itertools.product`:产生多个列表和迭代器的(积)
    ```python
    x = itertools.product('ABC', range(3))
    ```
    * `itertools.permutations`:产生指定数目的元素的所有排列(顺序有关)
    ```python
    permutations('ABCD', 2)
    ```
    * `itertools.combinations`:有序，无重复元素
    * `itertools.combinations_with_replacement`:有序，有重复元素
                
        
