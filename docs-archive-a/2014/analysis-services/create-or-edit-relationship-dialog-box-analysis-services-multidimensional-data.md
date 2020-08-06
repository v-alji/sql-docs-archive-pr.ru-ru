---
title: Диалоговое окно «Создание или изменение связи» (Analysis Services-многомерные данные) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dsvdesigner.createrelationship.f1
helpviewer_keywords:
- Create Relationship dialog box
ms.assetid: da3c7074-623e-4ddf-a707-d3276a47cf1c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4edae3f78ac6b764d91e1be97787fe59d49421db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657991"
---
# <a name="create-or-edit-relationship-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="547ba-102">диалоговое окно "Создание/Изменение связи" (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="547ba-102">Create or Edit Relationship Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="547ba-103">Используйте диалоговое окно **Создание связи/изменение связи** в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] для определения или редактирования связи в представлении источника данных.</span><span class="sxs-lookup"><span data-stu-id="547ba-103">Use the **Create/Edit Relationship** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to define or modify a relationship in a data source view.</span></span> <span data-ttu-id="547ba-104">Диалоговое окно **Создание связи/изменение связи** можно вызвать следующими способами:</span><span class="sxs-lookup"><span data-stu-id="547ba-104">You can display the **Create/Edit Relationship** dialog box by:</span></span>  
  
-   <span data-ttu-id="547ba-105">Нажмите кнопку **Создать связь** на панели **Панель инструментов** диалогового окна **Конструктор представлений источников данных**.</span><span class="sxs-lookup"><span data-stu-id="547ba-105">Clicking **New Relationship** in the **Toolbar** pane of **Data Source View Designer**.</span></span>  
  
-   <span data-ttu-id="547ba-106">Щелкните правой кнопкой мыши таблицу на панели **Таблицы** или **Диаграмма\*\*\*\*конструктора представлений источника данных** и выберите пункт **Создать связь**.</span><span class="sxs-lookup"><span data-stu-id="547ba-106">Right-clicking a table in either the **Tables** or **Diagram** pane of **Data Source View Designer** and selecting **New Relationship**.</span></span>  
  
-   <span data-ttu-id="547ba-107">Щелкните правой кнопкой мыши связь на панели **Диаграмма\*\*\*\*конструктора представлений источника данных** и выберите пункт **Изменить связь**.</span><span class="sxs-lookup"><span data-stu-id="547ba-107">Right-clicking a relationship in the **Diagram** pane of **Data Source View Designer** and selecting **Edit Relationship**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="547ba-108"> В **конструкторе представления источников данных** можно создать связи, не существующие в исходном источнике данных, и удалить связи, созданные **конструктором представления источников данных** из существующих связей внешних ключей в исходном источнике данных.</span><span class="sxs-lookup"><span data-stu-id="547ba-108">You can create relationships in **Data Source View Designer** that do not exist in the underlying data source, and remove relationships created by **Data Source View Designer** from existing foreign key relationships in the underlying data source.</span></span>  
  
## <a name="options"></a><span data-ttu-id="547ba-109">Варианты</span><span class="sxs-lookup"><span data-stu-id="547ba-109">Options</span></span>  
 <span data-ttu-id="547ba-110">**Исходная таблица (внешний ключ)**</span><span class="sxs-lookup"><span data-stu-id="547ba-110">**Source (foreign key) table**</span></span>  
 <span data-ttu-id="547ba-111">Выберите таблицу или именованный запрос, содержащий ссылку на один или несколько столбцов в целевой таблице.</span><span class="sxs-lookup"><span data-stu-id="547ba-111">Select the table or named query that contains the reference to one or more columns in the destination table.</span></span>  
  
 <span data-ttu-id="547ba-112">**Целевая таблица (первичный ключ)**</span><span class="sxs-lookup"><span data-stu-id="547ba-112">**Destination (primary key) table**</span></span>  
 <span data-ttu-id="547ba-113">Выберите таблицу, содержащую один или несколько столбцов, на которые имеются ссылки из исходной таблицы.</span><span class="sxs-lookup"><span data-stu-id="547ba-113">Select the table that contains one or more columns referenced by the source table.</span></span> <span data-ttu-id="547ba-114">Для самосоединений укажите таблицу, выбранную в параметре **Исходная таблица (внешний ключ)**.</span><span class="sxs-lookup"><span data-stu-id="547ba-114">For self-joins, select the same table selected in **Source (foreign key) table**.</span></span>  
  
 <span data-ttu-id="547ba-115">**Исходные столбцы**</span><span class="sxs-lookup"><span data-stu-id="547ba-115">**Source columns**</span></span>  
 <span data-ttu-id="547ba-116">Выберите столбцы, которые ссылаются на столбцы в целевой таблице.</span><span class="sxs-lookup"><span data-stu-id="547ba-116">Select the columns that reference columns in the destination table.</span></span>  
  
 <span data-ttu-id="547ba-117">**Целевые столбцы**</span><span class="sxs-lookup"><span data-stu-id="547ba-117">**Destination columns**</span></span>  
 <span data-ttu-id="547ba-118">Выберите столбцы, на которые ссылаются столбцы исходной таблицы.</span><span class="sxs-lookup"><span data-stu-id="547ba-118">Select the columns that are referenced by columns in the source table.</span></span>  
  
 <span data-ttu-id="547ba-119">**Отмена**</span><span class="sxs-lookup"><span data-stu-id="547ba-119">**Reverse**</span></span>  
 <span data-ttu-id="547ba-120">Щелкните для изменения направления связи.</span><span class="sxs-lookup"><span data-stu-id="547ba-120">Click to reverse the direction of the relationship.</span></span>  
  
 <span data-ttu-id="547ba-121">**Описание**</span><span class="sxs-lookup"><span data-stu-id="547ba-121">**Description**</span></span>  
 <span data-ttu-id="547ba-122">Введите необязательное описание связи.</span><span class="sxs-lookup"><span data-stu-id="547ba-122">Type an optional description for the relationship.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="547ba-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="547ba-123">See Also</span></span>  
 <span data-ttu-id="547ba-124">[Analysis Services конструкторов и диалоговых окон &#40;многомерных данных&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="547ba-124">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="547ba-125">Конструктор представлений источников данных (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="547ba-125">Data Source View Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](data-source-view-designer-analysis-services-multidimensional-data.md)  
  
  
