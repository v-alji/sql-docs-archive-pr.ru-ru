---
title: Разрешения гостя для пользовательских баз данных | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 540f1c6d-df51-497e-958a-3a0f429d2920
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 344c5fd0639876998f1585c32fac5f7599f664e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655698"
---
# <a name="guest-permissions-on-user-databases"></a><span data-ttu-id="24abd-102">Разрешения гостя для пользовательских баз данных</span><span class="sxs-lookup"><span data-stu-id="24abd-102">Guest Permissions on User Databases</span></span>
  <span data-ttu-id="24abd-103">Это правило определяет, имеет ли пользователь «Гость» разрешение на доступ к базе данных.</span><span class="sxs-lookup"><span data-stu-id="24abd-103">This rule determines whether the guest user has permission to access the database.</span></span> <span data-ttu-id="24abd-104">Это правило применяется только к пользовательским базам данных.</span><span class="sxs-lookup"><span data-stu-id="24abd-104">This rule applies to user databases only.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="24abd-105">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="24abd-105">Best Practices Recommendations</span></span>  
 <span data-ttu-id="24abd-106">Отмените разрешения гостя для доступа к базе данных, если оно не требуется.</span><span class="sxs-lookup"><span data-stu-id="24abd-106">Revoke the guest user permission to access the database if it is not required.</span></span>  
  
 <span data-ttu-id="24abd-107">Пользователь guest не может быть удален, однако пользователь guest может быть отключен путем отмены его разрешения на CONNECT с помощью инструкции REVOKE CONNECT FROM GUEST в базе данных, отличной от master, tempdb или msdb.</span><span class="sxs-lookup"><span data-stu-id="24abd-107">The guest user cannot be dropped, but guest user can be disabled by revoking its CONNECT permission by executing REVOKE CONNECT FROM GUEST within any database other than master, tempdb, or msdb.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="24abd-108">Дополнительные сведения см. в разделе</span><span class="sxs-lookup"><span data-stu-id="24abd-108">For More Information</span></span>  
 [<span data-ttu-id="24abd-109">Обеспечение безопасности SQL Server</span><span class="sxs-lookup"><span data-stu-id="24abd-109">Securing SQL Server</span></span>](../security/securing-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="24abd-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="24abd-110">See Also</span></span>  
 [<span data-ttu-id="24abd-111">Наблюдение с помощью управления на основе политик и принудительное применение рекомендаций с помощью управления на основе политик</span><span class="sxs-lookup"><span data-stu-id="24abd-111">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
