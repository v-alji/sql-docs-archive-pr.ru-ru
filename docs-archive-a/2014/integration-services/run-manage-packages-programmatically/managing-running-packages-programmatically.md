---
title: Программное управление запуском пакетов | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- packages [Integration Services], managing
- running packages [Integration Services]
ms.assetid: 0e91f4ac-6f29-40d7-8c28-9b82e4802c35
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 95c5f9c28b407631764d64523b37a6295870542a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740139"
---
# <a name="managing-running-packages-programmatically"></a><span data-ttu-id="f0f70-102">Программное управление запуском пакетов</span><span class="sxs-lookup"><span data-stu-id="f0f70-102">Managing Running Packages Programmatically</span></span>
  <span data-ttu-id="f0f70-103">При программном способе работы с пакетами служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] может потребоваться определить, какие пакеты уже запущены в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="f0f70-103">As you work programmatically with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, you may want to determine which packages are currently running.</span></span> <span data-ttu-id="f0f70-104">Класс <xref:Microsoft.SqlServer.Dts.Runtime.Application> пространства имен <xref:Microsoft.SqlServer.Dts.Runtime> предоставляет необходимые для этого методы и классы.</span><span class="sxs-lookup"><span data-stu-id="f0f70-104">The <xref:Microsoft.SqlServer.Dts.Runtime.Application> class of the <xref:Microsoft.SqlServer.Dts.Runtime> namespace provides methods and classes to satisfy these requirements.</span></span>  
  
 <span data-ttu-id="f0f70-105">Дополнительные сведения о мониторинге пакетов см. в разделе [Управление пакетами (службы SSIS)](../service/package-management-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="f0f70-105">For more information about monitoring packages, see [Package Management &#40;SSIS Service&#41;](../service/package-management-ssis-service.md).</span></span>  
  
 <span data-ttu-id="f0f70-106">Все методы, описываемые в этом разделе, должны ссылаться на сборку `Microsoft.SqlServer.ManagedDTS`.</span><span class="sxs-lookup"><span data-stu-id="f0f70-106">All the methods discussed in this topic require a reference to the `Microsoft.SqlServer.ManagedDTS` assembly.</span></span> <span data-ttu-id="f0f70-107">После добавления ссылки в новый проект импортируйте пространство имен <xref:Microsoft.SqlServer.Dts.Runtime> с помощью инструкции `using` или `Imports`.</span><span class="sxs-lookup"><span data-stu-id="f0f70-107">After you add the reference in a new project, import the <xref:Microsoft.SqlServer.Dts.Runtime> namespace with a `using` or `Imports` statement.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f0f70-108">Методы класса <xref:Microsoft.SqlServer.Dts.Runtime.Application> для работы с хранилищем пакетов служб SSIS поддерживают только имена «.», localhost и имя сервера для локального сервера.</span><span class="sxs-lookup"><span data-stu-id="f0f70-108">The methods of the <xref:Microsoft.SqlServer.Dts.Runtime.Application> class for working with the SSIS Package Store support only ".", localhost, or the server name for the local server.</span></span> <span data-ttu-id="f0f70-109">Нельзя использовать имя «(local)».</span><span class="sxs-lookup"><span data-stu-id="f0f70-109">You cannot use "(local)".</span></span>  
  
## <a name="determining-which-packages-are-currently-running"></a><span data-ttu-id="f0f70-110">Определение, какие пакеты запущены в настоящее время</span><span class="sxs-lookup"><span data-stu-id="f0f70-110">Determining Which Packages Are Currently Running</span></span>  
 <span data-ttu-id="f0f70-111">Чтобы определить, какие пакеты запущены в настоящее время на указанном сервере, вызовите метод <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetRunningPackages%2A>.</span><span class="sxs-lookup"><span data-stu-id="f0f70-111">To determine which packages are currently running on the specified server, call the <xref:Microsoft.SqlServer.Dts.Runtime.Application.GetRunningPackages%2A> method.</span></span> <span data-ttu-id="f0f70-112">Этот метод возвращает коллекцию <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackages> объектов <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage>.</span><span class="sxs-lookup"><span data-stu-id="f0f70-112">This method returns a <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackages> collection of <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage> objects.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f0f70-113">Администраторы могут видеть все пакеты, выполняющиеся в настоящее время на компьютере, а другие пользователи видят только те пакеты, которые запустили они сами.</span><span class="sxs-lookup"><span data-stu-id="f0f70-113">Administrators see all packages that are currently executing on the computer; other users see only those packages that they have launched.</span></span>  
  
## <a name="working-with-running-packages"></a><span data-ttu-id="f0f70-114">Работа с запущенными пакетами</span><span class="sxs-lookup"><span data-stu-id="f0f70-114">Working with Running Packages</span></span>  
 <span data-ttu-id="f0f70-115">Определив, какие пакеты запущены в настоящее время, можно получить сведения об этих пакетах и запросить остановку выполнения пакета.</span><span class="sxs-lookup"><span data-stu-id="f0f70-115">After you have determined which packages are currently running, you can retrieve information about the packages and request that a package be stopped.</span></span>  
  
### <a name="getting-information-about-a-running-package"></a><span data-ttu-id="f0f70-116">Получение сведений о запущенном пакете</span><span class="sxs-lookup"><span data-stu-id="f0f70-116">Getting Information about a Running Package</span></span>  
 <span data-ttu-id="f0f70-117">При просмотре коллекции <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackages> можно с помощью свойств объекта <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage> найти пакет или получить дополнительные сведения о запущенных пакетах.</span><span class="sxs-lookup"><span data-stu-id="f0f70-117">As you iterate through the <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackages> collection, you can use the properties of the <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage> object to locate a package or to obtain additional information about the packages that are running:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.ExecutionDuration%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.ExecutionStartTime%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.InstanceID%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.PackageDescription%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.PackageID%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.PackageName%2A>  
  
-   <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.UserName%2A>  
  
### <a name="stopping-a-running-package"></a><span data-ttu-id="f0f70-118">Остановка выполнения пакета</span><span class="sxs-lookup"><span data-stu-id="f0f70-118">Stopping a Running Package</span></span>  
 <span data-ttu-id="f0f70-119">Можно вызвать метод <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.Stop%2A> объекта <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage>, чтобы остановить выполнение пакета.</span><span class="sxs-lookup"><span data-stu-id="f0f70-119">You can call the <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage.Stop%2A> method of a <xref:Microsoft.SqlServer.Dts.Runtime.RunningPackage> object to request that the package be stopped.</span></span> <span data-ttu-id="f0f70-120">Между созданием запроса на остановку пакета и действительной остановкой пакета может пройти некоторое время.</span><span class="sxs-lookup"><span data-stu-id="f0f70-120">There may be a delay between the time that a stop request is issued and the time that the package actually stops.</span></span>  
  
<span data-ttu-id="f0f70-121">![Значок Integration Services (маленький)](../media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="f0f70-121">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="f0f70-122">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="f0f70-122">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="f0f70-123">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="f0f70-123">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="f0f70-124">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="f0f70-124">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0f70-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="f0f70-125">See Also</span></span>  
 <span data-ttu-id="f0f70-126">[Управление пакетами &#40;служб SSIS&#41;](../service/package-management-ssis-service.md) </span><span class="sxs-lookup"><span data-stu-id="f0f70-126">[Package Management &#40;SSIS Service&#41;](../service/package-management-ssis-service.md) </span></span>  
 [<span data-ttu-id="f0f70-127">Программное перечисление доступных пакетов</span><span class="sxs-lookup"><span data-stu-id="f0f70-127">Enumerating Available Packages Programmatically</span></span>](../run-manage-packages-programmatically/enumerating-available-packages-programmatically.md)  
  
  
