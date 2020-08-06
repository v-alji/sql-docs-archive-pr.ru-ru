---
title: Настройка инструментария WMI для отображения состояния сервера в инструментальных средствах SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- WMI Provider for Server Events, setting permissions
- WMI permissions [SQL Server]
ms.assetid: 7e97197b-ed4d-40d1-9a52-9ab1d92401d7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 138abbe2b7b819d6afd6da62135f7cd7ce86496f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737421"
---
# <a name="configure-wmi-to-show-server-status-in-sql-server-tools"></a><span data-ttu-id="1499d-102">Настройка инструментария WMI для отображения состояния сервера в инструментальных средствах SQL Server</span><span class="sxs-lookup"><span data-stu-id="1499d-102">Configure WMI to Show Server Status in SQL Server Tools</span></span>
  <span data-ttu-id="1499d-103">В этом разделе описывается настройка инструментария WMI для отображения состояния сервера в средствах SQL Server в [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1499d-103">This topic describes how to configure WMI to show the server status in SQL Server tools in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="1499d-104">При соединении с сервером компоненты «Зарегистрированные серверы» и «Обозреватель объектов» среды [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], как и диспетчер конфигурации [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , используют инструментарий WMI для получения сведений о состоянии служб [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] (MSSQLSERVER) и агента [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] (MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="1499d-104">When connecting to servers, both the Registered Servers and Object Explorer components of [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], as well as [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Configuration Manager, use Windows Management Instrumentation (WMI) to obtain the status of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] (MSSQLSERVER) and [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent (MSSQLSERVER) services.</span></span> <span data-ttu-id="1499d-105">Для отображения состояния службы пользователь должен иметь права удаленного доступа к объекту инструментария WMI.</span><span class="sxs-lookup"><span data-stu-id="1499d-105">To display the status of the service, the user must have rights to remotely access the WMI object.</span></span> <span data-ttu-id="1499d-106">Для настройки этого разрешения на сервере должен быть установлен инструментарий WMI.</span><span class="sxs-lookup"><span data-stu-id="1499d-106">The server must have WMI installed to configure this permission.</span></span>  
  
##  <a name="to-configure-wmi-permission"></a><a name="SSMSProcedure"></a><span data-ttu-id="1499d-107">Настройка разрешения WMI</span><span class="sxs-lookup"><span data-stu-id="1499d-107">To configure WMI permission</span></span>  
  
1.  <span data-ttu-id="1499d-108">В меню **Пуск** на удаленном сервере выберите **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="1499d-108">On the **Start** menu on the remote server, click **Run**.</span></span>  
  
2.  <span data-ttu-id="1499d-109">В поле **Открыть** введите `wmimgmt.msc` и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1499d-109">In the **Open** box type `wmimgmt.msc`, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="1499d-110">В программе **инфраструктуры управления Windows** щелкните правой кнопкой мыши **Элемент управления WMI (локальный)** и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="1499d-110">In the **Windows Management Infrastructure** program, right-click **WMI Control (Local)**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="1499d-111">В диалоговом окне **Свойства элемента управления WMI (локальный)** на вкладке **Безопасность** разверните **Корень**и щелкните **CIMV2**.</span><span class="sxs-lookup"><span data-stu-id="1499d-111">In the **WMI Control (Local) Properties** dialog box, on the **Security** tab, expand **Root**, and then click **CIMV2**.</span></span>  
  
5.  <span data-ttu-id="1499d-112">Щелкните **Безопасность** , чтобы открыть диалоговое окно **Защита для ROOT\CIMV2** .</span><span class="sxs-lookup"><span data-stu-id="1499d-112">Click **Security** to open the **Security for ROOT\CIMV2** dialog box.</span></span>  
  
6.  <span data-ttu-id="1499d-113">Добавьте группу или пользователя в поле **Имена групп или пользователей** и выберите их.</span><span class="sxs-lookup"><span data-stu-id="1499d-113">Add a group or user to the **Group or user names** box and select it.</span></span>  
  
7.  <span data-ttu-id="1499d-114">В поле **Разрешение для** _\<group or user>_ выберите столбец **Разрешить** для разрешения **Включить удаленно** у пользователей, которым требуется удаленно определить состояние службы.</span><span class="sxs-lookup"><span data-stu-id="1499d-114">In the **Permissions for**_\<group or user>_ box, select the **Allow** column, for the **Remote Enable** permission, for users whom you wish to remotely detect the service status.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1499d-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="1499d-115">See Also</span></span>  
 [<span data-ttu-id="1499d-116">Запуск, остановка или приостановка службы агента SQL Server</span><span class="sxs-lookup"><span data-stu-id="1499d-116">Start, Stop, or Pause the SQL Server Agent Service</span></span>](agent/start-stop-or-pause-the-sql-server-agent-service.md)  
  
  
