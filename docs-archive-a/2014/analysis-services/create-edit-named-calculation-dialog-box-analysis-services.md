---
title: Диалоговое окно «Создание именованного вычисления» (Analysis Services) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dsveditor.createnamedcalculation.f1
helpviewer_keywords:
- Named Calculation dialog box
ms.assetid: 66fb30ae-f5c5-4bfc-80ca-8c8a3a9bb30d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0b6777feb47a1ce6b601d0190e413b4baae35f1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654619"
---
# <a name="create-edit-named-calculation-dialog-box-analysis-services"></a><span data-ttu-id="e6516-102">Диалоговое окно «Создание именованного вычисления» (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="e6516-102">Create-Edit Named Calculation Dialog Box (Analysis Services)</span></span>
  <span data-ttu-id="e6516-103">Используйте диалоговое окно **Создание именованного вычисления/Изменение именованного вычисления** в среде [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] для определения или редактирования именованного вычисления для таблицы в представлении источника данных.</span><span class="sxs-lookup"><span data-stu-id="e6516-103">Use the **Create/Edit Named Calculation** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to define or modify a named calculation for a table in a data source view.</span></span> <span data-ttu-id="e6516-104">Диалоговое окно **Создание именованного вычисления/Изменение именованного вычисления** можно открыть следующими способами:</span><span class="sxs-lookup"><span data-stu-id="e6516-104">You can display the **Create/Edit Named Calculation** dialog box by:</span></span>  
  
-   <span data-ttu-id="e6516-105">нажмите кнопку **Создать именованное вычисление** на панели **Панель инструментов\*\*\*\*конструктора представлений источников данных**;</span><span class="sxs-lookup"><span data-stu-id="e6516-105">Clicking **New Named Calculation** in the **Toolbar** pane of **Data Source View Designer**.</span></span>  
  
-   <span data-ttu-id="e6516-106">щелкните правой кнопкой мыши таблицу на панели **Таблицы** или **Диаграмма\*\*\*\*конструктора представлений источников данных** и выберите команду **Создать именованное вычисление**;</span><span class="sxs-lookup"><span data-stu-id="e6516-106">Right-clicking a table in either the **Tables** or **Diagram** pane of **Data Source View Designer** and selecting **New Named Calculation**.</span></span>  
  
-   <span data-ttu-id="e6516-107">щелкните правой кнопкой мыши именованное вычисление на панели **Диаграмма\*\*\*\*конструктора представлений источников данных** и выберите команду **Изменить именованное вычисление**.</span><span class="sxs-lookup"><span data-stu-id="e6516-107">Right-clicking the name of a named calculation in the **Diagram** pane of **Data Source View Designer** and selecting **Edit Named Calculation**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e6516-108">Варианты</span><span class="sxs-lookup"><span data-stu-id="e6516-108">Options</span></span>  
 <span data-ttu-id="e6516-109">**Имя столбца**</span><span class="sxs-lookup"><span data-stu-id="e6516-109">**Column Name**</span></span>  
 <span data-ttu-id="e6516-110">Введите имя именованного вычисления.</span><span class="sxs-lookup"><span data-stu-id="e6516-110">Type the name of the named calculation.</span></span>  
  
 <span data-ttu-id="e6516-111">**Описание**</span><span class="sxs-lookup"><span data-stu-id="e6516-111">**Description**</span></span>  
 <span data-ttu-id="e6516-112">Введите необязательное описание именованного вычисления.</span><span class="sxs-lookup"><span data-stu-id="e6516-112">Type the optional description of the named calculation.</span></span>  
  
 <span data-ttu-id="e6516-113">**Выражение**</span><span class="sxs-lookup"><span data-stu-id="e6516-113">**Expression**</span></span>  
 <span data-ttu-id="e6516-114">Введите допустимое выражение SQL, возвращающее скалярное значение.</span><span class="sxs-lookup"><span data-stu-id="e6516-114">Type a valid SQL expression that returns a scalar value.</span></span> <span data-ttu-id="e6516-115">The expression is sent to the provider, and validated in the following expression:</span><span class="sxs-lookup"><span data-stu-id="e6516-115">The expression is sent to the provider, and validated in the following expression:</span></span>  
  
```  
SELECT <Table Name in Data Source>.* , <Expression> AS <Column Name> FROM <Table Name in Data Source>AS <Table Name in Data Source View>  
```  
  
 <span data-ttu-id="e6516-116">The expression can contain references to other tables, by means of a sub-select statement.</span><span class="sxs-lookup"><span data-stu-id="e6516-116">The expression can contain references to other tables, by means of a sub-select statement.</span></span> <span data-ttu-id="e6516-117">If the expression would require parentheses in a SELECT statement, the expression entered must be enclosed between parentheses.</span><span class="sxs-lookup"><span data-stu-id="e6516-117">If the expression would require parentheses in a SELECT statement, the expression entered must be enclosed between parentheses.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6516-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="e6516-118">See Also</span></span>  
 <span data-ttu-id="e6516-119">[Analysis Services конструкторов и диалоговых окон &#40;многомерных данных&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="e6516-119">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="e6516-120">Конструктор представлений источников данных (службы Analysis Services — многомерные данные)</span><span class="sxs-lookup"><span data-stu-id="e6516-120">Data Source View Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](data-source-view-designer-analysis-services-multidimensional-data.md)  
  
  
