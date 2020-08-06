---
title: Диалоговое окно "Параметры запроса" (визуальные инструменты для баз данных) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdtsql.chm:69645
- vdt.dlgbox.definequeryparameters
ms.assetid: 31cdaee2-d7cd-4d64-a45f-924b27e8b1f0
author: stevestein
ms.author: sstein
ms.openlocfilehash: 76052876ad2899fc959aa7fc49f4299e08bac713
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730002"
---
# <a name="query-parameters-dialog-box-visual-database-tools"></a><span data-ttu-id="55afb-102">Диалоговое окно «Параметры запроса» (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="55afb-102">Query Parameters Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="55afb-103">Данное диалоговое окно позволяет вводить значения для параметров, определенных в запросе.</span><span class="sxs-lookup"><span data-stu-id="55afb-103">This dialog allows you to enter values for the parameters defined in the query.</span></span> <span data-ttu-id="55afb-104">Это диалоговое окно появляется при выполнении запроса, содержащего параметры, которые должны быть введены конечным пользователем во время запуска.</span><span class="sxs-lookup"><span data-stu-id="55afb-104">This dialog box appears when you execute a query that contains parameters that require end-user input at run time.</span></span>  
  
## <a name="options"></a><span data-ttu-id="55afb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="55afb-105">Options</span></span>  
 <span data-ttu-id="55afb-106">**Название**</span><span class="sxs-lookup"><span data-stu-id="55afb-106">**Name**</span></span>  
 <span data-ttu-id="55afb-107">Список параметров, определенных для выполняемого запроса.</span><span class="sxs-lookup"><span data-stu-id="55afb-107">Lists the parameters defined for the query being executed.</span></span> <span data-ttu-id="55afb-108">Если запрос содержит именованные параметры, то имена отобразятся в списке.</span><span class="sxs-lookup"><span data-stu-id="55afb-108">If the query contains named parameters, the names appear in the list.</span></span> <span data-ttu-id="55afb-109">Если запрос содержит неименованные параметры, то для каждого параметра запроса в списке будут приведены имена параметров, определенные системой.</span><span class="sxs-lookup"><span data-stu-id="55afb-109">If the query contains unnamed parameters, system-defined parameter names are listed for each parameter in the query.</span></span>  
  
 <span data-ttu-id="55afb-110">**Value**</span><span class="sxs-lookup"><span data-stu-id="55afb-110">**Value**</span></span>  
 <span data-ttu-id="55afb-111">Введите значение для каждого параметра, приведенного в списке **Имя**.</span><span class="sxs-lookup"><span data-stu-id="55afb-111">Enter the value for each parameter listed under **Name**.</span></span> <span data-ttu-id="55afb-112">Значение, использованное в последний раз, будет отображено в качестве значения параметра по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="55afb-112">The value used most recently appears as the default parameter value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="55afb-113">Пример</span><span class="sxs-lookup"><span data-stu-id="55afb-113">Example</span></span>  
 <span data-ttu-id="55afb-114">Следующий запрос на панели SQL открывает диалоговое окно «Параметры запроса» при выполнении в базе данных [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="55afb-114">The following query in the SQL Pane, opens the Query Parameters dialog box when executed in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
```  
SELECT   FirstName, LastName  
FROM    Person.Person AS Lastname  
WHERE   (LastName = @Param1);  
```  
  
## <a name="see-also"></a><span data-ttu-id="55afb-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="55afb-115">See Also</span></span>  
 [<span data-ttu-id="55afb-116">Запрос с параметрами (визуальные инструменты для баз данных)</span><span class="sxs-lookup"><span data-stu-id="55afb-116">Query with Parameters &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
