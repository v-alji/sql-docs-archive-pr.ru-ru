---
title: Безопасность на уровне строк | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- row level security described
- row level security
- access control predicates
- security [SQL Server], predicate based access control
- predicate based security
ms.assetid: 7221fa4e-ca4a-4d5c-9f93-1b8a4af7b9e8
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: c67f84723e79b66d0454fb509f2fa9ced03dac7c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730345"
---
# <a name="row-level-security"></a><span data-ttu-id="b1846-102">Безопасность на уровне строк</span><span class="sxs-lookup"><span data-stu-id="b1846-102">Row-Level Security</span></span>
  <span data-ttu-id="b1846-103">Безопасность на уровне строк позволяет пользователям управлять доступом к строкам в таблице базы данных в зависимости от характеристик пользователя, выполняющего запрос (например, членство в группе или контекст выполнения).</span><span class="sxs-lookup"><span data-stu-id="b1846-103">Row-Level Security enables customers to control access to rows in a database table based on the characteristics of the user executing a query (e.g., group membership or execution context).</span></span> <span data-ttu-id="b1846-104">Безопасность на уровне строк теперь доступна в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2016.</span><span class="sxs-lookup"><span data-stu-id="b1846-104">Row-Level Security is now available in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2016.</span></span> <span data-ttu-id="b1846-105">Существующее описание этой функции см. в текущей документации, в разделе [Безопасность на уровне строк](https://msdn.microsoft.com/library/dn765131.aspx) .</span><span class="sxs-lookup"><span data-stu-id="b1846-105">See [Row-Level Security](https://msdn.microsoft.com/library/dn765131.aspx) in the current documentation for the current description of this feature.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1846-106">См. также:</span><span class="sxs-lookup"><span data-stu-id="b1846-106">See Also</span></span>  
 <span data-ttu-id="b1846-107">[Создание политики безопасности &#40;базе данных SQL Azure&#41;](/sql/t-sql/statements/create-security-policy-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b1846-107">[CREATE SECURITY POLICY &#40;Azure SQL Database&#41;](/sql/t-sql/statements/create-security-policy-transact-sql) </span></span>  
 <span data-ttu-id="b1846-108">[ALTER SECURITY POLICY &#40;база данных SQL Azure&#41;](/sql/t-sql/statements/alter-security-policy-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b1846-108">[ALTER SECURITY POLICY &#40;Azure SQL Database&#41;](/sql/t-sql/statements/alter-security-policy-transact-sql) </span></span>  
 <span data-ttu-id="b1846-109">[Удаление политики безопасности &#40;базы данных SQL Azure&#41;](/sql/t-sql/statements/drop-security-policy-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b1846-109">[DROP SECURITY POLICY &#40;Azure SQL Database&#41;](/sql/t-sql/statements/drop-security-policy-transact-sql) </span></span>  
 <span data-ttu-id="b1846-110">[CREATE FUNCTION (Transact-SQL)](/sql/t-sql/statements/create-function-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b1846-110">[CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql) </span></span>  
 <span data-ttu-id="b1846-111">[sys. security_policies &#40;базы данных SQL Azure&#41;](/sql/relational-databases/system-catalog-views/sys-security-policies-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b1846-111">[sys.security_policies &#40;Azure SQL Database&#41;](/sql/relational-databases/system-catalog-views/sys-security-policies-transact-sql) </span></span>  
 <span data-ttu-id="b1846-112">[sys. security_predicates &#40;базы данных SQL Azure&#41;](/sql/relational-databases/system-catalog-views/sys-security-predicates-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b1846-112">[sys.security_predicates &#40;Azure SQL Database&#41;](/sql/relational-databases/system-catalog-views/sys-security-predicates-transact-sql) </span></span>  
 [<span data-ttu-id="b1846-113">Создание определяемых пользователем функций (компонент Database Engine)</span><span class="sxs-lookup"><span data-stu-id="b1846-113">Create User-defined Functions &#40;Database Engine&#41;</span></span>](../user-defined-functions/create-user-defined-functions-database-engine.md)  
  
  
