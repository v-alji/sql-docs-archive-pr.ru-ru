---
title: INFORMATION_SCHEMA. SCHEMATA возвращает имена схем в базе данных, а не базы данных в экземпляре | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- INFORMATION_SCHEMA.SCHEMATA view
ms.assetid: 4337b643-910d-47d7-bea8-f4052066b9a2
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cb2a34a59bf6257c188210fc7bf2aeacb70f6b7f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668047"
---
# <a name="information_schemaschemata-returns-schema-names-in-a-database-not-databases-in-an-instance"></a><span data-ttu-id="a4d61-102">Представление INFORMATION_SCHEMA.SCHEMATA возвращает имена схем в базе данных, а не баз данных в экземпляре</span><span class="sxs-lookup"><span data-stu-id="a4d61-102">INFORMATION_SCHEMA.SCHEMATA returns schema names in a database, not databases in an instance</span></span>
  <span data-ttu-id="a4d61-103">Помощник по обновлению обнаружил инструкции, в которых используется представление INFORMATION_SCHEMA.SCHEMATA.</span><span class="sxs-lookup"><span data-stu-id="a4d61-103">Upgrade Advisor detected statements that reference the INFORMATION_SCHEMA.SCHEMATA view.</span></span> <span data-ttu-id="a4d61-104">В более ранних версиях [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] это представление возвращало все базы данных в экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a4d61-104">In earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], this view returned all databases in an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a4d61-105">В [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] и последующих версиях представление возвращает все схемы в базе данных.</span><span class="sxs-lookup"><span data-stu-id="a4d61-105">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later, the view returns all schemas in a database.</span></span>  
  
## <a name="component"></a><span data-ttu-id="a4d61-106">Компонент</span><span class="sxs-lookup"><span data-stu-id="a4d61-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="a4d61-107">Описание</span><span class="sxs-lookup"><span data-stu-id="a4d61-107">Description</span></span>  
 <span data-ttu-id="a4d61-108">В более ранних версиях [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] представление INFORMATION_SCHEMA.SCHEMATA возвращало все базы данных в экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a4d61-108">In earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the INFORMATION_SCHEMA.SCHEMATA view returned all databases in an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a4d61-109">Представление возвращает все схемы в базе данных, что соответствует стандарту языка SQL.</span><span class="sxs-lookup"><span data-stu-id="a4d61-109">Now, the view returns all schemas in a database, which complies with the SQL Standard.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="a4d61-110">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="a4d61-110">Corrective Action</span></span>  
 <span data-ttu-id="a4d61-111">Измените приложение, чтобы оно ссылалось на представление каталога **sys. databases** , чтобы возвращались все базы данных в экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a4d61-111">Modify your application to reference the **sys.databases** catalog view to return all databases in an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4d61-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="a4d61-112">See Also</span></span>  
 <span data-ttu-id="a4d61-113">[Проблемы обновления ядро СУБД](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="a4d61-113">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="a4d61-114">Советник по переходу SQL Server 2014 &#91;New&#93;</span><span class="sxs-lookup"><span data-stu-id="a4d61-114">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
