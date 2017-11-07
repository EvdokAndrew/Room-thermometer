# ��������� ���������
��������� ��������� �������� ��������� �������. 
```arduino
#include <math.h>
```
���� ������� �� ��������� � ��� ��� ����������.
```arduino
#define FIRST_LED_PIN 2
#define LED_COUNT 10
```
������� ���������. ��������� ������ ��� � �������� ��������� ������ ���������. � ������� ����� � ��� �����������.
```arduino
void setup()
{
for (int i = 0; < LED_COUNT; ++i)
pinMode(i + FIRST_LED_PIN, OUTPUT);
}
```
����� �� � ������� ����� for ���������� ��� ���� � ��������� �� ����� ���� OUTPUT.
```arduino
void loop()
{
float voltage = analogRead(A0) * 5.0 / 1023.0; 
float temperature = 1.0 / (log(voltage / 2.5) / 4300.0 +
1.0 / 298.0) - 273.0; 
```
��������� ����������� � �������� �������� ������� ������ �� ������ ���������� � ����������.
�� ���������� ��� ���� �� ����� �����.
```arduino
for (int i = 0; i < LED_COUNT; ++i) {
boolean enableSegment = (temperature >= 21+i);
digitalWrite(i + FIRST_LED_PIN, enableSegment);
	}
}
```
����� �� ������� ,��� ��� ����������� 21 ������ ������ ������ 1 ���������, ��� 22 �������� ���. � ��� �����.
� ���������� ������ �� ������ i-�. 



