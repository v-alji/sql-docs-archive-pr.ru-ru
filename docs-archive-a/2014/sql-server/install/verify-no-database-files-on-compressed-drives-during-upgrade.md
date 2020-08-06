---
title: Убедитесь, что в процессе обновления нет файлов базы данных на сжатых дисках | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- compressed drives [SQL Server]
ms.assetid: 63be6853-c54a-42b2-ae1a-db2175f1d28e
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 9c04f7890ba8d8efe64afaf11b922af156c5de46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655531"
---
# <a name="verify-that-no-database-files-are-on-compressed-drives-during-the-upgrade-process"></a><span data-ttu-id="091bf-102">Убедитесь, что во время процесса обновления на сжатых дисках отсутствуют файлы базы данных</span><span class="sxs-lookup"><span data-stu-id="091bf-102">Verify that no database files are on compressed drives during the upgrade process</span></span>
  <span data-ttu-id="091bf-103">Помощник по обновлению обнаружил файлы базы данных на сжатом диске.</span><span class="sxs-lookup"><span data-stu-id="091bf-103">Upgrade Advisor detected database files on a compressed drive.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="091bf-104">не может создавать или обновлять базы данных на сжатых дисках.</span><span class="sxs-lookup"><span data-stu-id="091bf-104">cannot create or upgrade databases on compressed drives.</span></span>  
  
## <a name="component"></a><span data-ttu-id="091bf-105">Компонент</span><span class="sxs-lookup"><span data-stu-id="091bf-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="091bf-106">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="091bf-106">Corrective Action</span></span>  
 <span data-ttu-id="091bf-107">При установке [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] выберите несжатый диск для системных баз данных, а также убедитесь, что обновляемые базы данных не находятся на сжатых дисках.</span><span class="sxs-lookup"><span data-stu-id="091bf-107">When you install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], select an uncompressed drive for system databases and verify that databases to be upgraded are not on compressed drives.</span></span> <span data-ttu-id="091bf-108">Однако обратите внимание, что после обновления базы данных можно записывать на диск со сжатой файловой системой NTFS базы данных и вторичные файловые группы, доступные только для чтения.</span><span class="sxs-lookup"><span data-stu-id="091bf-108">However, note that after the database has been upgraded, you can put read-only databases and read-only secondary filegroups on an NTFS compressed file system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="091bf-109">См. также:</span><span class="sxs-lookup"><span data-stu-id="091bf-109">See Also</span></span>  
 <span data-ttu-id="091bf-110">[Проблемы обновления ядро СУБД](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="091bf-110">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="091bf-111">Советник по переходу SQL Server 2014 &#91;New&#93;</span><span class="sxs-lookup"><span data-stu-id="091bf-111">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
