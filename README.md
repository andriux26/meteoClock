﻿# meteoClock

Это доработка прошивки AlexGyver под метеостанцию.

Чуток доработал прошивку под экран 2004 (1602 не проверял, но старался оставить
все как было, т.к. тестировать не на чем). Что изменилось:

## v1.3b6

-   большие цифры на главном экране сделал более «квадратными», что в свою
    очередь позволило высвободить пару символов, которые использовал для
    написания двухбуквенного обозначения дня недели по-русски (например: ПН, ЧТ,
    ПТ, СБ);

![1](https://github.com/Norovl/meteoClock/blob/master/ScreenPhoto/136Time.jpg)

-   из-за сокращения длины написания дня недели по-русски появилась возможность
    добавить рядом секунды;

-   выровнял большую цифру «1» по центру, что на мой взгляд выглядит более
    наглядно;

-   на главном экране двойным нажатием на кнопку в цикле переключаются режимы
    крупного отображения значений следующих показателей: время – содержание СО2
    – температура – давление;

![2](https://github.com/Norovl/meteoClock/blob/master/ScreenPhoto/136co2.jpg)
![3](https://github.com/Norovl/meteoClock/blob/master/ScreenPhoto/136temp.jpg)
![4](https://github.com/Norovl/meteoClock/blob/master/ScreenPhoto/136mmhg.jpg)
![5](https://github.com/Norovl/meteoClock/blob/master/ScreenPhoto/136h.jpg)
![6](https://github.com/Norovl/meteoClock/blob/master/ScreenPhoto/136Time.jpg)

-   на главном экране удержанием кнопки переключается режим большие цифры/очень
    большие цифры – работает только для LCD 2004. В режиме четырехстрочных цифр
    некоторые данные не выводятся, т.к. просто нет места (прогноз дождя,
    влажность)

![7](https://github.com/Norovl/meteoClock/blob/master/ScreenPhoto/136BigTime.jpg)
![8](https://github.com/Norovl/meteoClock/blob/master/ScreenPhoto/136BigTemp.jpg)

-   на графических экранах при минимальных значениях были пропуски в графике.
    Добавил минимально отображаемое значения, чтобы график выглядел цельным.

-   на графических экранах двойным нажатием на кнопку переключаются макс/мин
    пределы между указанными значениями в прошивке и фактическим максимумом и
    минимумом за период (т.е. более наглядное графическое изменение
    показателей). При этом с правой стороны графика появляются стрелочки
    (вовнутрь и наружу соответственно) в качестве индикации режима;

![9](https://github.com/Norovl/meteoClock/blob/master/ScreenPhoto/136Grafco2max.jpg)
![10](https://github.com/Norovl/meteoClock/blob/master/ScreenPhoto/136Grafco2.jpg)

-   мелкие изменения, не влияющие на функциональность (например, на графике
    температуры за обозначением «t» поставил значок градуса и пр…)

## v1.3b7

Новая версия прошивки с возможностью сохранения вида настроек: текущие крупные
показания (время, содержание СО2, температура, давление, влажность), размер
крупных цифр (2-х строчные или 4-х строчные), пределы графиков (указанные в
прошивке или исходя из значений за период).

Меню сохранения вызывается тройным нажатием на кнопку, затем одинарным нажатием
выбирается ДА или НЕТ и длинным нажатием применяется. Все настройки сохраняются
в энергонезависимой памяти ардуинки, поэтому потеря питания теперь не страшна.

![11](https://github.com/Norovl/meteoClock/blob/master/ScreenPhoto/137save.jpg)

поправлен баг наложения элементов часов (времени) на температуру, если она была
выбрана основной.

## v1.5b8

### v1.5b81

Изменения в меню (вызывается тройным нажатием кнопки в главном окне):

-   Добавлен пункт меню «Выход», чтобы можно было выйти не сохраняя значения в
    энергонезависимую память (однако выбранные параметры будут использоваться до
    перезагрузки устройства)

-   Убрано подтверждение сохранения, теперь сохраняется сразу при удержании
    кнопки на меню «Сохранить»

![Сохранение настроек](https://github.com/Norovl/meteoClock/blob/master/ScreenPhoto/158Save.jpg)

-   Добавлена настройка выбора яркости индикатора (0% - 100%, АВТО) и экрана 
    (0% - 100%, АВТО, но для регулировки экрана необходима доработка схемы 
    под версию 1.5 Алекса).

![Настройка яркости индикатора](https://github.com/Norovl/meteoClock/blob/master/ScreenPhoto/158LEDBright.jpg)
![Настройка яркости дисплея](https://github.com/Norovl/meteoClock/blob/master/ScreenPhoto/158LCDBright.jpg)
![Установка яркости дисплея](https://github.com/Norovl/meteoClock/blob/master/ScreenPhoto/158LCDBright10.jpg)

-   Добавлена возможность настройки отображения и скрытия графиков при их
    последовательном переборе.

![Отключение отображения влажности за сутки](https://github.com/Norovl/meteoClock/blob/master/ScreenPhoto/158GrafOff.jpg)
![Включение отображения графика уровня СО2 за час](https://github.com/Norovl/meteoClock/blob/master/ScreenPhoto/158GrafOn.jpg)

-   Добавлена возможность работы от аккумулятора 18650 с индикацией остатка
    заряда. Так же есть индикатор работы от сети. Необходима доработка схемы –
    см. рисунок ниже.

![Работа от батареи](https://github.com/Norovl/meteoClock/blob/master/ScreenPhoto/158battery.jpg)
![Работа от внешнего источника (сети)](https://github.com/Norovl/meteoClock/blob/master/ScreenPhoto/158DC.jpg)

![Доработка схемы для работы от батареи](https://github.com/Norovl/meteoClock/blob/master/ScreenPhoto/scheme1.jpg)

### v1.5b82

-   Теперь из любого пункта меню настроек можно выйти в пункт "Сохранить" 
    двойным нажатием на кнопку;

-   в заголовке скетча (blinkLED) можно установить порог значений СО2, при
    превышении которого будет мигать индикатор;

-   поправлена ошибка в режиме debug;
