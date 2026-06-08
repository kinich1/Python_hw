# Задание 28677 (Тип 2)
<img width="1449" height="361" alt="image" src="https://github.com/user-attachments/assets/bf77a992-2742-4a71-bb72-651a56968818" />

**Решение:**
~~~
print('x y z w')
for x in range(0, 2):
    for y in range(0, 2):
        for z in range(0, 2):
            for w in range(0, 2):
                if ((x <= y) or (y == w)) and ((x or z) == w):
                    print(x, y, z, w)
~~~
**Ответ: zyxw**

# Задание 18808 (Тип 2)
<img width="1444" height="435" alt="image" src="https://github.com/user-attachments/assets/2469c8e3-65d8-4d41-869d-6b503d52ce35" />

**Решение:**

~~~
print('x y z w')
for x in range(0, 2):
    for y in range(0, 2):
        for z in range(0, 2):
            for w in range(0, 2):
                if not ((x and not y) or (y == z) or w):
                    print(x, y, z, w)
~~~
**Ответ: yxwz**

# Задание 3697 (Тип 8)
<img width="1029" height="185" alt="image" src="https://github.com/user-attachments/assets/f3d1f7fa-f7ba-4b44-9b23-109a943665fb" />

**Решение:**
~~~
word = 'ВИНТ'
x = 0
for x1 in range (0, len(word)):
    for x2 in range (0, len(word)):
        for x3 in range (0, len(word)):
            for x4 in range (0, len(word)):
                for x5 in range (0, len(word)):
                    x += 1
                    if x == 1019:
                        print(word[x1], word[x2], word[x3], word[x4], word[x5])
~~~
**Ответ: Н Н Н Т Т**

# Задание 56536 (Тип 8)
<img width="769" height="32" alt="image" src="https://github.com/user-attachments/assets/69e67a40-50ac-4870-a4be-d57b7b78238b" />

**Решение:**
~~~
# Импортируем все функции из модуля itertools (например, product для декартова произведения)
from itertools import *
# Счётчик шаблонов, у которых первая цифра нечётная ('Н')
cnt1 = 0
# Счётчик шаблонов, у которых первая цифра чётная ('Ч')
cnt2 = 0
# Перебираем все возможные строки (кортежи) длины 12 из символов 'Н' и 'Ч'
# product('НЧ', repeat=12) генерирует 2^12 = 4096 комбинаций
for i in product('НЧ', repeat = 12):
    # Преобразуем кортеж символов в строку (например, ('Н','Ч','Н',...) -> "НЧН...")
    p = ''.join(i)
    # Условие для шаблонов, начинающихся с 'Н':
    # p[0]=='Н' — первая цифра нечётная
    # p.count('Н')==3 — ровно три позиции с 'Н' (нечётные цифры)
    # p.count('НН')==0 — нет двух 'Н' подряд (никакие две нечётные не стоят рядом)
    if p[0]=='Н' and p.count('Н')==3 and p.count('НН')==0:
        cnt1 += 1   # Увеличиваем счётчик шаблонов с первой нечётной

    # Иначе, если шаблон начинается с 'Ч' и также удовлетворяет условиям:
    elif p[0]=='Ч' and p.count('Н')==3 and p.count('НН')==0:
        cnt2 += 1   # Увеличиваем счётчик шаблонов с первой чётной

# Вычисляем общее количество чисел:
# Для каждого шаблона cnt1: все позиции с 'Н' можно заполнить 4 нечётными цифрами (1,3,5,7),
#   все позиции с 'Ч' — 4 чётными (0,2,4,6), включая первую? Да, но первая здесь 'Н', так что ноль не на первом месте.
#   Всего 4^12 способов на один шаблон.
# Для каждого шаблона cnt2: первая позиция чётная, но не может быть 0 (иначе число станет 11-значным),
#   поэтому для неё 3 варианта (2,4,6), а для остальных чётных позиций — 4 варианта.
#   Всего 3 * 4^11 способов на один шаблон.
print(4**12 * cnt1 + 3 * 4**11 * cnt2)
~~~
**Ответ: 1660944384**

# Задание 25840 (Тип 8)
<img width="771" height="61" alt="image" src="https://github.com/user-attachments/assets/6778a92b-2b51-4f06-93c4-7f6417f6c3f9" />

**Решение:**
~~~
from itertools import *
words = 'БЕЛКА'
c = 0
for i in product(words, repeat = 4):
    if i.count('Б') == 1:
        c += 1
print(c)
~~~
**Ответ: 256**

# Задание 15124 (Тип 2)
<img width="713" height="173" alt="image" src="https://github.com/user-attachments/assets/4846c81a-e866-4a2d-8ba3-57c081c9b0e1" />

**Решение:**
~~~
print('x y z')
for x in range(0, 2):
    for y in range(0, 2):
        for z in range(0, 2):
            if not ((x == y) or ((y or z) <= x)):
                print(x, y, z)
~~~

**Ответ: xzy**

# Задание 18071 (Тип 2)
<img width="718" height="197" alt="image" src="https://github.com/user-attachments/assets/1678b18f-5659-4f83-996b-b89d3d3882b3" />

**Решение:**
~~~
print('x y z w')
for x in range (0, 2):
    for y in range (0, 2):
        for z in range (0, 2):
            for w in range (0, 2):
                if not ((x and not y) or (y == z) or not w):
                    print(x, y, z, w)
~~~

**Ответ: xwzy**

# Задание 15939
<img width="723" height="201" alt="image" src="https://github.com/user-attachments/assets/0cc8c76b-b485-454c-9882-38a92c87a20c" />

**Решение:**
~~~
print('x y z w')
for x in range(0, 2):
    for y in range(0, 2):
        for z in range(0, 2):
            for w in range(0, 2):
                if not ((z and y) or (x <= z) == (y <= w)):
                    print(x, y, z, w)
~~~

**Ответ: wzyx**

# Задание 78064 (Тип 8)
<img width="774" height="185" alt="image" src="https://github.com/user-attachments/assets/afb1be42-a412-423f-8bd6-4eab8c5693c2" />

**Решение:**
~~~
from itertools import product
# 1. Задаём алфавит в нужном порядке (как в условии)
alphabet = sorted('КРОВАТЬ')   # буквы: А, В, К, О, Р, Т, Ь
# Переменная для хранения номера последнего подходящего слова с нечётным номером
last_odd_number = None
# 2. Генерируем все 5-буквенные слова
#    product перебирает все комбинации в алфавитном порядке
for number, letters in enumerate(product(alphabet, repeat=5), start=1):
    word = ''.join(letters)   # собираем строку из кортежа букв
    # 3. Проверяем условия для слова
    if word.count('Т') <= 1:                      # не более одной буквы Т
        if word.count('В') == 2:                  # ровно две буквы В
            if 'ЬЬ' not in word:                  # нет двух Ь рядом
                # 4. Если номер нечётный, запоминаем его
                if number % 2 != 0:
                    last_odd_number = number
# 5. Выводим ответ
print("Номер последнего подходящего слова с нечётным номером:", last_odd_number)
~~~
**Ответ: 16277**

# Задание 3570 (Тип 8)
<img width="634" height="138" alt="image" src="https://github.com/user-attachments/assets/b6bb112d-8bda-43fe-b164-df8eb5b06ef3" />

**Решение:**
~~~
a = {0: "Л", 1: "Н", 2: "О", 3: "С"}
x = 0
for i in range(0, len(a)):
    for j in range(0, len(a)):
        for k in range(0, len(a)):
            for l in range(0, len(a)):
                x += 1
                if x == 250:
                    print(a[i], a[j], a[k], a[l])
~~~

**Ответ: ССОН**

# Задание 35460 (Тип 2)
<img width="781" height="204" alt="image" src="https://github.com/user-attachments/assets/f1ec949d-c9e1-4d89-8d51-e953ce92e46c" />

**Решение:**
~~~
print('x y z w')
k = 0
for x in range(0, 2):
    for y in range(0, 2):
        for z in range(0, 2):
            for w in range(0, 2):
                if (not ((x or y) <= (z and w)) and (x <= w)):
                    print(x, y, z, w)
~~~

**Ответ: zxyw**
# Задание 8098 (Тип 8)
<img width="781" height="63" alt="image" src="https://github.com/user-attachments/assets/41a0cf8b-ee94-4b72-a0f5-d3d53d6c9092" />

**Решение:**
~~~
from itertools import product
word = 'СЛОН'
x = 0
for word in product(word, repeat = 5):
    arl = ''.join(word)
    if arl.count('С') == 1:
        x += 1
print(x)
~~~

**Ответ: 405**

# Задание 16431 (Тип 2)
<img width="732" height="202" alt="image" src="https://github.com/user-attachments/assets/62b0a0b9-bf09-43b4-a6a0-8284268a86d0" />

**Решение:**
~~~
print('x y z w')
for x in range(0, 2):
    for y in range(0, 2):
        for z in range(0, 2):
            for w in range(0, 2):
                if ((y <= x) == (x <= w) and (z or x)):
                    print(x, y, z, w)
~~~

**Ответ: ywxz**

# Задание 18491 (Тип 8)
<img width="769" height="36" alt="image" src="https://github.com/user-attachments/assets/a3d3fe29-af9c-413e-a0ea-50b36596e984" />

**Решение:**
~~~
from itertools import product
word = 'ОЛЬГА'
x = 0
for word in product(word, repeat = 5):
    arl = ''.join(word)
    if arl[0] != 'Ь' and arl.count('О') == 1 and word.count('Л') == 1 and arl.count('Ь') == 1 and arl.count('Г') == 1 and arl.count('А') == 1 and arl.count('ОЬ') == 0 and arl.count('АЬ') == 0:
        x += 1
print(x)
~~~

**Ответ: 48**

# Задание 19051 (Тип 2)
<img width="771" height="188" alt="image" src="https://github.com/user-attachments/assets/fcb37398-283e-43c8-9899-05204ae04bb5" />

**Решение:**
~~~
print('x y z w')
for x in range(0, 2):
    for y in range(0, 2):
        for z in range(0, 2):
            for w in range(0, 2):
                if not ((x and not y) or (x == z) or not w):
                    print(x, y, z, w)
~~~

**Ответ: xwzy**

# Задание 28685
<img width="773" height="57" alt="image" src="https://github.com/user-attachments/assets/c71462e4-785d-4d68-80b5-116000d823f0" />

**Решение:**
~~~
from itertools import product
word = 'ПЕТЯ'
x = 0
for word in product(word, repeat = 6):
    arl = ''.join(word)
    if arl.count('ЕЕ') == 0 and arl.count('ЕЯ') == 0 and arl.count('ЯЯ') == 0 and arl.count('ЯЕ') == 0 and arl.count('ПП') == 0 and arl.count('ПТ') == 0 and arl.count('ТТ') == 0 and arl.count('ТП') == 0:
        x += 1
print(x)
~~~

**Ответ: 128**

# Задание 55589 (Тип 2)
<img width="763" height="227" alt="image" src="https://github.com/user-attachments/assets/e1555e93-9770-4d99-a073-00447a093aa3" />

**Решение:**
~~~
print('x y z w f1 f2')
for x in range(0, 2):
    for y in range(0, 2):
        for z in range(0, 2):
            for w in range(0, 2):
                f1 = (x <= y) == (w or not z)
                f2 = (x <= y) and (not w == z)
                print(x, y, z, w, int(f1), int(f2))
~~~

**Ответ: xzyw**

# Задание 16886 (Тип 8)
<img width="772" height="54" alt="image" src="https://github.com/user-attachments/assets/3e62dbb5-b6e3-40a7-9f77-66e58cb6c196" />

**Решение:**
~~~
from itertools import product
word = 'МАТВЕЙ'
x = 0
for word in product(word, repeat=6):
    newword = ''.join(word)
    if newword[0] != 'Й' and newword.count('АЕ') == 0 and newword.count('М') == 1 and newword.count('А') == 1 and newword.count('Т') == 1 and newword.count('В') == 1 and newword.count('Е') == 1 and newword.count('Й') == 1:
        x += 1
print(x)
~~~

**Ответ: 504**

# Задание 51971 (Тип 2)
<img width="744" height="237" alt="image" src="https://github.com/user-attachments/assets/f9802200-8af9-4b51-be5f-4bcc67562c4e" />

**Решение:**
~~~
print('x y z w')
for x in range(0, 2):
    for y in range(0, 2):
        for z in range(0, 2):
            for w in range(0, 2):
                if not ((x == (not y)) <= ((z <= (not w)) and (w <= y))):
                    print(x, y, z, w )
~~~

**Ответ: ywzx**

# Задание 78033 (Тип 8)
<img width="764" height="190" alt="image" src="https://github.com/user-attachments/assets/1f4ecb4f-b8b8-4857-b38d-7cc87485ce23" />

**Решение:**
~~~
from itertools import product
word = 'БЛРСУЬЭ'
x = 0
for word in product(word, repeat=5):
    newword = ''.join(word)
    x += 1
    all = str(x) + ". " + newword
    if x % 2 == 0 and newword.count('С') >= 2 and newword.count('Л') == 1 and newword.count('ЭЭ') == 0 and newword.count('ЭЭЭ') == 0:
        print(all)
~~~

**Ответ: 15948**

# Задание 27371 (Тип 2)
<img width="772" height="172" alt="image" src="https://github.com/user-attachments/assets/c21cdff4-0609-4b6d-8d90-5e093c0a3db8" />

**Решение:**
~~~
print('x y z w')
for x in range(0, 2):
    for y in range(0, 2):
        for z in range(0, 2):
            for w in range(0, 2):
                if not (((x and (not y)) <= ((not z) or (not w)) and ((w <= x) or y))):
                    print(x, y, z, w)
~~~

**Ответ: zywx**

# Задание 59801 (Тип 8)
<img width="776" height="83" alt="image" src="https://github.com/user-attachments/assets/2dc12d0b-817c-47dc-b8d0-f7bafb81fa58" />

**Решение:**
~~~
from itertools import product
word = 'КОНФЕТА'
x = 0
for word in product(word, repeat=5):
    newword = ''.join(word)
    if newword.count('Е') == 2 and newword[1] != 'Ф':
        x += 1
print(x)
~~~

**Ответ: 1944**

# Задание 85715 (Тип 2)
<img width="781" height="214" alt="image" src="https://github.com/user-attachments/assets/d6b543b8-0554-4ab8-b2be-62d0529624eb" />

**Решение:**
~~~
print('x y z w')
for x in range(0, 2):
    for y in range(0, 2):
        for z in range(0, 2):
            for w in range(0, 2):
                if not ((not x) or ((w <= y) <= z)):
                    print(x, y, z, w)
~~~

**Ответ: wxyz**

# Задание 10473 (Тип 8)
<img width="768" height="62" alt="image" src="https://github.com/user-attachments/assets/9f02e3e0-2aa6-4364-9dcc-10354cf2ed90" />

**Решение:**
~~~
from itertools import product
num = '1234'
x = 0
for num in product(num, repeat=5):
    code = ''.join(num)
    if code.count('1') == 2:
        x += 1
print(x)
~~~

**Ответ: 270**

# Задание 18578 (Тип 2)
<img width="718" height="201" alt="image" src="https://github.com/user-attachments/assets/449c7aa0-1e1b-457e-9658-67fdba5fe9fb" />

**Решение:**
~~~
print('x y z w')
for x in range(0, 2):
    for y in range(0, 2):
        for z in range(0, 2):
            for w in range(0, 2):
                if (((x and not y) or (w <= z)) == (z == x)):
                    print(x, y, z, w)
~~~

**Ответ: zywx**

# Задание 56508 (Тип 8)
<img width="770" height="34" alt="image" src="https://github.com/user-attachments/assets/6db217ac-e55e-4602-9705-8e9908fe45f4" />

**Решение:**
~~~
from itertools import product
s = product('НЧ', repeat = 11)
c1 = 0
c2 = 0
for i in s:
    p=''.join(i)
    if p.count('НН') == 0 and p.count('Н') == 3:
        if p[0] == 'Н':
            c1 += 1
        else:
            c2 += 1
print(4**11*c1 + 3*4**10*c2)
~~~

**Ответ: 293601280**

# Задание 81786 (Тип 2)
<img width="776" height="221" alt="image" src="https://github.com/user-attachments/assets/3ef8cf5b-4aa7-40f2-8e1c-c5d5651c3ead" />

**Решение:**
~~~
print('x y z w')
for x in range(0, 2):
    for y in range(0, 2):
        for z in range(0, 2):
            for w in range(0, 2):
                if ((x or y) and not (y == z) and (not w)):
                    print(x, y, z, w)
~~~
**Ответ: zyxw**

# Задание 10384 (Тип 8)
<img width="773" height="70" alt="image" src="https://github.com/user-attachments/assets/39e24cc1-78bd-4226-9832-1f43cbc60872" />

**Решение:**
~~~
from itertools import product
x = 0
words = 'ABCDX'
for words in product(words, repeat=4):
    code = ''.join(words)
    if (code[0] == 'X' and code.count('X') == 1) or code.count('X') == 0:
        x += 1
        print(code)
print(x)
~~~

**Ответ: 320**

# Задание 18483 (Тип 2)
<img width="713" height="194" alt="image" src="https://github.com/user-attachments/assets/0bc9936a-422d-4620-8d54-7b1f2319308d" />

**Решение:**
~~~
print('x y z w')
for x in range(0, 2):
    for y in range(0, 2):
        for z in range(0, 2):
            for w in range(0, 2):
                if not (((y <= w) == (x <= (not z)) and (x or w))):
                    print(x, y, z, w)
~~~

**Ответ: yzwx**

# Задание 3233 (Тип 8)
<img width="731" height="139" alt="image" src="https://github.com/user-attachments/assets/0ac170d8-fe49-4d5b-a8d9-48a53c9d64f0" />

**Решение:**
~~~
from itertools import product
words = 'АКРУ'
x = 0
for words in product(words, repeat=5):
    word = "".join(words)
    x += 1
    print(str(x) + '. ' + str(word))
~~~

**Ответ: АУУРК**

# Задание 33747 (Тип 2)
<img width="768" height="205" alt="image" src="https://github.com/user-attachments/assets/c5fcc953-9f93-4b9f-ae80-192b95c643c4" />

**Решение:**
~~~
print('x y z w')
for x in range(0, 2):
    for y in range(0, 2):
        for z in range(0, 2):
            for w in range(0, 2):
                if not (((not (z == w)) <= (w and (not x)) or (x and (not y)))):
                    print(x, y, z, w)
~~~

**Ответ: wzyx**

## Задание 27009 (Тип 8)
<img width="772" height="49" alt="image" src="https://github.com/user-attachments/assets/f4c99b94-bd12-457a-a4cc-f7c86fb03e4e" />

**Решение:**
~~~
from itertools import product
word = 'НИКОЛАЙ'
x = 0
for word in product(word, repeat=4):
    word2 = ''.join(word)
    if word2[0] != 'Й' and (word2.count('И') >= 1 or word2.count('О') >= 1 or word2.count('А') >= 1):
        x += 1
print(x)
~~~

**Ответ: 1866**

## Задание 40718 (Тип 2)
<img width="774" height="202" alt="image" src="https://github.com/user-attachments/assets/287a26e9-f9b5-4b9f-9387-28441d51aa41" />

**Решение:**
~~~
print('x y z w')
for x in range(0, 2):
    for y in range(0, 2):
        for z in range(0, 2):
            for w in range(0, 2):
                if not (((x <= y) and (z or w)) <= ((x == w) or (y and (not z)))):
                    print(x, y, z, w)
~~~

**Ответ: yxwz**

## Задание 15822 (Тип 8)
<img width="770" height="158" alt="image" src="https://github.com/user-attachments/assets/535e8025-5b78-4fcb-8c70-3bf502aaa6fa" />

**Решение:**
~~~
from itertools import product
word = 'АЕКР'
x = 0
for word in product(word, repeat = 4):
    x += 1
    word2 = str(x) + '.' + ''.join(word)
    if word2.count('А') == 0:
        print(word2)
~~~

**Ответ: 86**

## Задание 73828 (Тип 2)
<img width="703" height="192" alt="image" src="https://github.com/user-attachments/assets/53581bf9-cf6d-4a28-a01c-06e0367ca08d" />

**Решение:**
~~~
print('x y z w')
for x in range(0, 2):
    for y in range(0, 2):
        for z in range(0, 2):
            for w in range(0, 2):
                if ((x == (y <= z)) and (y == (not (z <= w)))):
                    print(x, y, z, w)
~~~

**Ответ: wzxy**

## Задание 3697 (Тип 8)
<img width="773" height="159" alt="image" src="https://github.com/user-attachments/assets/57661332-8fec-45f2-b578-30989901d54d" />

**Решение:**
~~~
from itertools import product
word = 'ВИНТ'
x = 0
for word in product(word, repeat=5):
    x += 1
    word2 = str(x) + '. ' + ''.join(word)
    if x == 1019:
        print(word2)
~~~

**Ответ: ТТТНН**

## Задание 28546 (Тип 8)
<img width="722" height="48" alt="image" src="https://github.com/user-attachments/assets/8daa8323-0d84-44bb-9dc1-26ff212be6d1" />

**Решение:**
~~~
from itertools import product
word = 'НАСТЯ'
count = 0
for word in product(word, repeat=4):
    word2 = ''.join(word)
    if word2.count('Н') <= 1 and word2.count('А') <= 1 and word2.count('С') <= 1 and word2.count('Т') <= 1 and word2.count('Я') <= 1 and word2.count('АЯ') == 0 and word2.count('ЯА') == 0 and word2.count('НС') == 0 and word2.count('НТ') == 0 and word2.count('СН') == 0 and word2.count('СТ') == 0 and word2.count('ТН') == 0 and word2.count('ТС') == 0:
        count += 1
print(count)
~~~

**Ответ: 24**

## Задание 45236 (Тип 2)
<img width="721" height="222" alt="image" src="https://github.com/user-attachments/assets/47fe36cc-4ad2-4f29-9c5b-1c224e91931c" />

**Решение:**
~~~
print('x y z w')
for x in range(0, 2):
    for y in range(0, 2):
        for z in range(0, 2):
            for w in range(0, 2):
                if not (not (x <= w) or (y == z) or y):
                    print(x, y, z, w)
~~~

**Ответ: zxwy**

## Задание 15795 (Тип 8)
<img width="719" height="169" alt="image" src="https://github.com/user-attachments/assets/1622b188-7baf-48e2-ba3f-ecf75b1696f1" />

**Решение:**
~~~
from itertools import product
word = 'АПРСУ'
count = 0
for word in product(word, repeat = 4):
    word2 = ''.join(word)
    count += 1
    var = str(count) + '. ' + word2
    if var.count('А') == 0:
        print(var)
        break
~~~

**Ответ: 157**

## Задание 33504 (Тип )
<img width="726" height="206" alt="image" src="https://github.com/user-attachments/assets/486ca093-d4c9-4942-b793-d3954e9e6d3c" />

**Решение:**
~~~
print('x y z w')
for x in range(0, 2):
    for y in range(0, 2):
        for z in range(0, 2):
            for w in range(0, 2):
                if not (((x == (not y)) <= (y and (not z)) or (z and (not w)))):
                    print(x, y, z, w)
~~~

**Ответ: wzyx**

## Задание 3700 (Тип 8)
<img width="719" height="157" alt="image" src="https://github.com/user-attachments/assets/61e7762d-ae77-4084-8319-ebfa199ffd2d" />

**Решение:**
~~~
from itertools import product
word = 'БКФЦ'
count = 0
for word in product(word, repeat = 5):
    word2 = ''.join(word)
    count += 1
    code = str(count) + '. ' + word2
    if count == 486:
        print(code)
~~~

**Ответ: КЦФКК**

## Задание 64932 (Тип 2)
<img width="725" height="214" alt="image" src="https://github.com/user-attachments/assets/a2be9690-b4ea-4464-8eb7-cc39b6d5ae47" />

**Решение:**
~~~
print('x y z w')
for x in range(0, 2):
    for y in range(0, 2):
        for z in range(0, 2):
            for w in range(0, 2):
                if ((x == z) <= ((not y) or w)) == (not ((w <= z) or (x <= y))):
                    print(x, y, z, w)
~~~

**Ответ: zyxw**

## Задание 3237 (Тип 8)
<img width="699" height="124" alt="image" src="https://github.com/user-attachments/assets/734066aa-6abe-4987-b9e0-23fc8d46b3d6" />

**Решение:**
~~~
from itertools import product
words = 'АОУ'
count = 0
for words in product(words, repeat=5):
    word = ''.join(words)
    count += 1
    code = str(count) + '. ' + word
    if count == 170:
        print(code)
        break
~~~

**Ответ: УААУО**

## Задание 64887 (Тип 2)
<img width="724" height="206" alt="image" src="https://github.com/user-attachments/assets/efd03256-f484-4016-a9b0-8b37c7961668" />

**Решение:**
~~~
print('x y z w')
for x in range(0, 2):
    for y in range(0, 2):
        for z in range(0, 2):
            for w in range(0, 2):
                if ((x == y) <= ((not z) or w)) == (not ((w <= x) or (y <= z))):
                    print(x, y, z, w)
~~~

**Ответ: wzyx**

## Задание 13486 (Тип 8)
<img width="716" height="82" alt="image" src="https://github.com/user-attachments/assets/4dc9f749-deb0-4797-80b6-f95e8914193e" />

**Решение:**
~~~
from itertools import product
words = 'АВСХ'
count = 0
for words in product(words, repeat=5):
    code = ''.join(words)
    if (code[0] == 'Х' or code[4] == 'Х') and code.count('Х') == 1:
        count += 1
print(count)
~~~

**Ответ: 162**

## Задание 72587 (Тип 2)
<img width="721" height="220" alt="image" src="https://github.com/user-attachments/assets/936c7617-a765-4192-984a-7910d859d84b" />

**Решение:**
~~~
print('x y z w')
for x in range(0, 2):
    for y in range(0, 2):
        for z in range(0, 2):
            for w in range(0, 2):
                if not ((x <= (z <= w)) and (z <= (y == (not w)))):
                    print(x, y, z, w)
~~~

**Ответ: zxwy**

## Задание 59741 (Тип 8)

**Решение:**
~~~

~~~

**Ответ: **
