---
title: Просмотр результатов действия политики исправности ресурсов (служебная программа SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 80cb14fb-f4c6-4be2-ba17-eb4e4cddd35f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c4ab30ad0e87782f8187370a53747be4cf5d313d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732610"
---
# <a name="view-resource-health-policy-results-sql-server-utility"></a><span data-ttu-id="13fa2-102">Просмотр результатов политики исправности ресурсов (служебная программа SQL Server)</span><span class="sxs-lookup"><span data-stu-id="13fa2-102">View Resource Health Policy Results (SQL Server Utility)</span></span>
  <span data-ttu-id="13fa2-103">Панель мониторинга служебной программы в среде [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] позволяет просмотреть параметры служебной программы [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] для управляемых экземпляров [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] и приложений уровня данных.</span><span class="sxs-lookup"><span data-stu-id="13fa2-103">Use the Utility dashboard in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] to view [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Utility resource parameters for managed instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and data-tier applications.</span></span> <span data-ttu-id="13fa2-104">Дополнительные сведения см. в разделе [Функции и задачи служебной программы SQL Server](sql-server-utility-features-and-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="13fa2-104">For more information, see [SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md).</span></span>  
  
##  <a name="SSMSProcedure"></a>  
  
#### <a name="view-sql-server-utility-resource-health-policy-results"></a><span data-ttu-id="13fa2-105">Просмотр результатов политики исправности ресурсов (SQL Server Utility)</span><span class="sxs-lookup"><span data-stu-id="13fa2-105">View SQL Server Utility resource health policy results.</span></span>  
  
1.  <span data-ttu-id="13fa2-106">В меню [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Вид **среды**(SSMS) выберите пункт **Обозреватель программы** , чтобы открыть панель навигации проводника служебной программы.</span><span class="sxs-lookup"><span data-stu-id="13fa2-106">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] (SSMS), click **View**, then click **Utility Explorer** to view the Utility Explorer navigation pane.</span></span> <span data-ttu-id="13fa2-107">Чтобы открыть панель содержимого, в меню **Вид**выберите пункт **Содержимое обозревателя программ**.</span><span class="sxs-lookup"><span data-stu-id="13fa2-107">To view the content pane, click **View**, then click **Utility Explorer Content**.</span></span>  
  
2.  <span data-ttu-id="13fa2-108">На панели навигации щелкните ![](../../database-engine/media/connect-to-utility.gif "Connect_to_Utility")**Соединение со служебной программой**.</span><span class="sxs-lookup"><span data-stu-id="13fa2-108">In the navigation pane, click ![](../../database-engine/media/connect-to-utility.gif "Connect_to_Utility")**Connect to Utility**.</span></span> <span data-ttu-id="13fa2-109">Если точка управления служебной программой еще не создана либо экземпляры [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] или приложения уровня данных не зарегистрированы в служебной программе [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , см. раздел [Функции и задачи служебной программы SQL Server](sql-server-utility-features-and-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="13fa2-109">If you have not created a utility control point (UCP) or if you have not enrolled instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or data-tier applications into the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Utility, see [SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md).</span></span>  
  
3.  <span data-ttu-id="13fa2-110">Щелкните узел точки управления служебной программой, чтобы отобразить сводные данные по управляемым экземплярам [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] и приложениям уровня данных (щелкните правой кнопкой мыши, чтобы выполнить обновление).</span><span class="sxs-lookup"><span data-stu-id="13fa2-110">Click the UCP node to view summary data for managed instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and data-tier applications (right-click to refresh).</span></span> <span data-ttu-id="13fa2-111">Данные панели мониторинга отображаются в области содержимого.</span><span class="sxs-lookup"><span data-stu-id="13fa2-111">Dashboard data is displayed in the content pane.</span></span>  
  
4.  <span data-ttu-id="13fa2-112">Щелкните узел **Управляемые экземпляры** , чтобы открыть список данных по управляемым экземплярам [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (щелкните его правой кнопкой мыши, чтобы выполнить обновление).</span><span class="sxs-lookup"><span data-stu-id="13fa2-112">Click the **Managed Instances** node to view list view data for managed instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (right-click to refresh).</span></span> <span data-ttu-id="13fa2-113">Данные в представлении списка отображаются на панели содержимого.</span><span class="sxs-lookup"><span data-stu-id="13fa2-113">List view data is displayed in the content pane.</span></span>  
  
5.  <span data-ttu-id="13fa2-114">Щелкните узел **Развернутые приложения уровня данных** , чтобы отобразить список данных по приложениям уровня данных (щелкните его правой кнопкой мыши, чтобы выполнить обновление).</span><span class="sxs-lookup"><span data-stu-id="13fa2-114">Click the **Deployed Data-tier Applications** node to view list view data for data-tier applications (right-click to refresh).</span></span> <span data-ttu-id="13fa2-115">Данные в представлении списка отображаются на панели содержимого.</span><span class="sxs-lookup"><span data-stu-id="13fa2-115">List view data is displayed in the content pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13fa2-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="13fa2-116">See Also</span></span>  
 <span data-ttu-id="13fa2-117">[Функции и задачи служебной программы SQL Server](sql-server-utility-features-and-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="13fa2-117">[SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md) </span></span>  
 <span data-ttu-id="13fa2-118">[Уменьшение уровня шума в политиках загрузки ЦП (служебная программа SQL Server)](reduce-noise-in-cpu-utilization-policies-sql-server-utility.md) </span><span class="sxs-lookup"><span data-stu-id="13fa2-118">[Reduce Noise in CPU Utilization Policies &#40;SQL Server Utility&#41;](reduce-noise-in-cpu-utilization-policies-sql-server-utility.md) </span></span>  
 <span data-ttu-id="13fa2-119">[Подробные сведения о развернутом приложении уровня данных (служебная программа SQL Server)](../../database-engine/deployed-data-tier-application-details-sql-server-utility.md) </span><span class="sxs-lookup"><span data-stu-id="13fa2-119">[Deployed Data-tier Application Details &#40;SQL Server Utility&#41;](../../database-engine/deployed-data-tier-application-details-sql-server-utility.md) </span></span>  
 <span data-ttu-id="13fa2-120">[Подробные сведения об управляемом экземпляре (служебная программа SQL Server)](../../database-engine/managed-instance-details-sql-server-utility.md) </span><span class="sxs-lookup"><span data-stu-id="13fa2-120">[Managed Instance Details &#40;SQL Server Utility&#41;](../../database-engine/managed-instance-details-sql-server-utility.md) </span></span>  
 [<span data-ttu-id="13fa2-121">Администрирование программ (служебная программа SQL Server)</span><span class="sxs-lookup"><span data-stu-id="13fa2-121">Utility Administration &#40;SQL Server Utility&#41;</span></span>](../../database-engine/utility-administration-sql-server-utility.md)  
  
  
