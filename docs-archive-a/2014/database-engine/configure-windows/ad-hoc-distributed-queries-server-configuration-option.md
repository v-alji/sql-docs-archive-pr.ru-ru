---
title: Параметр конфигурации сервера "ad hoc distributed queries" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- OPENROWSET function, ad hoc distributed queries option
- Ad Hoc Distributed Queries option
- ad hoc distributed queries
- 7415 (Database Engine Error)
- OPENDATASOURCE function, ad hoc distributed queries option
- ad hoc access
ms.assetid: 5b982015-e196-44c3-83b8-275fb9d769b2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d07b3c038597916cdaf026e24e90aab9d6b61616
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654497"
---
# <a name="ad-hoc-distributed-queries-server-configuration-option"></a><span data-ttu-id="1137b-102">Параметр конфигурации сервера «ad hoc distributed queries»</span><span class="sxs-lookup"><span data-stu-id="1137b-102">ad hoc distributed queries Server Configuration Option</span></span>
  <span data-ttu-id="1137b-103">По умолчанию [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не разрешает нерегламентированные распределенные запросы, использующие операторы OPENROWSET и OPENDATASOURCE.</span><span class="sxs-lookup"><span data-stu-id="1137b-103">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not allow ad hoc distributed queries using OPENROWSET and OPENDATASOURCE.</span></span> <span data-ttu-id="1137b-104">Если этот параметр равен 1, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] допускает выполнение нерегламентированных распределенных запросов.</span><span class="sxs-lookup"><span data-stu-id="1137b-104">When this option is set to 1, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] allows ad hoc access.</span></span> <span data-ttu-id="1137b-105">Если этот параметр не задан или равен 0, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] не разрешает нерегламентированный доступ.</span><span class="sxs-lookup"><span data-stu-id="1137b-105">When this option is not set or is set to 0, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not allow ad hoc access.</span></span>  
  
 <span data-ttu-id="1137b-106">В нерегламентированных распределенных запросах с помощью функций OPENROWSET и OPENDATASOURCE осуществляется подключение к удаленным источникам данных, использующим OLE DB.</span><span class="sxs-lookup"><span data-stu-id="1137b-106">Ad hoc distributed queries use the OPENROWSET and OPENDATASOURCE functions to connect to remote data sources that use OLE DB.</span></span> <span data-ttu-id="1137b-107">Функции OPENROWSET и OPENDATASOURCE должны использоваться с теми источниками данных OLE DB, обращения к которым происходят нечасто.</span><span class="sxs-lookup"><span data-stu-id="1137b-107">OPENROWSET and OPENDATASOURCE should be used only to reference OLE DB data sources that are accessed infrequently.</span></span> <span data-ttu-id="1137b-108">Для источников данных, к которым обращение производится более чем несколько раз, определите связанный сервер.</span><span class="sxs-lookup"><span data-stu-id="1137b-108">For any data sources that will be accessed more than several times, define a linked server.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1137b-109">Разрешение использования нерегламентированных имен означает, что любой пользователь, прошедший проверку подлинности при входе в [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , будет иметь доступ к поставщику.</span><span class="sxs-lookup"><span data-stu-id="1137b-109">Enabling the use of ad hoc names means that any authenticated login to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can access the provider.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="1137b-110">следует включить эту функцию для поставщиков, любой локальный доступ к которым не представляет опасности.</span><span class="sxs-lookup"><span data-stu-id="1137b-110">administrators should enable this feature for providers that are safe to be accessed by any local login.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1137b-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="1137b-111">Remarks</span></span>  
 <span data-ttu-id="1137b-112">Попытка установки нерегламентированного соединения без включенной функции **Нерегламентированные распределенные запросы** приведет к ошибке. Сообщение 7415, уровень 16, состояние 1, строка 1</span><span class="sxs-lookup"><span data-stu-id="1137b-112">Attempting to make an ad hoc connection with **Ad Hoc Distributed Queries** not enabled results in error: Msg 7415, Level 16, State 1, Line 1</span></span>  
  
 <span data-ttu-id="1137b-113">Нерегламентированный доступ к поставщику OLE DB «Microsoft.ACE.OLEDB.12.0» запрещен.</span><span class="sxs-lookup"><span data-stu-id="1137b-113">Ad hoc access to OLE DB provider 'Microsoft.ACE.OLEDB.12.0' has been denied.</span></span> <span data-ttu-id="1137b-114">К данному поставщику доступ необходимо производить через связанный сервер.</span><span class="sxs-lookup"><span data-stu-id="1137b-114">You must access this provider through a linked server.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="1137b-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="1137b-115">Examples</span></span>  
 <span data-ttu-id="1137b-116">Следующий пример включает распределенные нерегламентированные запросы и выполняет запрос к серверу `Seattle1` с использованием функции `OPENROWSET` .</span><span class="sxs-lookup"><span data-stu-id="1137b-116">The following example enables ad hoc distributed queries and then queries a server named `Seattle1` using the `OPENROWSET` function.</span></span>  
  
```  
sp_configure 'show advanced options', 1;  
RECONFIGURE;  
sp_configure 'Ad Hoc Distributed Queries', 1;  
RECONFIGURE;  
GO  
  
SELECT a.*  
FROM OPENROWSET('SQLNCLI', 'Server=Seattle1;Trusted_Connection=yes;',  
     'SELECT GroupName, Name, DepartmentID  
      FROM AdventureWorks2012.HumanResources.Department  
      ORDER BY GroupName, Name') AS a;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="1137b-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="1137b-117">See Also</span></span>  
 <span data-ttu-id="1137b-118">[Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1137b-118">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="1137b-119">[Связанные серверы (компонент Database Engine)](../../relational-databases/linked-servers/linked-servers-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="1137b-119">[Linked Servers &#40;Database Engine&#41;](../../relational-databases/linked-servers/linked-servers-database-engine.md) </span></span>  
 <span data-ttu-id="1137b-120">[OPENROWSET (Transact-SQL)](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1137b-120">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="1137b-121">[OPENDATASOURCE (Transact-SQL)](/sql/t-sql/functions/opendatasource-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1137b-121">[OPENDATASOURCE &#40;Transact-SQL&#41;](/sql/t-sql/functions/opendatasource-transact-sql) </span></span>  
 [<span data-ttu-id="1137b-122">sp_addlinkedserver (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="1137b-122">sp_addlinkedserver &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql)  
  
  
