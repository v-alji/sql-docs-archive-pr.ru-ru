---
title: Удалите инструкции, удаляющие системные объекты | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- drop system objects [SQL Server]
ms.assetid: cdfc3c50-c801-4039-a4bf-b35f876f1c61
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: d9e8fbfd4a436e87cee413d95468ccf5dd36b9dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654754"
---
# <a name="remove-statements-that-drop-system-objects"></a><span data-ttu-id="8765b-102">Удалите инструкции, которые удаляют системные объекты</span><span class="sxs-lookup"><span data-stu-id="8765b-102">Remove statements that drop system objects</span></span>
  <span data-ttu-id="8765b-103">Советник по переходу обнаружил инструкции, удаляющие системные объекты.</span><span class="sxs-lookup"><span data-stu-id="8765b-103">Upgrade Advisor detected statements that drop system objects.</span></span> <span data-ttu-id="8765b-104">Системные объекты, включая расширенные хранимые процедуры, развертываются в базе данных **resource** , доступной только для чтения (mssqlsystemresource), и не могут быть удалены.</span><span class="sxs-lookup"><span data-stu-id="8765b-104">System objects, including extended stored procedures, are deployed in the read-only **resource** database (mssqlsystemresource) and cannot be dropped.</span></span> <span data-ttu-id="8765b-105">Измените свои приложения так, чтобы они отменяли или запрещали разрешение EXECUTE для системных объектов.</span><span class="sxs-lookup"><span data-stu-id="8765b-105">Modify your applications to either revoke or deny EXECUTE permission on system objects.</span></span>  
  
## <a name="component"></a><span data-ttu-id="8765b-106">Компонент</span><span class="sxs-lookup"><span data-stu-id="8765b-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="8765b-107">Описание</span><span class="sxs-lookup"><span data-stu-id="8765b-107">Description</span></span>  
 <span data-ttu-id="8765b-108">Такие инструкции, как DROP TABLE, DROP PROCEDURE и **sp_dropextendedproc** , не могут использоваться для удаления системных объектов, поскольку эти объекты развернуты в базе данных **resource** , доступной только для чтения.</span><span class="sxs-lookup"><span data-stu-id="8765b-108">Statements such as DROP TABLE, DROP PROCEDURE, and **sp_dropextendedproc** cannot be used to remove system objects, because these objects are deployed in the read-only **resource** database.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="8765b-109">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="8765b-109">Corrective Action</span></span>  
 <span data-ttu-id="8765b-110">Удалите из своих приложений все инструкции, которые пытаются удалить системные объекты.</span><span class="sxs-lookup"><span data-stu-id="8765b-110">Remove all statements that try to drop system objects from your applications.</span></span> <span data-ttu-id="8765b-111">Измените свои приложения так, чтобы они отменяли или запрещали разрешение EXECUTE для системных объектов.</span><span class="sxs-lookup"><span data-stu-id="8765b-111">Modify your applications to either revoke or deny EXECUTE permission on system objects.</span></span> <span data-ttu-id="8765b-112">В качестве альтернативы для отключения некоторых из этих объектов можно воспользоваться средством настройки контактной зоны (SAC).</span><span class="sxs-lookup"><span data-stu-id="8765b-112">Alternatively, you can use the Surface Area Configuration (SAC) tool to disable some of these objects.</span></span> <span data-ttu-id="8765b-113">Например, с помощью средства SAC можно отключить или включить расширенную хранимую процедуру **xp_cmdshell** .</span><span class="sxs-lookup"><span data-stu-id="8765b-113">For example, the **xp_cmdshell** extended stored procedure can be disabled or enabled using the SAC tool.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8765b-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="8765b-114">See Also</span></span>  
 <span data-ttu-id="8765b-115">[Проблемы обновления ядро СУБД](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="8765b-115">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="8765b-116">Советник по переходу SQL Server 2014 &#91;New&#93;</span><span class="sxs-lookup"><span data-stu-id="8765b-116">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
