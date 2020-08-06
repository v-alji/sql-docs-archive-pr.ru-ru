---
title: Занятие 4. исполнение прогнозов потребительской корзины | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b3238f1b-ea04-4253-ade2-838a806b62fe
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 3b49fc242eb8b2242269c5af33cc094937bbe0de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658588"
---
# <a name="lesson-4-executing-market-basket-predictions"></a>Занятие 4: Прогнозирование покупательского поведения
  На этом занятии будет использоваться `SELECT` Инструкция DMX для создания прогнозов на основе моделей взаимосвязей, созданных на [занятии 2. Добавление моделей интеллектуального анализа данных в структуру интеллектуального анализа данных для рынка](../../2014/tutorials/lesson-2-adding-mining-models-to-the-market-basket-mining-structure.md). Прогнозирующий запрос создается с помощью инструкции расширений интеллектуального анализа данных `SELECT` с добавлением предложения `PREDICTION JOIN`. Дополнительные сведения о синтаксисе прогнозирующего подключения см. в разделе [SELECT FROM &#60;model&#62; PREDICTION join &#40;DMX&#41;](/sql/dmx/select-from-model-cases-dmx).  
  
 Форма **Выбор из \<model> прогнозного подключения** `SELECT` инструкции содержит три части:  
  
-   Список столбцов модели интеллектуального анализа и функции прогнозирования, возвращаемые в результирующем наборе. В этом списке также могут содержаться входные столбцы источника данных.  
  
-   Исходный запрос, определяющий данные, которые используются при создании прогноза. Например, если в пакете создается много прогнозов, исходный запрос может получить список клиентов.  
  
-   Сопоставление столбцов модели интеллектуального анализа данных с исходными данными. При совпадении имен столбцов можно использовать синтаксис `NATURAL PREDICTION JOIN` и пропустить процесс сопоставления столбцов.  
  
 Запрос можно расширить функциями прогнозирования. Функции прогнозирования предоставляют дополнительные данные, например вероятность возникновения предсказанного события, а также поддержку прогнозирования на наборе обучающих данных. Дополнительные сведения о функциях прогнозирования см. в разделе [функции &#40;DMX&#41;](/sql/dmx/functions-dmx).  
  
 Для создания прогнозирующих запросов можно также использовать построитель прогнозирующих запросов среды [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].  
  
## <a name="singleton-prediction-join-statement"></a>Одноэлементная инструкция PREDICTION JOIN  
 Первым шагом является создание одноэлементного запроса с помощью синтаксиса **выборки из \<model> прогнозируемого объединения** и предоставление одного набора значений в качестве входных данных. В следующем фрагменте показан общий пример одноэлементной инструкции:  
  
```  
SELECT <select list>  
    FROM [<mining model>]   
[NATURAL] PREDICTION JOIN  
(SELECT '<value>' AS [<column>],   
    (SELECT 'value' AS [<nested column>] UNION  
        SELECT 'value' AS [<nested column>] ...)   
    AS [<nested table>])  
AS [<input alias>]  
```  
  
 В первой строке кода определяются столбцы модели интеллектуального анализа, которые возвращают запрос, а также указывается имя модели интеллектуального анализа данных, которая использовалась для создания прогноза:  
  
```  
SELECT <select list> FROM [<mining model>]   
```  
  
 В следующей строке кода указывается операция, которая будет выполнена. Поскольку имена столбцов и их значения будут введены именно так, как это требуется для модели, можно использовать синтаксис `NATURAL PREDICTION JOIN`. Однако если имена столбцов отличались друг от друга, потребуется указать сопоставления между столбцами в модели и столбцами в новых данных путем добавления предложения `ON`.  
  
```  
[NATURAL] PREDICTION JOIN  
```  
  
 Следующие строки кода определяют товар в корзине покупателя, на основе которого будет сформирован прогноз относительно следующих покупок данного клиента:  
  
```  
(SELECT '<value>' AS [<column>],   
    (SELECT 'value' AS [<nested column>] UNION  
        SELECT 'value' AS [<nested column>] ...)   
    AS [<nested table>])  
```  
  
## <a name="lesson-tasks"></a>Задачи занятия  
 На этом занятии будут выполнены следующие задачи.  
  
-   Создание запроса для прогнозирования последующих возможных покупок клиента на основе данных о позициях товара, уже находящихся в его корзине. Этот запрос будет создан с использованием модели интеллектуального анализа данных с *MINIMUM_PROBABILITY*по умолчанию.  
  
-   Создание запроса для прогнозирования последующих возможных покупок клиента на основе данных о позициях товара, уже находящихся в его корзине. Этот запрос основан на другой модели, в которой *MINIMUM_PROBABILITY* установлен в значение 0,01. Поскольку значение по умолчанию для *MINIMUM_PROBABILITY* в моделях взаимосвязей равно 0,3, запрос в этой модели должен возвращать больше элементов, чем запрос по модели по умолчанию.  
  
## <a name="create-a-prediction-by-using-a-model-with-the-default-minimum_probability"></a>Формирование прогноза с помощью модели со значением свойства MINIMUM_PROBABILITY по умолчанию  
  
#### <a name="to-create-an-association-query"></a>Создание запроса взаимосвязей  
  
1.  В **обозревателе объектов**щелкните правой кнопкой мыши экземпляр служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , наведите указатель на пункт **создать запрос**и выберите **DMX (расширения интеллектуального анализа данных** ), чтобы открыть редактор запросов.  
  
2.  Скопируйте общий пример инструкции `PREDICTION JOIN` в пустой запрос.  
  
3.  Вместо  
  
    ```  
    <select list>   
    ```  
  
     на:  
  
    ```  
    PREDICT([Default Association].[Products],INCLUDE_STATISTICS,3)  
    ```  
  
     Можно просто включить имя столбца [Products], но с помощью функции [прогнозирования &#40;расширений интеллектуального анализа данных&#41;](/sql/dmx/predict-dmx) можно ограничить количество продуктов, возвращаемых алгоритмом, на три. С помощью инструкции `INCLUDE_STATISTICS` можно получить сведения о поддержке, вероятности и скорректированной вероятности для каждой позиции товара. Такие статистические данные позволяют оценить точность прогнозирования.  
  
4.  Вместо  
  
    ```  
    [<mining model>]   
    ```  
  
     на:  
  
    ```  
    [Default Association]  
    ```  
  
5.  Вместо  
  
    ```  
    (SELECT '<value>' AS [<column>],   
        (SELECT 'value' AS [<nested column>] UNION  
            SELECT 'value' AS [<nested column>] ...)   
        AS [<nested table>])  
    ```  
  
     на:  
  
    ```  
    (SELECT (SELECT 'Mountain Bottle Cage' AS [Model]  
      UNION SELECT 'Mountain Tire Tube' AS [Model]  
      UNION SELECT 'Mountain-200' AS [Model]) AS [Products]) AS t  
    ```  
  
     Здесь инструкция `UNION` используется для указания трех позиций товара, которые должны быть добавлены в корзину вместе с прогнозируемыми товарами. Столбец Model инструкции `SELECT` относится к столбцу модели, содержащемуся во вложенной таблице товаров.  
  
     Полная инструкция теперь должна выглядеть следующим образом.  
  
    ```  
    SELECT  
      PREDICT([Default Association].[Products],INCLUDE_STATISTICS,3)  
    From  
      [Default Association]  
    NATURAL PREDICTION JOIN  
    (SELECT (SELECT 'Mountain Bottle Cage' AS [Model]  
      UNION SELECT 'Mountain Tire Tube' AS [Model]  
      UNION SELECT 'Mountain-200' AS [Model]) AS [Products]) AS t  
    ```  
  
6.  В меню **Файл** щелкните **Сохранить DMXQuery1.dmx как**.  
  
7.  В диалоговом окне **Сохранить как** перейдите в соответствующую папку и присвойте файлу имя `Association Prediction.dmx` .  
  
8.  На панели инструментов нажмите кнопку **Выполнить** .  
  
     Запрос возвращает таблицу, содержащую три продукта: HL Mountain, крыльев Set-Mountain и ML Mountain. В таблице эти продукты перечислены в порядке их вероятности. Возвращаемый продукт, который имеет наибольшую вероятность попасть в один и тот же список покупок с тремя продуктами, перечисленными в запросе, отображается в верхней части таблицы. Два продукта, расположенные ниже, — следующие по вероятности включения в список покупок. Кроме этого, в таблице содержатся статистические данные, описывающие точность прогноза.  
  
## <a name="create-a-prediction-by-using-a-model-with-a-minimum_probability-of-001"></a>Формирование прогноза с помощью модели со значением 0,01 у свойства MINIMUM_PROBABILITY  
  
#### <a name="to-create-an-association-query"></a>Создание запроса взаимосвязей  
  
1.  В **обозревателе объектов**щелкните правой кнопкой мыши экземпляр служб [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , наведите указатель на пункт **создать запрос**и выберите **DMX (расширения интеллектуального анализа данных** ), чтобы открыть редактор запросов.  
  
2.  Скопируйте общий пример инструкции `PREDICTION JOIN` в пустой запрос.  
  
3.  Вместо  
  
    ```  
    <select list>   
    ```  
  
     на:  
  
    ```  
    PREDICT([Modified Association].[Products],INCLUDE_STATISTICS,3)  
    ```  
  
4.  Вместо  
  
    ```  
    [<mining model>]   
    ```  
  
     на:  
  
    ```  
    [Modified Association]  
    ```  
  
5.  Вместо  
  
    ```  
    (SELECT '<value>' AS [<column>],   
        (SELECT 'value' AS [<nested column>] UNION  
            SELECT 'value' AS [<nested column>] ...)   
        AS [<nested table>])  
    ```  
  
     на:  
  
    ```  
    (SELECT (SELECT 'Mountain Bottle Cage' AS [Model]  
      UNION SELECT 'Mountain Tire Tube' AS [Model]  
      UNION SELECT 'Mountain-200' AS [Model]) AS [Products]) AS t  
    ```  
  
     Здесь инструкция `UNION` используется для указания трех позиций товара, которые должны быть добавлены в корзину вместе с прогнозируемыми товарами. Столбец `[Model]` инструкции `SELECT` относится к столбцу, содержащемуся во вложенной таблице товаров.  
  
     Полная инструкция теперь должна выглядеть следующим образом.  
  
    ```  
    SELECT  
      PREDICT([Modified Association].[Products],INCLUDE_STATISTICS,3)  
    From  
      [Modified Association]  
    NATURAL PREDICTION JOIN  
    (SELECT (SELECT 'Mountain Bottle Cage' AS [Model]  
      UNION SELECT 'Mountain Tire Tube' AS [Model]  
      UNION SELECT 'Mountain-200' AS [Model]) AS [Products]) AS t  
    ```  
  
6.  В меню **Файл** щелкните **Сохранить DMXQuery1.dmx как**.  
  
7.  В диалоговом окне **Сохранить как** перейдите в соответствующую папку и присвойте файлу имя `Modified Association Prediction.dmx` .  
  
8.  На панели инструментов нажмите кнопку **Выполнить** .  
  
     Запрос возвращает таблицу, содержащую три продукта: HL Mountain, бутылки воды и крыльев Set-Mountain. В таблице эти продукты перечислены в порядке их вероятности. Продукт, который имеет наибольшую вероятность попасть в один и тот же список покупок с тремя продуктами, перечисленными в запросе, отображается в верхней части таблицы. Продукты, расположенные ниже, — следующие по вероятности включения в список покупок. Кроме этого, в таблице содержатся статистические данные, описывающие точность прогноза.  
  
     В результатах этого запроса можно увидеть, что значение параметра *MINIMUM_PROBABILITY* влияет на результаты, возвращаемые запросом.  
  
 Это было последним этапом учебника «Потребительская корзина». Созданный набор моделей может быть использован для прогнозирования товаров, которые клиент обычно покупает одновременно.  
  
 Сведения об использовании расширений интеллектуального анализа данных в другом прогнозном сценарии см. в руководстве по использованию расширений интеллектуального анализа [данных Bike](../../2014/tutorials/bike-buyer-dmx-tutorial.md)Buyer.  
  
## <a name="see-also"></a>См. также:  
 [Примеры запросов к модели взаимосвязей](../../2014/analysis-services/data-mining/association-model-query-examples.md)   
 [Интерфейсы запросов интеллектуального анализа данных](../../2014/analysis-services/data-mining/data-mining-query-tools.md)  
  
  