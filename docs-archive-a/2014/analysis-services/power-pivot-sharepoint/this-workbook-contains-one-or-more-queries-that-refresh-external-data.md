---
title: Эта книга содержит один или несколько запросов на обновление внешних данных. | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: aa65c992-eb41-4032-9e11-a9ba871b6a3c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 25b2095e13d6151c68eb4a3507400dfdb1739564
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659024"
---
# <a name="this-workbook-contains-one-or-more-queries-that-refresh-external-data"></a><span data-ttu-id="ae14d-103">Эта книга содержит один или несколько запросов на обновление внешних данных.</span><span class="sxs-lookup"><span data-stu-id="ae14d-103">This workbook contains one or more queries that refresh external data.</span></span>
  <span data-ttu-id="ae14d-104">Для книг Excel, содержащих данные PowerPivot, службы Excel отображают это предупреждение при обнаружении сведений о соединении и предлагают пользователю включить или отключить запросы для этой книги.</span><span class="sxs-lookup"><span data-stu-id="ae14d-104">For Excel workbooks that contain PowerPivot data, Excel Services shows this warning when it detects connection information and prompts you to enable or disable queries for this workbook.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ae14d-105">Сведения</span><span class="sxs-lookup"><span data-stu-id="ae14d-105">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ae14d-106">Название продукта</span><span class="sxs-lookup"><span data-stu-id="ae14d-106">Product Name</span></span>|<span data-ttu-id="ae14d-107">PowerPivot для SharePoint</span><span class="sxs-lookup"><span data-stu-id="ae14d-107">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="ae14d-108">Версия продукта</span><span class="sxs-lookup"><span data-stu-id="ae14d-108">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="ae14d-109">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae14d-109">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="ae14d-110">Причина</span><span class="sxs-lookup"><span data-stu-id="ae14d-110">Cause</span></span>|<span data-ttu-id="ae14d-111">Службы Excel настроены на предупреждение об обновлении данных.</span><span class="sxs-lookup"><span data-stu-id="ae14d-111">Excel Services is configured to warn on data refresh.</span></span>|  
|<span data-ttu-id="ae14d-112">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="ae14d-112">Message Text</span></span>|<span data-ttu-id="ae14d-113">Эта книга содержит один или несколько запросов на обновление внешних данных.</span><span class="sxs-lookup"><span data-stu-id="ae14d-113">This workbook contains one or more queries that refresh external data.</span></span> <span data-ttu-id="ae14d-114">Злоумышленник может создать запрос для доступа к конфиденциальным сведениям и распространения их среди других пользователей или для выполнения других вредоносных действий.</span><span class="sxs-lookup"><span data-stu-id="ae14d-114">A malicious user can design a query to access confidential information and distribute it to other users or perform other harmful actions.</span></span><br /><br /> <span data-ttu-id="ae14d-115">Если вы доверяете источнику этой книги, нажмите кнопку «Да», чтобы разрешить в этой книге запросы к внешним данным.</span><span class="sxs-lookup"><span data-stu-id="ae14d-115">If you trust the source of this workbook, click Yes to enable queries to external data in this workbook.</span></span> <span data-ttu-id="ae14d-116">Если вы не уверены, нажмите кнопку «Нет», чтобы изменения к рабочей книге не применялись.</span><span class="sxs-lookup"><span data-stu-id="ae14d-116">If you are not sure, click No so that changes are not applied to your workbook.</span></span><br /><br /> <span data-ttu-id="ae14d-117">Разрешить в этой книге запросы к внешним данным?</span><span class="sxs-lookup"><span data-stu-id="ae14d-117">Do you want to enable queries to external data in this workbook?</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ae14d-118">Объяснение</span><span class="sxs-lookup"><span data-stu-id="ae14d-118">Explanation</span></span>  
 <span data-ttu-id="ae14d-119">Книги PowerPivot содержат строки подключения к внедренным данным, используемые Excel для обмена данными с внешним сервером PowerPivot, который загружает и вычисляет данные.</span><span class="sxs-lookup"><span data-stu-id="ae14d-119">PowerPivot workbooks contain embedded data connection strings that are used by Excel to communicate with an external PowerPivot server that loads and calculates the data.</span></span> <span data-ttu-id="ae14d-120">Если включены предупреждения об обновлении данных, службы Excel обнаруживают эту строку соединения и предупреждают пользователя.</span><span class="sxs-lookup"><span data-stu-id="ae14d-120">When warn on data refresh is enabled, Excel Services detects this connection string and warns the user accordingly.</span></span>  
  
 <span data-ttu-id="ae14d-121">Для фильтрации и создания срезов данных PowerPivot в книге должны быть включены запросы.</span><span class="sxs-lookup"><span data-stu-id="ae14d-121">To filter and slice PowerPivot data in the workbook, queries must be enabled.</span></span> <span data-ttu-id="ae14d-122">Убедитесь, что запросы включены только для доверенных книг PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="ae14d-122">Be sure that you enable queries for only those PowerPivot workbooks that you trust.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ae14d-123">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="ae14d-123">User Action</span></span>  
 <span data-ttu-id="ae14d-124">Чтобы включить запросы, нажмите кнопку **Да** .</span><span class="sxs-lookup"><span data-stu-id="ae14d-124">Click **Yes** to enable queries.</span></span>  
  
 <span data-ttu-id="ae14d-125">Также можно изменить параметры конфигурации, чтобы предупреждения об обновлениях больше не выдавались.</span><span class="sxs-lookup"><span data-stu-id="ae14d-125">You can also change the configuration settings so that warn on refresh no longer occurs:</span></span>  
  
1.  <span data-ttu-id="ae14d-126">В разделе «Управление приложениями» центра администрирования выберите пункт **Управление приложениями служб**.</span><span class="sxs-lookup"><span data-stu-id="ae14d-126">In Central Administration, in Application Management, click **Manage service applications**.</span></span>  
  
2.  <span data-ttu-id="ae14d-127">Щелкните **Приложение служб Excel**.</span><span class="sxs-lookup"><span data-stu-id="ae14d-127">Click **Excel Services Application**.</span></span>  
  
3.  <span data-ttu-id="ae14d-128">Щелкните **Надежные расположения файлов**.</span><span class="sxs-lookup"><span data-stu-id="ae14d-128">Click **Trusted File Location**.</span></span>  
  
4.  <span data-ttu-id="ae14d-129">Щелкните **http://** или расположение, которое требуется настроить.</span><span class="sxs-lookup"><span data-stu-id="ae14d-129">Click **http://** or the location you want to configure.</span></span>  
  
5.  <span data-ttu-id="ae14d-130">В области "Внешние данные" снимите флажок **Предупреждать при обновлении данных**.</span><span class="sxs-lookup"><span data-stu-id="ae14d-130">In External Data, clear the checkbox for **Warn on data refresh**.</span></span>  
  
6.  <span data-ttu-id="ae14d-131">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ae14d-131">Click **OK**.</span></span>  
  
 <span data-ttu-id="ae14d-132">Или можно создать новое надежное местоположение для сайтов, содержащих книги PowerPivot, а затем изменить параметры конфигурации только для этого сайта.</span><span class="sxs-lookup"><span data-stu-id="ae14d-132">Alternatively, you can create a new trusted location for sites that contain PowerPivot workbooks, and then modify the configuration settings for just that site.</span></span> <span data-ttu-id="ae14d-133">Дополнительные сведения см. в разделе [Create a trusted location for PowerPivot sites in Central Administration](create-a-trusted-location-for-power-pivot-sites-in-central-administration.md).</span><span class="sxs-lookup"><span data-stu-id="ae14d-133">For more information, see [Create a trusted location for PowerPivot sites in Central Administration](create-a-trusted-location-for-power-pivot-sites-in-central-administration.md).</span></span>  
  
  
