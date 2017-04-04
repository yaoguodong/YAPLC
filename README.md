# YAPLC

YAPLC - это свободная система программирования [ПЛК](https://ru.wikipedia.org/wiki/%D0%9F%D1%80%D0%BE%D0%B3%D1%80%D0%B0%D0%BC%D0%BC%D0%B8%D1%80%D1%83%D0%B5%D0%BC%D1%8B%D0%B9_%D0%BB%D0%BE%D0%B3%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%B8%D0%B9_%D0%BA%D0%BE%D0%BD%D1%82%D1%80%D0%BE%D0%BB%D0%BB%D0%B5%D1%80).

YAPLC представляет собой набор программ и бибилиотек со свободными лицензиями, 
которые позволяют создавать программное обеспечение ПЛК на базе микроконтроллеров.

Особенности системы программирования:
* Прозрачность: компоненты системы являются свободным программным обеспечением с открытым исходным кодом.
* Для программирования используются пять языков стандарта IEC-61131-3, для расширения программ можно использовать Си.
* В качестве формата обмена данными используется [PLCopen XML](http://www.plcopen.org/pages/tc6_xml/).
* Простота расширения:
  * для добавления новой аппаратной платформы достаточно: 
    * создать проект среды выполнения, 
    * добавить туда общие файлы, 
    * написать [BSP](https://ru.wikipedia.org/wiki/Board_Support_Package);
  * для связывания со средой разработки достаточно:
    * скопировать один из наборов целевых файлов,
    * внести изменения в соответствии с возможностями аппаратной платформы (периферия описывается простым декларативным языком);

По состоянию на 4 апреля 2017 г. YAPLC включает следующие компоненты:
* [Beremiz](https://bitbucket.org/skvorl/beremiz) - интегрированная среда разработки программных ПЛК на языках IEC-61131-3;
* [matiec](https://bitbucket.org/mjsousa/matiec) - транслятор языков програмрования IEC-61131-3, генерирует программный ПЛК на Си;
* [GNU ARM Embedded Toolchain](https://launchpad.net/gcc-arm-embedded) - легендарный набор инструментов разработчика на Си/Си++.
* [CanFestival](https://github.com/nucleron/CanFestival-3) - стек CanOpen;
* [FreeModbus](https://github.com/nucleron/freemodbus-v1.5.0) - стек ModBus;
* [libopencm3](https://github.com/libopencm3/libopencm3) - библиотека драйверов периферии для микроконтроллеров с ядрами Cortex-Mх;
* [stm32flash](https://github.com/nucleron/stm32flash) - загрузчик для микрконтроллеров STM32;
* [YAPLC/RTE](https://github.com/nucleron/RTE) - минималистичная среда выполнения программмных ПЛК;
* [YAPLC/IDE](https://github.com/nucleron/IDE) - расширения для Beremiz, позволяющие создавать приложения YAPLC/RTE:
* [YaPySerial](https://github.com/nucleron/YaPySerial) - динамическая библиотека для замены PySerial (замечено, что PySerial не всегда корректно определяет платформу).

# Статус проекта

В данный момент система программирования YAPLC переходит на этап открытого тестирования. 

ООО НПК "Нуклерон" была разработана линейка программируемых реле NUC-24x/251. Линейка обладает следующими особенностями:
* Отсутствие искусственных ограничений на количество используемых программой ресурсов, таких как функциональные блоки при программировании на языке FBD.
* Низкое время цикла (от 300 мкc).
* Питание 24 В либо 220 В.
* Дискретные входы с внешним питанием на 24 В либо 220 В, либо с внутренним питанием напряжением 24 В.
* Дискретные выходы типов: контакты реле, транзисторная оптопара, симисторная оптопара.
* Аналоговые входы с возможностью измерения тока 0-20 мА, напряжения 0-10 В, сопротивления 0-100 Ом или 0-4 кОм.
* Аналоговые выходы 0-20 мА с внешним или внутренним питанием.
* Связь по RS-485 по протоколам MODBUS RTU/ASCII.
* Индивидуальная гальваническая развязка портов питания, RS-485, аналоговых и дискретных выходов, групповая гальваническая развязка дискретных входов.
* Все программируемые реле линейки имеют часы реального времени.
* Прочие характеристики изделий линейки:
![](https://cloud.githubusercontent.com/assets/16999214/24648364/d1fcf818-193c-11e7-903c-ce661a768e57.png)

# Скачать
[Текушщий релиз.](https://github.com/nucleron/YAPLC/releases/tag/v0.9.9)

# Бесплатные образцы
ООО НПК "Нуклерон" приглашает специалистов по АСУТП принять участие в открытом тестировании YAPLC на программируемых реле NUC-243.

Желающим принять участие в тетсировании системы преддлагаются бесплатные наборы инженерных образцов изделий линейки, включающие в себя программируемое реле NUC-243 и адаптер для программирования NUC-246.

Заявки принимаются по электронной почте pab@nucleron.ru
