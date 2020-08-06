---
title: Параметр конфигурации сервера "allow updates" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- allow updates option
ms.assetid: 3967c3ed-280a-4de8-a2ce-393e82745a7b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d7e3ede317509a2044be90635db46e30a932af66
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665565"
---
# <a name="allow-updates-server-configuration-option"></a><span data-ttu-id="9fdc4-102">Параметр конфигурации сервера «allow updates»</span><span class="sxs-lookup"><span data-stu-id="9fdc4-102">allow updates Server Configuration Option</span></span>
  <span data-ttu-id="9fdc4-103">Этот параметр по-прежнему присутствует в хранимой процедуре **sp_configure** , хотя его функции недоступны в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9fdc4-103">This option is still present in the **sp_configure** stored procedure, although its functionality is unavailable in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="9fdc4-104">Параметр не влияет на работу сервера.</span><span class="sxs-lookup"><span data-stu-id="9fdc4-104">The setting has no effect.</span></span> <span data-ttu-id="9fdc4-105">Непосредственные обновления системных таблиц не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="9fdc4-105">Direct updates to the system tables are not supported.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)]  
  
 <span data-ttu-id="9fdc4-106">Изменение параметра **allow updates** приведет к сбою при выполнении инструкции RECONFIGURE.</span><span class="sxs-lookup"><span data-stu-id="9fdc4-106">Changing the **allow updates** option will cause the RECONFIGURE statement to fail.</span></span> <span data-ttu-id="9fdc4-107">Изменения параметра **allow updates** необходимо удалить из всех скриптов.</span><span class="sxs-lookup"><span data-stu-id="9fdc4-107">Changes to the **allow updates** option should be removed from all scripts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fdc4-108">См. также:</span><span class="sxs-lookup"><span data-stu-id="9fdc4-108">See Also</span></span>  
 [<span data-ttu-id="9fdc4-109">Параметры конфигурации сервера (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9fdc4-109">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
