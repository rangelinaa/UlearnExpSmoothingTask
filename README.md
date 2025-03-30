# UlearnExpSmoothingTask

## Диаграмма классов
![Диаграмма классов](https://www.mermaidchart.com/raw/8a2dbc46-e2b3-469a-b9a6-0ddfb631d54a?theme=light&version=v0.1&format=svg)

---

## Описание классов

### DataPoint
Точка данных с различными значениями:
- 'X' — координата точки.
- 'OriginalY' — оригинальное значение.
- 'ExpSmoothedY' — экспоненциально сглаженное значение.
- 'AvgSmoothedY, MaxY' — другие варианты обработки данных.
- Методы 'WithExpSmoothedY()', 'WithAvgSmoothedY()', 'WithMaxY()' создают копии объекта с изменённым значением.

### ExpSmoothingTask
- Метод 'SmoothExponentialy()' выполняет экспоненциальное сглаживание.
Принимает на вход:
- 'data' — последовательность точек (IEnumerable<DataPoint>).
- 'alpha' — коэффициент сглаживания.
Использует формулу:
'S_t = S_{t-1} + \alpha (X_t - S_{t-1})'
- Первое значение остаётся неизменным, затем идёт сглаживание.
- Возвращает новую последовательность точек с обновлённым ExpSmoothedY.
