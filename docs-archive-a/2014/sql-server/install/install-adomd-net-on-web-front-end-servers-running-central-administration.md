---
title: Установка ADOMD.NET на серверах клиентского веб-интерфейса под управлением центра администрирования | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: c2372180-e847-4cdb-b267-4befac3faf7e
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 0d9f52bf612c4878a8dacd4f5acfdcc135ae115e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655546"
---
# <a name="install-adomdnet-on-web-front-end-servers-running-central-administration"></a><span data-ttu-id="5886f-102">Установка ADOMD.NET на веб-серверах, обслуживающих клиентские запросы, под управлением центра администрирования</span><span class="sxs-lookup"><span data-stu-id="5886f-102">Install ADOMD.NET on Web Front-End Servers Running Central Administration</span></span>
  <span data-ttu-id="5886f-103">При установке PowerPivot для SharePoint в ферму с топологией центра администрирования без служб Excel или PowerPivot для SharePoint загрузите и установите клиентскую библиотеку Microsoft ADOMD.NET, если желаете иметь полный доступ к встроенным на панели управления PowerPivot отчетам.</span><span class="sxs-lookup"><span data-stu-id="5886f-103">If you install PowerPivot for SharePoint into a farm that has the topology of Central Administration, without Excel Services or PowerPivot for SharePoint, download and install the Microsoft ADOMD.NET client library if you want full access to the built-in reports in the PowerPivot management dashboard.</span></span> <span data-ttu-id="5886f-104">Некоторые отчеты с панели мониторинга используют ADOMD.NET для доступа к внутренним данным, предоставляющим сведения об обработке запросов PowerPivot и исправности сервера в ферме.</span><span class="sxs-lookup"><span data-stu-id="5886f-104">Some reports in the dashboard use ADOMD.NET to access internal data that provides reporting data on PowerPivot query processing and server health in the farm.</span></span>  
  
 <span data-ttu-id="5886f-105">**[!INCLUDE[applies](../../includes/applies-md.md)]** SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="5886f-105">**[!INCLUDE[applies](../../includes/applies-md.md)]**  SharePoint 2010</span></span>  
  
 <span data-ttu-id="5886f-106">Для SharePoint 2013 поставщик включен в пакет дополнительных компонентов SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5886f-106">For SharePoint 2013, the provider is included in the SQL Server feature pack.</span></span> <span data-ttu-id="5886f-107">Сведения о загрузке spPowerPivot.msi см. в статье [пакет дополнительных компонентов Microsoft SQL Server 2014](https://www.microsoft.com/download/details.aspx?id=35577) .</span><span class="sxs-lookup"><span data-stu-id="5886f-107">For information on how to download spPowerPivot.msi, see [Microsoft SQL Server 2014 Feature Pack](https://www.microsoft.com/download/details.aspx?id=35577)</span></span>  
  
### <a name="download-and-install-the-client-library"></a><span data-ttu-id="5886f-108">Загрузка и установка клиентской библиотеки</span><span class="sxs-lookup"><span data-stu-id="5886f-108">Download and install the client library</span></span>  
  
1.  <span data-ttu-id="5886f-109">На [странице пакета дополнительных компонентов SQL Server 2014](https://go.microsoft.com/fwlink/?LinkID=296473)найдите Microsoft ADOMD.NET.</span><span class="sxs-lookup"><span data-stu-id="5886f-109">On the [SQL Server 2014 Feature Pack page](https://go.microsoft.com/fwlink/?LinkID=296473), find Microsoft ADOMD.NET.</span></span>  
  
2.  <span data-ttu-id="5886f-110">Загрузите пакет x64 программы установки `SQL_AS_ADOMD.msi`.</span><span class="sxs-lookup"><span data-stu-id="5886f-110">Download the x64 Package of the `SQL_AS_ADOMD.msi` installation program.</span></span>  
  
3.  <span data-ttu-id="5886f-111">Запустите MSI-файл, чтобы установить библиотеку.</span><span class="sxs-lookup"><span data-stu-id="5886f-111">Run the .msi to install the library.</span></span>  
  
4.  <span data-ttu-id="5886f-112">По завершении установки сбросьте IIS.</span><span class="sxs-lookup"><span data-stu-id="5886f-112">Reset IIS after installation is finished.</span></span> <span data-ttu-id="5886f-113">Откройте административную командную строку и введите команду **iisreset**.</span><span class="sxs-lookup"><span data-stu-id="5886f-113">Open an administrative command prompt and type **IISRESET**.</span></span>  
  
### <a name="verify-installation"></a><span data-ttu-id="5886f-114">Проверка установки</span><span class="sxs-lookup"><span data-stu-id="5886f-114">Verify installation</span></span>  
  
1.  <span data-ttu-id="5886f-115">Перейдите к папке Windows\Assembly.</span><span class="sxs-lookup"><span data-stu-id="5886f-115">Go to Windows\Assembly.</span></span>  
  
2.  <span data-ttu-id="5886f-116">Щелкните правой кнопкой мыши Microsoft. AnalysisServices. AdomdClient и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="5886f-116">Right-click Microsoft.AnalysisServices.AdomdClient and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="5886f-117">Нажмите **Версия**.</span><span class="sxs-lookup"><span data-stu-id="5886f-117">Click **Version**.</span></span>  
  
4.  <span data-ttu-id="5886f-118">Убедитесь, что версия включает 12,00.\<build number></span><span class="sxs-lookup"><span data-stu-id="5886f-118">Verify that the version includes 12.00.\<build number></span></span> <span data-ttu-id="5886f-119">и это описание — Microsoft. AnalysisService. AdomdClient.</span><span class="sxs-lookup"><span data-stu-id="5886f-119">and that the description is Microsoft.AnalysisService.AdomdClient.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5886f-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="5886f-120">See Also</span></span>  
 [<span data-ttu-id="5886f-121">Панель мониторинга управления PowerPivot и данные об использовании</span><span class="sxs-lookup"><span data-stu-id="5886f-121">PowerPivot Management Dashboard and Usage Data</span></span>](https://docs.microsoft.com/analysis-services/power-pivot-sharepoint/power-pivot-management-dashboard-and-usage-data)  
  
  
