---
title: Управление заголовками строк и столбцов (построитель отчетов и службы SSRS) | Документация Майкрософт
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4be6e836-158e-4bc9-8870-7f394d7c7e11
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 19d0deb86bfeea70c92ffb17ec79966788102748
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663984"
---
# <a name="controlling-row-and-column-headings-report-builder-and-ssrs"></a>Управление заголовками строк и столбцов (построитель отчетов и службы SSRS)
  Табличная область данных, матричная область данных или область списка данных может занимать несколько страниц по горизонтали или по вертикали. Можно указать, нужно ли повторять заголовки строк и столбцов на каждой странице. В интерактивном модуле подготовки отчетов, таком как диспетчер отчетов, или при предварительном просмотре отчета также можно указать, нужно ли закреплять заголовки строк и столбцов, чтобы они оставались видимыми во время прокрутки отчета. В таблице или матрице первая строка обычно содержит заголовки столбцов с метками для данных в каждом столбце, а первый столбец обычно содержит заголовки строк с метками для данных в каждой строке. Для вложенных групп может понадобиться повторить первоначальный набор заголовков строк и столбцов, которые содержат метки групп. По умолчанию в область данных списка заголовки не включаются.

 Способ управления повторением или закреплением заголовков зависит от следующих факторов.

-   Для заголовков столбцов, которые повторяются в верхней части каждой страницы:

    -   Содержит ли таблица или матрица область группы столбцов, которая расширяется по горизонтали.

    -   Нужно ли управлять всеми строками, сопоставленными с группами столбцов, как единым целым.

-   Для заголовков строк, которые повторяются в боковой части каждой страницы.

    -   Содержит ли таблица или матрица область группы строк, которая расширяется по вертикали. Заголовки строк поддерживаются только для групп строк с заголовками.

> [!NOTE]
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]

## <a name="understanding-rows-and-columns-in-a-tablix-data-region"></a>Основные сведения о строках и столбцах в области данных табликса
 Таблица или матрица является шаблоном для базовой области данных табликса. Область данных табликса содержит четыре области: область групп строк, которая управляет строками, расширяющимися вниз по отчету, область групп столбцов, которая управляет столбцами, расширяющимися по отчету, область текста, в которой отображаются данные, и угловую область. Чтобы понять, где следует задавать свойства, управляющие повтором или закреплением заголовков, важно знать, что для области данных табликса существуют два представления.

-   **В определении отчета** . Каждая строка или столбец в определении области данных табликса являются элементом табликса из определенной группы строк или столбцов. Элемент табликса может быть статическим или динамическим. Статический элемент табликса содержит метки или подытоги и повторяется один раз на группу. Динамический элемент табликса содержит значения группы и повторяется один раз для каждого уникального значения группы, также называемого экземпляром группы.

-   **В области конструктора.** В области конструктора область данных табликса разделена пунктирными линиями на четыре части. Каждая ячейка в той части, которая соответствует области данных табликса, организована в виде строк и столбов. Строки и столбцы сопоставлены группам, включая группу подробностей. Для выбранной области данных табликса маркеры строк и столбцов, а также выделяющие полоски указывают на принадлежность к группе. Ячейки в области группы строк или столбцов представляют заголовки групп для элементов табликса. Одну строку или столбец можно сопоставить нескольким группам.

     Дополнительные сведения см. в разделах [Область данных табликса &#40;построитель отчетов и службы SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) и [Ячейки, строки и столбцы области данных табликса &#40;построитель отчетов и службы SSRS&#41;](tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md).

 Для областей данных табликса, содержащих области групп строк или столбцов, сопоставленными строками и столбцами можно управлять, задавая свойства в области данных табликса. Во всех остальных случаях управление строками и столбцами выполняется путем установки свойств в панели «Свойства» для выбранного элемента табликса. Пошаговые инструкции см. в разделах [Отображение заголовков строк и столбцов на нескольких страницах (построитель отчетов и службы SSRS)](display-row-and-column-headers-on-multiple-pages-report-builder-and-ssrs.md) и [Сохранение заголовков видимыми при прокрутке отчета (построитель отчетов и службы SSRS)](keep-headers-visible-when-scrolling-through-a-report-report-builder-and-ssrs.md).

##  <a name="examples"></a><a name="Top"></a> Примеры
 Наиболее распространенными примерами области данных табликса являются матрица, таблица без групп, таблица с группой строк и заголовком группы строк, а также таблица с группой строк без заголовка группы строк. Чтобы управлять повтором или закреплением заголовков, необходимо определить, сопоставлены ли нужные строки или столбцы заголовку группы в области группы строк или группы столбцов.

 В следующих разделах приводятся примеры распространенных макетов области данных табликса.

-   [Матрица](#Matrix)

-   [Таблица без групп](#TableNoGroups)

-   [Таблица с группами строк и областью групп строк](#TableRowGroupsGroupHeader)

-   [Таблица с группами строк и без области групп строк](#TableRowGroupsNoGroupHeader)

###  <a name="matrix"></a><a name="Matrix"></a>Таблицу
 По умолчанию простая матрица имеет одну группу строк и одну группу столбцов. На следующем рисунке показана матрица с группой строк, основанной на категориях, и группой столбцов, основанной на географических объектах.

 ![Матрица, строка Category и группа столбцов Geography](../media/rs-basicmatrixdesign.gif "Матрица, строка Category и группа столбцов Geography")

 Пунктирными линиями показаны четыре части табликса. Область групп строк содержит заголовок группы строк, который управляет метками категорий в первом столбце. Аналогично: область групп столбцов содержит заголовок группы столбцов, который управляет метками географических объектов в первой строке. Во время предварительного просмотра при расширении матрицы по странице в первой строке выводятся заголовки столбцов, как показано на следующем рисунке.

 ![Просмотр подготовленной матрицы с развернутыми группами](../media/rs-basicmatrixpreview.gif "Просмотр подготовленной матрицы с развернутыми группами")

 Чтобы повторить или закрепить заголовки столбцов в первой строке, задайте свойства для заголовков столбцов в области данных табликса. Для вложенных групп столбцов автоматически включаются заголовки столбцов.

 Чтобы повторить или закрепить заголовки строк в первом столбце, задайте свойства для заголовков строк в области данных табликса. Для вложенных групп строк автоматически включаются заголовки строк.

 [В начало](#Top)

###  <a name="table-with-no-row-groups"></a><a name="TableNoGroups"></a>Таблица без групп строк
 По умолчанию в простую таблицу без групп включается группа подробностей. На следующем рисунке показана таблица, в которой отображаются категория, номер заказа и данные продаж.

 ![Конструктор, таблица с одной статической и одной динамической строками](../media/rs-tableheaderstaticdesign.gif "Конструктор, таблица с одной статической и одной динамической строками")

 Пунктирные линии отсутствуют, поскольку таблица состоит только из области текста табликса. В первой строке выводятся заголовки столбцов. Эта строка представляет статический элемент табликса, который не сопоставлен группе. Во второй строке выводятся подробные данные. Она представляет динамический элемент табликса, сопоставленный группе подробностей. На следующем рисунке таблица показана в режиме предварительного просмотра.

 ![Просмотр, таблица с одной статической и одной динамической строками](../media/rs-tableheaderstaticpreview.gif "Просмотр, таблица с одной статической и одной динамической строками")

 Чтобы повторить или закрепить заголовки столбцов, задайте в элементе табликса свойства статической строки, входящей в определение области данных табликса. Чтобы выбрать статическую строку, необходимо использовать расширенный режим для панели группирования. На следующем рисунке показана панель групп строк.

 ![Группы строк, таблица с одной статической и одной динамической строками](../media/rs-tableheaderstaticgroupingpanedefault.gif "Группы строк, таблица с одной статической и одной динамической строками")

 На следующем рисунке в расширенном режиме показаны статические и динамические элементы табликса для групп строк в таблице.

 ![Группы строк, расширенный режим, таблица по умолчанию](../media/rs-tableheaderstaticgroupingpaneadvanced.gif "Группы строк, расширенный режим, таблица по умолчанию")

 Чтобы повторить или закрепить заголовки столбцов для элемента табликса, выберите помеченную статическую строку (с меткой**Статическая**). В панели свойств будут выведены свойства для выбранного элемента табликса. Задавая свойства для этого элемента табликса, можно управлять повторением или закреплением первой строки.

 [В начало](#Top)

###  <a name="table-with-row-groups-and-a-row-group-area"></a><a name="TableRowGroupsGroupHeader"></a>Таблица с группами строк и областью групп строк
 Если добавить в простую таблицу группу строк, в области конструктора к таблице будет добавлена область групп строк. На следующем рисунке показана таблица с группой строк, основанной на категориях.

 ![Конструктор, таблица с одной группой строк и подробностями](../media/rs-tableheaderdynamicwithgroupheadercelldesign.gif "Конструктор, таблица с одной группой строк и подробностями")

 Пунктирными линиями показаны область групп строк табликса и область текста табликса. Область групп строк содержит заголовок группы строк, но не содержит заголовка группы столбцов. На следующем рисунке эта таблица показана в режиме предварительного просмотра.

 ![Предварительный просмотр, таблица с одной группой строк и подробностями](../media/rs-tableheaderdynamicwithgroupheadercellpreview.gif "Предварительный просмотр, таблица с одной группой строк и подробностями")

 Чтобы повторить или закрепить заголовки столбцов, используйте метод, описанный в предыдущем примере. На следующем рисунке показан стандартный вид для панели групп строк.

 ![Группы строк, режим по умолчанию с динамическими элементами](../media/rs-tableheaderdynamicgroupingpanedefault.gif "Группы строк, режим по умолчанию с динамическими элементами")

 Чтобы вывести элементы табликса, используйте **Расширенный** режим панели групп строк, как показано на следующем рисунке.

 ![Группы строк, расширенный режим со статическими элементами](../media/rs-tableheaderdynamicwithgroupheadercelladvanced.gif "Группы строк, расширенный режим со статическими элементами")

 Представлены элементы табликса: **Статический**, (**Статический**), "Категория" и (**Подробности**). Если элемент табликса заключен в скобки, это означает, что отсутствует соответствующий заголовок группы. Чтобы повторить или закрепить заголовки столбцов, выберите верхний элемент табликса «Статический» и задайте свойства в панели свойств.

 [В начало](#Top)

###  <a name="table-with-row-groups-and-no-row-group-area"></a><a name="TableRowGroupsNoGroupHeader"></a>Таблица с группами строк и без области групп строк
 В ряде случаев таблица может содержать группы строк, но не содержать область групп строк. Такую таблицу можно получить, например, следующими способами.

-   Возьмите таблицу, содержащую группы строк и область групп строк, и удалите столбцы для области групп строк. Удаляйте только столбцы, не удаляя группы. Например, может понадобиться сделать форматом таблицы простую сетку.

-   Обновите отчет, созданный для предыдущей версии языка определения отчетов, когда не использовались области данных табликса.

 На следующем рисунке показана таблица с группой строк, не содержащая область групп строк в области конструктора.

 ![Конструктор, таблица с группой строк, но без заголовка группы](../media/rs-tableheaderdynamicwithnogroupheadercelldesign.gif "Конструктор, таблица с группой строк, но без заголовка группы")

 Таблица содержит три строки. В первой строке находятся заголовки столбцов. Во второй строке содержится значение группы и подытоги. Третья строка содержит подробные данные. Пунктирные линии отсутствуют, поскольку имеется только область текста табликса. На следующем рисунке эта таблица показана в режиме предварительного просмотра.

 ![Предварительный просмотр, таблица с группой строк, но без заголовка группы](../media/rs-tableheaderdynamicwithnogroupheadercellpreview.gif "Предварительный просмотр, таблица с группой строк, но без заголовка группы")

 Чтобы управлять повтором или закреплением строк, необходимо задать в элементе табликса свойства для каждой строки. В режиме по умолчанию нет разницы между этим примером и предыдущим примером таблицы с группой строк и заголовком группы. На следующем рисунке показана панель группирования для этой таблицы в режиме по умолчанию.

 ![Группы строк, режим по умолчанию с динамическими элементами](../media/rs-tableheaderdynamicgroupingpanedefault.gif "Группы строк, режим по умолчанию с динамическими элементами")

 Однако в расширенном режиме в данной структуре макета выводится другой набор элементов табликса. На следующем рисунке показана панель группирования для этой таблицы в расширенном режиме.

 ![Группы строк, расширенный режим, без заголовка группы](../media/rs-tableheaderdynamicwithnogroupheadercelladvanced.gif "Группы строк, расширенный режим, без заголовка группы")

 В области групп строк показаны следующие элементы табликса: (**Статический**), (Категория), (**Статический**) и (**Подробности**). Чтобы повторить или закрепить заголовки столбцов, выберите верхний элемент табликса (**Статический**) и задайте свойства в панели свойств.

 [В начало](#Top)

## <a name="renderer-support-for-repeating-or-freezing-headers"></a>Поддержка повторения и закрепления заголовков в модулях подготовки отчетов
 Различные модули подготовки отчетов по-разному поддерживают повторение и закрепление заголовков.

 Модули подготовки отчетов, использующие физические страницы (PDF, Image, Print), поддерживают следующие функции:

-   повторение заголовков строк, если область данных табликса занимает несколько страниц по горизонтали;

-   повторение заголовков столбцов, если область данных табликса занимает несколько страниц по вертикали.

 Кроме того, модули подготовки отчетов, использующие мягкие разрывы страниц (диспетчер отчетов, предварительный просмотр отчетов, элемент управления средством просмотра отчетов), поддерживают следующие функции:

-   сохранение заголовков строк в видимой области во время горизонтальной прокрутки отчета;

-   сохранение заголовков столбцов в видимой области во время вертикальной прокрутки отчета.

 Дополнительные сведения см. в разделе [Поведение при подготовке к просмотру (построитель отчетов и службы SSRS)](rendering-behaviors-report-builder-and-ssrs.md).

## <a name="see-also"></a>См. также:
 [Фильтрация, группировка и сортировка данных &#40;построитель отчетов и ssrs&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md) [списки &#40;ПОСТРОИТЕЛЬ отчетов и службы SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md) [разбиения на страницы](pagination-in-reporting-services-report-builder-and-ssrs.md) Reporting Services &#40;построитель отчетов и службы SSRS&#41;[Экспорт отчетов &#40;построитель отчетов и SSRS&#41;](../report-builder/export-reports-report-builder-and-ssrs.md)

