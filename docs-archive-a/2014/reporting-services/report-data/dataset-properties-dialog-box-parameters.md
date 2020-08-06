---
title: Диалоговое окно "Свойства набора данных" — "Параметры" (построитель отчетов) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10150"
- sql12.rtp.rptdesigner.datasetproperties.parameters.f1
ms.assetid: 43b00aab-e2c3-4e85-abe1-a2b5a21efeed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0073971de373321ce347f416657671e1f497dd1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751788"
---
# <a name="dataset-properties-dialog-box-parameters"></a><span data-ttu-id="202f3-102">Диалоговое окно «Свойства набора данных» — «Настройки»</span><span class="sxs-lookup"><span data-stu-id="202f3-102">Dataset Properties Dialog Box, Parameters</span></span>
  <span data-ttu-id="202f3-103">Для добавления, изменения и удаления параметров запроса, включая те, которые связаны с параметрами отчета, используется вкладка **Параметры** диалогового окна **Свойства набора данных** .</span><span class="sxs-lookup"><span data-stu-id="202f3-103">Select **Parameters** on the **Dataset Properties** dialog box to add, change, and delete query parameters, including query parameters that link to report parameters.</span></span>  
  
 <span data-ttu-id="202f3-104">Каждый раз при изменении запроса на вкладке запросов выполняется синтаксический анализ команды запроса.</span><span class="sxs-lookup"><span data-stu-id="202f3-104">Whenever the query is changed on the query tab, the query command is parsed.</span></span> <span data-ttu-id="202f3-105">Для каждого параметра запроса, определенного здесь, создается параметр отчета с идентичным именем с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="202f3-105">For each query parameter that is identified, a report parameter with an identical case-sensitive name is created.</span></span> <span data-ttu-id="202f3-106">По умолчанию параметр запроса автоматически добавляется к списку параметров запроса и связывается с соответствующим параметром отчета.</span><span class="sxs-lookup"><span data-stu-id="202f3-106">By default, the query parameter is automatically added to the query parameter list and linked to the corresponding report parameter.</span></span>  
  
 <span data-ttu-id="202f3-107">Если значение по умолчанию одного параметра отчета зависит от значения по умолчанию другого параметра отчета, связанного с параметром запроса, порядок параметров отчета (тот, в котором они перечислены в диалоговом окне **Свойства параметров отчета** ) важен.</span><span class="sxs-lookup"><span data-stu-id="202f3-107">If there are dependencies for the default values of one report parameter on another report parameter that is linked to a query parameter, the order of report parameters (as they appear in the **Report Parameters Properties** dialog box) is important.</span></span> <span data-ttu-id="202f3-108">Параметр, расположенный ближе к концу списка, может зависеть от параметров, расположенных ближе к началу.</span><span class="sxs-lookup"><span data-stu-id="202f3-108">Report parameters later in the list can refer to report parameters earlier in the list.</span></span> <span data-ttu-id="202f3-109">Дополнительные сведения о параметрах отчета см. в разделе [Параметры отчета (построитель отчетов и конструктор отчетов)](../report-design/report-parameters-report-builder-and-report-designer.md).</span><span class="sxs-lookup"><span data-stu-id="202f3-109">For more information about report parameters, see [Report Parameters &#40;Report Builder and Report Designer&#41;](../report-design/report-parameters-report-builder-and-report-designer.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="202f3-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="202f3-110">Options</span></span>  
 <span data-ttu-id="202f3-111">**Добавление**</span><span class="sxs-lookup"><span data-stu-id="202f3-111">**Add**</span></span>  
 <span data-ttu-id="202f3-112">Добавить в список новый параметр.</span><span class="sxs-lookup"><span data-stu-id="202f3-112">Add a new parameter to the list.</span></span>  
  
 <span data-ttu-id="202f3-113">**Удаление**</span><span class="sxs-lookup"><span data-stu-id="202f3-113">**Delete**</span></span>  
 <span data-ttu-id="202f3-114">Удалить выбранный параметр из списка.</span><span class="sxs-lookup"><span data-stu-id="202f3-114">Remove the selected parameter from the list.</span></span>  
  
 <span data-ttu-id="202f3-115">**Имя параметра**</span><span class="sxs-lookup"><span data-stu-id="202f3-115">**Parameter name**</span></span>  
 <span data-ttu-id="202f3-116">Введите имя параметра запроса, добавленного к набору данных на вкладке **Запрос** диалогового окна **Свойства набора данных** .</span><span class="sxs-lookup"><span data-stu-id="202f3-116">Type the name of a query parameter that you added to the dataset on the **Query** tab of the **Dataset Properties** dialog box.</span></span>  
  
 <span data-ttu-id="202f3-117">**Значение параметра**</span><span class="sxs-lookup"><span data-stu-id="202f3-117">**Parameter value**</span></span>  
 <span data-ttu-id="202f3-118">Введите значение параметра запроса.</span><span class="sxs-lookup"><span data-stu-id="202f3-118">Enter a value for the query parameter.</span></span> <span data-ttu-id="202f3-119">Это может быть статическое значение или выражение, которое может ссылаться на объект в отчете, но не на любой элемент или поле отчета.</span><span class="sxs-lookup"><span data-stu-id="202f3-119">This can be a static value or an expression that refers to an object within the report, but it cannot refer to any report items or fields.</span></span> <span data-ttu-id="202f3-120">По умолчанию в поле **Значение** содержится выражение, указывающее параметр отчета.</span><span class="sxs-lookup"><span data-stu-id="202f3-120">By default, **Value** contains an expression that points to a report parameter.</span></span>  
  
 <span data-ttu-id="202f3-121">**Стрелка вверх**</span><span class="sxs-lookup"><span data-stu-id="202f3-121">**Up arrow**</span></span>  
 <span data-ttu-id="202f3-122">Переместить выбранный параметр вверх по списку.</span><span class="sxs-lookup"><span data-stu-id="202f3-122">Move the selected parameter up in the list.</span></span>  
  
 <span data-ttu-id="202f3-123">**Стрелка вниз**</span><span class="sxs-lookup"><span data-stu-id="202f3-123">**Down arrow**</span></span>  
 <span data-ttu-id="202f3-124">Переместить выбранный параметр вниз по списку.</span><span class="sxs-lookup"><span data-stu-id="202f3-124">Move the selected parameter down in the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="202f3-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="202f3-125">See Also</span></span>  
 <span data-ttu-id="202f3-126">[Параметры отчета (построитель отчетов и конструктор отчетов)](../report-design/report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="202f3-126">[Report Parameters &#40;Report Builder and Report Designer&#41;](../report-design/report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="202f3-127">[Добавление данных в построитель отчетов &#40;отчетов и SSRS&#41;](report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="202f3-127">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-datasets-ssrs.md) </span></span>  
 [<span data-ttu-id="202f3-128">Изменение порядка параметров отчета (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="202f3-128">Change the Order of a Report Parameter &#40;Report Builder and SSRS&#41;</span></span>](../report-design/change-the-order-of-a-report-parameter-report-builder-and-ssrs.md)  
  
  
