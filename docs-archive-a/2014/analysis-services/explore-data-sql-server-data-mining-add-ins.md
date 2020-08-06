---
title: Просмотр данных (SQL Server надстроек интеллектуального анализа данных) | Документация Майкрософт
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data preparation
- histogram [data mining]
- data visualization
ms.assetid: 714845a9-4c27-461a-9ba3-149e1e818386
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2572c11e92dcf99dfa3adf661603e8f65f05116e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87734558"
---
# <a name="explore-data-sql-server-data-mining-add-ins"></a>Просмотр данных (надстройки интеллектуального анализа данных SQL Server)
  ![Мастер просмотра данных](media/dmc-explore.gif "Мастер просмотра данных")  
  
 Мастер **просмотра данных** помогает понять тип и объем данных в таблице данных. Мастер наносит на диаграмму распределение и значения для выбранных столбцов поочередно. Можно поэкспериментировать с изменением числа сегментов, способом группировки данных или скопировать диаграмму с содержимым в книгу Excel для просмотра.  
  
 Если в данных содержатся непрерывные числовые данные, можно переключаться между следующими двумя представлениями.  
  
-   **Линейный график.** На этом графике значения данных расположены на оси X, а число вариантов — на оси Y.  
  
-   **Линейчатая диаграмма.** Эта диаграмма группирует значения по числу случаев для каждого значения.  
  
 Если мастер обнаруживает в данных группы, он использует реальное распределение значений данных. Вследствие этого в линейчатой диаграмме не отображаются маркеры обычной целочисленной числовой оси, например 10 или 100. Вместо этого диапазоны на линейчатой диаграмме могут быть, например, 43 521–55 603 (в столбце дохода).  
  
 Если необходимо группировать данные в другие диапазоны, это следует выполнить в Excel перед выполнением анализа данных. Можно также переметить данные с помощью мастера [переразметки](relabel-sql-server-data-mining-add-ins.md) .  
  
## <a name="using-the-explore-data-wizard"></a>Использование мастера просмотра данных  
  
1.  На ленте **интеллектуальный анализ данных** нажмите кнопку **Просмотр данных**.  
  
2.  В диалоговом окне **Выбор источника** выберите таблицу или диапазон ячеек, содержащих данные.  
  
3.  В диалоговом окне **Выбор столбца** выберите столбец для анализа из демонстрационных данных, отображаемых на панели.  
  
4.  В диалоговом окне **Просмотр данных** выберите типы диаграмм для отображения распределения данных.  
  
5.  Можно дополнительно добавить новые столбцы к данным, изменить порядок сегментации данных или скопировать диаграмму в Excel.  
  
### <a name="requirements"></a>Требования  
 Чтобы использовать мастер **просмотра данных** , данные должны находиться в таблице данных Excel.   
  
## <a name="see-also"></a>См. также:  
 [Контрольный список для подготовки к интеллектуальному анализу данных](checklist-of-preparation-for-data-mining.md)  
  
  