---
title: Задача 2. Сопоставление столбцов Excel с доменами DQS | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: f347cc92-950f-4021-b7af-393640dfe821
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 293b035ff52845959e2c8b70c63df643ae6e3e55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667506"
---
# <a name="task-2-mapping-excel-columns-to-dqs-domains"></a>Задача 2. Сопоставление столбцов Excel с доменами DQS
    
1.  На странице **Сопоставление** выберите **Файл Excel** как **Источник данных**.  
  
2.  Нажмите кнопку **Обзор**, выберите **Suppliers.xlsx**и нажмите кнопку **Открыть**.  
  
3.  Выберите **инкомингсупплиерс $** для **листа**.  
  
4.  Сопоставьте столбцы, как показано в следующей таблице и на следующем снимке экрана. При создании сопоставлений для домена **состояния** нажмите кнопку **Добавить сопоставление столбцов** на панели инструментов, расположенной непосредственно над списком.  
  
    > [!TIP]  
    >  Для очистки не используется **идентификатор поставщика** (столбец или домен). Домен с **идентификатором поставщика** будет использоваться позже в действии сопоставления.  
  
    |Столбец Excel|Домен DQS|  
    |------------------|----------------|  
    |Имя поставщика|Имя поставщика|  
    |ContactEmailAddress|Контактный адрес электронной почты|  
    |Строка адреса|Строка адреса|  
    |Город|Город|  
    |Состояние|Состояние|  
    |Страна (нажмите кнопку **+ (добавить сопоставление столбцов)** , чтобы добавить строку)|Страна или регион|  
    |Почтовый индекс|Почтовый индекс|  
  
     ![Сопоставление столбцов Excel с доменами](../../2014/tutorials/media/et-mappingexcelcolumnstodqsdomains-01.jpg "Сопоставление столбцов Excel с доменами")  
  
5.  После сопоставления всех отдельных доменов в составном домене **Проверка адреса** составной домен автоматически участвует в процессе очистки. Нажмите кнопку **Просмотр/выбор составных доменов** , чтобы увидеть, что автоматически выбран составной домен **Проверка адреса** , а затем нажмите кнопку **ОК**.  
  
     ![Диалоговое окно «Просмотр или выбор составных доменов»](../../2014/tutorials/media/et-mappingexcelcolumnstodqsdomains-02.jpg "Диалоговое окно «Просмотр или выбор составных доменов»")  
  
6.  Нажмите кнопку **Далее** , чтобы перейти на страницу **Очистка** .  
  
## <a name="next-step"></a>Следующий шаг  
 [Задача 3. Очистка данных в базе знаний о поставщиках](../../2014/tutorials/task-3-cleansing-data-against-the-suppliers-knowledge-base.md)  
  
  