### 1. Мови програмування та мовні процесори

При вивченні мов програмування, як правило, виділяють три аспекти:
- Прагматичний;
- Семантичний;
- Синтаксичний.

_Прагматичний аспект_ (прагматика мови програмування) визначає клас задач, на
рішення яких орієнтується мова програмування. Як правило, прагматичний аспект
менш формалізований в порівнянні з семантичним та синтаксичним аспектами.

З урахуванням на рішення задач певного класу мови програмування можна
поділити на процедурні та непроцедурні.

Процедурні мови програмування орієнтовані перш за все на опис
(визначення) алгоритмів, тобто по суті використовуються для побудови процедур
обробки даних. До таких мов ми відносимо всім відомі мови програмування, такі
як `Pascal`, `Fortran`, `C` та ін.

Непроцедурні мови програмування на відміну від процедурних неявно
визначають процедури обробки даних. Частіше всього такі мови
використовуються для побудови завдань на обробку даних. При цьому, при
допомозі інструкцій непроцедурної мови програмування визначається що
необхідно зробити з даними і явно не визначається як (при допомозі яких
алгоритмів) необхідно розв'язати задачу. До непроцедурних мов програмування
ми відносимо командні мови операційних систем, мови управління в пакетах
прикладних програм та ін.

Як процедурні, так і непроцедурні мови програмування можуть
орієнтуватися як на декілька класів задач, так і конкретну предметну область. В
першому випадку ми будемо говорити про універсальні мови програмування
(`Pascal`, `Fortran`, `C`), в другому &mdash; про спеціалізовані мови програмування (`Snobol`,
`Lisp`).

_Семантичний аспект_ (семантика мови програмування) визначається
шляхом конкретизації базових функцій обробки даних, набору конструкцій
управління та методами побудови більш "складних" програм на основі "простих".

Наприклад, визначивши як базовий тип даних "рядок" ми повинні
запропонувати "традиційний" набір функцій обробки таких даних: порівняння
рядків, виділення частини рядка, конкатенацію рядків та ін.

Семантика мови програмування має бути визначена формально, інакше в
подальшому неможливо буде побудувати відповідний мовний процесор. На
сьогодні існують два основних напрямки визначення семантики мов
програмування: методи денотаційної семантики та методи операційної семантик.
Методи денотаційної семантики базуються на відповідних алгебрах, методи
операційної семантики базуються на синтаксичних структурах програм.

_Синтаксичний аспект_ (синтаксис мови програмування) визначає набір
синтаксичних конструкцій мови програмування, які використовуються для нотації
(запису) семантичних одиниць в програмі. Про синтаксис мови програмування
можна сказати як про форму, яка є суть похідною від семантики. Для визначення
(опису) синтаксису мови програмування використовуються як механізми, що
орієнтовані на синтез, так і механізми, орієнтовані на аналіз. Задачі аналізу та
синтезу синтаксичних структур програм &mdash; це дуальні задачі. Їх конкретизацію ми
будемо розглядати в наступних розділах.

Виходячи з вищенаведеного, щоб побудувати мову програмування потрібно:
- визначити клас (класи) задач, на розв'язок яких орієнтована мова 
	програмування;
- виділити базові типи даних та функції їх обробки, указати конструкції
	управління в програмах. Побудувати механізми конструювання більш складних
	програм та структур даних на основі більш простих одиниць;
- визначити синтаксис мови програмування.

_Мовні процесори_ реалізують мови програмування. Точніше, мовний
процесор призначений для обробки програм відповідної мови програмування. З
точки зору прагматики, мовні процесори діляться на транслятори та
інтерпретатори.

_Мовний процесор типу транслятор (транслятор)_ &mdash; це програмний
комплекс, котрий на вході отримує текст програми на вхідній мові, а на виході
видає версію програми на вихідній мові, що називається об'єктною мовою. В
більшості випадків як об'єктна мова виступає мова команд деякої обчислювальної
машини. Серед трансляторів можна виділити дві програмні системи:
- компілятори &mdash; транслятори з мов програмування високого рівня;
- асемблери &mdash; транслятори машинно-орієнтованих мов програмування.

_Мовний процесор типу інтерпретатор (інтерпретатор)_ &mdash; це програмний
комплекс, котрий на вході отримує текст програми на вхідній мові та вхідні дані,
які в подальшому обробляються програмою, а на виході видає результати
обчислень (вихідні дані).

Оскільки транслятори та інтерпретатори реалізують мови програмування,
вони мають спільні риси: їх структура досить схожа, в основу їх реалізації
покладено спільні теоретичні результати та практичні методи реалізації.

**Структура транслятора:**
1. Вхідний текст програми
2. Лексичний аналіз
3. Синтаксичний аналіз
4. Семантичний аналіз
5. Оптимізація проміжного коду
6. Генерація коду
7. Вихідний (об'єктний) код

Призначення основних компонентів транслятора:
1. _Лексичний аналізатор._
	Вхід: вхідний текст (послідовність літер) програми.
	Вихід: послідовність лексем програми.
	Лексема &mdash; це ланцюжок літер, що має певний зміст. Всі лексеми мови
	програмування (їх кількість, як правило, нескінчена) можна розбити на скінчену
	множину класів. Для більшості мов програмування актуальні наступні класи
	лексем:
	- зарезервовані слова;
	- ідентифікатори;
	- числові константи (цілі та дійсні числа);
	- літерні константи;
	- рядкові константи;
	- коди операцій;
	- коментарі. Коментарі безпосередньо не несуть інформації щодо структури
		програми. В подальшому вони не використовуються, тобто не передаються
		синтаксичному аналізатору.
	- дужки та інші елементи програми.
2. _Синтаксичний аналізатор._
	Вхід: послідовність лексем програми.
	Вихід: 
	- "Так" + синтаксична структура (синтаксичний терм) програми,
	- "Ні" + синтаксичні помилки в програмі.
3. _Семантичний аналізатор._
	Вхід: Синтаксичний терм програми.
	Вихід: 
	- "Так" + семантична структура (семантичний терм) програми,
	- "Ні" + семантичні помилки в програмі.
4. _Оптимізація проміжного коду._
	Вхід: семантичний терм програми.
	Вихід: оптимізований семантичний терм програми.

	Оптимізація &mdash; це еквівалентне перетворення програми на основі певних
	критеріїв. Серед критеріїв оптимізації можна виділити оптимізацію по пам'яті та
	оптимізацію по швидкості виконання результуючої програми. В залежності від
	підходів по оптимізації програми можна розглядати машиннозалежні та
	машиннонезалежні методи оптимізації. На відміну від машиннонезалежних
	методів машиннозалежні методи оптимізації враховують архітектурні особливості
	ЕОМ, наприклад, наявність апаратного стека, наявність вільних регістрів тощо.
5. _Генерація об'єктного коду._
	Вхід: семантичний терм програми.
	Вихід: результуючий (об'єктний) код програми.