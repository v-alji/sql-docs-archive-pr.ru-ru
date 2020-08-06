---
title: Табличные указания в определениях индексированных представлений игнорируются в режиме совместимости 80 и не разрешены в режиме 90 или более поздней версии | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- query hints [SQL Server]
- indexed views [SQL Server], query hints
ms.assetid: 405dfcff-a3a6-4e6d-a53a-ed77bbacdd13
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cf3cb2b06dc477d93c8fd42312b4835ded42afb4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735842"
---
# <a name="table-hints-in-indexed-view-definitions-are-ignored-in-80-compatibility-mode-and-are-not-allowed-in-90-mode-or-later"></a><span data-ttu-id="9f960-102">Табличные указания в определении индексированных представлений в режиме совместимости 80 не учитываются, а в режиме совместимости 90 недопустимы</span><span class="sxs-lookup"><span data-stu-id="9f960-102">Table hints in indexed view definitions are ignored in 80 compatibility mode and are not allowed in 90 mode or later</span></span>
  <span data-ttu-id="9f960-103">Табличные указания в определении индексированных представлений не разрешены в режиме совместимости 90 и выше.</span><span class="sxs-lookup"><span data-stu-id="9f960-103">Table hints in the definitions of indexed views are not permitted in the compatibility mode of 90 or later.</span></span> <span data-ttu-id="9f960-104">Дополнительные сведения см. в следующих разделах [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] электронной документации: «проектирование индексированных представлений», «создание индексированных представлений» и «указание запроса ( [!INCLUDE[tsql](../../includes/tsql-md.md)] )».</span><span class="sxs-lookup"><span data-stu-id="9f960-104">For more information, see the following topics in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online: "Designing Indexed Views," "Creating Indexed Views," and "Query Hint ([!INCLUDE[tsql](../../includes/tsql-md.md)])."</span></span>  
  
## <a name="component"></a><span data-ttu-id="9f960-105">Компонент</span><span class="sxs-lookup"><span data-stu-id="9f960-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="9f960-106">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="9f960-106">Corrective Action</span></span>  
 <span data-ttu-id="9f960-107">Табличные указания должны быть удалены из определений индексированных представлений.</span><span class="sxs-lookup"><span data-stu-id="9f960-107">Table hints must be removed from the definitions of indexed views.</span></span> <span data-ttu-id="9f960-108">Независимо от используемого режима совместимости рекомендуется провести тестирование приложения.</span><span class="sxs-lookup"><span data-stu-id="9f960-108">Regardless of which compatibility mode is used, we recommend that you test the application.</span></span> <span data-ttu-id="9f960-109">Проверка приложения позволяет убедиться, что оно работает согласно ожиданиям при создании индексированных представлений, их обновлении и доступе к ним, включая сопоставление индексированных представлений с запросами.</span><span class="sxs-lookup"><span data-stu-id="9f960-109">By testing the application, you can make sure it performs as expected when indexed views are created, updated, and accessed, including when indexed views are matched to queries.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f960-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="9f960-110">See Also</span></span>  
 <span data-ttu-id="9f960-111">[Проблемы обновления ядро СУБД](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="9f960-111">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="9f960-112">Советник по переходу SQL Server 2014 &#91;New&#93;</span><span class="sxs-lookup"><span data-stu-id="9f960-112">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
