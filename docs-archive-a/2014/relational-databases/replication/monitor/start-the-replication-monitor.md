---
title: Запуск монитора репликации | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Replication Monitor, starting
ms.assetid: e037bd27-cc87-4ee9-9e5f-83f6d717cfa4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cff23206923825d0e86e47ad6921c19f45e68b35
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750724"
---
# <a name="start-the-replication-monitor"></a><span data-ttu-id="042c3-102">Запуск монитора репликации</span><span class="sxs-lookup"><span data-stu-id="042c3-102">Start the Replication Monitor</span></span>
  <span data-ttu-id="042c3-103">Монитор репликации может быть запущен из командной строки или в среде [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] на любом экземпляре [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="042c3-103">Replication Monitor can be started from [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] on any instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], or from the command prompt.</span></span> <span data-ttu-id="042c3-104">Запустив монитор репликации, добавьте в монитор одного или несколько издателей.</span><span class="sxs-lookup"><span data-stu-id="042c3-104">After starting Replication Monitor, add one or more Publishers to monitor.</span></span> <span data-ttu-id="042c3-105">Дополнительные сведения см. в статье [Добавление и удаление издателей в мониторе репликации](add-and-remove-publishers-from-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="042c3-105">For more information, see [Add and Remove Publishers from Replication Monitor](add-and-remove-publishers-from-replication-monitor.md).</span></span>  
  
### <a name="to-start-replication-monitor-from-sql-server-management-studio"></a><span data-ttu-id="042c3-106">Запуск монитора репликации из среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="042c3-106">To start Replication Monitor from SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="042c3-107">Подключитесь к экземпляру [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] в среде [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], а затем раскройте узел сервера.</span><span class="sxs-lookup"><span data-stu-id="042c3-107">Connect to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="042c3-108">Щелкните правой кнопкой мыши папку **Репликация** или любую из ее вложенных папок, а затем щелкните **Запустить монитор репликации**.</span><span class="sxs-lookup"><span data-stu-id="042c3-108">Right-click the **Replication** folder or any of its subfolders, and then click **Launch Replication Monitor**.</span></span>  
  
### <a name="to-start-replication-monitor-from-the-command-prompt"></a><span data-ttu-id="042c3-109">Запуск монитора репликации из командной строки</span><span class="sxs-lookup"><span data-stu-id="042c3-109">To start Replication Monitor from the command prompt</span></span>  
  
1.  <span data-ttu-id="042c3-110">Находясь в командной строке, перейдите в каталог установки средств.</span><span class="sxs-lookup"><span data-stu-id="042c3-110">From the command prompt, navigate to the tools installation directory.</span></span> <span data-ttu-id="042c3-111">Путь по умолчанию: [!INCLUDE[ssInstallPath](../../../includes/ssinstallpath-md.md)]Tools\Binn\.</span><span class="sxs-lookup"><span data-stu-id="042c3-111">The default path is [!INCLUDE[ssInstallPath](../../../includes/ssinstallpath-md.md)]Tools\Binn\ .</span></span>  
  
2.  <span data-ttu-id="042c3-112">Запустите файл sqlmonitor.exe.</span><span class="sxs-lookup"><span data-stu-id="042c3-112">Run sqlmonitor.exe.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="042c3-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="042c3-113">See Also</span></span>  
 [<span data-ttu-id="042c3-114">Наблюдение за репликацией</span><span class="sxs-lookup"><span data-stu-id="042c3-114">Monitoring Replication</span></span>](../monitoring-replication.md)  
  
  
