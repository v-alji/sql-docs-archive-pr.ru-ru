---
title: Использование WQL и языков сценариев с поставщиком WMI для управления конфигурацией | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- queries [WMI]
- scripts [WMI]
- query language [WMI]
- WMI Query Language [WMI]
- WQL [WMI]
- WMI Provider for Configuration Management, WQL
- WMI Provider for Configuration Management, scripts
ms.assetid: c1e64905-3c2b-4974-88f4-abf17cf7e289
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d8c903cd0e993728865bce3371c349a2d0ba7485
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664059"
---
# <a name="using-wql-and-scripting-languages-with-the-wmi-provider-for-configuration-management"></a><span data-ttu-id="2743f-102">Использование WQL и языков сценариев с поставщиком WMI для управления конфигурациями</span><span class="sxs-lookup"><span data-stu-id="2743f-102">Using WQL and Scripting Languages with the WMI Provider for Configuration Management</span></span>
  <span data-ttu-id="2743f-103">Управляющие приложения получают доступ к службам [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и сетевым настройкам, используя поставщик инструментария управления Windows (WMI) для объектов управления конфигурацией двумя способами.</span><span class="sxs-lookup"><span data-stu-id="2743f-103">Management applications access [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services and network settings using the Windows Management Instrumentation (WMI) Provider for Configuration Management objects in two ways:</span></span>  
  
-   <span data-ttu-id="2743f-104">С помощью редактора WQL или средства создания запросов, например WBEMTest.exe, создается запрос к набору объектов на языке WQL (языке запросов к инструментарию управления Windows).</span><span class="sxs-lookup"><span data-stu-id="2743f-104">Using a WQL editor or query tool, such as WBEMTest.exe to query the object set with the Windows Management Instrumentation Language (WQL).</span></span>  
  
-   <span data-ttu-id="2743f-105">С помощью языка для создания сценариев (например, VBScript).</span><span class="sxs-lookup"><span data-stu-id="2743f-105">Using a scripting language, such as VBScript.</span></span>  
  
 <span data-ttu-id="2743f-106">Другой способ — управлять службами и сетевыми настройками [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] программным образом, используя управляемые объекты WMI в SMO.</span><span class="sxs-lookup"><span data-stu-id="2743f-106">Alternatively, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services and network settings can be managed programmatically using the WMI managed objects in SMO.</span></span> <span data-ttu-id="2743f-107">Дополнительные сведения о программировании управляемых WMI объектов см. в разделе [Управление службами и сетевыми параметрами с помощью поставщика WMI](../server-management-objects-smo/tasks/managing-services-and-network-settings-by-using-wmi-provider.md).</span><span class="sxs-lookup"><span data-stu-id="2743f-107">For more information about programming WMI managed objects, see [Managing Services and Network Settings by Using WMI Provider](../server-management-objects-smo/tasks/managing-services-and-network-settings-by-using-wmi-provider.md).</span></span>  
  
 <span data-ttu-id="2743f-108">Доступ к поставщику WMI для управления конфигурацией можно получить с помощью [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager и [!INCLUDE[msCoName](../../includes/msconame-md.md)] консоли управления.</span><span class="sxs-lookup"><span data-stu-id="2743f-108">The WMI provider for Configuration Management can be accessed by using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager and [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console.</span></span> <span data-ttu-id="2743f-109">Дополнительные сведения о доступе к поставщику WMI из пользовательского интерфейса см. [в разделах руководства по управлению службами &#40;диспетчер конфигурации SQL Server&#41;](../../database-engine/managing-services-how-to-topics-sql-server-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="2743f-109">For more information about accessing the WMI provider from a user interface, see [Managing Services How-to Topics &#40;SQL Server Configuration Manager&#41;](../../database-engine/managing-services-how-to-topics-sql-server-configuration-manager.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2743f-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="2743f-110">See Also</span></span>  
 <span data-ttu-id="2743f-111">[Доступ к поставщику WMI для управления конфигурацией с помощью WQL](access-wmi-provider-for-configuration-management-using-wql.md) </span><span class="sxs-lookup"><span data-stu-id="2743f-111">[Access WMI Provider for Configuration Management using WQL](access-wmi-provider-for-configuration-management-using-wql.md) </span></span>  
 [<span data-ttu-id="2743f-112">изменить расширенные свойства службы SQL Server с помощью VBScript</span><span class="sxs-lookup"><span data-stu-id="2743f-112">Modify SQL Server Service Advanced Properties using VBScript</span></span>](access-wmi-provider-for-configuration-management-using-vbscript.md)  
  
  
