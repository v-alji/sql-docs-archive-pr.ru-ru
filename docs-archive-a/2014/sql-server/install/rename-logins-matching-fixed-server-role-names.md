---
title: Переименовывать имена входа, совпадающие с именами предопределенных ролей сервера | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- user-defined login names [SQL Server]
- fixed server roles [SQL Server]
- renamed logins [SQL Server]
- logins [SQL Server], names
ms.assetid: 10a1d77c-3153-474f-a6a0-969556794467
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 296ae4d4051e79e3c5d3bc158ef3e87c9164ecd3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735869"
---
# <a name="rename-logins-matching-fixed-server-role-names"></a><span data-ttu-id="456ca-102">Переименование имен входа, которые совпадают с именами предопределенной роли сервера</span><span class="sxs-lookup"><span data-stu-id="456ca-102">Rename logins matching fixed server role names</span></span>
  <span data-ttu-id="456ca-103">Помощник по обновлению обнаружил одно или несколько определяемых пользователем имен входа, совпадающих с именами предопределенных ролей сервера.</span><span class="sxs-lookup"><span data-stu-id="456ca-103">Upgrade Advisor detected one or more user-defined login names that match the names of fixed server roles.</span></span> <span data-ttu-id="456ca-104">Имена предопределенных ролей сервера зарезервированы.</span><span class="sxs-lookup"><span data-stu-id="456ca-104">Fixed server role names are reserved.</span></span> <span data-ttu-id="456ca-105">Прежде чем производить обновление, измените имя входа.</span><span class="sxs-lookup"><span data-stu-id="456ca-105">Rename the login before you upgrade.</span></span>  
  
## <a name="component"></a><span data-ttu-id="456ca-106">Компонент</span><span class="sxs-lookup"><span data-stu-id="456ca-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="456ca-107">Описание</span><span class="sxs-lookup"><span data-stu-id="456ca-107">Description</span></span>  
 <span data-ttu-id="456ca-108">Следующие имена предопределенных ролей сервера зарезервированы и не могут быть использованы как пользовательские имена входа.</span><span class="sxs-lookup"><span data-stu-id="456ca-108">The following fixed server role names are reserved and cannot be used as user-defined login names.</span></span>  
  
-   <span data-ttu-id="456ca-109">**sysadmin**</span><span class="sxs-lookup"><span data-stu-id="456ca-109">**sysadmin**</span></span>  
  
-   <span data-ttu-id="456ca-110">**serveradmin**</span><span class="sxs-lookup"><span data-stu-id="456ca-110">**serveradmin**</span></span>  
  
-   <span data-ttu-id="456ca-111">**setupadmin**</span><span class="sxs-lookup"><span data-stu-id="456ca-111">**setupadmin**</span></span>  
  
-   <span data-ttu-id="456ca-112">**securityadmin**</span><span class="sxs-lookup"><span data-stu-id="456ca-112">**securityadmin**</span></span>  
  
-   <span data-ttu-id="456ca-113">**processadmin**</span><span class="sxs-lookup"><span data-stu-id="456ca-113">**processadmin**</span></span>  
  
-   <span data-ttu-id="456ca-114">**dbcreator**</span><span class="sxs-lookup"><span data-stu-id="456ca-114">**dbcreator**</span></span>  
  
-   <span data-ttu-id="456ca-115">**diskadmin**</span><span class="sxs-lookup"><span data-stu-id="456ca-115">**diskadmin**</span></span>  
  
-   <span data-ttu-id="456ca-116">**bulkadmin**</span><span class="sxs-lookup"><span data-stu-id="456ca-116">**bulkadmin**</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="456ca-117">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="456ca-117">Corrective Action</span></span>  
 <span data-ttu-id="456ca-118">Прежде чем производить обновление, выполните следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="456ca-118">Before upgrading, perform the following steps:</span></span>  
  
1.  <span data-ttu-id="456ca-119">Зарегистрируйте идентификаторы безопасности (SID) имен входа, выполнив следующую инструкцию.</span><span class="sxs-lookup"><span data-stu-id="456ca-119">Record the security identifiers (SIDs) of the logins by executing the following statement.</span></span>  
  
    ```  
    SELECT name, sid   
    FROM master.dbo.syslogins   
    WHERE name IN('sysadmin', 'serveradmin','setupadmin', 'securityadmin','processadmin', 'dbcreator','diskadmin','bulkadmin')  
    ```  
  
2.  <span data-ttu-id="456ca-120">Удалите имена входа.</span><span class="sxs-lookup"><span data-stu-id="456ca-120">Drop the logins.</span></span>  
  
3.  <span data-ttu-id="456ca-121">Для создания новых имен входа используйте системную процедуру **sp_addlogin** .</span><span class="sxs-lookup"><span data-stu-id="456ca-121">Use the **sp_addlogin** system procedure to create new logins.</span></span> <span data-ttu-id="456ca-122">Укажите идентификатор безопасности, возвращенный на шаге 1 в параметре \*\* \@ SID\*\* для каждого соответствующего имени входа.</span><span class="sxs-lookup"><span data-stu-id="456ca-122">Specify the SID returned in step 1 in the **\@sid** parameter for each corresponding login.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="456ca-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="456ca-123">See Also</span></span>  
 <span data-ttu-id="456ca-124">[Проблемы обновления ядро СУБД](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="456ca-124">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="456ca-125">Советник по переходу SQL Server 2014 &#91;New&#93;</span><span class="sxs-lookup"><span data-stu-id="456ca-125">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
