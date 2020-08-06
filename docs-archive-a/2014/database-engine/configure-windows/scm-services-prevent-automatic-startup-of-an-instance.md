---
title: Запрет автоматического запуска экземпляра SQL Server (диспетчер конфигурации SQL Server) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- automatic SQL Server startup
- SQL Server, stopping
- SQL Server, automatic startup
- canceling automatic startup
- stopping SQL Server
- preventing automatic startups [SQL Server]
ms.assetid: 782663cf-f3d7-4cc6-b621-21e4550f0322
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8f93f5abc749f589ab4208b3a4c9434ca63b8769
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665118"
---
# <a name="prevent-automatic-startup-of-an-instance-of-sql-server-sql-server-configuration-manager"></a><span data-ttu-id="7a73a-102">Отключение автоматического запуска экземпляра SQL Server (диспетчер конфигурации SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7a73a-102">Prevent Automatic Startup of an Instance of SQL Server (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="7a73a-103">В этом разделе описано, как отключить автоматический запуск экземпляра [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью диспетчера конфигурации SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7a73a-103">This topic describes how prevent an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from starting automatically in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using SQL Server Configuration Manager.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7a73a-104">обычно настраивается для автоматического запуска.</span><span class="sxs-lookup"><span data-stu-id="7a73a-104">is normally configured to start automatically.</span></span> <span data-ttu-id="7a73a-105">Это вы можете изменить, задав для экземпляра режим запуска вручную.</span><span class="sxs-lookup"><span data-stu-id="7a73a-105">You can change that by setting the start mode for the instance to manual.</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7a73a-106">Использование диспетчера конфигурации SQL Server</span><span class="sxs-lookup"><span data-stu-id="7a73a-106">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-prevent-automatic-startup-of-an-instance-of-sql-server"></a><span data-ttu-id="7a73a-107">Отключение автоматического запуска экземпляра SQL Server</span><span class="sxs-lookup"><span data-stu-id="7a73a-107">To prevent automatic startup of an instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="7a73a-108">В меню **Пуск** последовательно выберите пункты **Все программы**, [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], **Средства настройки**и щелкните **Диспетчер конфигурации SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="7a73a-108">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="7a73a-109">В диспетчере конфигурации SQL Server разверните **Службы**, затем выберите **SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="7a73a-109">In SQL Server Configuration Manager, expand **Services**, and then click **SQL Server**.</span></span>  
  
3.  <span data-ttu-id="7a73a-110">В области сведений щелкните правой кнопкой мыши **MSSQLServer**и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="7a73a-110">In the details pane, right-click **MSSQLServer**, and then click **Properties.**</span></span>  
  
4.  <span data-ttu-id="7a73a-111">В диалоговом окне \*\* \<**_instancename_**> Свойства SQL Server\*\* в поле **Свойства** установите для параметра **режим запуска** значение **вручную**.</span><span class="sxs-lookup"><span data-stu-id="7a73a-111">In the **SQL Server \<**_instancename_**> Properties** dialog box, in the **Properties** box, set the value of **Start Mode** to **Manual**.</span></span>  
  
5.  <span data-ttu-id="7a73a-112">Нажмите кнопку **OK**, чтобы закрыть диалоговое окно **Свойства SQL Server \<**_instancename_**>** , а затем закройте диспетчер конфигурации [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7a73a-112">Click **OK** to close the **SQL Server \<**_instancename_**> Properties** dialog box, and then close [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a73a-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="7a73a-113">See Also</span></span>  
 [<span data-ttu-id="7a73a-114">Запуск, остановка, приостановка, возобновление и перезапуск компонента Database Engine, агента SQL и службы браузера SQL Server</span><span class="sxs-lookup"><span data-stu-id="7a73a-114">Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service</span></span>](start-stop-pause-resume-restart-sql-server-services.md)  
  
  
