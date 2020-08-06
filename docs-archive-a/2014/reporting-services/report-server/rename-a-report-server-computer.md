---
title: Переименование компьютера, на котором установлен сервер отчетов | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- renaming report servers
ms.assetid: 82fc4ba2-291a-4939-a025-271b8d687c54
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fe8f699c17f9e5f1e11406ac6e5c161488767ed1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668651"
---
# <a name="rename-a-report-server-computer"></a><span data-ttu-id="aced3-102">Переименование компьютера, на котором установлен сервер отчетов</span><span class="sxs-lookup"><span data-stu-id="aced3-102">Rename a Report Server Computer</span></span>
  <span data-ttu-id="aced3-103">Переименование компьютера приведет к изменению соответствующих имен веб-сервера и экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (если они установлены на одном компьютере).</span><span class="sxs-lookup"><span data-stu-id="aced3-103">Renaming a computer causes a corresponding name change for the Web server and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance (if it is on the same computer).</span></span> <span data-ttu-id="aced3-104">В некоторых случаях службы [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] могут оказаться недоступным после изменения имени компьютера.</span><span class="sxs-lookup"><span data-stu-id="aced3-104">In some cases, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] may not be accessible after a computer name change.</span></span> <span data-ttu-id="aced3-105">Чтобы заново настроить сервер отчетов после изменения имени компьютера, выполните шаги, описанные в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="aced3-105">Use the steps provided in this topic to reconfigure a report server after a computer name change.</span></span>  
  
## <a name="renaming-a-sql-server-database-engine"></a><span data-ttu-id="aced3-106">Переименование компонента SQL Server Database Engine</span><span class="sxs-lookup"><span data-stu-id="aced3-106">Renaming a SQL Server Database Engine</span></span>  
 <span data-ttu-id="aced3-107">При переименовании экземпляра компонента [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , на котором работает база данных сервера отчетов, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="aced3-107">If you rename the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] instance that runs the report server database, do the following:</span></span>  
  
1.  <span data-ttu-id="aced3-108">Запустите программу настройки служб Reporting Services и подключитесь к серверу отчетов, который использует базу данных сервера отчетов на переименованном сервере.</span><span class="sxs-lookup"><span data-stu-id="aced3-108">Start the Reporting Services Configuration tool and connect to the report server that uses the report server database on the renamed server.</span></span>  
  
2.  <span data-ttu-id="aced3-109">Откройте страницу «Установка базы данных».</span><span class="sxs-lookup"><span data-stu-id="aced3-109">Open the Database Setup page.</span></span>  
  
3.  <span data-ttu-id="aced3-110">В окне **Имя сервера**введите или выберите имя [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , затем нажмите кнопку **Подключиться**.</span><span class="sxs-lookup"><span data-stu-id="aced3-110">In **Server Name**, type or select the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] name, and then click **Connect**.</span></span>  
  
4.  <span data-ttu-id="aced3-111">Нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="aced3-111">Click **Apply**.</span></span>  
  
 <span data-ttu-id="aced3-112">Если сервер отчетов применяет локальный экземпляр компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] , для указания сервера можно использовать имя *(local)* или *(local)\имя_экземпляра* .</span><span class="sxs-lookup"><span data-stu-id="aced3-112">If the report server is using a local [!INCLUDE[ssDE](../../includes/ssde-md.md)] instance, you can use *(local)* or *(local)\instancename* to specify the server.</span></span> <span data-ttu-id="aced3-113">Если для ссылки на сервер используется имя *(local)* , переименование сервера не повлияет на работу соединений.</span><span class="sxs-lookup"><span data-stu-id="aced3-113">If you use *(local)* to refer to the server, you can rename the server and the connections will continue to work.</span></span> <span data-ttu-id="aced3-114">Если используется удаленный сервер или службы [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] настроены с помощью имени сервера, при изменении имени сервера необходимо обновлять сведения о подключении к базе данных.</span><span class="sxs-lookup"><span data-stu-id="aced3-114">If you are using a remote server, or if [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is configured using the server name, you must update the database connection information whenever the server name is changed.</span></span>  
  
## <a name="renaming-a-report-server-computer"></a><span data-ttu-id="aced3-115">Переименование компьютера, на котором установлен сервер отчетов</span><span class="sxs-lookup"><span data-stu-id="aced3-115">Renaming a Report Server Computer</span></span>  
 <span data-ttu-id="aced3-116">Если был переименован компьютер, на котором выполняется сервер отчетов, выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="aced3-116">If you rename a computer that runs a report server, do the following:</span></span>  
  
1.  <span data-ttu-id="aced3-117">Откройте **RSReportServer.config** в текстовом редакторе и измените параметр, `UrlRoot` чтобы он отражал новое имя сервера.</span><span class="sxs-lookup"><span data-stu-id="aced3-117">Open **RSReportServer.config** in a text editor and modify the `UrlRoot` setting to reflect the new server name.</span></span> <span data-ttu-id="aced3-118">Настройка `UrlRoot` используется модулями доставки при формировании URL-адреса, предназначенного для доступа к элементам, хранящимся на сервере отчетов.</span><span class="sxs-lookup"><span data-stu-id="aced3-118">The `UrlRoot` setting is used by delivery extensions to compose the URL used to access items stored on the report server.</span></span> <span data-ttu-id="aced3-119">При изменении URL-адреса сервера отчетов необходимо обновить настройку `UrlRoot`, чтобы подписки продолжали выполнять доставку отчетов должным образом.</span><span class="sxs-lookup"><span data-stu-id="aced3-119">Changing the report server URL address requires that you update the `UrlRoot` setting so that subscriptions continue to deliver reports as expected.</span></span>  
  
2.  <span data-ttu-id="aced3-120">В том же файле, если он задан, измените значение параметра `ReportServerUrl`, чтобы оно отражало новое имя сервера.</span><span class="sxs-lookup"><span data-stu-id="aced3-120">In the same file, if it is set, modify the `ReportServerUrl` setting to reflect the new server name.</span></span> <span data-ttu-id="aced3-121">Имейте в виду, что эта настройка используется не во всех установках.</span><span class="sxs-lookup"><span data-stu-id="aced3-121">Note that this setting is not used in every installation.</span></span> <span data-ttu-id="aced3-122">Если она отсутствует, ничего не меняйте.</span><span class="sxs-lookup"><span data-stu-id="aced3-122">If it is empty, do nothing.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="aced3-123">Если в корпоративной сети используется служба WINS, сервер отчетов и диспетчер отчетов некоторое время могут быть доступны под предыдущим именем.</span><span class="sxs-lookup"><span data-stu-id="aced3-123">If you are using Windows Internet Naming Service (WINS) on your corporate network, the report server and Report Manager may continue to be available under the previous name for a period of time.</span></span> <span data-ttu-id="aced3-124">Служба WINS сопоставляет IP-адрес с каждым из компьютеров, которые она обслуживает.</span><span class="sxs-lookup"><span data-stu-id="aced3-124">WINS maps an IP address to each computer it services.</span></span> <span data-ttu-id="aced3-125">После того как службой WINS будет обновлен IP-адрес переименованного компьютера, старое имя компьютера больше не сможет использоваться для доступа к серверу отчетов или диспетчеру отчетов.</span><span class="sxs-lookup"><span data-stu-id="aced3-125">After WINS refreshes the IP address for the renamed computer, the old computer name can no longer be used to access a report server or Report Manager.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aced3-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="aced3-126">See Also</span></span>  
 <span data-ttu-id="aced3-127">[Файл конфигурации RSReportServer](rsreportserver-config-configuration-file.md) </span><span class="sxs-lookup"><span data-stu-id="aced3-127">[RSReportServer Configuration File](rsreportserver-config-configuration-file.md) </span></span>  
 <span data-ttu-id="aced3-128">[Использование диспетчера конфигурации служб Reporting Services (собственный режим)](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="aced3-128">[Reporting Services Configuration Manager &#40;Native Mode&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span></span>  
 <span data-ttu-id="aced3-129">[Сервер отчетов служб Reporting Services (основной режим)](reporting-services-report-server-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="aced3-129">[Reporting Services Report Server &#40;Native Mode&#41;](reporting-services-report-server-native-mode.md) </span></span>  
 <span data-ttu-id="aced3-130">[Запуск и остановка службы сервера отчетов](start-and-stop-the-report-server-service.md) </span><span class="sxs-lookup"><span data-stu-id="aced3-130">[Start and Stop the Report Server Service](start-and-stop-the-report-server-service.md) </span></span>  
 [<span data-ttu-id="aced3-131">Программа rsconfig (SSRS)</span><span class="sxs-lookup"><span data-stu-id="aced3-131">rsconfig Utility &#40;SSRS&#41;</span></span>](../tools/rsconfig-utility-ssrs.md)  
  
  
