---
title: Свойства общей памяти | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- shared memory [SQL Server]
ms.assetid: dc1704da-eacd-4d26-b529-c996f958ca4b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6275215afdb6de3aa134dbffe74aa22b9e7b6f5d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667984"
---
# <a name="shared-memory-properties"></a><span data-ttu-id="22e1f-102">Свойства общей памяти</span><span class="sxs-lookup"><span data-stu-id="22e1f-102">Shared Memory Properties</span></span>
  <span data-ttu-id="22e1f-103">Используйте страницу **Протокол**в диалоговом окне **Свойства общей памяти** , чтобы включить или выключить протокол общей памяти.</span><span class="sxs-lookup"><span data-stu-id="22e1f-103">Use the **Protocol**page on the **Shared Memory Properties** dialog box to enable or disable the shared memory protocol.</span></span> <span data-ttu-id="22e1f-104">Общая память является простейшим протоколом и не имеет настраиваемых параметров.</span><span class="sxs-lookup"><span data-stu-id="22e1f-104">Shared memory is the simplest protocol to use and has no configurable settings.</span></span> <span data-ttu-id="22e1f-105">Поскольку клиенты, использующие протокол общей памяти, могут подключаться только к экземпляру [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], запущенному на том же компьютере, этот протокол не подходит для большинства операций с базами данных.</span><span class="sxs-lookup"><span data-stu-id="22e1f-105">Because clients using the shared memory protocol can only connect to a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance running on the same computer, it is not useful for most database activity.</span></span> <span data-ttu-id="22e1f-106">Используйте протокол общей памяти, чтобы устранить неполадки, если есть вероятность того, что другие протоколы настроены некорректно.</span><span class="sxs-lookup"><span data-stu-id="22e1f-106">Use the shared memory protocol for troubleshooting when you suspect the other protocols are configured incorrectly.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="22e1f-107">должен быть перезапущен, чтобы включить или отключить протокол.</span><span class="sxs-lookup"><span data-stu-id="22e1f-107">must be restarted to enable or disable the protocol.</span></span>  
  
## <a name="options"></a><span data-ttu-id="22e1f-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="22e1f-108">Options</span></span>  
 <span data-ttu-id="22e1f-109">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="22e1f-109">**Enabled**</span></span>  
 <span data-ttu-id="22e1f-110">Возможные значения: **Да** и **Нет**.</span><span class="sxs-lookup"><span data-stu-id="22e1f-110">Possible values are **Yes** and **No**.</span></span> <span data-ttu-id="22e1f-111">По умолчанию протокол общей памяти включен.</span><span class="sxs-lookup"><span data-stu-id="22e1f-111">The shared memory protocol is enabled by default.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22e1f-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="22e1f-112">See Also</span></span>  
 <span data-ttu-id="22e1f-113">[Выбор сетевого протокола](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="22e1f-113">[Choosing a Network Protocol](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span></span>  
 [<span data-ttu-id="22e1f-114">Создание допустимой строки соединения с использованием протокола общей памяти</span><span class="sxs-lookup"><span data-stu-id="22e1f-114">Creating a Valid Connection String Using Shared Memory Protocol</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md)  
  
  
