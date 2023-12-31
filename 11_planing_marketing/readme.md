Анализ данных и состаление прогнозов
Статус проекта: Завершен

Выявление закономерностей, определяющих успешность игры для поиска потенциально популярных продуктов и планирования рекламных кампаний.

Описание данных

• Name — название игры
• Platform — платформа
• Year_of_Release — год выпуска
• Genre — жанр игры
• NA_sales — продажи в Северной Америке (миллионы проданных копий)
• EU_sales — продажи в Европе (миллионы проданных копий)
• JP_sales — продажи в Японии (миллионы проданных копий)
• Other_sales — продажи в других странах (миллионы проданных копий)
• Critic_Score — оценка критиков (максимум 100)
• User_Score — оценка пользователей (максимум 10)
• Rating — рейтинг от организации ESRB (англ. Entertainment Software Rating Board). Эта ассоциация определяет рейтинг компьютерных игр и присваивает им подходящую возрастную категорию.
Шаг 2. Подготовить данные
• Заменить названия столбцов (приведите к нижнему регистру);
• Преобразуйте данные в нужные типы. Опишите, в каких столбцах заменили тип данных и почему;
• Обработать пропуски при необходимости:
• Объяснить, почему заполнили пропуски определённым образом или почему не стали это делать;
• Описать причины, которые могли привести к пропускам;
• Обратить внимание на аббревиатуру 'tbd' в столбце с оценкой пользователей. Отдельно разобрать это значение и описать, как его обработать;
• Посчитать суммарные продажи во всех регионах и записать их в отдельный столбец.
Шаг 3. Провести исследовательский анализ данных
• Посмотреть, сколько игр выпускалось в разные годы. Важны ли данные за все периоды?
• Посмотрть, как менялись продажи по платформам. Выберите платформы с наибольшими суммарными продажами и постройте распределение по годам. За какой характерный срок появляются новые и исчезают старые платформы?
• Возять данные за соответствующий актуальный период. Актуальный период определите самостоятельно в результате исследования предыдущих вопросов. Основной фактор — эти данные помогут построить прогноз на 2017 год.
• Не учитывайть в работе данные за предыдущие годы.
• Какие платформы лидируют по продажам, растут или падают? Выберать несколько потенциально прибыльных платформ.
• Построить график «ящик с усами» по глобальным продажам игр в разбивке по платформам. Опишите результат.
• Посмотреть, как влияют на продажи внутри одной популярной платформы отзывы пользователей и критиков. Постройте диаграмму рассеяния и посчитайте корреляцию между отзывами и продажами. Сформулируйте выводы.
• Соотнести выводы с продажами игр на других платформах.
• Посмотреть на общее распределение игр по жанрам. Что можно сказать о самых прибыльных жанрах? Выделяются ли жанры с высокими и низкими продажами?
Шаг 4. Составить портрет пользователя каждого региона
• Определить для пользователя каждого региона (NA, EU, JP):
• Самые популярные платформы (топ-5). Опишите различия в долях продаж.
• Самые популярные жанры (топ-5). Поясните разницу.
• Влияет ли рейтинг ESRB на продажи в отдельном регионе?
Шаг 5. Проверить гипотезы
• Средние пользовательские рейтинги платформ Xbox One и PC одинаковые;
• Средние пользовательские рейтинги жанров Action (англ. «действие», экшен-игры) и Sports (англ. «спортивные соревнования») разные.Задать самостоятельно пороговое значение alpha.
• Пояснить: Как сформулированы нулевая и альтернативная гипотезы;
• Пояснить: Какой критерий применяются для проверки гипотез и почему.


Выводы:
0.1. Изучение и предобработка данных
Мы видим 16715 записей. 2 проуска в имени, 2 пропуска в жанре, 269 пропусков в годе выпуска, 6701 пропуск в оценке пользователей, 6766 пропусков в рейтинге и 8578 пропусков в оценке критиков. По типам: оценки пользователей лучше перевести во float. Явных дубликатов не обнаружено.

В данних по имени присутствуют 11559 уникальных значений, чаще всего встречается Need for Speed: Most Wanted; 31 уникальная платформа, самая популярная PS2; годы выпуска с 1980 по 2016; 12 уникальных жарнов, самый частый Action; продажи в Америке от 0 до 41.3 млн, в среднем 0.26 млн; продажи в Европе от 0 до 28,96 млн, в среднем 0.14 млн; продажи в Японнии от 0 до 10.22 млн, в среднем 0.07 млн; продажи в других странах от 0 до 10.57 млн, в среднем 0.047 млн; Оценки критиков от 13 до 98, в среднем 68;

Оценки пользователей тип object - уникальных значений 96 и чаще всего встречается tbd (возможно еще не определена); В рейтингах уникальных значений 8 и чаще всего встречается 'E'

Четкой кореляции между данными в столбцах не наблюдается.

Видим 2 пропуска имени совпадают с пропуском жанра. В этих строчках пропуске везде кроме даты выпуска и продаж. Не поддаются восстановлению, поэтому удаляем. Так же были найдены 2 неявных дубликата в столбцах название, жанр и год - были удалены. Теперь пропуски остались только в дате выпуска, ценках и рейтинге - 4 столбца. Значение tbd скорее всего означает что оценка не определена. Можем заменить его на пустые значения. Так же меняемт тип на Float

Мы определяем игры с пропусками в рейтинге и где у этой же игры есть присвоенный рейтинг(единсвтенный и уникальный у этой игры) по другой платформе и заполняем пропуски значанем рейтинга этой же игры с дургой платформы. Таким образоам мы восстановили 416 значений. Так же есть некоторые игры - 17 штук, по которым одной и той же игре на разных платформах присовен разный рейтинг. Возможно это ошибка, тк одной игре, вероятнее всего не может быть присвлено 2 и более рейтинга. Поэтому мы проанализироапли рейтинги и заменяем их на тот, который более полно отражает возрастную группу.

Причиной пропусков в датасете могут быть как человеческий фактор при занесении данных, так и техническая обшибка при импорте/экспорте данных. Остальные пропуски мы оставляем без обработки

0.2. Исследовательский анализ данных
Всего было выпущено 11426 игр с 1980 по 2016 год, в среднем 2005 игр в год. Большая часть игр выпущена с 2002 по 2010 год.

Мы видим в среднем что от 2 до 5 лет набирает пополярность и потом переходит к спаду каждая платформа и почти каждая платформа за это период сменяется на другую.

Возьмеме даннные по платформам за последние 3 года. Мы видим что на ибольшей популярностью пользуются PS4, Xone, 3Ds. На них и нужно делать ставыку в разработке на 2017 год. Так же мы вимдим наиболее популярные игры - Wii Sports, Grand Theft Auto V, Super Mario Bros. Последние годы продажи по всем платформам падают.

За 2016 год потенциально наиболее прибыльнмыи могту явлться платформы PS4, XOne и 3DS. На основнаии ящика с усами мы видимо что большая часть продаж игр в разбиввке по 3-м лидирующим платформам за 2016 год имеет примерно одинаековую медиану и большая часть значений нахоодится в интервале от 0 до 0.8 млн штук. В лилирующих платформах выделяются много значений выше среднего, которые по определению графика - могут являться вбросами.

Мы наблюдаем небольшую прямую зависмость общих продаж по платформам от отзывов критиков. И еще меньшую обратную зависиомсть от отзывов пользователей. . Если звять корреляцию по всем играм и всем платформам общих продаж и отзывов, мы видимо что отзывы не оказывают решающего влияния на продажи.

За 2014-2016 годы потенциально наиболее прибыльнмыи могту явлться платформы PS4, XOne и 3DS. На основнаии ящика с усами мы видимо что большая часть продаж игр в разбиввке по 3-м лидирующим платформам за 2016 год имеет примерно одинаековую медиану и большая часть значений нахоодится в интервале от 0 до 0.8 млн штук. В лилирующих платформах выделяются много значений выше среднего, которые по определению графика - могут являться вбросами.

Всего в датасете за 2014-2016г. 12 жанров и 956 игр. Чаще всего встречаются игры в жанре Action и меньше всего в Puzzle. Топ 3 жанра с наиболее высоким медианным показателем продаж: Shooter, Sports, Platform.

Самые больше продажи в США были по платформе PS4. Топ 5 платформ по продажам: PS4, XOne, X360, 3DS, PS3. Первые 2 составляют 71% от всех пролдаж

В Еврое похожий на США рейтинг платформ по продажам от США. Перое место PS4 - 55%. Рейтинг Европы PS4, XOne, PS3, PC, 3DS.

Япония отличаиеся от США и Европы. На 1 месте платформа 3DS - 48%. Второе место делят PS4 и PSV - примерно по 16% у каждой. Рейтинг Японии по платформам 3DS, PS4, PSV, PS3, WiiU.

На 1 месте в США продаются игры жанра Shooter. Топ 5 по жанрам: Shooter, Action, Sports, Role-Playing, Misc. Первые два вместе более 60%.

В Европе первая тройка жанров игр совпадает с США. На первом месте Action. Дальше идут: Shooter, Spotrs, Role-Playing, Racing

В Японнии рейтинг игр по жанрам отличается от США и Европы. На первом месте Role-Playing. Дальше идут: Action, Fighting, Misc, Shooter

В США наибольше популярностью по продажам пользуется рейтинг игр M - 44%.

В Европе так же наибольше популярностью по продажам пользуется рейтинг игр M- более 44%.

В Японнии же наибольше популярностью по продажам пользуется рейтинг игр T - более 40%. Таким образом можно сказать что рейтирга США и Европы местами похож, а в Японии отличаются.

0.3. Проферка гипотез
Гипотеза1: Средние пользовательские рейтинги платформ Xbox One и PC одинаковые. Мы приняли за нулевую гипотезу, что они равны, и за алтернатиыную, что нет. Уровень статистической значимостии примем 5%. В результате не получилось отвергнуть нулевую гипотезу - вероятнее всего рейтинги могут быть равны.

Гипотеза: Средние пользовательские рейтинги жанров Action и Sports разные. Мы приняли за нулевую гипотезу, что они равны, и за алтернативную, что нет. Уровень статистической значимостии примем 5%. В результате нулевую гипотезу отвергаем - вероятнее всего средние значения рейтингов этих жанров разные.

Рекомендации:

Соредоточиться на платформах PS4, XOne и 3DS.
наиболее популярные игры - Wii Sports, Grand Theft Auto V, Super Mario Bros
Для США: платформы PS4, XOne, жанры: Shooter, Action, Sports, рейтинг: M
Для Европы:PS4, XOne, жанры: Action, Shooter, Spotrs, рейтинг: M
Для Японии: 3DS, PS4, жанры: Role-Playing, Action, Fighting, рейтинг: T
