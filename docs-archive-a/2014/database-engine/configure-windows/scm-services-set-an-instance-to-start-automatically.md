---
title: Настройка автоматического запуска экземпляра SQL Server (диспетчер конфигурации SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 01/07/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- automatic SQL Server startup
- SQL Server, automatic startup
- starting SQL Server, automatically
ms.assetid: aa2b6bde-e76d-4fea-a560-54a63745d9b1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2fc21bd881c1588da47710c6d8437e31d3df2ab4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87738753"
---
# <a name="set-an-instance-of-sql-server-to-start-automatically-sql-server-configuration-manager"></a><span data-ttu-id="c82d8-102">Настройка автоматического запуска экземпляра SQL Server (диспетчер конфигурации SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c82d8-102">Set an Instance of SQL Server to Start Automatically (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="c82d8-103">В этом разделе описано, как настроить автоматический запуск экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью диспетчера конфигурации SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c82d8-103">This topic describes how to set an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to start automatically in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="c82d8-104">Во время установки [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] обычно настраивается для автоматического запуска.</span><span class="sxs-lookup"><span data-stu-id="c82d8-104">During setup, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is normally configured to start automatically.</span></span> <span data-ttu-id="c82d8-105">Если это не было выполнено, настройку можно произвести в любой момент.</span><span class="sxs-lookup"><span data-stu-id="c82d8-105">If this was not done, you can change that setting at any time.</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c82d8-106">Использование диспетчера конфигурации SQL Server</span><span class="sxs-lookup"><span data-stu-id="c82d8-106">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-set-an-instance-of-sql-server-to-start-automatically"></a><span data-ttu-id="c82d8-107">Настройка автоматического запуска экземпляра SQL Server</span><span class="sxs-lookup"><span data-stu-id="c82d8-107">To set an instance of SQL Server to start automatically</span></span>  
  
1.  <span data-ttu-id="c82d8-108">В меню **Пуск** последовательно выберите пункты **Все программы**, [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], **Средства настройки**и щелкните **Диспетчер конфигурации SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="c82d8-108">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c82d8-109">Поскольку диспетчер конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] является оснасткой консоли управления ( [!INCLUDE[msCoName](../../includes/msconame-md.md)] ), а не изолированной программой, при работе в более новых версиях Windows диспетчер конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не отображается как приложение.</span><span class="sxs-lookup"><span data-stu-id="c82d8-109">Because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager is a snap-in for the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console program and not a stand-alone program, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager does not appear as an application in newer versions of Windows.</span></span>  
    >   
    >  -   <span data-ttu-id="c82d8-110">**Windows 10**:</span><span class="sxs-lookup"><span data-stu-id="c82d8-110">**Windows 10**:</span></span>  
    >          <span data-ttu-id="c82d8-111">Чтобы открыть [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, на **начальной странице**введите SQLServerManager12. msc (для [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="c82d8-111">To open [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, on the **Start Page**, type SQLServerManager12.msc (for [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]).</span></span> <span data-ttu-id="c82d8-112">Для предыдущих версий [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] замените 12 на меньшее число.</span><span class="sxs-lookup"><span data-stu-id="c82d8-112">For previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] replace 12 with a smaller number.</span></span> <span data-ttu-id="c82d8-113">Если щелкнуть SQLServerManager12.msc, откроется диспетчер конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c82d8-113">Clicking SQLServerManager12.msc opens the Configuration Manager.</span></span> <span data-ttu-id="c82d8-114">Чтобы закрепить Configuration Manager на начальной странице или на панели задач, щелкните правой кнопкой мыши SQLServerManager12. msc и выберите **открыть расположение файла**.</span><span class="sxs-lookup"><span data-stu-id="c82d8-114">To pin the Configuration Manager to the Start Page or Task Bar, right-click SQLServerManager12.msc, and then click **Open file location**.</span></span> <span data-ttu-id="c82d8-115">В проводнике Windows щелкните правой кнопкой мыши файл SQLServerManager12. msc и выберите пункт **закрепить на** **панели задач или закрепить на**ней.</span><span class="sxs-lookup"><span data-stu-id="c82d8-115">In the Windows File Explorer, right-click SQLServerManager12.msc, and then click **Pin to Start** or **Pin to taskbar**.</span></span>  
    > -   <span data-ttu-id="c82d8-116">**Windows 8**:</span><span class="sxs-lookup"><span data-stu-id="c82d8-116">**Windows 8**:</span></span>  
    >          <span data-ttu-id="c82d8-117">Чтобы открыть [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, во вложенном поле **Поиск** в разделе **приложения**введите **SQLServerManager \<version> . msc** , например `SQLServerManager12.msc` , и нажмите клавишу **Ввод**.</span><span class="sxs-lookup"><span data-stu-id="c82d8-117">To open [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, in the **Search** charm, under **Apps**, type **SQLServerManager\<version>.msc** such as `SQLServerManager12.msc`, and then press **Enter**.</span></span>  
  
2.  <span data-ttu-id="c82d8-118">Откройте **Диспетчер конфигурации SQL Server**, раскройте **Службы**и щелкните **SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="c82d8-118">In **SQL Server Configuration Manager**, expand **Services**, and then click **SQL Server**.</span></span>  
  
3.  <span data-ttu-id="c82d8-119">В области сведений щелкните правой кнопкой имя экземпляра, который должен запускаться автоматически, и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="c82d8-119">In the details pane, right-click the name of the instance you want to start automatically, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="c82d8-120">В диалоговом окне **Свойства \<***instancename***> SQL Server** установите для параметра **Режим запуска** значение **Автоматически**.</span><span class="sxs-lookup"><span data-stu-id="c82d8-120">In the **SQL Server \<***instancename***> Properties** dialog box, set **Start Mode** to **Automatic**.</span></span>  
  
5.  <span data-ttu-id="c82d8-121">Нажмите кнопку **ОК**и закройте диспетчер конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c82d8-121">Click **OK**, and then close [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c82d8-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="c82d8-122">See Also</span></span>  
 <span data-ttu-id="c82d8-123">[Отключение автоматического запуска экземпляра SQL Server (диспетчер конфигурации SQL Server)](scm-services-prevent-automatic-startup-of-an-instance.md) </span><span class="sxs-lookup"><span data-stu-id="c82d8-123">[Prevent Automatic Startup of an Instance of SQL Server &#40;SQL Server Configuration Manager&#41;](scm-services-prevent-automatic-startup-of-an-instance.md) </span></span>  
 <span data-ttu-id="c82d8-124">[Подключение к другому компьютеру (диспетчер конфигурации SQL Server)](scm-services-connect-to-another-computer.md) </span><span class="sxs-lookup"><span data-stu-id="c82d8-124">[Connect to Another Computer &#40;SQL Server Configuration Manager&#41;](scm-services-connect-to-another-computer.md) </span></span>  
 [<span data-ttu-id="c82d8-125">Настройка инструментария WMI для отображения состояния сервера в инструментальных средствах SQL Server</span><span class="sxs-lookup"><span data-stu-id="c82d8-125">Configure WMI to Show Server Status in SQL Server Tools</span></span>](../../ssms/configure-wmi-to-show-server-status-in-sql-server-tools.md)  
  
  
