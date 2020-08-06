---
title: Убедитесь, что все файловые группы доступны для записи в процессе обновления | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- filegroups [SQL Server], writeable
- writeable filegroups [SQL Server]
ms.assetid: 2985efc1-4b14-46c3-abbd-a656b159f23c
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 8146efb876bf97c36c549a2b58d104592df611e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751647"
---
# <a name="verify-all-filegroups-are-writeable-during-the-upgrade-process"></a><span data-ttu-id="9ddf0-102">Убедитесь, что все файловые группы доступны для записи во время процесса обновления</span><span class="sxs-lookup"><span data-stu-id="9ddf0-102">Verify all filegroups are writeable during the upgrade process</span></span>
  <span data-ttu-id="9ddf0-103">Помощник по обновлению обнаружил базу данных, содержащую одну или несколько файловых групп, доступных только для чтения.</span><span class="sxs-lookup"><span data-stu-id="9ddf0-103">Upgrade Advisor detected a database that has one or more read-only filegroups.</span></span> <span data-ttu-id="9ddf0-104">Все базы данных в экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] должны содержать файловые группы, доступные для чтения и записи, до начала обновления.</span><span class="sxs-lookup"><span data-stu-id="9ddf0-104">All databases in the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must have filegroups set to READ_WRITE before upgrading.</span></span>  
  
## <a name="component"></a><span data-ttu-id="9ddf0-105">Компонент</span><span class="sxs-lookup"><span data-stu-id="9ddf0-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="9ddf0-106">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="9ddf0-106">Corrective Action</span></span>  
 <span data-ttu-id="9ddf0-107">С помощью инструкции ALTER DATABASE переведите файловые группы в режим READ_WRITE.</span><span class="sxs-lookup"><span data-stu-id="9ddf0-107">Use ALTER DATABASE to set the filegroup to READ_WRITE.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ddf0-108">См. также:</span><span class="sxs-lookup"><span data-stu-id="9ddf0-108">See Also</span></span>  
 <span data-ttu-id="9ddf0-109">[Проблемы обновления ядро СУБД](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="9ddf0-109">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="9ddf0-110">Советник по переходу SQL Server 2014 &#91;New&#93;</span><span class="sxs-lookup"><span data-stu-id="9ddf0-110">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
