---
title: Как конструктор запросов и представлений представляет объединения (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL pane [Visual Database Tools]
- joins [SQL Server], Query and View Designer
- Diagram pane [Visual Database Tools]
ms.assetid: 20a99dcb-83bd-4aa6-9139-92e2e5ba4887
author: stevestein
ms.author: sstein
ms.openlocfilehash: 55fdea533436f9fa7c2a902667b3166085c27e99
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665197"
---
# <a name="how-the-query-and-view-designer-represents-joins-visual-database-tools"></a>Как конструктор запросов и представлений представляет соединения (визуальные инструменты для баз данных)
  При соединении таблиц [конструктор запросов и представлений](visual-database-tools.md) представляет соединение графически на [панели диаграммы](diagram-pane-visual-database-tools.md) и в виде синтаксиса языка SQL на [панели SQL](sql-pane-visual-database-tools.md).  
  
## <a name="diagram-pane"></a>панели диаграммы  
 На панели диаграмм конструктор запросов и представлений отображает строку соединения данных столбцов, включенных в соединение. Конструктор запросов и представлений отображает одну строку соединения для каждого условия соединения. Например, на следующей иллюстрации показана строка соединения для двух соединяемых таблиц.  
  
 ![Линия соединения показывает связь между двумя таблицами](../../database-engine/media//dv3wbig.gif "Линия соединения показывает связь между двумя таблицами")  
  
 Если таблицы соединяются с использованием более чем одного условия соединения, то в конструкторе запросов и представлений отображается несколько строк соединения, как в следующем примере:  
  
 ![Таблицы, соединенные по нескольким условиям](../../database-engine/media//dv3w9n1.gif "Таблицы, соединенные по нескольким условиям")  
  
 Если соединяемые столбцы данных не отображаются (например прямоугольник, представляющий таблицу или объект с табличной структурой, свернут, или в соединении содержится выражение), то строка соединения помещается в строку заголовка прямоугольника, представляющего таблицу или объект с табличной структурой.  
  
 Форма значка в середине строки соединения показывает, как соединяются таблицы или объекты с табличной структурой. Если в предложении соединения используется оператор, отличный от оператора сравнения равно (=), то данный оператор отображается в значке строки соединения. В следующей таблице перечислены значки, которые появляются в строке соединения.  
  
|**Значок строки соединения**|**Описание**|  
|------------------------|---------------------|  
|![Значок визуальных инструментов для баз данных](../../database-engine/media//dv3wbih.gif "Значок визуальных инструментов для баз данных")|Внутреннее соединение (создается с использованием знака равенства)|  
|![Значок визуальных инструментов для баз данных](../../database-engine/media//dv3wbii.gif "Значок визуальных инструментов для баз данных")|Внутреннее соединение, основанное на операторе «больше».|  
|![Значок визуальных инструментов для баз данных](../../database-engine/media//dv3wbij.gif "Значок визуальных инструментов для баз данных")|Внешнее соединение, в котором участвуют все строки отображаемой слева таблицы, даже если они не имеют соответствий в связанной с ней таблице.|  
|![Значок визуальных инструментов для баз данных](../../database-engine/media//dv3wbik.gif "Значок визуальных инструментов для баз данных")|Внешнее соединение, в котором участвуют все строки отображаемой справа таблицы, даже если они не имеют соответствий в связанной с ней таблице.|  
|![Значок визуальных инструментов для баз данных](../../database-engine/media//dv3wbil.gif "Значок визуальных инструментов для баз данных")|Полное внешнее соединение, включающее все строки из соединяемых таблиц (даже те строки таблиц, для которых нет соответствующих строк в другой соединяемой таблице).|  
  
 Символ в конце строки соединения указывает тип соединения. В следующей таблице перечислены типы соединений и значков, которые появляются в конце строки соединения.  
  
|**Значок в конце строки соединения**|**Тип соединения**|  
|-----------------------------------|----------------------|  
|![Значок визуальных инструментов для баз данных](../../database-engine/media//dv3wbim.gif "Значок визуальных инструментов для баз данных")|Соединение «один к одному»|  
|![Значок визуальных инструментов для баз данных](../../database-engine/media//dv3wbin.gif "Значок визуальных инструментов для баз данных")|Соединение «один ко многим»|  
|![Значок визуальных инструментов для баз данных](../../database-engine/media//dv3wbio.gif "Значок визуальных инструментов для баз данных")|Конструктор запросов и представлений не может определить тип соединения. Такая ситуация часто возникает при создании соединения вручную.|  
  
## <a name="sql-pane"></a>панели SQL  
 В инструкции SQL соединение может быть выражено несколькими способами. Точный синтаксис зависит от используемой базы данных и от того, как определено соединение.  
  
 Параметры синтаксиса для соединения таблиц включают:  
  
-   **Квалификатор JOIN для предложения FROM**.   Ключевые слова INNER и OUTER определяют тип соединения. Такой синтаксис относится к стандарту ANSI SQL-92.  
  
     Например, при соединении таблиц `publishers` и `pub_info` на основе столбца `pub_id` в каждой таблице результирующая инструкция SQL может выглядеть так:  
  
    ```  
    SELECT *  
    FROM publishers INNER JOIN pub_info ON  
       publishers.pub_id = pub_info.pub_id  
    ```  
  
     При создании внешнего соединения вместо слова INNER появляются слова LEFT OUTER или RIGHT OUTER.  
  
-   **Предложение WHERE сравнивает столбцы обеих таблиц**.   Предложение WHERE появляется тогда, когда база данных не поддерживает синтаксис JOIN (или если WHERE введено вручную). Если используется предложение WHERE для создания соединения, то названия обеих таблиц появляются в предложении FROM.  
  
     Например, следующая инструкция соединяет таблицы `publishers` и `pub_info` .  
  
    ```  
    SELECT *  
    FROM publishers, pub_info  
    WHERE publishers.pub_id = pub_info.pub_id  
    ```  
  
## <a name="see-also"></a>См. также:  
 [Запрос с помощью соединений &#40;визуальных инструментов для баз данных&#41;](query-with-joins-visual-database-tools.md)   
 [Диалоговое окно "Соединение" (визуальные инструменты для баз данных)](join-dialog-box-visual-database-tools.md)  
  
  