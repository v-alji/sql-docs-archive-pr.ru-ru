---
title: Создание структуры модели интеллектуального анализа данных кластеризации последовательностей (учебник по интеллектуальному анализу данных — средний уровень) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: e9339227-6c2e-4c4b-8be2-8c1960bc4a8d
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 37d0a1738a758a9d8c4fd6b80310037937a9803f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658006"
---
# <a name="creating-a-sequence-clustering-mining-model-structure-intermediate-data-mining-tutorial"></a>Создание структуры модели интеллектуального анализа данных кластеризации последовательностей (учебник по интеллектуальному анализу данных — средний уровень)
  Первым шагом при создании модели интеллектуального анализа кластеризации последовательностей является использование мастера интеллектуального анализа данных для создания новой структуры интеллектуального анализа и модели интеллектуального анализа данных на основе [!INCLUDE[msCoName](../includes/msconame-md.md)] алгоритма кластеризации последовательностей.  
  
 Для этой цели будет использоваться представление источника данных, которое использовалось для анализа покупательского поведения, к которому добавляется столбец, содержащий идентификатор `sequence`. В данном сценарии «sequence» означает порядок, в котором покупатели добавляют элементы в свою корзину во время покупок.  
  
 Также будут добавлены несколько столбцов, которые используются в одной из моделей для группировки покупателей по демографическому признаку.  
  
### <a name="to-create-a-sequence-clustering-structure-and-model"></a>Создание структуры кластеризации последовательностей и модели  
  
1.  В обозреватель решений в щелкните [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] правой кнопкой мыши элемент **структуры интеллектуального анализа данных** и выберите пункт **создать структуру интеллектуального анализа данных**.  
  
2.  На странице **Вас приветствует мастер интеллектуального анализа данных** нажмите кнопку **Далее**.  
  
3.  На странице **Выбор метода определения** убедитесь, что выбран параметр **из существующей реляционной базы данных или хранилища данных** , а затем нажмите кнопку **Далее**.  
  
4.  На странице **Создание структуры интеллектуального анализа данных** убедитесь, что выбран параметр **создать структуру интеллектуального анализа с моделью интеллектуального** анализа. Затем щелкните раскрывающийся список для параметра, **какой метод интеллектуального анализа данных вы хотите использовать?** и выберите пункт **Кластеризация последовательностей (Майкрософт**). Щелкните **Далее**.  
  
     Откроется страница **Выбор представления источника данных** . В разделе **Доступные представления источников данных**выберите `Orders` .  
  
     Заказы — это то представление источника данных, которое использовалось для сценария потребительской корзины. Если вы не создали это представление источника данных, см. [руководство по добавлению представления источников данных с вложенными таблицами &#40;учебник по интеллектуальному анализу данных&#41;](../../2014/tutorials/adding-a-data-source-view-with-nested-tables-intermediate-data-mining-tutorial.md).  
  
5.  Щелкните **Далее**.  
  
6.  На странице **Выбор типов таблиц** установите флажок Case ( **регистр** ) рядом с таблицей **vAssocSeqOrders** и установите флажок **Nested (вложенный** ) рядом с таблицей **vAssocSeqLineItems** . Щелкните **Далее**.  
  
    > [!NOTE]  
    >  Если при выборе флажка « **case** » или « **Nested** » появляется ошибка, то возможно, что соединение в представлении источника данных неверно. Вложенная таблица **vAssocSeqLineItems**должна быть подключена к таблице вариантов, **vAssocSeqOrders** с соединением типа «многие к одному». Можно изменить эту связь, щелкнув правой кнопкой мыши на линии соединения и затем изменив направление соединения на обратное. Дополнительные сведения см. в разделе [диалоговое окно "Создание или изменение связи" &#40;Analysis Services многомерных данных&#41;](../../2014/analysis-services/create-or-edit-relationship-dialog-box-analysis-services-multidimensional-data.md).  
  
7.  На странице **Определение обучающих данных** выберите столбцы для использования в модели, установив флажок следующим образом:  
  
    -   **IncomeGroup** Установите флажок **Вход** .  
  
         Данный столбец содержит полезную информацию о покупателях, которую можно использовать для кластеризации. Такая информация будет использоваться в первой модели и не будет учитываться во второй.  
  
    -   **OrderNumber** Установите `Key` флажок.  
  
         Данное поле будет использоваться в качестве идентификатора таблицы вариантов либо значения `Key`. В целом ключевое поле таблицы вариантов никогда не используется в качестве входных данных, поскольку ключ содержит уникальные значения, не представляющие интереса для кластеризации.  
  
    -   **Регион** Установите флажок **Вход** .  
  
         Данный столбец содержит полезную информацию о покупателях, которую можно использовать для кластеризации. Такая информация будет использоваться в первой модели и не будет учитываться во второй.  
  
    -   **Номер_строки** Установите флажки `Key` и **ввода** .  
  
         Поле **LineNumber** будет использоваться в качестве идентификатора для вложенной таблицы или `Sequence Key` . Ключ для вложенной таблицы всегда должен использоваться для ввода.  
  
    -   **Модель** Установите флажки **Вход** и **прогнозируемые** .  
  
     Убедитесь, что выбраны правильные параметры, а затем нажмите кнопку **Далее**.  
  
8.  На странице **Определение содержимого и типа данных столбцов** убедитесь, что сетка содержит столбцы, типы содержимого и типы данных, приведенные в следующей таблице, а затем нажмите кнопку **Далее**.  
  
    |Таблицы и столбцы|Тип содержимого|Тип данных|  
    |---------------------|------------------|---------------|  
    |IncomeGroup|Discrete|Text|  
    |OrderNumber|Клавиши|Text|  
    |Регион|Discrete|Text|  
    |vAssocSeqLineItems|||  
    |Line Number|Ключевая последовательность|Long|  
    |Модель|Discrete|Text|  
  
9. На странице **Создание проверочного набора** измените **процент данных для тестирования** на 20, а затем нажмите кнопку **Далее**.  
  
10. На странице **Завершение работы мастера** для **имени структуры интеллектуального анализа данных**введите `Sequence Clustering with Region` .  
  
11. В поле **имя модели интеллектуального анализа данных**введите `Sequence Clustering with Region` .  
  
12. Установите флажок **Разрешить детализацию** и нажмите кнопку **Готово**.  
  
## <a name="next-task-in-lesson"></a>Следующая задача занятия  
 [Обработка модели кластеризации последовательностей](../../2014/tutorials/processing-the-sequence-clustering-model.md)  
  
## <a name="see-also"></a>См. также:  
 [Конструктор интеллектуального анализа данных](../../2014/analysis-services/data-mining/data-mining-designer.md)   
 [Алгоритм кластеризации последовательностей (Майкрософт)](../../2014/analysis-services/data-mining/microsoft-sequence-clustering-algorithm.md)  
  
  