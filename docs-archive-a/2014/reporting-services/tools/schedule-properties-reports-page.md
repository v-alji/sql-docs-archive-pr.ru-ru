---
title: Свойства расписания (страница "Отчеты") | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.scheduleproperties.reports.f1
ms.assetid: 7db728bd-4b08-43ef-a49a-e8dcdd37cf89
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: da0b5255e73522572fa22da8668329a28f108104
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658076"
---
# <a name="schedule-properties-reports-page"></a><span data-ttu-id="1336e-102">Свойства расписания (страница отчетов)</span><span class="sxs-lookup"><span data-stu-id="1336e-102">Schedule Properties (Reports Page)</span></span>
  <span data-ttu-id="1336e-103">Эта страница используется для просмотра списка всех отчетов, использующих общее расписание.</span><span class="sxs-lookup"><span data-stu-id="1336e-103">Use this page to view a list of all reports that use this shared schedule.</span></span> <span data-ttu-id="1336e-104">Расписания могут использоваться для обновления моментальных снимков отчетов, формирования журнала отчета, запуска подписки или истечения срока действия кэшированной копии отчета.</span><span class="sxs-lookup"><span data-stu-id="1336e-104">Schedules can be used to refresh report snapshots, generate report history, trigger a subscription, or expire a cached copy of the report.</span></span> <span data-ttu-id="1336e-105">Сведения об использовании расписания можно найти в свойствах и сведениях о подписке на отчет.</span><span class="sxs-lookup"><span data-stu-id="1336e-105">To find out how the schedule is used, view the property and subscription information of the report.</span></span>  
  
 <span data-ttu-id="1336e-106">Несмотря на то, что на данной странице отображаются все отчеты, в которых используется общее расписание, здесь не указывается, сколько раз общее расписание используется в рамках отдельного отчета.</span><span class="sxs-lookup"><span data-stu-id="1336e-106">Although this page shows each report that uses the shared schedule, it does not indicate how many times the shared schedule is used within that single report.</span></span> <span data-ttu-id="1336e-107">Например, предположим, что есть 20 различных подписчиков отчета «Продажи компании» (Company Sales), использующих для запуска обработки подписки одно и то же общее расписание.</span><span class="sxs-lookup"><span data-stu-id="1336e-107">For example, suppose 20 different subscribers to the Company Sales report all use the same shared schedule to trigger subscription processing.</span></span> <span data-ttu-id="1336e-108">В этом случае в упомянутом списке отчет «Продажи компании» (Company Sales) будет указан лишь один раз, несмотря на то, что в отчете имеется 20 ссылок на общее расписание.</span><span class="sxs-lookup"><span data-stu-id="1336e-108">In this case, the Company Sales report will only appear once in this list, even though the report has 20 references to the shared schedule.</span></span>  
  
 <span data-ttu-id="1336e-109">Чтобы открыть эту страницу, запустите среду [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], подключитесь к серверу отчетов, откройте папку **Общие расписания** , щелкните одно из общих расписаний правой кнопкой мыши, выберите пункт **Свойства**, после чего нажмите кнопку **Отчеты**.</span><span class="sxs-lookup"><span data-stu-id="1336e-109">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server, open the **Shared Schedules** folder, right-click a shared schedule, select **Properties**, and then click **Reports**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1336e-110">Эта функция поддерживается не во всех выпусках [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1336e-110">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1336e-111">Список функций, поддерживаемых различными выпусками [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , см. [в разделе функции, поддерживаемые различными выпусками SQL Server 2012](https://go.microsoft.com/fwlink/?linkid=232473) ( https://go.microsoft.com/fwlink/?linkid=232473) .</span><span class="sxs-lookup"><span data-stu-id="1336e-111">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2012](https://go.microsoft.com/fwlink/?linkid=232473) (https://go.microsoft.com/fwlink/?linkid=232473).</span></span>  
  
## <a name="options"></a><span data-ttu-id="1336e-112">Параметры</span><span class="sxs-lookup"><span data-stu-id="1336e-112">Options</span></span>  
 <span data-ttu-id="1336e-113">**Папка**</span><span class="sxs-lookup"><span data-stu-id="1336e-113">**Folder**</span></span>  
 <span data-ttu-id="1336e-114">Позволяет задать путь к отчету.</span><span class="sxs-lookup"><span data-stu-id="1336e-114">Specifies the path of the report.</span></span>  
  
 <span data-ttu-id="1336e-115">**Отчет**</span><span class="sxs-lookup"><span data-stu-id="1336e-115">**Report**</span></span>  
 <span data-ttu-id="1336e-116">Позволяет задать имя отчета, использующего расписание.</span><span class="sxs-lookup"><span data-stu-id="1336e-116">Specifies the name of the report that uses the schedule.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1336e-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="1336e-117">See Also</span></span>  
 <span data-ttu-id="1336e-118">[Создание, изменение и удаление расписаний](../subscriptions/create-modify-and-delete-schedules.md) </span><span class="sxs-lookup"><span data-stu-id="1336e-118">[Create, Modify, and Delete Schedules](../subscriptions/create-modify-and-delete-schedules.md) </span></span>  
 <span data-ttu-id="1336e-119">[Расписания](../subscriptions/schedules.md) </span><span class="sxs-lookup"><span data-stu-id="1336e-119">[Schedules](../subscriptions/schedules.md) </span></span>  
 <span data-ttu-id="1336e-120">[Сервер отчетов в справке Management Studio F1](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="1336e-120">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 <span data-ttu-id="1336e-121">[Соединение с сервером отчетов в Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="1336e-121">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 [<span data-ttu-id="1336e-122">Настройка общих свойств для диспетчер отчетов &#40;отчетов&#41;</span><span class="sxs-lookup"><span data-stu-id="1336e-122">Configure General Properties for a Report &#40;Report Manager&#41;</span></span>](../configure-general-properties-for-a-report-report-manager.md)  
  
  
