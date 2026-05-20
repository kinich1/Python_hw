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

# Задание 
