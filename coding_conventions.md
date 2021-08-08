### コーディング規約

*インデントは半角スペース2個分とする
```
f x > 0
  if y > 0
    puts "x > 0 && y > 0"
  end
end
```

*一行の桁数は80までとする。
*複数のクラス、メソッドの区切には空行を挿入する。
```例
def Foo
  ...
end

def Bar
  ...
end
```

```誤った例
def Foo
  ...
end
def Bar
  ...
end
```
