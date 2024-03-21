# Decorator範例
## 程式碼
```python
def a(func):
    print("This is decorator.")
    return func

@a
def b():
    print("This is b.")

b()
```

## 結果
```
This is decorator.
This is b.
```
