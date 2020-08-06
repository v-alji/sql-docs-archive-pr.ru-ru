---
title: Работа с отчетами и PowerShell в Reporting Services | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- scripts [Reporting Services]
- Reporting Services, scripting
- scripting [Reporting Services]
ms.assetid: 1ac2646d-ed5a-4436-b18f-2150c33f3d87
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a7a8dc805351897c11202467ed8bcb0373ef77c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665235"
---
# <a name="scripting-and-powershell-with-reporting-services"></a><span data-ttu-id="1a3ae-102">Сценарии и PowerShell со службами Reporting Services</span><span class="sxs-lookup"><span data-stu-id="1a3ae-102">Scripting and PowerShell with Reporting Services</span></span>
  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="1a3ae-103">поддерживает целый ряд сценариев разработки и управления посредством скриптов, включая служебную программу командной строки rs.exe, командлеты PowerShell для серверов отчетов в режиме SharePoint и использование объектной модели [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] из PowerShell для режима SharePoint и собственного режима.</span><span class="sxs-lookup"><span data-stu-id="1a3ae-103">supports a wide range of development and management scenarios through script, including the rs.exe command line utility, PowerShell cmdlets for SharePoint mode report servers, and leveraging the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] object model from PowerShell for both Native and SharePoint mode.</span></span>

-   <span data-ttu-id="1a3ae-104">Администратор может написать скрипт на [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)], чтобы автоматизировать развертывание установки сервера отчетов и управление ей.</span><span class="sxs-lookup"><span data-stu-id="1a3ae-104">Administrators can write script in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] to automate how they deploy and manage a report server installation.</span></span> <span data-ttu-id="1a3ae-105">Администраторы также могут создавать и запускать скрипты [!INCLUDE[tsql](../../includes/tsql-md.md)] для создания, настройки и обновления базы данных сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="1a3ae-105">Administrators can also generate and run [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts that create, configure, and update a report server database.</span></span> <span data-ttu-id="1a3ae-106">Администраторы также могут использовать возможности записи и воспроизведения компонентов скрипта в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], чтобы автоматизировать стандартные задачи обслуживания.</span><span class="sxs-lookup"><span data-stu-id="1a3ae-106">Administrators can also use the record and playback script features in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] to automate routine maintenance tasks.</span></span>

-   <span data-ttu-id="1a3ae-107">Разработчики могут создавать пользовательские приложения, включающие скрипты.</span><span class="sxs-lookup"><span data-stu-id="1a3ae-107">Developers can create custom applications that include script.</span></span> <span data-ttu-id="1a3ae-108">Можно запустить скрипт, который выполнит вызовы к веб-службе сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="1a3ae-108">You can run script that makes calls to the Report Server Web service.</span></span> <span data-ttu-id="1a3ae-109">Практически любая операция доступная в управляемом коде, может быть написана и в скрипте.</span><span class="sxs-lookup"><span data-stu-id="1a3ae-109">Almost any operation that you can write in managed code can also be written in script.</span></span>

-   [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="1a3ae-110">поддерживает скрипт .NET [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] как язык скриптов, который можно обработать с помощью программы RS.exe (сервер скриптов, который выполняется на сервере отчетов).</span><span class="sxs-lookup"><span data-stu-id="1a3ae-110">supports [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] .NET script as the script language that can be processed by the RS.exe utility, a script host that runs on the report server.</span></span>

## <a name="reporting-services-sharepoint-mode-powershell-cmdlets-and-samples"></a><span data-ttu-id="1a3ae-111">Образцы и командлеты PowerShell в режиме SharePoint для служб Reporting Services</span><span class="sxs-lookup"><span data-stu-id="1a3ae-111">Reporting Services SharePoint mode PowerShell cmdlets and samples</span></span>
 <span data-ttu-id="1a3ae-112">![Содержимое, связанное с PowerShell](../media/rs-powershellicon.jpg "Содержимое, связанное с PowerShell")</span><span class="sxs-lookup"><span data-stu-id="1a3ae-112">![PowerShell related content](../media/rs-powershellicon.jpg "PowerShell related content")</span></span>

 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="1a3ae-113">включает [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] командлеты для администрирования сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="1a3ae-113">SharePoint mode includes [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] cmdlets for report server administration.</span></span>

-   <span data-ttu-id="1a3ae-114">[PowerShell cmdlets for Reporting Services SharePoint Mode](../powershell-cmdlets-for-reporting-services-sharepoint-mode.md) содержит следующие примеры.</span><span class="sxs-lookup"><span data-stu-id="1a3ae-114">[PowerShell cmdlets for Reporting Services SharePoint Mode](../powershell-cmdlets-for-reporting-services-sharepoint-mode.md) Includes the following examples:</span></span>

    -   <span data-ttu-id="1a3ae-115">Создайте приложение службы и прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="1a3ae-115">Create a service application and proxy</span></span>

    -   <span data-ttu-id="1a3ae-116">Проверьте и обновите модуль доставки</span><span class="sxs-lookup"><span data-stu-id="1a3ae-116">Review and update a delivery extension</span></span>

    -   <span data-ttu-id="1a3ae-117">Получение и задание свойств базы данных приложения служб Reporting Services, например времени ожидания базы данных</span><span class="sxs-lookup"><span data-stu-id="1a3ae-117">Get and set Properties of the Reporting Service Application Database, for example database timeout</span></span>

    -   <span data-ttu-id="1a3ae-118">Расширения данных списка</span><span class="sxs-lookup"><span data-stu-id="1a3ae-118">List Data Extensions</span></span>

## <a name="reporting-services-object-model-and-powershell-samples"></a><span data-ttu-id="1a3ae-119">Объектная модель служб Reporting Services и примеры отчетов Powershell</span><span class="sxs-lookup"><span data-stu-id="1a3ae-119">Reporting Services Object model and Powershell samples</span></span>
 <span data-ttu-id="1a3ae-120">![Содержимое, связанное с PowerShell](../media/rs-powershellicon.jpg "Содержимое, связанное с PowerShell")</span><span class="sxs-lookup"><span data-stu-id="1a3ae-120">![PowerShell related content](../media/rs-powershellicon.jpg "PowerShell related content")</span></span>

 <span data-ttu-id="1a3ae-121">Вызов PowerShell основной объектной модели, в большинстве случаев допустимый для режима SharePoint и собственного режима, например при работе с миграцией и подписками, а также дополнительные сопутствующие примеры по работе с подписками в SQL15.</span><span class="sxs-lookup"><span data-stu-id="1a3ae-121">PowerShell calling the core object model and for the most part valid for SharePoint and native mode, for example the migration work, subscription work, and more related samples for subscriptions work in SQL15.</span></span>

-   <span data-ttu-id="1a3ae-122">[Использование PowerShell для смены и перечисления владельцев подписок служб Reporting Services и запуска подписки](../subscriptions/manage-subscription-owners-and-run-subscription-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="1a3ae-122">[Use PowerShell to Change and List Reporting Services Subscription Owners and Run a Subscription](../subscriptions/manage-subscription-owners-and-run-subscription-powershell.md).</span></span>

-   <span data-ttu-id="1a3ae-123">[Использование PowerShell для создания виртуальной машины Windows Azure с помощью сервера отчетов, работающего в собственном режиме](https://msdn.microsoft.com/library/azure/dn449661.aspx).</span><span class="sxs-lookup"><span data-stu-id="1a3ae-123">[Use PowerShell to Create an Azure VM With a Native Mode Report Server](https://msdn.microsoft.com/library/azure/dn449661.aspx).</span></span>

-   <span data-ttu-id="1a3ae-124">См. раздел "Доступ к классам WMI с помощью PowerShell" в статье [Доступ к поставщику WMI для служб Reporting Services](access-the-reporting-services-wmi-provider.md).</span><span class="sxs-lookup"><span data-stu-id="1a3ae-124">See the section "Access the WMI classes using PowerShell" in [Access the Reporting Services WMI Provider](access-the-reporting-services-wmi-provider.md).</span></span>

-   <span data-ttu-id="1a3ae-125">[Администрирование служб SSRS с помощью PowerShell](https://www.sqlshack.com/how-to-administer-sql-server-reporting-services-ssrs-subscriptions-using-powershell/).scriptin</span><span class="sxs-lookup"><span data-stu-id="1a3ae-125">[How to Administer SSRS using PowerShell](https://www.sqlshack.com/how-to-administer-sql-server-reporting-services-ssrs-subscriptions-using-powershell/).scriptin</span></span>

## <a name="rsexe-scripting-samples"></a><span data-ttu-id="1a3ae-126">Образцы скриптов RS.exe</span><span class="sxs-lookup"><span data-stu-id="1a3ae-126">RS.exe scripting samples</span></span>

-   <span data-ttu-id="1a3ae-127">[Пример Reporting Services rs.exe сценария для переноса содержимого между серверами отчетов](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span><span class="sxs-lookup"><span data-stu-id="1a3ae-127">[Sample Reporting Services rs.exe Script to Migrate Content between Report Servers](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span></span>

-   <span data-ttu-id="1a3ae-128">Дополнительные примеры скриптов, приложений и расширений см. в разделе [Примеры продуктов SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="1a3ae-128">For additional script, application, and extension examples, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>

## <a name="see-also"></a><span data-ttu-id="1a3ae-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="1a3ae-129">See Also</span></span>
 <span data-ttu-id="1a3ae-130">[RS.exe служебной программы &#40;службы SSRS&#41;](rs-exe-utility-ssrs.md) скрипт [развертывания и администрирования сценариев](script-deployment-and-administrative-tasks.md) [с помощью служебной программы rs.exe и веб-службы](script-with-the-rs-exe-utility-and-the-web-service.md)</span><span class="sxs-lookup"><span data-stu-id="1a3ae-130">[RS.exe Utility &#40;SSRS&#41;](rs-exe-utility-ssrs.md) [Script Deployment and Administrative Tasks](script-deployment-and-administrative-tasks.md) [Script with the rs.exe Utility and the Web Service](script-with-the-rs-exe-utility-and-the-web-service.md)</span></span>


