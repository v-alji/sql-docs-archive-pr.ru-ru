---
title: Невозможно обновить базы данных, которые доступны только для чтения | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- database cannot be upgraded
ms.assetid: 27964211-ea30-4390-b791-dcf225fb9ae7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ba48ed2bd80961a4949dc13f04fed0637ecc27ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87666921"
---
# <a name="read-only-databases-cannot-be-upgraded"></a><span data-ttu-id="4ee55-102">Доступные только для чтения базы данных не могут быть обновлены</span><span class="sxs-lookup"><span data-stu-id="4ee55-102">Read-only databases cannot be upgraded</span></span>
  <span data-ttu-id="4ee55-103">Помощник по обновлению определил, что некоторые базы данных в этом экземпляре служб [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не могут быть обновлены.</span><span class="sxs-lookup"><span data-stu-id="4ee55-103">Upgrade Advisor has determined that some databases on this instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot be upgraded.</span></span>  
  
## <a name="component"></a><span data-ttu-id="4ee55-104">Компонент</span><span class="sxs-lookup"><span data-stu-id="4ee55-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="4ee55-105">Описание</span><span class="sxs-lookup"><span data-stu-id="4ee55-105">Description</span></span>  
 <span data-ttu-id="4ee55-106">Обнаружена база данных, доступная только для чтения.</span><span class="sxs-lookup"><span data-stu-id="4ee55-106">A read-only database has been detected.</span></span> <span data-ttu-id="4ee55-107">Чтобы обновить базу данных, программа установки должна иметь возможность записи в базу данных.</span><span class="sxs-lookup"><span data-stu-id="4ee55-107">To upgrade the database, Setup must be able to write to the database.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="4ee55-108">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="4ee55-108">Corrective Action</span></span>  
 <span data-ttu-id="4ee55-109">Если база данных не используется, используйте [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Диспетчер Enterprise Manager, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] или ИНСТРУКЦИю ALTER DATABASE, чтобы изменить базу данных на чтение и запись.</span><span class="sxs-lookup"><span data-stu-id="4ee55-109">When no one is using the database, use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Enterprise Manager, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], or the ALTER DATABASE statement to change the database to read-write.</span></span> <span data-ttu-id="4ee55-110">Следующая инструкция переводит базу данных в режим чтения и записи.</span><span class="sxs-lookup"><span data-stu-id="4ee55-110">The following statement changes the database to read-write.</span></span>  
  
```  
USE master;  
GO  
ALTER DATABASE <database name>  
SET READ_WRITE;  
GO  
```  
  
 <span data-ttu-id="4ee55-111">Дополнительные сведения об инструкции ALTER DATABASE см. в разделе «ALTER DATABASE ([!INCLUDE[tsql](../../includes/tsql-md.md)])» электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4ee55-111">For more information about the ALTER DATABASE statement, see the "ALTER DATABASE ([!INCLUDE[tsql](../../includes/tsql-md.md)])" topic in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ee55-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="4ee55-112">See Also</span></span>  
 <span data-ttu-id="4ee55-113">[Проблемы обновления ядро СУБД](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="4ee55-113">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="4ee55-114">Советник по переходу SQL Server 2014 &#91;New&#93;</span><span class="sxs-lookup"><span data-stu-id="4ee55-114">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
