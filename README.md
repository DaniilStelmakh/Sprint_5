# fit-module-go 

## Модуль фитнес-трекер
```
Программный модуль, который будет рассчитывать и отображать результаты тренировки.

```
## Описание 
```
Программный модуль фитнес-трекера, который обрабатывает данные для трех видов тренировок: бега, ходьбы и плавания.

```
## Модуль 
``` 
Рассчитывать результаты тренировки,
Выводить информационное сообщение о результатах тренировки.

```
### Информационное сообщение должно включать такие данные:
```sh
- тип тренировки (бег, ходьба или плавание);
- длительность тренировки;
- дистанция, которую преодолел пользователь, в километрах;
- среднюю скорость на дистанции, в км/ч;
- расход энергии, в килокалориях.

```
### Структура `Training{}`:
```sh 
`TrainingType` - описывает вид тренировки `string`
`Action` - описывает количество шагов при беге и ходьбе или количество гребков при плавании `int` 
`LenStep` - описывает длину одного шага или гребка `float64`
`Duration` - описывает продолжительность тренировки `time.Duration` 
`Weight` - описывает вес пользователя в килограммах `float64`
```
### Методы структуры `Training{}`:
```sh 
`distance()` - возвращает дистанцию в километрах, которую преодолел пользователь за время тренировки
`meanSpeed()` - возвращает значение средней скорости движения во время тренировки
`Calories()` - возвращает количество килокалорий, израсходованных во время тренировки
`TrainingInfo()` - возвращает переменную структуры `InfoMessage{}` 
```
### Структура `Walking{}`:
```sh 
Структура `Walking{}` реализовывает интерфейс `CaloriesCalculator`. В интерфейсе `CaloriesCalculator` всего два метода: `Calories()` и `TrainingInfo()`.
Метод `Calories()` возвращает количество израсходованных калорий при ходьбе.
Метод `TrainingInfo()` возвращает переменную структуры `InfoMessage{}` с информацией о проведённой
тренировке.

```
### Структура `Swimming{}`:
```sh 
Структура описывает тренировку Плавание. В интерфейсе `CaloriesCalculator` всего два метода: `Calories()` и `TrainingInfo()`.
Метод `Calories()` возвращает количество израсходованных калорий при плавании.
Реализация `TrainingInfo()` для `Swimming{}` похожа на реализацию `TrainingInfo()` для `Training{}`, но с иcпользованием методов для `Swimming{}`.

```
### Функция получения данных `ReadDate()`:
```sh 
Это общая функция с одним параметром типа `CaloriesCalculator`, интерфейса для всех видов тренировок.

```


