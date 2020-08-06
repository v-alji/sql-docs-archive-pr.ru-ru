---
title: Не удалось загрузить файл или сборку &#39;Microsoft. Data. Services, Version = 3.5.0.0, культура = Neutral, PublicKeyToken = b77a5c561934e089»&#39; или одну из его зависимостей. Системе не удается найти указанный файл. | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 81ed0f44-8782-462d-af8f-0ba5b975df27
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3f9eed7ad90c1e720d07c714e351c24ae6657717
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666803"
---
# <a name="could-not-load-file-or-assembly-39microsoftdataservices-version3500-cultureneutral-publickeytokenb77a5c561934e08939-or-one-of-its-dependencies-the-system-cannot-find-the-file-specified"></a><span data-ttu-id="a339f-104">Не удалось загрузить файл или сборку &#39;Microsoft. Data. Services, Version = 3.5.0.0, культура = Neutral, PublicKeyToken = b77a5c561934e089»&#39; или одну из его зависимостей.</span><span class="sxs-lookup"><span data-stu-id="a339f-104">Could not load file or assembly &#39;Microsoft.Data.Services, Version=3.5.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089&#39; or one of its dependencies.</span></span> <span data-ttu-id="a339f-105">Системе не удается найти указанный файл.</span><span class="sxs-lookup"><span data-stu-id="a339f-105">The system cannot find the file specified.</span></span>
  <span data-ttu-id="a339f-106">В средах SharePoint 2010 с PowerPivot для SharePoint эта ошибка возникает при попытке выполнить экспорт веб-канала данных, когда в системе отсутствует требуемая версия службы Microsoft ADO.NET Data Services.</span><span class="sxs-lookup"><span data-stu-id="a339f-106">In SharePoint 2010 environments that have PowerPivot for SharePoint, this error will occur if you attempt a data feed export and the system is missing the required version of Microsoft ADO.NET Data Services.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a339f-107">Сведения</span><span class="sxs-lookup"><span data-stu-id="a339f-107">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a339f-108">Применяется к</span><span class="sxs-lookup"><span data-stu-id="a339f-108">Applies to</span></span>|<span data-ttu-id="a339f-109">PowerPivot для SharePoint</span><span class="sxs-lookup"><span data-stu-id="a339f-109">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="a339f-110">Версия продукта</span><span class="sxs-lookup"><span data-stu-id="a339f-110">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="a339f-111">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a339f-111">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="a339f-112">Причина</span><span class="sxs-lookup"><span data-stu-id="a339f-112">Cause</span></span>|<span data-ttu-id="a339f-113">Служба ADO.NET Data Services 3.5 с пакетом обновления 1 (SP1) не найдена.</span><span class="sxs-lookup"><span data-stu-id="a339f-113">ADO.NET Data Services 3.5 SP1 was not found.</span></span>|  
|<span data-ttu-id="a339f-114">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="a339f-114">Message Text</span></span>|<span data-ttu-id="a339f-115">Не удалось загрузить файл или сборку «Microsoft.Data.Services, Version=3.5.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089» или одну из его зависимостей.</span><span class="sxs-lookup"><span data-stu-id="a339f-115">Could not load file or assembly 'Microsoft.Data.Services, Version=3.5.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089' or one of its dependencies.</span></span> <span data-ttu-id="a339f-116">Система не может найти указанный файл.</span><span class="sxs-lookup"><span data-stu-id="a339f-116">The system cannot find the file specified</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a339f-117">Объяснение</span><span class="sxs-lookup"><span data-stu-id="a339f-117">Explanation</span></span>  
 <span data-ttu-id="a339f-118">В SharePoint 2010 есть кнопка «Экспортировать как веб-канал данных», с помощью которой можно экспортировать список SharePoint в виде веб-канала данных XML.</span><span class="sxs-lookup"><span data-stu-id="a339f-118">SharePoint 2010 includes an Export as Data Feed button that you can use to export a SharePoint list as an XML data feed.</span></span> <span data-ttu-id="a339f-119">Кроме того, и службы Reporting Services в режиме SharePoint, и PowerPivot для SharePoint поддерживают функции веб-канала данных, для которых требуются службы ADO.NET Data Services.</span><span class="sxs-lookup"><span data-stu-id="a339f-119">In addition, both Reporting Services in SharePoint mode and PowerPivot for SharePoint support data feed features that require ADO.NET Data Services.</span></span>  
  
 <span data-ttu-id="a339f-120">Если служба ADO.NET Data Services не установлена, то при запросе веб-канала данных возникнет эта ошибка.</span><span class="sxs-lookup"><span data-stu-id="a339f-120">If ADO.NET Data Services is not installed, this error will occur when you request a data feed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a339f-121">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="a339f-121">User Action</span></span>  
  
1.  <span data-ttu-id="a339f-122">Перейдите к документации по требованиям к оборудованию и программному обеспечению для SharePoint 2010, [Определите требования к оборудованию и программному обеспечению (SharePoint 2010)](https://go.microsoft.com/fwlink/?LinkId=169734) ( https://go.microsoft.com/fwlink/?LinkId=169734) .</span><span class="sxs-lookup"><span data-stu-id="a339f-122">Go to the hardware and software requirements documentation for SharePoint 2010, [Determine Hardware and Software Requirements (SharePoint 2010)](https://go.microsoft.com/fwlink/?LinkId=169734) (https://go.microsoft.com/fwlink/?LinkId=169734).</span></span>  
  
2.  <span data-ttu-id="a339f-123">Найдите в разделе **Установить необходимые программы**ссылку на ADO.NET Data Services 3.5, соответствующую используемой операционной системе.</span><span class="sxs-lookup"><span data-stu-id="a339f-123">In **Installing software prerequisites**, find the link for ADO.NET Data Services 3.5 that corresponds to the operating system you are using.</span></span>  
  
3.  <span data-ttu-id="a339f-124">Щелкните ссылку и запустите программу установки службы.</span><span class="sxs-lookup"><span data-stu-id="a339f-124">Click the link and run the setup program that installs the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a339f-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="a339f-125">See Also</span></span>  
 [<span data-ttu-id="a339f-126">Развертывание решений PowerPivot в SharePoint</span><span class="sxs-lookup"><span data-stu-id="a339f-126">Deploy PowerPivot Solutions to SharePoint</span></span>](deploy-power-pivot-solutions-to-sharepoint.md)  
  
  
