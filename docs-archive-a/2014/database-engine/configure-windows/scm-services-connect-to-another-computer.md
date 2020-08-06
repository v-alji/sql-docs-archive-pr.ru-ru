---
title: Подключение к другому компьютеру (диспетчер конфигурации SQL Server) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- connections [SQL Server], other computers
ms.assetid: c4c1e94f-4f5f-431e-8b5b-d5ff97baf723
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f3d478cebc1ca36ccb8f87b0355b7c8fe0a928cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669106"
---
# <a name="connect-to-another-computer-sql-server-configuration-manager"></a><span data-ttu-id="ddbee-102">Подключение к другому компьютеру (диспетчер конфигурации SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ddbee-102">Connect to Another Computer (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="ddbee-103">В этом разделе описывается подключение к другому компьютеру в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ddbee-103">This topic describes how to connect to another computer in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="ddbee-104">Выполните первую процедуру, чтобы открыть консоль управления [!INCLUDE[msCoName](../../includes/msconame-md.md)] «Управление компьютером», подключитесь к компьютеру и разверните дерево «Службы и приложения».</span><span class="sxs-lookup"><span data-stu-id="ddbee-104">Follow the first procedure to open the Windows Computer Management [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console (mmc), connect to the computer, and expand the Services and Applications tree.</span></span> <span data-ttu-id="ddbee-105">Выполните вторую процедуру для создания файла с ссылкой на диспетчер конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ddbee-105">Follow the second procedure to create a file with a link to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager on a remote computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ddbee-106">Некоторые действия не могут выполняться с помощью Configuration Manager при удаленном подключении.</span><span class="sxs-lookup"><span data-stu-id="ddbee-106">Some actions cannot be performed by Configuration Manager when connecting remotely.</span></span>  
  
 <span data-ttu-id="ddbee-107">Для запуска, остановки и приостановки служб на другом компьютере можно также подключиться к этому серверу при помощи среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], щелкнуть правой кнопкой мыши этот сервер или агент [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , затем выбрать нужное действие.</span><span class="sxs-lookup"><span data-stu-id="ddbee-107">To start, stop, pause, or resume services on another computer, you can also connect to the server with [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], right-click the server or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent and then click the desired action.</span></span>  
  
##  <a name="SSMSProcedure"></a>  
  
#### <a name="to-connect-to-another-computer-with-windows-computer-management"></a><span data-ttu-id="ddbee-108">Подключение к другому компьютеру с помощью управления компьютерами Windows</span><span class="sxs-lookup"><span data-stu-id="ddbee-108">To connect to another computer with Windows Computer Management</span></span>  
  
1.  <span data-ttu-id="ddbee-109">В меню **Пуск** щелкните правой кнопкой мыши **Мой компьютер**, а затем выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="ddbee-109">On the **Start** menu, right-click **My Computer**, and then click **Manage.**</span></span>  
  
2.  <span data-ttu-id="ddbee-110">В диалоговом окне **Управление компьютером**щелкните правой кнопкой мыши **Управление компьютером (локальным)**, а затем нажмите **Подключиться к другому компьютеру**.</span><span class="sxs-lookup"><span data-stu-id="ddbee-110">In **Computer Management**, right-click **Computer Management (Local)**, and then click **Connect to another computer**.</span></span>  
  
3.  <span data-ttu-id="ddbee-111">В диалоговом окне **Выбор компьютера** , в текстовом поле **Другой компьютер** введите имя компьютера, которым нужно управлять, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ddbee-111">In the **Select Computer** dialog box, in the **Another computer** text box, type the name of the computer you want to manage, and then click **OK**.</span></span>  
  
     <span data-ttu-id="ddbee-112">Управление компьютером отображает службы, выполняющиеся на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ddbee-112">Computer Management displays the services running on the remote computer.</span></span> <span data-ttu-id="ddbee-113">Узел верхнего уровня сменится на **Управление компьютером** \<*remotecomputer*>.</span><span class="sxs-lookup"><span data-stu-id="ddbee-113">The top-level node changes to **Computer Management** \<*remotecomputer*>.</span></span>  
  
4.  <span data-ttu-id="ddbee-114">В дереве консоли разверните **Службы и приложения**, затем разверните **Диспетчер конфигурации SQL Server** для управления службами удаленного компьютера.</span><span class="sxs-lookup"><span data-stu-id="ddbee-114">In the console tree, expand **Services and Applications**, and then expand **SQL Server Configuration Manager** to manage the remote computer's services.</span></span>  
  
#### <a name="to-save-a-link-to-sql-server-configuration-manager-for-another-computer"></a><span data-ttu-id="ddbee-115">Сохранение ссылки на диспетчер конфигурации SQL Server для другого компьютера</span><span class="sxs-lookup"><span data-stu-id="ddbee-115">To save a link to SQL Server Configuration Manager for another computer</span></span>  
  
1.  <span data-ttu-id="ddbee-116">В меню **Пуск** выберите команду **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="ddbee-116">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="ddbee-117">В поле **Открыть** введите, `mmc -a` чтобы открыть [!INCLUDE[msCoName](../../includes/msconame-md.md)] консоль управления в режиме автора.</span><span class="sxs-lookup"><span data-stu-id="ddbee-117">In the **Open** box, type `mmc -a` to open the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console in author mode.</span></span>  
  
3.  <span data-ttu-id="ddbee-118">В меню **Файл** выберите **Добавить или удалить оснастку**.</span><span class="sxs-lookup"><span data-stu-id="ddbee-118">On the **File** menu, click **Add/Remove Snap-in**.</span></span>  
  
4.  <span data-ttu-id="ddbee-119">В диалоговом окне **Добавить или удалить оснастку** нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="ddbee-119">In the **Add/Remove Snap-in** window, click **Add**.</span></span>  
  
5.  <span data-ttu-id="ddbee-120">В диалоговом окне **Добавить изолированную оснастку** выберите **Управление компьютером** и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="ddbee-120">In the **Add Standalone Snap-in** window, click **Computer Management** and then click **Add**.</span></span>  
  
6.  <span data-ttu-id="ddbee-121">В диалоговом окне **Управление компьютером** выберите **Другой компьютер**, введите имя компьютера, которым нужно управлять и нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="ddbee-121">In the **Computer Management** window, click **Another computer**, type the name of the remote computer you wish to manage, and then click **Finish**.</span></span>  
  
7.  <span data-ttu-id="ddbee-122">В диалоговом окне **Добавить изолированную оснастку** нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="ddbee-122">In the **Add Standalone Snap-in** window, click **Close**.</span></span>  
  
8.  <span data-ttu-id="ddbee-123">В диалоговом окне **Добавить или удалить оснастку** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ddbee-123">In the **Add/Remove Snap-in** window, click **OK**.</span></span>  
  
9. <span data-ttu-id="ddbee-124">Разверните узел **Управление компьютером ( ***\<computer name>*** )**, а затем **службы и приложения**.</span><span class="sxs-lookup"><span data-stu-id="ddbee-124">Expand **Computer Management (***\<computer name>***)**, and **Services and Applications**.</span></span>  
  
10. <span data-ttu-id="ddbee-125">Щелкните правой кнопкой мыши **Диспетчер конфигурации SQL Server**, затем щелкните **Новое окно отсюда**.</span><span class="sxs-lookup"><span data-stu-id="ddbee-125">Right-click **SQL Server Configuration Manager**, and then click **New Window from here**.</span></span>  
  
11. <span data-ttu-id="ddbee-126">В меню **Окно** выберите **Корень консоли**, чтобы вернуться в первое окно, и удалите его.</span><span class="sxs-lookup"><span data-stu-id="ddbee-126">On the **Window** menu, click **Console Root**, to switch back to the first window, and delete the window.</span></span>  
  
12. <span data-ttu-id="ddbee-127">В меню **файл** выберите команду **Сохранить как**и сохраните файл в нужной папке с соответствующим именем с `.msc` расширением файла.</span><span class="sxs-lookup"><span data-stu-id="ddbee-127">On the **File** menu, click **Save As**, and save the file in the desired folder, with an appropriate name with the `.msc` file extension.</span></span> <span data-ttu-id="ddbee-128">Закройте консоль управления (MMC) [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ddbee-128">Close the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console.</span></span>  
  
13. <span data-ttu-id="ddbee-129">Чтобы открыть диспетчер конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на целевом компьютере, дважды щелкните этот файл.</span><span class="sxs-lookup"><span data-stu-id="ddbee-129">To open [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager on the target computer, double-click the file.</span></span> <span data-ttu-id="ddbee-130">При желании сохраните ссылку на этот файл на рабочем столе или в меню **Пуск** .</span><span class="sxs-lookup"><span data-stu-id="ddbee-130">If desired, save a link to the file on the desktop or in the **Start** menu.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="ddbee-131">При использовании диспетчера конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на удаленном компьютере имя компьютера не является очевидным, и можно по ошибке остановить или настроить не тот компьютер.</span><span class="sxs-lookup"><span data-stu-id="ddbee-131">When using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager on a remote computer, the computer name is not obvious and it is possible to mistakenly stop or configure the wrong computer.</span></span> <span data-ttu-id="ddbee-132">На вкладке **Служба** в поле **Имя узла** проверьте имя компьютера перед тем, как изменять службу.</span><span class="sxs-lookup"><span data-stu-id="ddbee-132">On the **Service** tab, check the **Host Name** box to confirm the computer name before modifying a service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddbee-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="ddbee-133">See Also</span></span>  
 [<span data-ttu-id="ddbee-134">Настройка инструментария WMI для отображения состояния сервера в инструментальных средствах SQL Server</span><span class="sxs-lookup"><span data-stu-id="ddbee-134">Configure WMI to Show Server Status in SQL Server Tools</span></span>](../../ssms/configure-wmi-to-show-server-status-in-sql-server-tools.md)  
  
  
