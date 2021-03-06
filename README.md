# Автоматическая обработка текстов

## Данные
В качестве корпуса текстов используется файл `data/example_text.txt` содержащий контексты цитирований
в научных публикация.

## Зависимости:
```bash
pip install DAWG-Python
pip install pymorphy2
pip install -U pymorphy2-dicts-ru
```

## Решения
Решение каждой из лабораторных работ представлены в виде `jupyter notebook` тетради.

| name         | Description |
| :------------: | ----------- |
| lab_1.1.ipynb | Реализация первой лабораторной работы на основе dict. Для работы требует порядка 500 Mb оперативной памяти|
| lab_1.2.ipynb | Реализация первой лабораторной работы на основе bedarev_analyzer. Для работы требует порядка 80 Mb оперативной памяти |
| lab_2.ipynb | Реализация второй лабораторной работы |
| lab_3.ipynb | Реализация третьей лабораторной работы (не завершена) |

В качестве реализации морфологического парсера используется: **bedarev_analyzer**.

## bedarev_analyzer
Библиотека представляет реализация морфологического анализа на основе [ODict](http://odict.ru/).

Для первоначальной предобработки текста исполтзовался скрипт `gen_data.py`. Для его работы необходимо поместить файл 
с данными odict в директорию data: `'./data/odict.csv'`.

**Важно**:
- Для работы библиотеки ничего дополнительно скачивать не нужно. Предобработанные данные включены в пакет.
- Необходимо разархивировать данные лежащие в `bedarev_analyzer/data`

Пример использования библиотеки:
```python
from bedarev_analyzer import MorphAnalyzer

morph = MorphAnalyzer()
parsed_objects = morph.parse('стекла')

print(type(parsed_objects), len(parsed_objects))
for result in parsed_objects:
    print(f'word: {result.word}, normal_form: {result.normal_form}, tag: {result.tag}')


```
Получаемый результат:
```text
<class 'list'> 2
word: стекла, normal_form: стекло, tag: с
word: стекла, normal_form: стечь, tag: св

```
