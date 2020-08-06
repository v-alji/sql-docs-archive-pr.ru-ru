---
title: Установка PowerPivot для SharePoint 2010 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 8d47dde7-c941-4280-a934-e2fe3f9a938f
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: ba04dfdc69b1c510a800c062586e45f8873c8e8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666934"
---
# <a name="powerpivot-for-sharepoint-2010-installation"></a><span data-ttu-id="28137-102">Установка PowerPivot для SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="28137-102">PowerPivot for SharePoint 2010 Installation</span></span>
  [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)] <span data-ttu-id="28137-103">представляет собой набор серверных компонентов, которые обеспечивают обработку запросов и административное управление книгами [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)], публикуемыми в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="28137-103">is a collection of server components that provide query processing and management control over [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] workbooks that you publish to SharePoint.</span></span> <span data-ttu-id="28137-104">Набор содержит ядро служб Analysis Services и системную службу [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="28137-104">Services include the Analysis Services engine and [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] System Service.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="28137-105">Дополнительные сведения о [!INCLUDE[ssSQL11SP1](../../includes/sssql11sp1-md.md)] и установке с SharePoint Server 2013 см. далее:</span><span class="sxs-lookup"><span data-stu-id="28137-105">For information regarding [!INCLUDE[ssSQL11SP1](../../includes/sssql11sp1-md.md)] and installation with SharePoint Server 2013, see the following:</span></span>  
>   
>  -   <span data-ttu-id="28137-106">Раздел "SQL Server 2012 с пакетом обновления 1 (SP1)" в статье [Общие сведения об установке SQL Server обслуживания](../../../2014/sql-server/install/overview-of-sql-server-servicing-installation.md).</span><span class="sxs-lookup"><span data-stu-id="28137-106">The "SQL Server 2012 SP1" section of [Overview of SQL Server Servicing Installation](../../../2014/sql-server/install/overview-of-sql-server-servicing-installation.md).</span></span>  
  
 <span data-ttu-id="28137-107">Службы Analysis Services обеспечивают серверную обработку для книг Excel, которые содержат данные [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="28137-107">Analysis Services provides server-side processing for Excel workbooks that contain [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] data.</span></span> <span data-ttu-id="28137-108">Системная служба [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] работает параллельно со службами Analysis Services, обеспечивая дополнительную интеграцию с SharePoint, балансировку нагрузки и возможности управления соединениями.</span><span class="sxs-lookup"><span data-stu-id="28137-108">[!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] System Service works alongside Analysis Services, adding SharePoint integration, load balancing and connection management.</span></span> [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)]<span data-ttu-id="28137-109">расширяет службы Excel, применяя возможности обработки больших объемов данных с помощью служб подготовки данных, предоставляемых Excel.</span><span class="sxs-lookup"><span data-stu-id="28137-109">extends Excel Services by pairing its large scale data processing capability with the data rendering services that Excel provides.</span></span>  
  
 <span data-ttu-id="28137-110">Для установки служб [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)]воспользуйтесь установочным носителем [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)].</span><span class="sxs-lookup"><span data-stu-id="28137-110">To install [!INCLUDE[ssGeminiShort](../../includes/ssgeminishort-md.md)], use the [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]installation media.</span></span>  
  
 <span data-ttu-id="28137-111">Инструкции по расширенным сценариям развертывания см. в разделе [Контрольный список развертывания: Reporting Services, Power View и PowerPivot для SharePoint](deployment-checklist-reporting-services-power-view-power-pivot-for-sharepoint.md) и [Контрольный список развертывания: развертывание путем добавления серверов PowerPivot в ферму SharePoint 2010](../../../2014/sql-server/install/deployment-checklist-scale-out-adding-powerpivot-servers-sharepoint-2010-farm.md).</span><span class="sxs-lookup"><span data-stu-id="28137-111">For instructions on advanced deployment scenarios, see [Deployment Checklist: Reporting Services, Power View, and PowerPivot for SharePoint](deployment-checklist-reporting-services-power-view-power-pivot-for-sharepoint.md) and [Deployment Checklist: Scale-out by adding PowerPivot Servers to a SharePoint 2010 farm](../../../2014/sql-server/install/deployment-checklist-scale-out-adding-powerpivot-servers-sharepoint-2010-farm.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="28137-112">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="28137-112">In This Section</span></span>  
 [<span data-ttu-id="28137-113">Установка PowerPivot для SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="28137-113">Install PowerPivot for SharePoint 2010</span></span>](../../../2014/sql-server/install/install-powerpivot-for-sharepoint-2010.md)  
  
 [<span data-ttu-id="28137-114">Установка поставщика OLE DB служб Analysis Services на серверах SharePoint</span><span class="sxs-lookup"><span data-stu-id="28137-114">Install the Analysis Services OLE DB Provider on SharePoint Servers</span></span>](../../../2014/sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md)  
  
 [<span data-ttu-id="28137-115">Установка ADOMD.NET на веб-серверах, обслуживающих клиентские запросы, под управлением центра администрирования</span><span class="sxs-lookup"><span data-stu-id="28137-115">Install ADOMD.NET on Web Front-End Servers Running Central Administration</span></span>](../../../2014/sql-server/install/install-adomd-net-on-web-front-end-servers-running-central-administration.md)  
  
 [<span data-ttu-id="28137-116">Для поддержки экспорта списков SharePoint в виде веб-каналов данных установите службы ADO.NET Data Services</span><span class="sxs-lookup"><span data-stu-id="28137-116">Install ADO.NET Data Services to support data feed exports of SharePoint lists</span></span>](../../../2014/sql-server/install/install-ado-net-data-services-to-support-data-feed-exports-of-sharepoint-lists.md)  
  
 [<span data-ttu-id="28137-117">Установка PowerPivot из командной строки</span><span class="sxs-lookup"><span data-stu-id="28137-117">Install PowerPivot from the Command Prompt</span></span>](../../../2014/sql-server/install/install-powerpivot-from-the-command-prompt.md)  
  
 [<span data-ttu-id="28137-118">Удаление PowerPivot для SharePoint</span><span class="sxs-lookup"><span data-stu-id="28137-118">Uninstall PowerPivot for SharePoint</span></span>](../../../2014/sql-server/install/uninstall-power-pivot-for-sharepoint.md)  
  
 [<span data-ttu-id="28137-119">Восстановление PowerPivot для SharePoint</span><span class="sxs-lookup"><span data-stu-id="28137-119">Repair PowerPivot for SharePoint</span></span>](../../../2014/sql-server/install/repair-powerpivot-for-sharepoint.md)  
  
 [<span data-ttu-id="28137-120">PowerPivot для SharePoint &#40;начальной конфигурации&#41;</span><span class="sxs-lookup"><span data-stu-id="28137-120">Initial Configuration &#40;PowerPivot for SharePoint&#41;</span></span>](../../../2014/sql-server/install/initial-configuration-powerpivot-for-sharepoint.md)  
  
## <a name="see-also"></a><span data-ttu-id="28137-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="28137-121">See Also</span></span>  
 [<span data-ttu-id="28137-122">Настройка и администрирование сервера PowerPivot в центре администрирования</span><span class="sxs-lookup"><span data-stu-id="28137-122">PowerPivot Server Administration and Configuration in Central Administration</span></span>](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/power-pivot-server-administration-and-configuration-in-central-administration)  
  
  
