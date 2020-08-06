---
title: SQL Native Client конфигурация 11,0 | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- client configuration [SQL Server], SQL Server Native Client
ms.assetid: e73143e9-5e7b-4d0a-8827-ab900efdcb35
author: stevestein
ms.author: sstein
ms.openlocfilehash: 183dd2d161b1bf0b13140a607167b81dab086fdf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656129"
---
# <a name="sql-native-client-110-configuration"></a><span data-ttu-id="3a729-102">Конфигурация собственного клиента SQL 11.0</span><span class="sxs-lookup"><span data-stu-id="3a729-102">SQL Native Client 11.0 Configuration</span></span>
  <span data-ttu-id="3a729-103">В этом разделе содержатся разделы справки F1 диалоговых окон модуля **Конфигурация SQL Server Native Client** в диспетчере конфигурации [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a729-103">This section contains the F1 Help topics for the **SQL Server Native Client Configuration** dialogs in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="3a729-104">Native Client является сетевой библиотекой, при помощи которой клиентские компьютеры подключаются к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], начиная с [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a729-104">Native Client is the network library that client computers use to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], starting with [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="3a729-105">Настройки, установленные в конфигурации собственного клиента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , используются на компьютере, на котором запущена программа клиента.</span><span class="sxs-lookup"><span data-stu-id="3a729-105">The settings configured in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client Configuration, are used on the computer running the client program.</span></span> <span data-ttu-id="3a729-106">Если настройки выполняются на компьютере, где запущен [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], они затрагивают только те клиентские программы, которые работают на сервере.</span><span class="sxs-lookup"><span data-stu-id="3a729-106">When configured on the computer running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], they affect only those client programs running on the server.</span></span>  
  
 <span data-ttu-id="3a729-107">Эти настройки не затрагивают клиентов, подключающихся к предыдущим версиям [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], за исключением случая, когда клиенты используют клиентские средства [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]и последующих версий, такие как [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a729-107">These settings do not affect clients connecting to previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], unless they are using the client tools starting with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], such as [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3a729-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="3a729-108">In this Section</span></span>  
  
-   [<span data-ttu-id="3a729-109">Свойства конфигурации собственного клиента SQL Server (вкладка "Флаги")</span><span class="sxs-lookup"><span data-stu-id="3a729-109">SQL Server Native Client Configuration Properties &#40;Flags Tab&#41;</span></span>](../../../2014/tools/configuration-manager/sql-server-native-client-configuration-properties-flags-tab.md)  
  
-   [<span data-ttu-id="3a729-110">Клиентские протоколы (диспетчер конфигурации SQL Server)</span><span class="sxs-lookup"><span data-stu-id="3a729-110">Client Protocols &#40;SQL Server Configuration Manager&#41;</span></span>](../../relational-databases/sql-server-configuration-manager.md)  
  
    -   [<span data-ttu-id="3a729-111">Свойства клиентских протоколов (вкладка "Порядок")</span><span class="sxs-lookup"><span data-stu-id="3a729-111">Client Protocols Properties &#40;Order Tab&#41;</span></span>](../../../2014/tools/configuration-manager/client-protocols-properties-order-tab.md)  
  
    -   [<span data-ttu-id="3a729-112">Клиентские протоколы — свойства общей памяти (вкладка "Протокол")</span><span class="sxs-lookup"><span data-stu-id="3a729-112">Client Protocols - Shared Memory Properties &#40;Protocol Tab&#41;</span></span>](../../../2014/tools/configuration-manager/client-protocols-shared-memory-properties-protocol-tab.md)  
  
    -   [<span data-ttu-id="3a729-113">Клиентские протоколы — вкладка «Свойства TCP и IP» &#40;«протокол»&#41;</span><span class="sxs-lookup"><span data-stu-id="3a729-113">Client Protocols - TCP and IP Properties &#40;Protocol Tab&#41;</span></span>](../../../2014/tools/configuration-manager/client-protocols-tcp-and-ip-properties-protocol-tab.md)  
  
    -   [<span data-ttu-id="3a729-114">Клиентские протоколы — свойства именованных каналов (вкладка "Протокол")</span><span class="sxs-lookup"><span data-stu-id="3a729-114">Client Protocols - Named Pipes Properties &#40;Protocol Tab&#41;</span></span>](../../../2014/tools/configuration-manager/client-protocols-named-pipes-properties-protocol-tab.md)  
  
-   [<span data-ttu-id="3a729-115">Псевдонимы (диспетчер конфигурации SQL Server)</span><span class="sxs-lookup"><span data-stu-id="3a729-115">Aliases &#40;SQL Server Configuration Manager&#41;</span></span>](../../../2014/tools/configuration-manager/aliases-sql-server-configuration-manager.md)  
  
    -   [<span data-ttu-id="3a729-116">Создание псевдонима (вкладка "Псевдоним")</span><span class="sxs-lookup"><span data-stu-id="3a729-116">New Alias &#40;Alias Tab&#41;</span></span>](../../../2014/tools/configuration-manager/new-alias-alias-tab.md)  
  
    -   [<span data-ttu-id="3a729-117">Свойства &#60;Псевдоним&#62; (вкладка "Псевдоним")</span><span class="sxs-lookup"><span data-stu-id="3a729-117">&#60;Alias&#62; Properties &#40;Alias Tab&#41;</span></span>](../../../2014/tools/configuration-manager/alias-properties-alias-tab.md)  
  
    -   [<span data-ttu-id="3a729-118">Создание допустимой строки соединения с использованием протокола общей памяти</span><span class="sxs-lookup"><span data-stu-id="3a729-118">Creating a Valid Connection String Using Shared Memory Protocol</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md)  
  
    -   [<span data-ttu-id="3a729-119">Создание допустимой строки подключения с использованием протокола TCP/IP</span><span class="sxs-lookup"><span data-stu-id="3a729-119">Creating a Valid Connection String Using TCP IP</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md)  
  
    -   [<span data-ttu-id="3a729-120">Создание допустимой строки подключения, использующей протокол именованных каналов</span><span class="sxs-lookup"><span data-stu-id="3a729-120">Creating a Valid Connection String Using Named Pipes</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md)  
  
  
