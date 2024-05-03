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
<li>辞書に対してgetメソッドを積極的に使う</li>
<li>ジェネレータを覚える</li>
<li>デコレータとwith構文を考える</li>  

