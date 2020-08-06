---
title: Связь параметра запроса с параметром отчета (построитель отчетов и службы SSRS) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- queries [Reporting Services], parameters
- parameters [Reporting Services], queries
ms.assetid: 6d297e1a-ff71-472a-addc-349e863092b5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f65aa36e8910378d68963c8c9990518b661025ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730214"
---
# <a name="associate-a-query-parameter-with-a-report-parameter-report-builder-and-ssrs"></a><span data-ttu-id="6f6aa-102">Связь параметра запроса с параметром отчета (построитель отчетов и службы SSRS)</span><span class="sxs-lookup"><span data-stu-id="6f6aa-102">Associate a Query Parameter with a Report Parameter (Report Builder and SSRS)</span></span>
  <span data-ttu-id="6f6aa-103">При определении запроса к набору данных, содержащего переменную запроса, команда запроса анализируется.</span><span class="sxs-lookup"><span data-stu-id="6f6aa-103">When you define a dataset query that contains a query variable, the query command is parsed.</span></span> <span data-ttu-id="6f6aa-104">Для каждой переменной запроса создается соответствующий параметр набора данных и параметр отчета.</span><span class="sxs-lookup"><span data-stu-id="6f6aa-104">For each query variable, a corresponding dataset parameter and report parameter are created.</span></span> <span data-ttu-id="6f6aa-105">Параметр набора данных указывает на параметр отчета.</span><span class="sxs-lookup"><span data-stu-id="6f6aa-105">The dataset parameter points to the report parameter.</span></span> <span data-ttu-id="6f6aa-106">Это позволяет пользователю вводить значение, которое передается непосредственно запросу.</span><span class="sxs-lookup"><span data-stu-id="6f6aa-106">This enables a user to enter a value that passes directly to the query.</span></span> <span data-ttu-id="6f6aa-107">Каждый раз при изменении команды запроса происходит тот же процесс.</span><span class="sxs-lookup"><span data-stu-id="6f6aa-107">Each time you edit the query command, the same process takes place.</span></span>  
  
 <span data-ttu-id="6f6aa-108">При переименовании параметра отчета, привязанного к параметру запроса, нужно вручную привязать параметры запроса к переименованному параметру отчета с помощью процедуры, описанной в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="6f6aa-108">If you rename a report parameter that is bound to a query parameter, you need to manually link the query parameters to the renamed report parameter by using the procedure in this topic.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-associate-a-query-parameter-with-a-report-parameter"></a><span data-ttu-id="6f6aa-109">Связывание параметра запроса с параметром отчета</span><span class="sxs-lookup"><span data-stu-id="6f6aa-109">To associate a query parameter with a report parameter</span></span>  
  
1.  <span data-ttu-id="6f6aa-110">В области данных отчета щелкните правой кнопкой мыши набор данных, выберите пункт **Свойства набора данных**и нажмите **Параметры**.</span><span class="sxs-lookup"><span data-stu-id="6f6aa-110">In the Report Data pane, right-click the dataset, click **Dataset Properties**, and then click **Parameters**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6f6aa-111"> Если область данных отчета не отображается, в меню **Вид** выберите пункт **Данные отчета** .</span><span class="sxs-lookup"><span data-stu-id="6f6aa-111">If the Report Data pane is not visible, click **Report Data** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="6f6aa-112">В столбце **Имя параметра**найдите имя параметра запроса.</span><span class="sxs-lookup"><span data-stu-id="6f6aa-112">In the column **Parameter Name**, find the name of the query parameter.</span></span> <span data-ttu-id="6f6aa-113">Имена параметров заполняются автоматически на основе запроса.</span><span class="sxs-lookup"><span data-stu-id="6f6aa-113">Parameter names are automatically populated based on the query.</span></span> <span data-ttu-id="6f6aa-114">Каждый раз при изменении запроса он проверяется на наличие новых параметров запроса.</span><span class="sxs-lookup"><span data-stu-id="6f6aa-114">Every time you change the query, the query is checked for new query parameters.</span></span> <span data-ttu-id="6f6aa-115">Созданные вручную параметры запроса не меняются при изменении запроса.</span><span class="sxs-lookup"><span data-stu-id="6f6aa-115">Query parameters that you create manually are not changed when the query changes.</span></span>  
  
    -   <span data-ttu-id="6f6aa-116">В поле **Имя параметра**введите имя параметра запроса, как оно указано в запросе.</span><span class="sxs-lookup"><span data-stu-id="6f6aa-116">In **Parameter Name**, find the query parameter name as it exists in the query.</span></span> <span data-ttu-id="6f6aa-117">Можно также вручную добавить новый параметр запроса и ввести для него имя.</span><span class="sxs-lookup"><span data-stu-id="6f6aa-117">You can also manually add a new query parameter and enter a name.</span></span>  
  
    -   <span data-ttu-id="6f6aa-118">В поле **Значение параметра**введите или выберите выражение, значение оценки которого передается в параметр запроса.</span><span class="sxs-lookup"><span data-stu-id="6f6aa-118">In **Parameter Value**, type or select an expression that evaluates to the value to pass to the query parameter.</span></span> <span data-ttu-id="6f6aa-119">Обычно это имя параметра отчета.</span><span class="sxs-lookup"><span data-stu-id="6f6aa-119">This is typically the name of the report parameter.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="6f6aa-120">Можно указывать не только те параметры, которые являются значениями параметров для запроса.</span><span class="sxs-lookup"><span data-stu-id="6f6aa-120">You are not limited to report parameters as values for a query parameter.</span></span> <span data-ttu-id="6f6aa-121">Может быть указано любое выражение, значением которого является значение параметра.</span><span class="sxs-lookup"><span data-stu-id="6f6aa-121">You can use any expression that evaluates to a value for the parameter value.</span></span>  
  
3.  <span data-ttu-id="6f6aa-122">Повторите шаг 2 для остальных параметров запроса.</span><span class="sxs-lookup"><span data-stu-id="6f6aa-122">Repeat step 2 for additional query parameters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f6aa-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="6f6aa-123">See Also</span></span>  
 <span data-ttu-id="6f6aa-124">[Внедренные и общие наборы данных отчета &#40;построитель отчетов и службы SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6f6aa-124">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="6f6aa-125">Концепция параметров отчета &#40;построитель отчетов и службы SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="6f6aa-125">Report Parameters Concept &#40;Report Builder and SSRS&#41;</span></span>](../report-design/report-parameters-concepts-report-builder-and-ssrs.md)  
  
  
