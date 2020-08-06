---
title: Иерархия разрешений (ядро СУБД) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.server.permissions.f1--May use common.permissions
helpviewer_keywords:
- security [SQL Server], denying access
- hierarchies [SQL Server], permissions
- securables [SQL Server]
- security [SQL Server], permissions
- permissions [SQL Server], hierarchy
- security [SQL Server], granting access
ms.assetid: f6d20a55-ef03-4e14-85f9-009902889866
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 9a04e5595e509de63b362b31b240e113e635581d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87730374"
---
# <a name="permissions-hierarchy-database-engine"></a><span data-ttu-id="37fd9-102">Иерархия разрешений (компонент Database Engine)</span><span class="sxs-lookup"><span data-stu-id="37fd9-102">Permissions Hierarchy (Database Engine)</span></span>
  <span data-ttu-id="37fd9-103">Компонент [!INCLUDE[ssDE](../../../includes/ssde-md.md)] управляет иерархической коллекцией сущностей, защита которых производится при помощи разрешений.</span><span class="sxs-lookup"><span data-stu-id="37fd9-103">The [!INCLUDE[ssDE](../../../includes/ssde-md.md)] manages a hierarchical collection of entities that can be secured with permissions.</span></span> <span data-ttu-id="37fd9-104">Эти сущности называются *защищаемыми объектами*.</span><span class="sxs-lookup"><span data-stu-id="37fd9-104">These entities are known as *securables*.</span></span> <span data-ttu-id="37fd9-105">Важнейшими защищаемыми компонентами являются серверы и базы данных, однако отдельные разрешения можно задавать на гораздо более глубоком уровне.</span><span class="sxs-lookup"><span data-stu-id="37fd9-105">The most prominent securables are servers and databases, but discrete permissions can be set at a much finer level.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="37fd9-106">регулирует действия участников на защищаемых объектах, проверяя, что им были предоставлены соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="37fd9-106">regulates the actions of principals on securables by verifying that they have been granted appropriate permissions.</span></span>

 <span data-ttu-id="37fd9-107">На следующей иллюстрации показана связь между иерархиями разрешений компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="37fd9-107">The following illustration shows the relationships among the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] permissions hierarchies.</span></span>

 <span data-ttu-id="37fd9-108">![Диаграмма иерархий разрешений в ядре СУБД](../../database-engine/media/wj-security-layers.gif "Диаграмма иерархий разрешений в ядре СУБД")</span><span class="sxs-lookup"><span data-stu-id="37fd9-108">![Diagram of Database Engine permissions hierarchies](../../database-engine/media/wj-security-layers.gif "Diagram of Database Engine permissions hierarchies")</span></span>

## <a name="chart-of-sql-server-permissions"></a><span data-ttu-id="37fd9-109">Диаграмма разрешений SQL Server</span><span class="sxs-lookup"><span data-stu-id="37fd9-109">Chart of SQL Server Permissions</span></span>
 <span data-ttu-id="37fd9-110">Схему плакатного размера всех разрешений компонента [!INCLUDE[ssDE](../../../includes/ssde-md.md)] в формате PDF см. по ссылке [https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf](https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf).</span><span class="sxs-lookup"><span data-stu-id="37fd9-110">For a poster sized chart of all [!INCLUDE[ssDE](../../../includes/ssde-md.md)] permissions in pdf format, see [https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf](https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf).</span></span>

## <a name="working-with-permissions"></a><span data-ttu-id="37fd9-111">Работа с разрешениями</span><span class="sxs-lookup"><span data-stu-id="37fd9-111">Working with Permissions</span></span>
 <span data-ttu-id="37fd9-112">Выполнение различных действий с разрешениями осуществляется при помощи обычных запросов [!INCLUDE[tsql](../../includes/tsql-md.md)] : GRANT, DENY и REVOKE.</span><span class="sxs-lookup"><span data-stu-id="37fd9-112">Permissions can be manipulated with the familiar [!INCLUDE[tsql](../../includes/tsql-md.md)] queries GRANT, DENY, and REVOKE.</span></span> <span data-ttu-id="37fd9-113">Сведения о разрешениях доступны через представления каталога [sys.server_permissions](/sql/relational-databases/system-catalog-views/sys-server-permissions-transact-sql) и [sys.database_permissions](/sql/relational-databases/system-catalog-views/sys-database-permissions-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="37fd9-113">Information about permissions is visible in the [sys.server_permissions](/sql/relational-databases/system-catalog-views/sys-server-permissions-transact-sql) and [sys.database_permissions](/sql/relational-databases/system-catalog-views/sys-database-permissions-transact-sql) catalog views.</span></span> <span data-ttu-id="37fd9-114">Существует также поддержка запроса сведений о разрешениях при помощи встроенных функций.</span><span class="sxs-lookup"><span data-stu-id="37fd9-114">There is also support for querying permissions information by using built-in functions.</span></span>

## <a name="see-also"></a><span data-ttu-id="37fd9-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="37fd9-115">See Also</span></span>
 <span data-ttu-id="37fd9-116">[Обеспечение безопасности SQL Server](securing-sql-server.md) [разрешений &#40;ядро СУБД&#41;](permissions-database-engine.md) субъектов [защищаемых объектов](securables.md) [&#40;ядро СУБД](authentication-access/principals-database-engine.md)&#41;[Grant &#40;transact-sql](/sql/t-sql/statements/grant-transact-sql) [&#41;revoke &#40;transact-SQL&#41;](/sql/t-sql/statements/revoke-transact-sql) [Deny &#40;Transact-SQL&#41;](/sql/t-sql/statements/deny-transact-sql) HAS_PERMS_BY_NAME [&#40;Transact](/sql/t-sql/functions/has-perms-by-name-transact-sql) -SQL&#41;sys. fn_builtin_permissions &#40;Transact [-](/sql/relational-databases/system-functions/sys-fn-builtin-permissions-transact-sql) SQL&#41;sys. server_permissions &#40;Transact-SQL&#41;sys [sys.server_permissions &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-permissions-transact-sql) [. database_permissions &#40;Transact](/sql/relational-databases/system-catalog-views/sys-database-permissions-transact-sql) -SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="37fd9-116">[Securing SQL Server](securing-sql-server.md) [Permissions &#40;Database Engine&#41;](permissions-database-engine.md) [Securables](securables.md) [Principals &#40;Database Engine&#41;](authentication-access/principals-database-engine.md) [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) [REVOKE &#40;Transact-SQL&#41;](/sql/t-sql/statements/revoke-transact-sql) [DENY &#40;Transact-SQL&#41;](/sql/t-sql/statements/deny-transact-sql) [HAS_PERMS_BY_NAME &#40;Transact-SQL&#41;](/sql/t-sql/functions/has-perms-by-name-transact-sql) [sys.fn_builtin_permissions &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-builtin-permissions-transact-sql) [sys.server_permissions &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-permissions-transact-sql) [sys.database_permissions &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-permissions-transact-sql)</span></span>


