---
title: Изучение модели кластеризации последовательностей (учебник по интеллектуальному анализу данных — средний уровень) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: f8a485d5-47ed-4dd5-bb66-ef4d6d463845
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: bac603d2480ec1f344d14351757027de749f8c86
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735637"
---
# <a name="exploring-the-sequence-clustering-model-intermediate-data-mining-tutorial"></a>Изучение модели кластеризации последовательностей (учебник по интеллектуальному анализу данных — средний уровень)
  Теперь, когда **Кластеризация последовательностей** построена с использованием модели регионов, ее можно исследовать с помощью [!INCLUDE[msCoName](../includes/msconame-md.md)] средства просмотра кластеризации последовательностей на вкладке **средство просмотра моделей интеллектуального** анализа данных конструктора интеллектуального анализа. [!INCLUDE[msCoName](../includes/msconame-md.md)]Средство просмотра кластеров последовательностей содержит пять вкладок: **Диаграмма кластеров**, **Профили кластеров**, **характеристики кластера**, **клустердискриминатион**и **переходы состояния**. Дополнительные сведения об использовании этого средства просмотра см. в разделе [Просмотр модели с помощью средства просмотра кластеров последовательностей (Майкрософт](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-sequence-cluster-viewer.md)).  
  
-   [Вкладка «Диаграмма кластеров»](#bkmk_CDiagram)  
  
-   [Вкладка «Профили кластеров»](#bkmk_CProfiles)  
  
-   [Вкладка «Характеристики кластера»](#bkmk_CChars)  
  
-   [Вкладка «сравнения кластеров»](#bkmk_CDiscrim2)  
  
-   [Вкладка «Переходы состояния»](#bkmk_StateTran)  
  
-   [Представление общего содержимого](#bkmk_Generic)  
  
##  <a name="cluster-diagram-tab"></a><a name="bkmk_CDiagram"></a>Вкладка «Диаграмма кластеров»  
 На вкладке **Диаграмма кластеров** в графическом виде отображаются кластеры, обнаруженные алгоритмом в базе данных. Макет диаграммы отображает связи между кластерами, причем похожие кластеры расположены рядом. По умолчанию затенение каждого узла отражает концентрацию вариантов в кластере: чем интенсивнее затененность узла, тем больше вариантов он содержит. Можно изменить заливку узлов таким образом, чтобы оно отражало поддержку внутри каждого кластера для атрибута и состояния.  
  
 Кроме того, можно переименовать кластеры для удобства идентификации и работы с целевыми кластерами. В рамках данного учебника будет переименован кластер, у которого самый высокий процент клиентов из Тихоокеанского региона, а также кластер, который имеет наибольшее количество всех вариантов.  
  
> [!NOTE]  
>  При повторной обработке модели могут измениться варианты, назначенные определенным кластерам, что зависит от данных или параметров модели. Кроме того, в случае переименования кластеров имена будут утеряны при повторной обработке модели интеллектуального анализа данных.  
  
#### <a name="to-change-the-attribute-used-for-highlighting-clusters"></a>Изменение атрибута, используемого для выделения кластеров  
  
1.  В списке **Переменная заливки** выберите **модель**.  
  
2.  В списке **состояние** выберите **циклическое ограничение** .  
  
     После обновления на диаграмме отобразятся точки концентрации выбранного продукта в каждом из кластеров. Кластер с самой темной заливкой содержит максимальную концентрацию велосипедных шапочек. Можно изменить переменную заливки, чтобы использовать любое состояние любого входного столбца.  
  
3.  В списке **Переменная заливки** выберите **Заполнение**.  
  
     Если для переменной заливки задано значение заполнения, на диаграмме будут отображены различия кластеров в зависимости от их размера. Кластер с самой темной заливкой содержит большее количество вариантов, чем другие кластеры.  
  
#### <a name="to-rename-nodes-in-the-model"></a>Переименование узлов модели  
  
1.  Измените **переменную заливки** на `Region` и задайте для параметра **состояние** значение **тихоокеанское**.  
  
2.  Выделите самый затененный узел графа.  
  
3.  Щелкните этот кластер правой кнопкой мыши и выберите команду **Переименовать кластер.**  
  
4.  Введите имя по**тихоокеанскому кластеру.**  
  
5.  Измените значение **переменной заливки** на **Population**.  
  
6.  После обновления графа найдите кластер с наибольшим затенением, который должен быть самым крупным кластером. Если по заливке сложно определить самый крупный кластер, задержите указатель мыши на каждом кластере для отображения подсказки, после чего выберите кластер, который содержит наибольшее количество вариантов.  
  
7.  Щелкните этот кластер правой кнопкой мыши и выберите команду **Переименовать кластер**. Введите новое имя, `Largest Cluster` .  
  
 Можно выполнить детализацию от узла, представляющего кластер, для просмотра сведений о вариантах, содержащихся в каждом кластере. Это бывает полезным, если с результатами анализа нужно выполнить какие-либо действия (например, отправить клиенту сообщение электронной почты). Кроме того, можно просмотреть другие атрибуты вариантов, которые были включены в структуру, но не использовались в модели, например Region и IncomeGroup. Дополнительные сведения о детализации моделей интеллектуального анализа данных в базовых случаях см. в разделе [запросы детализации &#40;&#41;интеллектуального анализа ](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md).  
  
#### <a name="to-drill-through-to-details-from-the-cluster-diagram"></a>Детализация сведений из диаграммы кластеров  
  
1.  Щелкните правой кнопкой мыши `Pacific Cluster` , выберите **Детализация**, а затем выберите **столбцы модели и структуры**.  
  
     Откроется диалоговое окно **Детализация** . Столбцы, которые не используются в модели, но доступны для запросов, имеют префикс **Structure**.  
  
     Можно увидеть, что данный кластер в основном содержит клиентов из Тихоокеанского региона и совсем немного клиентов из других регионов.  
  
2.  Щелкните знак «плюс» во вложенном столбце v Assoc Seq Line Items, чтобы просмотреть последовательность элементов в заказе определенного клиента.  
  
3.  Закройте диалоговое окно **Детализация** .  
  
    > [!NOTE]  
    >  Кнопка **Воспроизведение позволяет выполнить повторный** запрос данных. Однако повторные запросы не изменяют отображаемые данные, если модель не будет динамически обновляться в фоновом режиме другими процессами.  
  
 [К началу](#bkmk_CDiagram)  
  
##  <a name="cluster-profiles-tab"></a><a name="bkmk_CProfiles"></a>Вкладка «Профили кластеров»  
 Вкладка **Профили кластеров** отображает последовательности, которые находятся в каждом кластере. Кластеры перечислены в отдельных столбцах справа от столбца **состояния** .  
  
 В средстве просмотра строка **модели** описывает общее распределение элементов в кластере, а строка **model. Samples** содержит последовательности элементов. Каждая строка цветовых последовательностей в каждой ячейке строки **model. Samples** представляет поведение случайно выбранного пользователя в кластере.  
  
 Каждый цвет в отдельной гистограмме последовательностей отражает модель товара. В условных обозначениях интеллектуального анализа данных последовательности продуктов показываются как с помощью выделения цветом, так и с помощью имен моделей продуктов. Если в модель для кластеризации были добавлены другие столбцы, например Region или Income Group, в средстве просмотра будет отображаться дополнительная строка для каждого такого столбца, содержащего распределение значений в каждом кластере.  
  
#### <a name="to-view-the-sequences-that-are-most-common-in-a-cluster"></a>Просмотр наиболее общих последовательностей в кластере  
  
1.  Щелкните правой кнопкой мыши строку **модели** в столбце для кластера `Largest Cluster` и выберите команду **отобразить условные обозначения**.  
  
     Столбец **Color** содержит затененную полосу, указывающую частоту элементов, найденных в последовательностях. Каждый элемент представлен разным цветом. В столбце **значение** перечислены названия моделей продуктов для каждого цвета. Столбец **Distribution** указывает процент вариантов, содержащих этот элемент в последовательности.  
  
2.  Закройте **обозначения интеллектуального анализа данных**.  
  
3.  Щелкните правой кнопкой мыши строку **model. Samples** в столбце с заголовком, **заполнением** и выберите команду **отобразить условные обозначения**.  
  
4.  Просмотр списка последовательностей в общей модели`.`  
  
     В начале списка «Обозначения интеллектуального анализа данных» располагаются наиболее общие последовательности, поэтому можно заметить, что камера для шины от горного велосипеда часто появляется в качестве первого элемента во многих последовательностях. Это означает, что существует большая вероятность того, что клиент в первую очередь поместит в список покупок камеру для шины от горного велосипеда.  
  
#### <a name="to-drill-through-to-cases-from-the-cluster-viewer"></a>Выполнение детализации к вариантам из средства просмотра кластера  
  
1.  Прокрутите вниз на панели атрибутов, пока не найдете строку для `Region` атрибута.  
  
     Строка содержит гистограмму для каждого кластера в модели, а также одну дополнительную гистограмму для **заполнения**, то есть весь набор вариантов, используемых в модели. Гистограмма представляет собой полосу, имеющую различную окраску, где каждый цвет соответствует определенному атрибуту, а размер окрашенного участка атрибута — проценту вариантов с таким атрибутом.  
  
2.  Сравните гистограммы для переименованных кластеров `Pacific Cluster` и `Largest Cluster` . Каждый кластер располагается в отдельном столбце.  
  
     Оба окрашены сплошными, но разными цветами.  
  
3.  В `Region` строке наведите указатель мыши на цветную гистограмму для `Largest Cluster` .  
  
     В подсказке будут отражены значения фактического процентного соотношения вариантов для каждого региона.  
  
4.  Щелкните правой кнопкой мыши цветную гистограмму в `Region` строке для `Pacific Cluster` , выберите **Детализация**и выберите **только столбцы модели**.  
  
5.  Используйте полосу прокрутки, чтобы просмотреть сведения обо всех клиентах в этом кластере.  
  
     Опять анализируя подробные сведения, можно увидеть, что в кластере содержатся в основном заказы из Тихоокеанского региона и небольшое количество заказов из Северной Америки и Европы.  
  
6.  Закройте диалоговое окно **Детализация** .  
  
 [К началу](#bkmk_CDiagram)  
  
##  <a name="cluster-characteristics-tab"></a><a name="bkmk_CChars"></a>Вкладка «Характеристики кластера»  
 Вкладка **характеристики кластера** содержит сводку переходов между состояниями в кластере за счет отображения полос, визуально отражающих важность значения атрибута для выбранного кластера. Столбец **переменные** указывает, какая модель важна для выбранного кластера или совокупности: определенное значение или связь между значениями, называемая *переходом*. Столбец **значения** содержит более подробные сведения о значении или переходе, а столбец **вероятность** визуально представляет вес этого атрибута или перехода.  
  
#### <a name="to-view-the-important-attributes-for-a-cluster"></a>Просмотр важных атрибутов для кластера  
  
1.  В раскрывающемся списке **кластер** выберите `Pacific Cluster` .  
  
     Список обновляется, отображая характеристики переименованного кластера `Pacific Cluster` . В этом кластере наиболее важной характеристикой является `Region` .  
  
2.  Наведите указатель мыши на затененную полосу в строке для `Region` .  
  
     Очень высока вероятность того, что значение будет «Тихоокеанский». Дополнительные сведения о том, как интерпретировать эти значения, см. в [статье Технический справочник по алгоритму кластеризации последовательностей](../../2014/analysis-services/data-mining/microsoft-sequence-clustering-algorithm-technical-reference.md).  
  
3.  В списке характеристик для кластера найдите первую строку перехода.  
  
4.  Строка перехода содержит текстовый переход в столбце **переменные** и некоторое сочетание последовательных значений атрибутов в столбце **значение** . Последовательность также может содержать исходные точки и отсутствующие значения.  
  
     Например, предположим, что переход имеет значение [Start]-> дорожной лампой. Это означает, что клиенты в данном кластере часто первой в свою корзину покупок помещают камеру для шины от дорожного велосипеда. А это может указывать на то, что данный товар популярен и клиенты ищут его в первую очередь, или на то, что этот товар всего лишь несложно найти на торговом сайте.  
  
5.  Прокрутите список до тех пор, пока не найдете первый переход, у которого нет **[Start]** или в нем **отсутствует** .  
  
     Например, предположим, что вы нашли переход, **Туристический велосипед, туристический лампу**. Это означает, что клиенты в данном кластере часто покупают данные товары одновременно, и именно в такой последовательности.  
  
6.  Задержите указатель мыши на затененной полосе для данного перехода.  
  
     Значение вероятности перехода отображается в виде процентного отношения.  
  
7.  В раскрывающемся списке **кластер** выберите значение **Заполнение (все)**.  
  
     В списке атрибутов после обновления отобразятся характеристики всех заказов, которые были использованы для создания данной модели. В этой модели интеллектуального анализа самая важная характеристика различий между кластерами — `Region` , со значением **Северная Америка**.  
  
 После выполнения указанных задач стали понятны две вещи. Первая — для получения значительного количества сочетаний необходим большой объем данных. Например, последовательности с самыми высокими вероятностью могут включать **[Start]** или **отсутствие** состояния.  
  
 Второй заключается в том, что в атрибутах для есть устойчивый результат кластеризации `Region` , что усложняет Просмотр групп последовательностей. Поэтому принимается решение о создании еще одной модели, в которой используются только последовательности и отсутствуют столбцы для региона или дохода.  
  
 [К началу](#bkmk_CDiagram)  
  
##  <a name="cluster-discrimination-tab"></a><a name="bkmk_CDiscrim2"></a>Вкладка «сравнения кластеров»  
 Вкладка **сравнения кластеров** помогает сравнить два кластера, чтобы определить, какие атрибуты отличают конкретный кластер от другого. Вкладка содержит четыре столбца: **переменные**, **значения**, **Кластер 1**и **Кластер 2**.  Можно выбрать любой кластер, который будет использоваться в качестве **кластера 1** и **кластера 2**.  
  
 Столбец **переменные** сообщает имя атрибута, которое может быть именем столбца или сочетанием имени столбца и **переходом**по слову. В столбце **значения** отображается точное значение атрибута или переход. Затененные полосы в столбцах для **кластера 1** и **кластера 2** указывают стойкость атрибута в сравниваемых кластерах. Чем длиннее полоса, тем выше вероятность, что этот кластер включает варианты с указанным атрибутом.  
  
#### <a name="to-compare-two-clusters-by-using-the-cluster-discrimination-tab"></a>Сравнение двух кластеров с использованием вкладки «Сравнения кластеров»  
  
1.  На вкладке **сравнения кластеров** для **кластера 1**выберите `Pacific Cluster` .  
  
     По умолчанию выбор **кластера 2** изменяется в дополнение к **тихоокеанскому кластеру**.  
  
     Верхний атрибут, отличающийся `Pacific Cluster` от всех остальных вариантов, является регионом. Регион является настолько весомым атрибутом для кластеризации, что нивелирует все остальные атрибуты. Чтобы избежать подобного эффекта, сравните несколько других меньших кластеров между собой. После этого список атрибутов изменится; в нем может появиться больше переходов между моделями.  
  
2.  Найдите строку перехода и задержите указатель мыши на затененной полосе.  
  
     Элементы в столбце **значения** могут включать состояния и переходы. Затемнение для каждого элемента отражает коэффициент сравнения. Дополнительные сведения о значении различных оценок см. в разделе [содержимое моделей интеллектуального анализа данных для моделей кластеризации Последовательностей &#40;Analysis Services-&#41;интеллектуального анализа ](../../2014/analysis-services/data-mining/mining-model-content-for-sequence-clustering-models.md).  
  
 [К началу](#bkmk_CDiagram)  
  
##  <a name="state-transitions-tab"></a><a name="bkmk_StateTran"></a>Вкладка «Переходы состояния»  
 На вкладке **переходы состояния** можно выбрать кластер и просмотреть его переходы по состоянию. Если выбрать значение **Заполнение (все)** из раскрывающегося списка кластер, на схеме отобразится распределение состояний для всей модели интеллектуального анализа данных.  
  
 Каждый узел диаграммы представляет собой состояние или возможное значение анализируемых последовательностей. Цвет фона узла указывает на частоту появления данного состояния. Переходы между состояниями указаны соединяющими такие состояния линиями. Можно переместить ползунок вверх или вниз для изменения порога вероятности переходов. Числа, связанные с некоторыми узлами, указывают на значение вероятности данного состояния.  
  
#### <a name="to-explore-the-relationships-in-the-state-transition-tab"></a>Изучение связей на вкладке «Переходы состояния»  
  
1.  На вкладке **переходы состояния** средства просмотра моделей интеллектуального анализа данных выберите `Pacific Cluster` из списка кластеров. Убедитесь, что выбран параметр **Показывать граничные метки** .  
  
     После обновления графа будут отображены наиболее общие переходы в данном кластере.  
  
2.  Щелкните любой узел, который соединен линией с другим узлом.  
  
     После обновления графа будут выделены связанные узлы. Числовое значение рядом с линией представляет собой вероятность перехода.  
  
3.  Увеличьте количество переходов на диаграмме с помощью ползунка вверх до **всех ссылок**.  
  
4.  Выберите **Заполнение (все)** из **кластера**.  
  
     Примите к сведению, что после загрузки другого кластера граф будет использовать параметры отображения по умолчанию, то есть ползунок будет находиться в среднем положении.  
  
5.  Щелкните самый темный узел в графе, который должен иметь вид " **Спорт-100**".  
  
     Обратите внимание, что данный товар не имеет линий, соединяющих его с другими товарами.  
  
6.  Поднимите ползунок вверх на один пункт, чтобы увеличить количество переходов, включаемых в граф. Не перейдем ко всем **ссылкам** еще.  
  
     После обновления на графе появится несколько новых переходов, но ни один из них не будет включать модель Sport-100.  
  
7.  Переместите ползунок элемент управления ко всем **ссылкам**. Щелкните узел Sport-100, если он еще не выбран.  
  
     После обновления на графе будет отображено большое количество переходов, которые включают модель Sport-100. Направление стрелки соединительной линии говорит о том, была ли модель Sport-100 выбрана в качестве первого или второго участника пары.  
  
8.  Щелкните узел шины для туристического велосипеда и переместите ползунок обратно в среднее положение.  
  
     Во первых, существует множество переходов, соединяющих велосипед с другими продуктами, но при повышении порога вероятности, менее вероятные переходы будут исключены из графа, что приведет только к переходу, обзору крышки > прокрутить трубку. Данный переход означает, что если клиент помещает в свою корзину покупок шину для туристического велосипеда, то существует большая вероятность того, что следующим товаром станет камера шины для туристического велосипеда.  
  
 [К началу](#bkmk_CDiagram)  
  
##  <a name="generic-content-tree-viewer"></a><a name="bkmk_Generic"></a>Средство просмотра деревьев содержимого общего вида  
 Это средство просмотра может использоваться для всех моделей независимо от типа модели и алгоритма. **Средство просмотра деревьев содержимого микрософтженерик** доступно из раскрывающегося списка **средство просмотра** .  
  
 Дерево содержимого представляет модель интеллектуального анализа данных в виде ряда узлов, каждый из которых представляет полученные знания относительно обучающих данных. Узел может содержать закономерность, набор правил, кластер или определение интервала дат, объединяемых некоторыми общими атрибутами. Конкретное содержимое узлов зависит от алгоритма и прогнозируемого атрибута, но общее представление содержимого одинаково.  
  
 Каждый узел можно раскрыть, чтобы увеличить уровень детализации, и скопировать содержимое любого узла в буфер обмена. Дополнительные сведения см. в разделе [Просмотр модели в средстве просмотра деревьев содержимого общего вида (Майкрософт)](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-generic-content-tree-viewer.md).  
  
#### <a name="to-view-details-for-a-sequence-clustering-model-by-using-the-generic-content-tree-viewer"></a>Просмотр сведений о модели кластеризации последовательностей с использованием средства просмотра деревьев содержимого общего вида  
  
1.  На вкладке **средство просмотра моделей интеллектуального анализа данных** щелкните список **средство просмотра** и выберите **средство просмотра деревьев содержимого общего вида (Майкрософт**).  
  
2.  На панели **заголовок узла** щелкните `Pacific Cluster (1)` .  
  
     Имя данного узла состоит из понятного имени кластера, присвоенного ему пользователем, и идентификатора базового узла. Идентификаторы узлов можно использовать для получения дополнительных сведений о модели.  
  
3.  Разверните первый дочерний узел с именем **уровень последовательности для кластера 1**.  
  
     Узел уровня последовательности для кластера содержит сведения о состояниях и переходах, имеющихся в таком кластере. Эти сведения (в столбце NODE_DISTRIBUTION) можно использовать с целью изучения последовательности и состояний каждого кластера или модели в целом.  
  
4.  Продолжайте разворачивать узлы для просмотра сведений на панели средства просмотра HTML-страниц.  
  
 Дополнительные сведения о содержимом модели интеллектуального анализа данных и об использовании сведений в средстве просмотра см. в разделе [содержимое моделей интеллектуального анализа данных для моделей кластеризации Последовательностей &#40;Analysis Services-&#41;интеллектуального анализа ](../../2014/analysis-services/data-mining/mining-model-content-for-sequence-clustering-models.md).  
  
 [К началу](#bkmk_CDiagram)  
  
## <a name="next-task-in-lesson"></a>Следующая задача занятия  
 [Создание связанной модели кластеризации последовательностей &#40;учебник по интеллектуальному анализу данных&#41;](../../2014/tutorials/creating-a-related-sequence-clustering-model-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a>См. также:  
 [Алгоритм кластеризации последовательностей (Майкрософт)](../../2014/analysis-services/data-mining/microsoft-sequence-clustering-algorithm.md)   
 [Примеры запросов к модели кластеризации последовательностей](../../2014/analysis-services/data-mining/sequence-clustering-model-query-examples.md)  
  
  