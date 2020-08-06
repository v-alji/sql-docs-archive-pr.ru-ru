---
title: Удаление операций DDL для таблиц inserted и deleted в триггерах DML | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- data definition language [SQL Server]
- DDL statements [SQL Server]
- DML triggers, removing DDL operations
ms.assetid: e49ba7d5-787f-4052-b985-b699195d982b
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 61f7ab78b5ab6251b7f27401d36423ec27141c4e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735913"
---
# <a name="remove-ddl-operations-on-the-inserted-and-deleted-tables-inside-dml-triggers"></a><span data-ttu-id="8cc2a-102">Удалите DDL-операции в таблицах inserted и deleted внутри триггеров DML</span><span class="sxs-lookup"><span data-stu-id="8cc2a-102">Remove DDL operations on the inserted and deleted tables inside DML triggers</span></span>
  <span data-ttu-id="8cc2a-103">Инструкции языка описания данных DDL, такие как CREATE INDEX, не могут быть выполнены для таблиц inserted и deleted в триггерах DML.</span><span class="sxs-lookup"><span data-stu-id="8cc2a-103">Data definition language (DDL) statements, such as CREATE INDEX, cannot be performed on the inserted and deleted tables inside DML triggers.</span></span> <span data-ttu-id="8cc2a-104">Некоторые инструкции языка DDL для таблиц inserted и deleted допускались в более ранних версиях [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8cc2a-104">Some DDL statements on the inserted and deleted tables are permitted in earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="8cc2a-105">Дополнительные сведения см. в разделе «Использование таблиц inserted и deleted» электронной документации по [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8cc2a-105">For more information, see "Using the inserted and deleted Tables" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="component"></a><span data-ttu-id="8cc2a-106">Компонент</span><span class="sxs-lookup"><span data-stu-id="8cc2a-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="8cc2a-107">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="8cc2a-107">Corrective Action</span></span>  
 <span data-ttu-id="8cc2a-108">Удалите любые DDL-операции, которые применяются к вставленным и удаленным таблицам внутри триггеров DML.</span><span class="sxs-lookup"><span data-stu-id="8cc2a-108">Remove any DDL operations that are performed on the inserted and deleted tables inside DML triggers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cc2a-109">См. также:</span><span class="sxs-lookup"><span data-stu-id="8cc2a-109">See Also</span></span>  
 <span data-ttu-id="8cc2a-110">[Проблемы обновления ядро СУБД](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="8cc2a-110">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="8cc2a-111">Советник по переходу SQL Server 2014 &#91;New&#93;</span><span class="sxs-lookup"><span data-stu-id="8cc2a-111">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
