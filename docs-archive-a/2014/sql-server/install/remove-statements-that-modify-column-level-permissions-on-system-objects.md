---
title: Удалите инструкции, изменяющие разрешения уровня столбца на системные объекты | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- column-level permissions [SQL Server]
- removed statement permissions [SQL Server]
ms.assetid: 7f4fbbef-2696-4911-903b-63f6d9e4484a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: e55af3dca0c55c2babd09bc6cfc48ed0ddf3ad7a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666369"
---
# <a name="remove-statements-that-modify-column-level-permissions-on-system-objects"></a><span data-ttu-id="af5d1-102">Удаление инструкций, которые изменяют разрешения уровня столбца в системных объектах</span><span class="sxs-lookup"><span data-stu-id="af5d1-102">Remove statements that modify column-level permissions on system objects</span></span>
  <span data-ttu-id="af5d1-103">Помощник по обновлению обнаружил нестандартные разрешения уровня столбцов на системные объекты.</span><span class="sxs-lookup"><span data-stu-id="af5d1-103">The Upgrade Advisor detected nonstandard column-level permissions on system objects.</span></span> <span data-ttu-id="af5d1-104">Эти изменения разрешений не поддерживаются при обновлении.</span><span class="sxs-lookup"><span data-stu-id="af5d1-104">These permission changes will not be maintained when you upgrade.</span></span> <span data-ttu-id="af5d1-105">Кроме того, разрешения уровня столбцов на системные объекты больше не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="af5d1-105">Additionally, column-level permissions on system objects are no longer supported.</span></span> <span data-ttu-id="af5d1-106">Удалите из своих приложений инструкции, задающие разрешения уровня столбца в системных объектах.</span><span class="sxs-lookup"><span data-stu-id="af5d1-106">Remove statements from your applications that set column-level permissions on system objects.</span></span>  
  
## <a name="component"></a><span data-ttu-id="af5d1-107">Компонент</span><span class="sxs-lookup"><span data-stu-id="af5d1-107">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="af5d1-108">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="af5d1-108">Corrective Action</span></span>  
 <span data-ttu-id="af5d1-109">Удалите из своих приложений инструкции, которые предоставляют, запрещают или отменяют разрешения уровня столбца для системных объектов.</span><span class="sxs-lookup"><span data-stu-id="af5d1-109">Remove statements from your application that grant, deny, or revoke column-level permissions on system objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af5d1-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="af5d1-110">See Also</span></span>  
 <span data-ttu-id="af5d1-111">[Проблемы обновления ядро СУБД](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="af5d1-111">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="af5d1-112">Советник по переходу SQL Server 2014 &#91;New&#93;</span><span class="sxs-lookup"><span data-stu-id="af5d1-112">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
