---
title: Создание Power View отчета с многомерным источником данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b9b6f4c9-7e1f-4f61-b657-8986e39a6af2
author: minewiskan
ms.author: owend
ms.openlocfilehash: 179bb9eed94cd0dbb579bdb06d630b213339d12f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737052"
---
# <a name="create-a-power-view-report-with-a-multidimensional-data-source"></a><span data-ttu-id="d3a15-102">Создание отчета Power View с многомерными источниками данных</span><span class="sxs-lookup"><span data-stu-id="d3a15-102">Create a Power View Report with a Multidimensional Data Source</span></span>
  <span data-ttu-id="d3a15-103">Создание отчета Power View на основе многомерной модели не отличается от создания отчета на основе книги PowerPivot или табличной модели служб Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="d3a15-103">Creating a Power View report based on a multidimensional model is no different than creating a report based on a PowerPivot workbook or an Analysis Services Tabular model.</span></span> <span data-ttu-id="d3a15-104">Отчеты Power View создаются из файла соединения с источником данных отчета (RSDS) в библиотеке SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d3a15-104">Power View reports are created from a Report Data Source connection file (.rsds) in a SharePoint library.</span></span> <span data-ttu-id="d3a15-105">Дополнительные сведения о создании RSDS см. в разделе [Create a Report Data Source](create-a-report-data-source.md).</span><span class="sxs-lookup"><span data-stu-id="d3a15-105">For more information about how to create an .rsds, see [Create a Report Data Source](create-a-report-data-source.md).</span></span>  
  
 <span data-ttu-id="d3a15-106">Перед началом работы нужно знать следующее:</span><span class="sxs-lookup"><span data-stu-id="d3a15-106">Before you begin, you need to know:</span></span>  
  
-   <span data-ttu-id="d3a15-107">Имя и расположение библиотеки SharePoint, содержащей общее соединение источника данных отчета (RSDS) с многомерной моделью.</span><span class="sxs-lookup"><span data-stu-id="d3a15-107">The name and location of the SharePoint library that contains a shared report data source connection (.rsds) to a multidimensional model.</span></span>  
  
#### <a name="create-a-new-blank-power-view-report"></a><span data-ttu-id="d3a15-108">Создание нового пустого отчета Power View</span><span class="sxs-lookup"><span data-stu-id="d3a15-108">Create a new, blank Power View report</span></span>  
  
-   <span data-ttu-id="d3a15-109">В библиотеке SharePoint щелкните стрелку рядом с общим соединением с источником данных отчета RSDS (RSDS-файл, который подключается к многомерной модели) и нажмите кнопку **Создать отчет Power View**.</span><span class="sxs-lookup"><span data-stu-id="d3a15-109">In the SharePoint library, click the arrow next to the .rsds shared report data source connection (the .rsds that connects to the multidimensional model), and then click **Create Power View Report**.</span></span>  
  
  
