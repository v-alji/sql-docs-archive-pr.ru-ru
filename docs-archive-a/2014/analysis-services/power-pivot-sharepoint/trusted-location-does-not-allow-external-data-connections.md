---
title: 'Надежное расположение, в котором находится книга, не разрешает подключения к внешним данным. Не удалось обновить следующие соединения: данные PowerPivot | Документация Майкрософт'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: dc0cedfd-a7d0-40ef-bdd6-ea508130640a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9b7f6d335eac0bec0f67012cc413f3917c50348b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654520"
---
# <a name="the-trusted-location-where-the-workbook-is-stored-does-not-allow-external-data-connections-the-following-connections-failed-to-refresh-powerpivot-data"></a><span data-ttu-id="2027f-103">Надежное расположение, в котором находится книга, не разрешает подключения к внешним данным.</span><span class="sxs-lookup"><span data-stu-id="2027f-103">The trusted location where the workbook is stored does not allow external data connections.</span></span> <span data-ttu-id="2027f-104">Следующие соединения не удалось обновить: данные PowerPivot</span><span class="sxs-lookup"><span data-stu-id="2027f-104">The following connections failed to refresh: PowerPivot Data</span></span>
  <span data-ttu-id="2027f-105">Служба Excel Services возвращает эту ошибку для книг Excel, содержащих данные PowerPivot, если она не может подключиться к внедренным источникам данных.</span><span class="sxs-lookup"><span data-stu-id="2027f-105">For Excel workbooks that contain PowerPivot data, Excel Services returns this error if it cannot connect to embedded data sources.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2027f-106">Сведения</span><span class="sxs-lookup"><span data-stu-id="2027f-106">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2027f-107">Применяется к</span><span class="sxs-lookup"><span data-stu-id="2027f-107">Applies to</span></span>|<span data-ttu-id="2027f-108">PowerPivot для SharePoint</span><span class="sxs-lookup"><span data-stu-id="2027f-108">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="2027f-109">Версия продукта</span><span class="sxs-lookup"><span data-stu-id="2027f-109">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="2027f-110">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2027f-110">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="2027f-111">Причина</span><span class="sxs-lookup"><span data-stu-id="2027f-111">Cause</span></span>|<span data-ttu-id="2027f-112">Служба Excel Services настроена так, чтобы отказывать в доступе к внешним данным.</span><span class="sxs-lookup"><span data-stu-id="2027f-112">Excel Services is configured to deny external data access.</span></span>|  
|<span data-ttu-id="2027f-113">Текст сообщения</span><span class="sxs-lookup"><span data-stu-id="2027f-113">Message Text</span></span>|<span data-ttu-id="2027f-114">Надежное расположение, в котором находится книга, не разрешает подключения к внешним данным.</span><span class="sxs-lookup"><span data-stu-id="2027f-114">The trusted location where the workbook is stored does not allow external data connections.</span></span> <span data-ttu-id="2027f-115">Следующие соединения не удалось обновить: данные PowerPivot</span><span class="sxs-lookup"><span data-stu-id="2027f-115">The following connections failed to refresh: PowerPivot Data</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2027f-116">Объяснение</span><span class="sxs-lookup"><span data-stu-id="2027f-116">Explanation</span></span>  
 <span data-ttu-id="2027f-117">Книги PowerPivot содержат подключения к внедренным данным.</span><span class="sxs-lookup"><span data-stu-id="2027f-117">PowerPivot workbooks contain embedded data connections.</span></span> <span data-ttu-id="2027f-118">Для поддержки взаимодействия книги через срезы и фильтры в настройках службы Excel Services должен быть разрешен доступ к внешним данным с помощью данных внедренных соединений.</span><span class="sxs-lookup"><span data-stu-id="2027f-118">To support workbook interaction through slicers and filters, Excel Services must be configured to allow external data access through embedded connection information.</span></span> <span data-ttu-id="2027f-119">Доступ к внешним данным требуется для получения данных PowerPivot, которые находятся на серверах PowerPivot в ферме.</span><span class="sxs-lookup"><span data-stu-id="2027f-119">External data access is required for retrieving PowerPivot data that is loaded on PowerPivot servers in the farm.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2027f-120">Действие пользователя</span><span class="sxs-lookup"><span data-stu-id="2027f-120">User Action</span></span>  
 <span data-ttu-id="2027f-121">Измените параметры конфигурации, чтобы разрешить внедренные источники данных.</span><span class="sxs-lookup"><span data-stu-id="2027f-121">Change the configuration settings to allow embedded data sources.</span></span>  
  
1.  <span data-ttu-id="2027f-122">В разделе «Управление приложениями» центра администрирования выберите пункт **Управление приложениями служб**.</span><span class="sxs-lookup"><span data-stu-id="2027f-122">In Central Administration, in Application Management, click **Manage service applications**.</span></span>  
  
2.  <span data-ttu-id="2027f-123">Щелкните **Приложение служб Excel**.</span><span class="sxs-lookup"><span data-stu-id="2027f-123">Click **Excel Services Application**.</span></span>  
  
3.  <span data-ttu-id="2027f-124">Щелкните **Надежные расположения файлов**.</span><span class="sxs-lookup"><span data-stu-id="2027f-124">Click **Trusted File Location**.</span></span>  
  
4.  <span data-ttu-id="2027f-125">Щелкните **http://** или расположение, которое требуется настроить.</span><span class="sxs-lookup"><span data-stu-id="2027f-125">Click **http://** or the location you want to configure.</span></span>  
  
5.  <span data-ttu-id="2027f-126">На странице «Внешние данные» для параметра «Разрешить внешние данные» установите значение **Надежные библиотеки подключений к данным и внедренные**.</span><span class="sxs-lookup"><span data-stu-id="2027f-126">In External Data, in Allow External Data, click **Trusted data connection libraries and embedded**.</span></span>  
  
6.  <span data-ttu-id="2027f-127">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2027f-127">Click **OK**.</span></span>  
  
 <span data-ttu-id="2027f-128">Или можно создать новое надежное местоположение для сайтов, содержащих книги PowerPivot, а затем изменить параметры конфигурации только для этого сайта.</span><span class="sxs-lookup"><span data-stu-id="2027f-128">Alternatively, you can create a new trusted location for sites that contain PowerPivot workbooks, and then modify the configuration settings for just that site.</span></span> <span data-ttu-id="2027f-129">Дополнительные сведения см. в разделе [Create a trusted location for PowerPivot sites in Central Administration](create-a-trusted-location-for-power-pivot-sites-in-central-administration.md).</span><span class="sxs-lookup"><span data-stu-id="2027f-129">For more information, see [Create a trusted location for PowerPivot sites in Central Administration](create-a-trusted-location-for-power-pivot-sites-in-central-administration.md).</span></span>  
  
  
