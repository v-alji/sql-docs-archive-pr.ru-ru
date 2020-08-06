---
title: Изменение прогнозирующего запроса вручную | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- modifying prediction queries
- Mining Model Prediction [Analysis Services], modifying prediction queries
- manual prediction query modification [Analysis Services]
ms.assetid: 9f6a9298-49d5-4675-ad49-977a47dff5a6
author: minewiskan
ms.author: owend
ms.openlocfilehash: e887e935dafcd2428859fd959cb7bc64650c660d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669172"
---
# <a name="manually-edit-a-prediction-query"></a>Изменение прогнозирующего запроса вручную
  После проектирования запроса с использованием построителя прогнозирующих запросов можно изменить этот запрос, переключившись в представление «Текст запроса» на вкладке **Прогноз модели интеллектуального анализа данных** конструктора интеллектуального анализа данных. В нижней части экрана появится текстовый редактор, отображающий запрос, созданный построителем запросов.  
  
 Переключение на представление «Текст запроса» полезно при внесении дополнений в запрос. Например, можно добавить предложение WHERE или ORDER BY.  
  
 С помощью сетки в построителе прогнозирующих запросов можно вставить имена объектов и столбцов и настроить синтаксис отдельных прогнозирующих функций, а затем переключиться в режим ручного редактирования для изменения значений параметров.  
  
> [!NOTE]  
>  При переключении из представления **Текст запроса** обратно в представление **Проектирование** все изменения, внесенные в представлении **Текст запроса** , будут потеряны.  
  
### <a name="modify-a-query"></a>Изменение запроса  
  
1.  На вкладке **Прогноз модели интеллектуального анализа данных** конструктора интеллектуального анализа данных в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]нажмите кнопку **SQL**.  
  
     Сетка в нижней части экрана заменится текстовым редактором, содержащим запрос. В этом редакторе можно ввести в запрос изменения.  
  
2.  Чтобы запустить запрос, выберите в меню **Модель интеллектуального анализа данных** команду **Результат**или нажмите соответствующую кнопку для переключения на результаты запроса.  
  
    > [!NOTE]  
    >  Если созданный запрос содержит ошибку, в окне результатов не будут показаны результаты и не будет выведено сообщение об ошибке. Чтобы исправить ошибку, нажмите кнопку **Конструктор** или выберите один из пунктов — **Конструктор** или **Запрос** — в меню **Модель интеллектуального анализа данных** .  
  
## <a name="see-also"></a>См. также:  
 [Запросы интеллектуального анализа данных](data-mining-queries.md)   
 [Прогнозирование конструктор запросов &#40;интеллектуального анализа данных&#41;](../prediction-query-builder-data-mining.md)   
 [Занятие 6. Создание прогнозов и работа с ними (учебник по интеллектуальному анализу данных — начальный уровень)](../../tutorials/lesson-6-creating-and-working-with-predictions-basic-data-mining-tutorial.md)  
  
  