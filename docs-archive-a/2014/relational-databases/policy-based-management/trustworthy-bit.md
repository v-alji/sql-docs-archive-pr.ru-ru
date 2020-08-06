---
title: Бит доверия | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 3198188a-2b59-4865-9560-10f760934b8e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 062a63dd52f4641a0ddfcbc20cb9bad3cce6dc61
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657711"
---
# <a name="trustworthy-bit"></a><span data-ttu-id="7cfef-102">Бит доверия</span><span class="sxs-lookup"><span data-stu-id="7cfef-102">Trustworthy Bit</span></span>
  <span data-ttu-id="7cfef-103">Это правило определяет, назначена ли роль базы данных dbo предопределенной роли сервера sysadmin и установлен ли бит доверия базы данных (значение ON).</span><span class="sxs-lookup"><span data-stu-id="7cfef-103">This rule determines whether the dbo role for a database is assigned to the sysadmin fixed server role and the database has its trustworthy bit set to ON.</span></span>  
  
 <span data-ttu-id="7cfef-104">Если эти условия выполняются, привилегированный пользователь базы данных может повысить право доступа до роли sysadmin.</span><span class="sxs-lookup"><span data-stu-id="7cfef-104">If these conditions are met, a privileged database user can elevate privileges to the sysadmin role.</span></span> <span data-ttu-id="7cfef-105">Члены этой роли могут создавать и выполнять небезопасные сборки, которые представляют угрозу для системы.</span><span class="sxs-lookup"><span data-stu-id="7cfef-105">In this role, the user can create and run unsafe assemblies that compromise the system.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="7cfef-106">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="7cfef-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="7cfef-107">Сбросьте бит доверия или отмените разрешения sysadmin из роли базы данных dbo.</span><span class="sxs-lookup"><span data-stu-id="7cfef-107">Turn off the trustworthy bit or revoke sysadmin permissions from the dbo database role.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="7cfef-108">Дополнительные сведения см. в разделе</span><span class="sxs-lookup"><span data-stu-id="7cfef-108">For More Information</span></span>  
 [<span data-ttu-id="7cfef-109">ALTER DATABASE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="7cfef-109">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="7cfef-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="7cfef-110">See Also</span></span>  
 [<span data-ttu-id="7cfef-111">Наблюдение с помощью управления на основе политик и принудительное применение рекомендаций с помощью управления на основе политик</span><span class="sxs-lookup"><span data-stu-id="7cfef-111">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
