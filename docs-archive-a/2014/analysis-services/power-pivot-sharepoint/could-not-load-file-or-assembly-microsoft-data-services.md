---
title: Не удалось загрузить файл или сборку &#39;Microsoft. AnalysisServices. SharePoint. Integration&#39; | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 6e350b67-5e18-4b90-8fb7-a0109cbb27b7
author: minewiskan
ms.author: owend
ms.openlocfilehash: b7ba75bdbd8e25f98d11d822c22fa7881352ad88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666804"
---
# <a name="could-not-load-file-or-assembly-39microsoftanalysisservicessharepointintegration39"></a><span data-ttu-id="a36d7-102">Не удалось загрузить файл или сборку &#39;Microsoft. AnalysisServices. SharePoint. Integration&#39;</span><span class="sxs-lookup"><span data-stu-id="a36d7-102">Could not load file or assembly &#39;Microsoft.AnalysisServices.SharePoint.Integration&#39;</span></span>
  <span data-ttu-id="a36d7-103">В среде SharePoint 2010, в которой установлен PowerPivot для SharePoint, эта ошибка возникает, если решение на уровне приложений для PowerPivot развернуто неправильно.</span><span class="sxs-lookup"><span data-stu-id="a36d7-103">In SharePoint 2010 environments that have PowerPivot for SharePoint, this error will occur if the application-level solution for PowerPivot did not deploy correctly.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a36d7-104">Сведения</span><span class="sxs-lookup"><span data-stu-id="a36d7-104">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a36d7-105">Применяется к</span><span class="sxs-lookup"><span data-stu-id="a36d7-105">Applies to</span></span>|<span data-ttu-id="a36d7-106">PowerPivot для SharePoint</span><span class="sxs-lookup"><span data-stu-id="a36d7-106">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="a36d7-107">Версия продукта</span><span class="sxs-lookup"><span data-stu-id="a36d7-107">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="a36d7-108">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a36d7-108">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="a36d7-109">Причина</span><span class="sxs-lookup"><span data-stu-id="a36d7-109">Cause</span></span>|<span data-ttu-id="a36d7-110">Решение Powerpivotwebapp не развернуто или развернуто неправильно.</span><span class="sxs-lookup"><span data-stu-id="a36d7-110">Powerpivotwebapp solution is not deployed or did not deploy correctly.</span></span>|  
|<span data-ttu-id="a36d7-111">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="a36d7-111">Message Text</span></span>|<span data-ttu-id="a36d7-112">Не удалось загрузить файл или сборку Microsoft.AnalysisServices.SharePoint.Integration</span><span class="sxs-lookup"><span data-stu-id="a36d7-112">Could not load file or assembly 'Microsoft.AnalysisServices.SharePoint.Integration'</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a36d7-113">Объяснение</span><span class="sxs-lookup"><span data-stu-id="a36d7-113">Explanation</span></span>  
 <span data-ttu-id="a36d7-114">PowerPivot для SharePoint использует пакеты решений для развертывания своих компонентов на сервере SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a36d7-114">PowerPivot for SharePoint uses solution packages to deploy its features on a SharePoint server.</span></span> <span data-ttu-id="a36d7-115">Одно из решений развернуто неправильно.</span><span class="sxs-lookup"><span data-stu-id="a36d7-115">One of the solutions is not deployed correctly.</span></span> <span data-ttu-id="a36d7-116">Поэтому при попытке открыть галерею PowerPivot или другие страницы приложения PowerPivot на сайте SharePoint возникает эта ошибка.</span><span class="sxs-lookup"><span data-stu-id="a36d7-116">As a result, this error appears whenever you try to open PowerPivot Gallery or other PowerPivot application pages on a SharePoint site.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a36d7-117">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="a36d7-117">User Action</span></span>  
 <span data-ttu-id="a36d7-118">Выполните развертывание пакета решения.</span><span class="sxs-lookup"><span data-stu-id="a36d7-118">Deploy the solution package.</span></span>  
  
1.  <span data-ttu-id="a36d7-119">В разделе «Системные параметры» центра администрирования выберите **Управление решениями фермы**.</span><span class="sxs-lookup"><span data-stu-id="a36d7-119">In Central Administration, in System Settings, click **Manage farm solutions**.</span></span>  
  
2.  <span data-ttu-id="a36d7-120">Щелкните **Powerpivotwebapp**.</span><span class="sxs-lookup"><span data-stu-id="a36d7-120">Click **Powerpivotwebapp**.</span></span>  
  
3.  <span data-ttu-id="a36d7-121">Нажмите **Развернуть решение**.</span><span class="sxs-lookup"><span data-stu-id="a36d7-121">Click **Deploy Solution**.</span></span>  
  
4.  <span data-ttu-id="a36d7-122">Выберите веб-приложение, для которого возникает эта ошибка.</span><span class="sxs-lookup"><span data-stu-id="a36d7-122">Choose the web application for which this error is occurring.</span></span> <span data-ttu-id="a36d7-123">Если имеются несколько веб-приложений, выполните повторное развертывание для них всех.</span><span class="sxs-lookup"><span data-stu-id="a36d7-123">If there is more than one web application, redeploy the solution for all of hem.</span></span>  
  
5.  <span data-ttu-id="a36d7-124">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a36d7-124">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a36d7-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="a36d7-125">See Also</span></span>  
 [<span data-ttu-id="a36d7-126">Развертывание решений PowerPivot в SharePoint</span><span class="sxs-lookup"><span data-stu-id="a36d7-126">Deploy PowerPivot Solutions to SharePoint</span></span>](deploy-power-pivot-solutions-to-sharepoint.md)  
  
  
