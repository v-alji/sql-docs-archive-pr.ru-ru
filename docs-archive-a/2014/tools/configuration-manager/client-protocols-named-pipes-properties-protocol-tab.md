---
title: Клиентские протоколы — свойства именованных каналов (вкладка "Протокол") | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- pipes [SQL Server], connecting to
- Named Pipes [SQL Server], default pipe
- client protocols [SQL Server]
ms.assetid: 30fbae62-2f2e-4d36-9c6e-3444fff68781
author: stevestein
ms.author: sstein
ms.openlocfilehash: 169b6d98212c724b8d6c43615ae2fa7eba9cfc7d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728998"
---
# <a name="client-protocols---named-pipes-properties-protocol-tab"></a><span data-ttu-id="521c5-102">Клиентские протоколы — свойства именованных каналов (вкладка «Протокол»)</span><span class="sxs-lookup"><span data-stu-id="521c5-102">Client Protocols - Named Pipes Properties (Protocol Tab)</span></span>
  <span data-ttu-id="521c5-103">В диспетчере конфигурации [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] используйте вкладку **Протокол** в диалоговом окне **Named Pipes Properties** (Свойства именованных каналов) для просмотра или изменения описания канала по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="521c5-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager use the **Protocol** tab on the **Named Pipes Properties** dialog box to view or modify the description of default pipe.</span></span> <span data-ttu-id="521c5-104">Для подключения к другому каналу введите название канала в поле **Канал по умолчанию** .</span><span class="sxs-lookup"><span data-stu-id="521c5-104">To connect to a different pipe, type the pipe in the **Default Pipe** box.</span></span> <span data-ttu-id="521c5-105">Дополнительные сведения о строках соединения см. в разделе [Creating a Valid Connection String Using Named Pipes](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md).</span><span class="sxs-lookup"><span data-stu-id="521c5-105">For more information about connection strings, see [Creating a Valid Connection String Using Named Pipes](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="521c5-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="521c5-106">Options</span></span>  
 <span data-ttu-id="521c5-107">**Канал по умолчанию**</span><span class="sxs-lookup"><span data-stu-id="521c5-107">**Default Pipe**</span></span>  
 <span data-ttu-id="521c5-108">Задает канал по умолчанию, который будет использоваться сетевой библиотекой именованных каналов для попыток подключения к целевому экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="521c5-108">Specifies the default pipe the Named Pipes Net-library will use to attempt to connect to the target instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="521c5-109">По умолчанию [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] прослушивает `\\.\pipe\sql\query`</span><span class="sxs-lookup"><span data-stu-id="521c5-109">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] listens on: `\\.\pipe\sql\query`</span></span>  
  
 <span data-ttu-id="521c5-110">Чтобы подключиться к каналу по умолчанию, введите `sql\query`</span><span class="sxs-lookup"><span data-stu-id="521c5-110">To connect to the default pipe, enter `sql\query`</span></span>  
  
 <span data-ttu-id="521c5-111">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="521c5-111">**Enabled**</span></span>  
 <span data-ttu-id="521c5-112">Возможные значения: **Да** и **Нет**.</span><span class="sxs-lookup"><span data-stu-id="521c5-112">Possible values are **Yes** and **No**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="521c5-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="521c5-113">See Also</span></span>  
 [<span data-ttu-id="521c5-114">Выбор сетевого протокола</span><span class="sxs-lookup"><span data-stu-id="521c5-114">Choosing a Network Protocol</span></span>](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md)  
  
  
