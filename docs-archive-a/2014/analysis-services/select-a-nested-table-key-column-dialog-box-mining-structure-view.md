---
title: Диалоговое окно "Выбор ключевого столбца вложенной таблицы" (представление структуры интеллектуального анализа данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.structure.addnestedtable.f1
helpviewer_keywords:
- Select a Nested Table Key Column dialog box
ms.assetid: f68b89a7-17df-45f8-ba7f-b458cd9b1ec3
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4dc524f6913b7be15e87869355515397a3e0b65c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666786"
---
# <a name="select-a-nested-table-key-column-dialog-box-mining-structure-view"></a><span data-ttu-id="377c4-102">Диалоговое окно «Выбор ключевого столбца вложенной таблицы» (представление структуры интеллектуального анализа данных)</span><span class="sxs-lookup"><span data-stu-id="377c4-102">Select a Nested Table Key Column Dialog Box (Mining Structure View)</span></span>
  <span data-ttu-id="377c4-103">С помощью диалогового окна **Выбор ключевого столбца вложенной таблицы** можно назначить столбец, который будет ключевым для новой вложенной таблицы.</span><span class="sxs-lookup"><span data-stu-id="377c4-103">Use the **Select a Nested Table Key Column** dialog box to designate a column that will act as the key for the new nested table.</span></span> <span data-ttu-id="377c4-104">При выходе из диалогового окна в структуру интеллектуального анализа данных, содержащую назначенный ключевой столбец, добавляется новая таблица.</span><span class="sxs-lookup"><span data-stu-id="377c4-104">When you exit the dialog box, a new table is added to the mining structure that contains the designated key column.</span></span> <span data-ttu-id="377c4-105">Во вложенную таблицу можно добавить дополнительные столбцы, щелкнув структуру правой кнопкой мыши и выбрав команду **Добавить столбец**.</span><span class="sxs-lookup"><span data-stu-id="377c4-105">You can add additional columns to the nested table by right-clicking the structure and selecting **Add a Column**.</span></span> <span data-ttu-id="377c4-106">Диалоговое окно предлагает несколько параметров в зависимости от того, работаете ли вы с моделью интеллектуального анализа данных OLAP или реляционной моделью интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="377c4-106">The dialog box contains different options depending on whether you are working with an OLAP mining model or a relational mining model.</span></span>  
  
## <a name="options"></a><span data-ttu-id="377c4-107">Варианты</span><span class="sxs-lookup"><span data-stu-id="377c4-107">Options</span></span>  
 <span data-ttu-id="377c4-108">**Исходная таблица**</span><span class="sxs-lookup"><span data-stu-id="377c4-108">**Source table**</span></span>  
 <span data-ttu-id="377c4-109">Таблица, на которой основана модель интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="377c4-109">The table on which the mining model is based.</span></span>  
  
 <span data-ttu-id="377c4-110">Это используется только для реляционных моделей интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="377c4-110">This is only used for relational mining models.</span></span>  
  
 <span data-ttu-id="377c4-111">**Исходный столбец**</span><span class="sxs-lookup"><span data-stu-id="377c4-111">**Source column**</span></span>  
 <span data-ttu-id="377c4-112">Список столбцов, доступных в исходной таблице, которые можно использовать в качестве ключевых для вложенной таблицы.</span><span class="sxs-lookup"><span data-stu-id="377c4-112">A list of all the available columns in the source table that you can use as the key of the nested table.</span></span>  
  
 <span data-ttu-id="377c4-113">Это используется только для реляционных моделей интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="377c4-113">This is only used for relational mining models.</span></span>  
  
 <span data-ttu-id="377c4-114">**Показать тип столбцов**</span><span class="sxs-lookup"><span data-stu-id="377c4-114">**Show column types**</span></span>  
 <span data-ttu-id="377c4-115">Список типов данных доступных столбцов.</span><span class="sxs-lookup"><span data-stu-id="377c4-115">A list of available column data types.</span></span> <span data-ttu-id="377c4-116">Выбрать или очистить типы данных для фильтрации столбцов в списке **Исходный столбец**.</span><span class="sxs-lookup"><span data-stu-id="377c4-116">Select or clear data types to filter the list of columns in **Source column**.</span></span> <span data-ttu-id="377c4-117">В списке **Исходный столбец** будут показаны только столбцы, удовлетворяющие отмеченным типам данных.</span><span class="sxs-lookup"><span data-stu-id="377c4-117">Only columns that match the checked data types will be shown in the **Source column** list.</span></span>  
  
 <span data-ttu-id="377c4-118">Это используется только для реляционных моделей интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="377c4-118">This is only used for relational mining models.</span></span>  
  
 <span data-ttu-id="377c4-119">**Атрибуты**</span><span class="sxs-lookup"><span data-stu-id="377c4-119">**Attributes**</span></span>  
 <span data-ttu-id="377c4-120">Список атрибутов, которые можно использовать в качестве ключевых для вложенной таблицы.</span><span class="sxs-lookup"><span data-stu-id="377c4-120">A list of attributes that you can use as the key of the nested table.</span></span>  
  
 <span data-ttu-id="377c4-121">Это используется только для моделей интеллектуального анализа данных OLAP.</span><span class="sxs-lookup"><span data-stu-id="377c4-121">This is only used for OLAP mining models.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="377c4-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="377c4-122">See Also</span></span>  
 [<span data-ttu-id="377c4-123">Представление структуры интеллектуального анализа &#40;конструктора моделей интеллектуального анализа данных&#41;</span><span class="sxs-lookup"><span data-stu-id="377c4-123">Mining Structure View &#40;Data Mining Model Designer&#41;</span></span>](mining-structure-view-data-mining-model-designer.md)  
  
  
