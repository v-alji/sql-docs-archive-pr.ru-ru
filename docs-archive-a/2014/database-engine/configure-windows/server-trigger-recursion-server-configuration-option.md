---
title: Параметр конфигурации сервера "server trigger recursion" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- recursive triggers [SQL Server]
- triggers [SQL Server], recursive
- server trigger recursion option
ms.assetid: da4c25f5-d04c-4951-a3db-409e71a1b468
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 23a4997bd1a6f8b2c04af34d5cdc3229575901a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740412"
---
# <a name="server-trigger-recursion-server-configuration-option"></a><span data-ttu-id="6b448-102">Параметр конфигурации сервера «server trigger recursion»</span><span class="sxs-lookup"><span data-stu-id="6b448-102">server trigger recursion Server Configuration Option</span></span>
  <span data-ttu-id="6b448-103">Параметр **server trigger recursion** предназначен для указания того, допускается ли рекурсивное срабатывание триггеров уровня сервера.</span><span class="sxs-lookup"><span data-stu-id="6b448-103">Use the **server trigger recursion** option to specify whether to allow server-level triggers to fire recursively.</span></span> <span data-ttu-id="6b448-104">Если этот параметр установлен в значение 1 (включено), рекурсивное срабатывание триггеров уровня сервера разрешено.</span><span class="sxs-lookup"><span data-stu-id="6b448-104">When this option is set to 1 (ON), server-level triggers will be allowed to fire recursively.</span></span> <span data-ttu-id="6b448-105">Если он установлен в значение 0 (выключено), рекурсивное срабатывание триггеров уровня сервера не допускается.</span><span class="sxs-lookup"><span data-stu-id="6b448-105">When set to 0 (OFF), server-level triggers cannot be fired recursively.</span></span> <span data-ttu-id="6b448-106">Установка этого параметра в 0 (выключено) предотвращает только прямую рекурсию при срабатывании триггеров</span><span class="sxs-lookup"><span data-stu-id="6b448-106">Only direct recursion is prevented when the server trigger recursion option is set to 0 (OFF).</span></span> <span data-ttu-id="6b448-107">(Чтобы отключить косвенную рекурсию, установите в значение 0 параметр **nested triggers**.) Значение по умолчанию для данного параметра равно 1 (включено).</span><span class="sxs-lookup"><span data-stu-id="6b448-107">(To disable indirect recursion, set the **nested triggers** option to 0.) The default value for this option is 1 (ON).</span></span> <span data-ttu-id="6b448-108">Параметр вступает в силу немедленно, без перезапуска сервера.</span><span class="sxs-lookup"><span data-stu-id="6b448-108">The setting takes effect immediately (without a server restart).</span></span>  
  
 <span data-ttu-id="6b448-109">Дополнительные сведения см. в разделе [Создание вложенных триггеров](../../relational-databases/triggers/create-nested-triggers.md).</span><span class="sxs-lookup"><span data-stu-id="6b448-109">For more information, see [Create Nested Triggers](../../relational-databases/triggers/create-nested-triggers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b448-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="6b448-110">See Also</span></span>  
 <span data-ttu-id="6b448-111">[RECONFIGURE (Transact-SQL)](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6b448-111">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="6b448-112">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6b448-112">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="6b448-113">sp_configure (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="6b448-113">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
