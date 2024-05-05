# コードをきれいに書くコツ
### 内包表記をマスターする
for文とか使って数行にするよりも実行速度も速くて、コードもきれい。最強  
内包表記にも種類はあってよく使われるのはリスト内包表記、辞書内包表記、セット内包表記  
全部書き方は基本的には一緒  
d = [式 for 任意の変数 in 反復可能オブジェクト] みたいな感じで構成されてる  
場合によってはオブジェクトの後にif文があったりもして条件式が追加できる  

**リスト内包表記**  
d = [式 for 任意の変数 in 反復可能オブジェクト]

```python:list_comprehension.py
#リスト内包表記
squares = [i**2 for i in range(5)]
print(squares)
# [0, 1, 4, 9, 16]
```

```python:for_comprehension.py
#for文の場合
squares = []
for i in range(5):
    squares.append(i**2)

print(squares)
# [0, 1, 4, 9, 16]
```


**辞書内包表記**  
d = {キー:式 for 任意の変数 in 反復可能オブジェクト}  

```python:dict_comprehension.py
#辞書内包表記
human = ["john", "alice", "mike"]
people = {s:i for i, s in enumerate(human)}
print(people)
# {'john': 0, 'alice': 1, 'mike': 2}
```

**セット内包表記**  
d = {式 for 任意の変数 in 反復可能オブジェクト}  

```python:set_comprehension.py
#辞書内包表記
squares = {i**2 for i in range(5)}
print(squares)
# {0, 1, 4, 9, 16}
```
### 辞書に対してgetメソッドを積極的に使う</li>
辞書に存在しないキーを指定するとエラーが起こるのでgetメソッドを利用してエラーを未然に防ごう。また、第２引数に文字を指定するとデフォルト値を変更することもできる。ちなみにデフォルト値はNoneだ。

```python:get_method.py
d = {'key1': 'val1', 'key2': 'val2', 'key3': 'val3'}

print(d.get('key1'))
# val1

print(d.get('key4'))
# None

print(d.get('key4', 'NO_KEY'))
# NO_KEY

p1rint(d('key4'))
# TypeError: 'dict' object is not callable
```
### ジェネレータを覚える
##### そもそもジェネレータって？
関数の処理の途中で一度処理を中断することができる。また、再開もできる  
##### なぜ使うのか
ジェネレータの最大の利点は、メモリ効率性。ジェネレータは全ての結果をメモリに保持しないため、大規模なデータを扱う際に役立つ。また、結果が必要となるまで計算を遅延するため、パフォーマンスの向上にも期待できる。

```python:generate.py
def gen():
    while True: 　　　　　　#無限ループ
        yield "start"
        yield "middle"
        yield "end" 

gen_obj = gen()
print(next(gen_obj),end=" ")
print(next(gen_obj),end=" ")
print(next(gen_obj),end=" ")
print(next(gen_obj),end=" ")
# start middle end start
```
このように無限ループしているはずなのにエラーが起きない！！


<li>デコレータとwith構文を考える</li>  

