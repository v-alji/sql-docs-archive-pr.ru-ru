---
title: Добавить столбцы в структуру интеллектуального анализа данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], columns
- columns [data mining], mining structure columns
- adding columns
ms.assetid: 3f879344-9f66-4178-851a-e8c5ccccf4cb
author: minewiskan
ms.author: owend
ms.openlocfilehash: 093d78b36ab3aae6600b890a8137025c9dc9134e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666280"
---
# <a name="add-columns-to-a-mining-structure"></a><span data-ttu-id="4ba62-102">добавить столбцы к структуре интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="4ba62-102">Add Columns to a Mining Structure</span></span>
  <span data-ttu-id="4ba62-103">Используйте конструктор интеллектуального анализа данных в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] , чтобы добавить столбцы к структуре интеллектуального анализа данных после ее определения в мастере интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="4ba62-103">Use Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] to add columns to a mining structure after you have defined it in the Data Mining Wizard.</span></span> <span data-ttu-id="4ba62-104">Можно добавить любой столбец, существующий в представлении источника данных, который использовался при определении структуры интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="4ba62-104">You can add any column that exists in the data source view that was used to define the mining structure.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4ba62-105">К структуре интеллектуального анализа данных можно добавить несколько копий столбцов. Тем не менее следует избегать использования более чем одного экземпляра столбца в одной и той же модели, поскольку в противном случае могут возникнуть ложные корреляции между исходным и производным столбцами.</span><span class="sxs-lookup"><span data-stu-id="4ba62-105">You can add multiple copies of columns to a mining structure; however, you should avoid using more than one instance of the column within the same model, to avoid false correlations between the source and the derived column.</span></span>  
  
### <a name="to-add-a-column-to-a-mining-structure"></a><span data-ttu-id="4ba62-106">Добавление столбца к структуре интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="4ba62-106">To add a column to a mining structure</span></span>  
  
1.  <span data-ttu-id="4ba62-107">Перейдите на вкладку **Структура интеллектуального анализа данных** в конструкторе интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="4ba62-107">Select the **Mining Structure** tab in Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="4ba62-108">Щелкните правой кнопкой мыши структуру интеллектуального анализа данных и выберите пункт **Добавить столбец**.</span><span class="sxs-lookup"><span data-stu-id="4ba62-108">Right-click the mining structure and select **Add a Column**.</span></span>  
  
     <span data-ttu-id="4ba62-109">Откроется диалоговое окно **Выбор столбца** .</span><span class="sxs-lookup"><span data-stu-id="4ba62-109">The **Select a Column** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="4ba62-110">В разделе **Исходная таблица**выберите таблицу в представлении источника данных, в которой находится столбец.</span><span class="sxs-lookup"><span data-stu-id="4ba62-110">Under **Source table**, select the table in the data source view where the column resides.</span></span>  
  
4.  <span data-ttu-id="4ba62-111">В разделе **Исходный столбец**выберите столбец, который необходимо добавить к структуре интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="4ba62-111">Under **Source column**, select the column that you want to add to the mining structure.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
> [!NOTE]  
>  <span data-ttu-id="4ba62-112">При добавлении уже существующего столбца в структуру будет включена копия, а к имени будет добавлена цифра 1.</span><span class="sxs-lookup"><span data-stu-id="4ba62-112">If you add a column that already exists, a copy will be included in the structure, and the name appended with a "1".</span></span> <span data-ttu-id="4ba62-113">Можно изменить имя скопированного столбца на более наглядное, введя новое имя в качестве значения свойства **Имя** столбца структуры интеллектуального анализа данных.</span><span class="sxs-lookup"><span data-stu-id="4ba62-113">You can change the name of the copied column to something more descriptive by typing a new name in the **Name** property of the mining structure column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ba62-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="4ba62-114">See Also</span></span>  
 [<span data-ttu-id="4ba62-115">Задачи и инструкции по структуре интеллектуального анализа данных</span><span class="sxs-lookup"><span data-stu-id="4ba62-115">Mining Structure Tasks and How-tos</span></span>](mining-structure-tasks-and-how-tos.md)  
  
  
