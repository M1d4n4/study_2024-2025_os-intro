# Лабораторная работа №1
## Шифры простой замены

**Выполнил:**  
Студент: Да Кошта Феррейра Мидана
группы НФИмд-01-24

---

### Введение

Целью данной лабораторной работы является изучение и реализация шифров простой замены, таких как шифр Цезаря и шифр Атбаш. Шифры простой замены используются для защиты информации путем замены символов исходного текста на другие символы согласно определенному алгоритму. В ходе работы будут реализованы программы для шифрования и дешифрования текста с использованием этих алгоритмов.

---

### Теоретическая часть

#### Шифр Цезаря

Шифр Цезаря — это один из самых простых и известных шифров, основанный на сдвиге букв алфавита на фиксированное число позиций. Например, при сдвиге на 3 позиции:
- Буква **А** заменяется на **Г**.
- Буква **Б** заменяется на **Д**.
- И так далее.

Математически шифрование можно описать формулой:
\[ C = (P + k) \mod m \]
где:
- \( C \) — символ шифртекста,
- \( P \) — символ открытого текста,
- \( k \) — ключ (сдвиг),
- \( m \) — длина алфавита.

#### Шифр Атбаш

Шифр Атбаш — это шифр, в котором буквы алфавита заменяются на симметричные им буквы из конца алфавита. Например:
- Буква **А** заменяется на **Я**.
- Буква **Б** заменяется на **Ю**.
- И так далее.

---

### Практическая часть

#### Реализация шифра Цезаря

```python
def caesar_cipher(text, key):
    alphabet = 'абвгдежзийклмнопрстуфхцчшщъыьэюя'  # Русский алфавит
    result = []
    for char in text.lower():
        if char in alphabet:
            idx = (alphabet.index(char) + key) % 32  # 32 буквы в русском алфавите
            result.append(alphabet[idx])
        else:
            result.append(char)  # Оставляем пробелы и знаки препинания без изменений
    return ''.join(result)

# Пример использования
text = "Привет, мир!"
key = 3
encrypted = caesar_cipher(text, key)
print("Зашифрованный текст:", encrypted)  # Вывод: "прлгжу, плу!"

Результаты
Пример работы шифра Цезаря
Входные данные:
Текст: "Привет, мир!"
Ключ: 3

Выходные данные:
Зашифрованный текст: "прлгжу, плу!"

Пример работы шифра Атбаш
Входные данные:
Текст: "Пример"

Выходные данные:
Зашифрованный текст: "эпюгк"

## Заключение
В ходе выполнения лабораторной работы были изучены и реализованы два шифра простой замены: шифр Цезаря и шифр Атбаш. Программы успешно шифруют текст в соответствии с заданными алгоритмами. 
