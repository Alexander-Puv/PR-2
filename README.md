# Практическая работа №2. Основы XML-разметки. Менеджеры размещения LinearLayout и GridLayout
#### Цель работы: Изучить основы языка разметки XML для описания пользовательского интерфейса Android-приложений. Научиться использовать менеджеры размещения (контейнеры) LinearLayout и GridLayout для создания сложных экранов. Освоить основные атрибуты View и создание простых Drawable-ресурсов.

Выполнил ИНС-б-о-24-1, Пузанов Александр Александрович

Репозиторий: https://github.com/Alexander-Puv/PR-2

### Ход выполнения практической работы:

#### 1. Создание проекта и подготовка ресурсов:
Красный прямоугольник с закруглёнными углами:

![img.png](%D0%BF%D0%B8%D0%BA%D1%87%D0%B8/img.png)

Синий круг:

![img_1.png](%D0%BF%D0%B8%D0%BA%D1%87%D0%B8/img_1.png)
#### 2. Работа с LinearLayout:
![img_2.png](%D0%BF%D0%B8%D0%BA%D1%87%D0%B8/img_2.png)
#### 3. Изменение ориентации и выравнивания:
Горизонтально и справа на лево:

![img_3.png](%D0%BF%D0%B8%D0%BA%D1%87%D0%B8/img_3.png)

android:gravity="bottom" и различные android:layout_gravity:

![img_4.png](%D0%BF%D0%B8%D0%BA%D1%87%D0%B8/img_4.png)
#### 4. Работа с GridLayout:
![img_5.png](%D0%BF%D0%B8%D0%BA%D1%87%D0%B8/img_5.png)
#### 5. Объединение ячеек в GridLayout:
Код:
```kotlin
<?xml version="1.0" encoding="utf-8"?>
<GridLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:id="@+id/grid"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:columnCount="3"
    android:rowCount="2"
    android:padding="16dp">

    <Button
        android:layout_width="0dp"
        android:layout_height="0dp"
        android:layout_columnWeight="2"
        android:layout_rowWeight="1"
        android:layout_columnSpan="2"
        android:layout_gravity="fill"
        android:text="Кнопка 1 (2 колонки)"
        android:layout_margin="4dp"/>

    <Button
        android:layout_width="0dp"
        android:layout_height="0dp"
        android:layout_columnWeight="1"
        android:layout_rowWeight="1"
        android:layout_column="2"
        android:text="Кнопка 2"
        android:layout_margin="4dp"/>

    <Button
        android:layout_width="0dp"
        android:layout_height="0dp"
        android:layout_columnWeight="3"
        android:layout_rowWeight="1"
        android:layout_row="1"
        android:layout_columnSpan="3"
        android:layout_gravity="fill"
        android:text="Кнопка 3 (3 колонки)"
        android:layout_margin="4dp"/>

</GridLayout>
```
Результат:

![img_6.png](%D0%BF%D0%B8%D0%BA%D1%87%D0%B8/img_6.png)
#### 6. Часть 2. Задание по варианту (вариант 2)
Код:
```kotlin
<?xml version="1.0" encoding="utf-8"?>
<GridLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:id="@+id/calc"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:columnCount="5">

    <TextView
        android:layout_columnSpan="5"
        android:layout_columnWeight="5"
        android:gravity="center"
        android:text="Calculator"
        android:textSize="32sp"/>

    <TextView
        android:layout_columnSpan="5"
        android:layout_columnWeight="5"
        android:gravity="end"
        android:text="168"
        android:textSize="24sp"
        android:paddingHorizontal="30dp"/>

    <Button android:text="7"/>
    <Button android:text="8"/>
    <Button android:text="9"/>
    <Button
        android:layout_columnWeight="2"
        android:layout_columnSpan="2"
        android:text="C"/>

    <Button android:text="4"/>
    <Button android:text="5"/>
    <Button android:text="6"/>
    <Button android:text="/"/>
    <Button android:text="*"/>

    <Button android:text="1"/>
    <Button android:text="2"/>
    <Button android:text="3"/>
    <Button android:text="+"/>
    <Button android:text="-"/>

    <Button
        android:text="0"
        android:layout_columnSpan="2"
        android:layout_columnWeight="2"/>

    <Space />

    <Button
        android:text="="
        android:layout_columnSpan="2"
        android:layout_columnWeight="2"/>

</GridLayout>
```
Результат:

![img_7.png](%D0%BF%D0%B8%D0%BA%D1%87%D0%B8/img_7.png)
### Контрольные вопросы:
1. Что такое XML? Для каких целей он используется в Android-разработке?
XML - язык разметки для описания интерфейса. В Android используется для создания экранов (разметка UI) без кода.
2. Что такое тег (элемент) в XML? Из каких частей он состоит?
Тег — это элемент разметки. Состоит из:
- открывающего тега <TextView>
- атрибутов (android:text="...")
- закрывающего тега </TextView> или самозакрывающийся <View />
3. Какие менеджеры размещения (контейнеры) вы знаете? Кратко опишите каждый.
- LinearLayout - элементы в строку или столбец
- GridLayout - сетка (таблица)
- ConstraintLayout - гибкое позиционирование через связи
- FrameLayout - элементы накладываются друг на друга
- RelativeLayout - расположение относительно других элементов
4. В чём разница между LinearLayout и GridLayout? В каких случаях какой контейнер удобнее использовать?
- LinearLayout - простой список (вертикально/горизонтально)
- GridLayout - таблица с строками и столбцами
5. Что такое match_parent и wrap_content? Приведите примеры использования.
- match_parent - занимает всё доступное место
- wrap_content - под размер содержимого
6. В чём разница между android:gravity и android:layout_gravity?
gravity - выравнивание внутри элемента
layout_gravity - положение элемента в родителе
7. Какие единицы измерения используются в Android? Для чего предназначены dp и sp?
dp - для размеров (адаптивность)
sp - для текста (учитывает масштаб)
px - редко используется
8. Как создать простую фигуру (прямоугольник, круг) с помощью XML-ресурса в папке drawable?
Создать XML в res/drawable с помощью тега shape и solid внутри. Например:
```kotlin
<shape xmlns:android="http://schemas.android.com/apk/res/android"
    android:shape="oval">
    <solid android:color="#0000FF" />
    <size android:width="100dp" android:height="100dp" />
</shape>
```
