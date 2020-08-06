---
title: Объектная модель объектов SMO | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- object models [SMO]
- SMO [SQL Server], object model
- SQL Server Management Objects, object model
ms.assetid: bd6e59b6-ca46-42c0-adb2-c9d64cf6e00b
author: stevestein
ms.author: sstein
ms.openlocfilehash: c973e381a6cc7de44a0072d012147271eaa609ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728181"
---
# <a name="smo-object-model"></a><span data-ttu-id="13599-102">Объектная модель SMO</span><span class="sxs-lookup"><span data-stu-id="13599-102">SMO Object Model</span></span>
  <span data-ttu-id="13599-103">Модель объектов SMO представляет собой иерархию объектов. </span><span class="sxs-lookup"><span data-stu-id="13599-103">The SMO object model is made up of a hierarchy of objects.</span></span> <span data-ttu-id="13599-104"><xref:Microsoft.SqlServer.Management.Smo.Server>Объект является объектом верхнего уровня, а все объекты класса экземпляра находятся в <xref:Microsoft.SqlServer.Management.Smo.Server> объекте.</span><span class="sxs-lookup"><span data-stu-id="13599-104">The <xref:Microsoft.SqlServer.Management.Smo.Server> object is the top level object and all instance class objects reside under the <xref:Microsoft.SqlServer.Management.Smo.Server> object.</span></span>  
  
 <span data-ttu-id="13599-105">Класс <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> является классом верхнего уровня со своей собственной иерархией объектов. </span><span class="sxs-lookup"><span data-stu-id="13599-105">The <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> class is a top level class with a separate object hierarchy.</span></span> <span data-ttu-id="13599-106"><xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer>Объект представляет [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] службы и сетевые параметры, доступные через поставщик WMI.</span><span class="sxs-lookup"><span data-stu-id="13599-106">The <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> object represents [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services and network settings available through the WMI Provider.</span></span>  
  
 <span data-ttu-id="13599-107">Помимо объектов <xref:Microsoft.SqlServer.Management.Smo.Server> и <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer>, существует несколько служебных классов, представляющих задачи или операции, например <xref:Microsoft.SqlServer.Management.Smo.Transfer>, <xref:Microsoft.SqlServer.Management.Smo.Backup> и <xref:Microsoft.SqlServer.Management.Smo.Restore>.</span><span class="sxs-lookup"><span data-stu-id="13599-107">Besides the <xref:Microsoft.SqlServer.Management.Smo.Server> and <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> objects, there are several utility classes that represent tasks or operations, such as <xref:Microsoft.SqlServer.Management.Smo.Transfer>, <xref:Microsoft.SqlServer.Management.Smo.Backup>, or <xref:Microsoft.SqlServer.Management.Smo.Restore></span></span>  
  
 <span data-ttu-id="13599-108">Модель объектов SMO состоит из нескольких пространств имен.</span><span class="sxs-lookup"><span data-stu-id="13599-108">The SMO object model is made up of several namespaces.</span></span> <span data-ttu-id="13599-109">Дополнительные сведения см. в разделе [Пространства имен объектов SMO](smo-object-model-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="13599-109">For more information, see [SMO Namespaces](smo-object-model-namespaces.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13599-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="13599-110">See Also</span></span>  
 <span data-ttu-id="13599-111">[Схема модели объектов SMO](smo-object-model-diagram.md) </span><span class="sxs-lookup"><span data-stu-id="13599-111">[SMO Object Model Diagram](smo-object-model-diagram.md) </span></span>  
 <span data-ttu-id="13599-112">[Пространства имен SMO](smo-object-model-namespaces.md) </span><span class="sxs-lookup"><span data-stu-id="13599-112">[SMO Namespaces](smo-object-model-namespaces.md) </span></span>  
 [<span data-ttu-id="13599-113">Основные понятия о поставщике WMI для управления конфигурацией</span><span class="sxs-lookup"><span data-stu-id="13599-113">WMI Provider for Configuration Management Concepts</span></span>](../wmi-provider-configuration/wmi-provider-for-configuration-management.md)  
  
  
