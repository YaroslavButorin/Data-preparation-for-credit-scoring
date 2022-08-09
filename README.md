# Исследование надёжности заёмщиков

## Описание проекта

Заказчик — кредитный отдел банка. Нужно разобраться, влияет ли семейное положение и количество детей клиента на факт погашения кредита в срок. Входные данные от банка — статистика о платёжеспособности клиентов.
Результаты исследования будут учтены при построении модели кредитного скоринга — специальной системы, которая оценивает способность потенциального заёмщика вернуть кредит банку.

## Описание данных

- children — количество детей в семье
- days_employed — общий трудовой стаж в днях
- dob_years — возраст клиента в годах
- education — уровень образования клиента
- education_id — идентификатор уровня образования
- family_status — семейное положение
- family_status_id — идентификатор семейного положения
- gender — пол клиента
- income_type — тип занятости
- debt — имел ли задолженность по возврату кредитов
- total_income — ежемесячный доход
- purpose — цель получения кредита

## Вывод по итогам исследования
Идеальный заёмщик это человек без детей, в разводе или вдовец, зарабатывающий 30001–50000 — 'D' берущий кредит на операции с недвижимостью.
Общий риск я думаю что можно расчитать следующим образом = children[%]+family_status_id[%]+total_income_category[%]+purpose_category[%] / Ко-во параметров(4)
Для идеального заёмщика это будет = 6,8% что не вернёт кредит.

Вообщем все вопросы можно разделить на отдельные df и потом их объеденить например на разных листах и уже основываясь на этих данных писать скоринг. Можно ещё и возраст разбить по категориям.
Вывод о том что чем больше детей тем меньше желающих взять кредит исходит от уменьшения количества строк в колонке "всего" тобиш самих людей. Только самые отчаенные будут брать кредиты когда у них больше 2 ребёнка. Так как это доп расходы. Соответвено об этом и говорит колонка потому что таких людей очень мало. А если они и есть то у них самый большой % невозврата 9.8%. При любом количестве детей % невозврата в любом случае выше чем без детей.
