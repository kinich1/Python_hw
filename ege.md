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

# Задание 78064
<img width="774" height="185" alt="image" src="https://github.com/user-attachments/assets/afb1be42-a412-423f-8bd6-4eab8c5693c2" />
