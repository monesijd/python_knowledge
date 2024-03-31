# Decorator

> ## 將函數傳入my_decorator中，進行函式的功能預先處理
> > ### 程式碼
> ```python
> def my_decorator(func):
>     print("This is decorator.")
>     return func
> 
> @my_decorator
> def b():
>     print("This is b.")
> 
> b()
> ```
> 
> > ### 執行結果
> ```python
> This is decorator.
> This is b.
> ```

* * *

> ## 裝飾子可透過回傳封包含式的方式，達到預處理函式的作用
> ### 下列為將mysleep函式透過timeit處理，透過wrapper封裝，得到mysleep的執行時間
> > ### 程式碼
> ```python
> import time
> def timeit(func):
>     def wrapper():
>         s = time.time()
>         func()
>         print(func.__name__, 'total time', time.time() - s)
>     return wrapper
>
> @timeit
> def mysleep():
>     time.sleep(10)
> 
> mysleep() 
> ```
>
> > ### 執行結果(會先等10秒再輸出)
> ```python
> mysleep total time 10.000132083892822
> ```
