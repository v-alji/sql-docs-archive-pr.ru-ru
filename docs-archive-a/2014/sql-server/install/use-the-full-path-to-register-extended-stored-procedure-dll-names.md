---
title: Использовать полный путь для регистрации имен библиотек DLL расширенных хранимых процедур | Документация Майкрософт
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- registering DLL names
- extended stored procedures [SQL Server], registering
- DLL names [SQL Server]
- full path DLL name registration [SQL Server]
ms.assetid: f648d57c-af32-4c71-9882-47b6766f3c2b
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 5ec4ef3fc2e0f2c4834ffa7479a00562ae15d07f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87732262"
---
# <a name="use-the-full-path-to-register-extended-stored-procedure-dll-names"></a><span data-ttu-id="22f80-102">Используйте полный путь для регистрации имен DLL-библиотек расширенных хранимых процедур</span><span class="sxs-lookup"><span data-stu-id="22f80-102">Use the full path to register extended stored procedure DLL names</span></span>
  <span data-ttu-id="22f80-103">Расширенные хранимые процедуры, ранее зарегистрированные без указания полного пути к DLL, могут не работать в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="22f80-103">Extended stored procedures that were previously registered without the full path for the DLL name may not work in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="component"></a><span data-ttu-id="22f80-104">Компонент</span><span class="sxs-lookup"><span data-stu-id="22f80-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="22f80-105">Описание</span><span class="sxs-lookup"><span data-stu-id="22f80-105">Description</span></span>  
 <span data-ttu-id="22f80-106">Расширенные хранимые процедуры, ранее зарегистрированные без указания полного пути к DLL-библиотеке, могут не работать после обновления.</span><span class="sxs-lookup"><span data-stu-id="22f80-106">Extended stored procedures that were previously registered without the full path for the DLL name may not work after you upgrade.</span></span> <span data-ttu-id="22f80-107">Это происходит, потому что прежний каталог BINN в процессе обновления не добавляется к новому пути.</span><span class="sxs-lookup"><span data-stu-id="22f80-107">This is because the old BINN directory is not added to the new path during the upgrade process.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="22f80-108">может не найти расширенные хранимые процедуры.</span><span class="sxs-lookup"><span data-stu-id="22f80-108">may not be able to locate the extended stored procedures.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="22f80-109">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="22f80-109">Corrective Action</span></span>  
 <span data-ttu-id="22f80-110">Перед обновлением выполните следующие шаги для каждой расширенной хранимой процедуры, не зарегистрированной с использованием полного пути.</span><span class="sxs-lookup"><span data-stu-id="22f80-110">Before you upgrade, follow these steps for each extended stored procedure that was not registered with a full path name:</span></span>  
  
1.  <span data-ttu-id="22f80-111">Чтобы удалить расширенную хранимую процедуру, выполните хранимую процедуру sp_dropextendedproc.</span><span class="sxs-lookup"><span data-stu-id="22f80-111">Run sp_dropextendedproc to remove the extended stored procedure.</span></span>  
  
2.  <span data-ttu-id="22f80-112">Чтобы зарегистрировать расширенную хранимую процедуру с указанием полного пути, выполните хранимую процедуру sp_addextendedproc.</span><span class="sxs-lookup"><span data-stu-id="22f80-112">Run sp_addextendedproc to register the extended stored procedure with the full path name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22f80-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="22f80-113">See Also</span></span>  
 <span data-ttu-id="22f80-114">[Проблемы обновления ядро СУБД](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="22f80-114">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="22f80-115">Советник по переходу SQL Server 2014 &#91;New&#93;</span><span class="sxs-lookup"><span data-stu-id="22f80-115">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
