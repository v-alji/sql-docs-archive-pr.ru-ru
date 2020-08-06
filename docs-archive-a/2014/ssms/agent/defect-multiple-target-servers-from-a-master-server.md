---
title: Отключение нескольких целевых серверов от главного | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, target servers
- target servers [SQL Server], defecting
- SQL Server Agent jobs, master servers
- master servers [SQL Server], defecting target servers
- defecting target servers
- multiple target server defections
ms.assetid: 61a3713b-403a-4806-bfc4-66db72ca1156
author: stevestein
ms.author: sstein
ms.openlocfilehash: b31a8bc38968733de0a23f67a71772721c8baedd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87731357"
---
# <a name="defect-multiple-target-servers-from-a-master-server"></a><span data-ttu-id="71ed3-102">Defect Multiple Target Servers from a Master Server</span><span class="sxs-lookup"><span data-stu-id="71ed3-102">Defect Multiple Target Servers from a Master Server</span></span>
  <span data-ttu-id="71ed3-103">В этом разделе описывается, как исключить несколько целевых серверов из конфигурации администрирования нескольких серверов в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="71ed3-103">This topic describes how to defect multiple target servers from a multiserver administration configuration in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="71ed3-104">Запустите эту процедуру с главного сервера.</span><span class="sxs-lookup"><span data-stu-id="71ed3-104">Run this procedure from the master server.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="71ed3-105">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="71ed3-105">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-defect-multiple-target-servers-from-a-master-server"></a><span data-ttu-id="71ed3-106">Отключение нескольких целевых серверов от главного</span><span class="sxs-lookup"><span data-stu-id="71ed3-106">To defect multiple target servers from a master server</span></span>  
  
1.  <span data-ttu-id="71ed3-107">В **Обозревателе объектов**разверните главный сервер.</span><span class="sxs-lookup"><span data-stu-id="71ed3-107">In **Object Explorer**, expand a server that is configured as a master server.</span></span>  
  
2.  <span data-ttu-id="71ed3-108">Щелкните правой кнопкой мыши элемент **Агент SQL Server**, укажите пункт **Администрирование нескольких серверов**, а затем выберите пункт **Управление целевыми серверами**.</span><span class="sxs-lookup"><span data-stu-id="71ed3-108">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Manage Target Servers**.</span></span>  
  
3.  <span data-ttu-id="71ed3-109">Щелкните **Отправить инструкции**и в списке **Тип инструкции** выберите **Отключить**.</span><span class="sxs-lookup"><span data-stu-id="71ed3-109">Click **Post Instructions**, and then in the **Instruction type** list, select **Defect**.</span></span>  
  
4.  <span data-ttu-id="71ed3-110">В пункте **Адресаты**выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="71ed3-110">Under **Recipients**, do one of the following:</span></span>  
  
    -   <span data-ttu-id="71ed3-111">щелкните **Все целевые серверы** , чтобы отключить от главного сервера все целевые</span><span class="sxs-lookup"><span data-stu-id="71ed3-111">Click **All target servers** to defect all target servers of this master server.</span></span> <span data-ttu-id="71ed3-112">(этот параметр используется в случае, когда нужно полностью удалить установленную текущую конфигурацию администрирования нескольких серверов);</span><span class="sxs-lookup"><span data-stu-id="71ed3-112">Use this option if you want to completely uninstall the current multiserver administration configuration.</span></span>  
  
    -   <span data-ttu-id="71ed3-113">щелкните **Эти целевые серверы**, а затем соответствующий пункт **Выбрать** , чтобы отключить от главного сервера некоторые, но не все целевые серверы.</span><span class="sxs-lookup"><span data-stu-id="71ed3-113">Click **These target servers**, and then click the corresponding **Select** box, to defect some, but not all, target servers of this master server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71ed3-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="71ed3-114">See Also</span></span>  
 <span data-ttu-id="71ed3-115">[Создание многосерверной среды](create-a-multiserver-environment.md) </span><span class="sxs-lookup"><span data-stu-id="71ed3-115">[Create a Multiserver Environment](create-a-multiserver-environment.md) </span></span>  
 <span data-ttu-id="71ed3-116">[Автоматизация администрирования в масштабах предприятия](automated-administration-across-an-enterprise.md) </span><span class="sxs-lookup"><span data-stu-id="71ed3-116">[Automated Administration Across an Enterprise](automated-administration-across-an-enterprise.md) </span></span>  
 [<span data-ttu-id="71ed3-117">Отключение целевого сервера от главного сервера</span><span class="sxs-lookup"><span data-stu-id="71ed3-117">Defect a Target Server from a Master Server</span></span>](defect-a-target-server-from-a-master-server.md)  
  
  
