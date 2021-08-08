# コーディング規約　 Ver1.0

# Ruby コーディング規約

- インデントは半角スペース 2 個分とする

```
f x > 0
  if y > 0
    puts "x > 0 && y > 0"
  end
end
```

- 一行の桁数は 80 までとする<br>
  超える場合は必ず改行する。プロパティを改行する場合か下記のように記載する
  半角スペース２個を開けて改行する。

```
<%= hoge @fuga,
  id: 'hoge',
  min: 0,
  max: 5,
  title: "hoge",
  colors: ['fff'],
  loading: "Loading...",
  empty:"no data"　%> ⇦とじタグの位置注意
<% end %>
```

- 複数のクラス、メソッドの区切には空行を挿入する。<br>また、クラス内の各構成要素の区切にも空行を挿入する。 ただし、最初の構成要素の前や、最後の構成要素の後には空行は挿入しない。

#### 例

```
class Foo
  attr :bar

  def baz
    ...
  end

  def quux
    ..
  end
end
```

#### 誤った例

```
class Foo

  attr :bar

  def baz
    ...
  end

  def quux
    ...
  end

end
```

- メソッド定義の仮引数リストには括弧を付ける。 ただし、引数がない場合は、括弧を省略する。<br>

#### 例

```
def foo(x, y)
  ...
end

def foo
  ...
end
```

#### 誤った例

```
def foo x, y
  ...
end

def foo()
  ...
end
```

- メソッドの値を返す場合は、必ず return を使用する。 また、return の括弧は省略する。

#### 例

```
def add(x, y)
  return x + y
end
```

#### 誤った例

```
def add(x, y)
  x + y
end

def add(x, y)
  return(x + y)
end
```

- if 式の then は省略する。また、if !x のような場合は、 unless x に置き換える。ただし、unless の場合、 else は使用しない。また、条件が十分に簡単で、一行で書ける場 合は、if/while 修飾子を使用してもよい。

#### 例

```
if x > 0
  puts "x > 0"
else
  puts "x <= 0"
end

unless x
  puts "x is false"
end

puts "x is true" if x
```

#### 誤った例

```
if x > 0 then
  puts "x > 0"
end

unless x
  puts "x is false"
else
  puts "x is true"
end

puts "foo && bar && baz && quux" if foo &&
  bar && baz && quux
```

- case を使用できる場合は、case を使用する。 また、then は省略する。

#### 例

```
case x
when 1
  ...
when 2
  ...
end
```

#### 誤った例

```
if x == 1
  ...
elsif x == 2
  ...
end

case x
when 1 then
  ...
when 2 then
  ...
end
```

#Rails コーディング規約

- 配列：代入の後ろに配列リテラルを複数行で書く場合は、[ の後ろで改行し、要素行のインデントを 1 レベル下げ、] は独立した行に置いて [ を書いた行の行頭にインデントを揃える。

#### 例

```
array = [
  :foo, # インデントレベルを1下げる（半角スペース2個分）
  :bar,
  :baz,
] # array行に揃える
```

#### 誤った例

```
array = [ :foo,
          :bar,
          :baz, ]

array = [ :foo,
          :bar,
          :baz,
        ]

array = [
  :foo,
  :bar,
  :baz, ]
```

- private や protected や public を引数なしで使用する場合、インデントレベルはメソッド定義と同じレベルとし、前後に 1 行ずつ空白を入れること。

#### 例

```
class Foo
  def foo
  end

  private

  def bar
  end
end
```

誤った例

```
class Foo
  def foo
  end

private

  def bar
  end
end


class Foo
  def foo
  end

  private

    def bar
    end
end


class Foo
  def foo
  end

  private
  def bar
  end
end
```
