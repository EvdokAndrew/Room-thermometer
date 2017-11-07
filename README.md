# Комнатный термометр
Комнатный термометр работает следующим образом. 
```arduino
#include <math.h>
```
Этой строкой мы добовляем в наш код библиотеку.
```arduino
#define FIRST_LED_PIN 2
#define LED_COUNT 10
```
Создаем константы. Указываем первый пин к которому подключен первый светодиод. И сколько всего у нас светодиодов.
```arduino
void setup()
{
for (int i = 0; < LED_COUNT; ++i)
pinMode(i + FIRST_LED_PIN, OUTPUT);
}
```
Здесь мы с помощью цикла for перебираем все пины и указываем им режим пина OUTPUT.
```arduino
void loop()
{
float voltage = analogRead(A0) * 5.0 / 1023.0; 
float temperature = 1.0 / (log(voltage / 2.5) / 4300.0 +
1.0 / 298.0) - 273.0; 
```
Вычисляем тембературу в градусах формулой которую вывели на основе информации о термисторе.
Но используем при этом не целые числа.
```arduino
for (int i = 0; i < LED_COUNT; ++i) {
boolean enableSegment = (temperature >= 21+i);
digitalWrite(i + FIRST_LED_PIN, enableSegment);
	}
}
```
Здесь мы говорим ,что при температуре 21 градус должен гореть 1 светодиод, при 22 градусах два. И так далее.
И определяем должен ли гореть i-й. 



