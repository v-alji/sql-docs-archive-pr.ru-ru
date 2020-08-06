---
title: Запуск и остановка службы сервера отчетов | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- stopping Report Server service
- Report Server Windows service, starting
- Report Server service, starting
- starting Report Server service
ms.assetid: 6ec69ac3-27b0-472d-91e1-733af9078ed2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b751fd1a31830ffdc96cb296fa39d08e396c8c50
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87659342"
---
# <a name="start-and-stop-the-report-server-service"></a><span data-ttu-id="d65d6-102">Запуск и остановка службы сервера отчетов</span><span class="sxs-lookup"><span data-stu-id="d65d6-102">Start and Stop the Report Server Service</span></span>
  <span data-ttu-id="d65d6-103">Сервер отчетов реализован в виде службы Windows, которая включает веб-службу сервера отчетов, диспетчер отчетов и приложение фоновой обработки.</span><span class="sxs-lookup"><span data-stu-id="d65d6-103">A report server is implemented as a Windows service that contains the Report Server Web service, Report Manager, and a background processing application.</span></span> <span data-ttu-id="d65d6-104">Чтобы использовать какие-либо функции сервера отчетов, эта служба должна работать.</span><span class="sxs-lookup"><span data-stu-id="d65d6-104">The service must be running if you want to use any report server functionality.</span></span> <span data-ttu-id="d65d6-105">Остановка службы приводит к прекращению всех операций сервера отчетов.</span><span class="sxs-lookup"><span data-stu-id="d65d6-105">Stopping the service stops all report server operations.</span></span>  
  
 <span data-ttu-id="d65d6-106">Пока служба остановлена, запросы для запланированных отчетов и обработки подписок, которые были бы удовлетворены, если бы служба работала, добавляются в очередь.</span><span class="sxs-lookup"><span data-stu-id="d65d6-106">While the service is stopped, requests for scheduled report and subscription processing that would have occurred had the service been running are added to the queue.</span></span> <span data-ttu-id="d65d6-107">Это связано с тем, что задания, выполняемые агентом [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , создают события.</span><span class="sxs-lookup"><span data-stu-id="d65d6-107">This is because jobs that are run by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent create the events.</span></span> <span data-ttu-id="d65d6-108">Если требуется предотвратить создание незавершенных операций во время простоя службы, рассмотрите возможность остановить работу агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d65d6-108">If you want to avoid a backlog of operations while the service is off, consider stopping [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent as well.</span></span>  
  
 <span data-ttu-id="d65d6-109">Чтобы запустить или остановить службу сервера отчетов, можно применить ряд средств, включая программу настройки служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , диспетчер конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и оснастку «Службы», существующую в [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="d65d6-109">You can use a variety of tools to start or stop the Report Server service, including the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, and the Services tool provided in [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span></span>  
  
 <span data-ttu-id="d65d6-110">Чтобы выполнить какие-либо другие операции, кроме запуска и остановки службы, например для смены учетной записи службы, необходимо пользоваться программой настройки служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d65d6-110">If you are doing more than starting or stopping the service, such as changing the service account, you must use the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool.</span></span> <span data-ttu-id="d65d6-111">Использование для смены учетной записи службы других средств может привести к неработоспособности установки служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d65d6-111">Using other tools to change the service account can break your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation.</span></span> <span data-ttu-id="d65d6-112">Дополнительные сведения см. в разделе [Настройка учетной записи службы сервера отчетов (диспетчер конфигурации служб SSRS)](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="d65d6-112">For more information, see [Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md).</span></span>  
  
 <span data-ttu-id="d65d6-113">Эту службу нельзя приостанавливать и возобновлять,</span><span class="sxs-lookup"><span data-stu-id="d65d6-113">You cannot pause and resume the service.</span></span> <span data-ttu-id="d65d6-114">и параметров запуска она не имеет.</span><span class="sxs-lookup"><span data-stu-id="d65d6-114">There are no start parameters.</span></span> <span data-ttu-id="d65d6-115">Хотя явные зависимости отсутствуют, для поддержки подписок и проводимых по расписанию операций с отчетами на сервере отчетов должен работать агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d65d6-115">Although there are no explicit dependencies, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent must be running if you support any subscriptions or scheduled report operations on the report server.</span></span>  
  
### <a name="to-start-or-stop-the-service-using-the-reporting-services-configuration-tool"></a><span data-ttu-id="d65d6-116">Запуск или остановка службы с помощью программы настройки служб Reporting Services</span><span class="sxs-lookup"><span data-stu-id="d65d6-116">To start or stop the service using the Reporting Services Configuration tool</span></span>  
  
1.  <span data-ttu-id="d65d6-117">Запустите программу настройки служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] и подключитесь к серверу отчетов.</span><span class="sxs-lookup"><span data-stu-id="d65d6-117">Start [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Configuration tool and connect to the report server.</span></span>  
  
2.  <span data-ttu-id="d65d6-118">На странице состояния сервера отчетов нажмите **Остановить** или **Запустить**.</span><span class="sxs-lookup"><span data-stu-id="d65d6-118">On the Report Server Status page, click **Stop** or **Start**.</span></span>  
  
### <a name="to-start-or-stop-the-service-using-services-in-administrative-tools"></a><span data-ttu-id="d65d6-119">Запуск или остановка службы с помощью оснастки «Службы» в разделе «Администрирование»</span><span class="sxs-lookup"><span data-stu-id="d65d6-119">To start or stop the service using Services in Administrative Tools</span></span>  
  
-   <span data-ttu-id="d65d6-120">В окне "Администрирование" откройте оснастку "Службы", щелкните правой кнопкой мыши элемент **Службы SQL Server Reporting Services (MSSQLSERVER)** и выберите команду **Стоп** или **Перезапустить**.</span><span class="sxs-lookup"><span data-stu-id="d65d6-120">In Administrative Tools, open Services, right-click **SQL Server Reporting Services (MSSQLSERVER)**, and click **Stop** or **Restart**.</span></span>  
  
 <span data-ttu-id="d65d6-121">Если используется несколько экземпляров параллельно или сервер отчетов работает в качестве именованного экземпляра, убедитесь в том, что имя экземпляра в круглых скобках соответствует экземпляру сервера отчетов, который планируется остановить или перезапустить.</span><span class="sxs-lookup"><span data-stu-id="d65d6-121">If you are running multiple instance or if the report server is running as a named instance, verify that the instance name in parentheses corresponds to the report server instance you want to stop or restart.</span></span>  
  
### <a name="to-start-or-stop-the-service-using-sql-server-configuration-manager"></a><span data-ttu-id="d65d6-122">Запуск или остановка службы с помощью диспетчера конфигурации SQL Server</span><span class="sxs-lookup"><span data-stu-id="d65d6-122">To start or stop the service using SQL Server Configuration Manager</span></span>  
  
1.  <span data-ttu-id="d65d6-123">Запуск диспетчера конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d65d6-123">Start [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
2.  <span data-ttu-id="d65d6-124">Выберите "Службы SQL Server", щелкните правой кнопкой мыши элемент **SQL Server Reporting Services**и выберите команду **Стоп** или **Перезапустить**.</span><span class="sxs-lookup"><span data-stu-id="d65d6-124">Select SQL Server Services, right-click **SQL Server Reporting Services**, and click **Stop** or **Restart**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d65d6-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="d65d6-125">See Also</span></span>  
 [<span data-ttu-id="d65d6-126">Использование диспетчера конфигурации служб Reporting Services (собственный режим)</span><span class="sxs-lookup"><span data-stu-id="d65d6-126">Reporting Services Configuration Manager &#40;Native Mode&#41;</span></span>](../../sql-server/install/reporting-services-configuration-manager-native-mode.md)  
  
  
