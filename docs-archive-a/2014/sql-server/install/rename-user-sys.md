---
title: Переименовать пользователя sys | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- sys user names [SQL Server]
ms.assetid: d622d646-83e4-4b6f-9a21-77b301af04b5
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 3af9d31a54adc5645cab6fcc7104ae7ff27a61b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654753"
---
# <a name="rename-user-sys"></a><span data-ttu-id="118a2-102">Переименуйте пользователя с именем sys</span><span class="sxs-lookup"><span data-stu-id="118a2-102">Rename user sys</span></span>
  <span data-ttu-id="118a2-103">Помощник по обновлению обнаружил в базе данных имя пользователя **sys** .</span><span class="sxs-lookup"><span data-stu-id="118a2-103">Upgrade Advisor detected the user name **sys** in a database.</span></span> <span data-ttu-id="118a2-104">Это имя зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="118a2-104">This name is reserved.</span></span> <span data-ttu-id="118a2-105">Переименуйте пользователя перед обновлением.</span><span class="sxs-lookup"><span data-stu-id="118a2-105">Rename the user before you upgrade.</span></span> <span data-ttu-id="118a2-106">Если пользователь не переименован, то после обновления база данных будет помечена как подозрительная и недоступна до тех пор, пока не будет переведена в режим «в сети».</span><span class="sxs-lookup"><span data-stu-id="118a2-106">If the user is not renamed, the database will be in a suspect state after the upgrade process and will be unavailable until the database is brought online.</span></span>  
  
## <a name="component"></a><span data-ttu-id="118a2-107">Компонент</span><span class="sxs-lookup"><span data-stu-id="118a2-107">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="118a2-108">Описание</span><span class="sxs-lookup"><span data-stu-id="118a2-108">Description</span></span>  
 <span data-ttu-id="118a2-109">Пользователь **sys** зарезервирован.</span><span class="sxs-lookup"><span data-stu-id="118a2-109">User **sys** is reserved.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="118a2-110">Действие по исправлению</span><span class="sxs-lookup"><span data-stu-id="118a2-110">Corrective Action</span></span>  
  
### <a name="before-upgrade-procedure"></a><span data-ttu-id="118a2-111">Процедура перед началом обновления</span><span class="sxs-lookup"><span data-stu-id="118a2-111">Before Upgrade Procedure</span></span>  
 <span data-ttu-id="118a2-112">Перед обновлением в каждой базе данных, содержащей пользователя **sys**, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="118a2-112">Before you upgrade, in each database that contains user **sys**, do the following:</span></span>  
  
1.  <span data-ttu-id="118a2-113">Создайте нового пользователя.</span><span class="sxs-lookup"><span data-stu-id="118a2-113">Create a new user.</span></span>  
  
2.  <span data-ttu-id="118a2-114">Используйте следующие инструкции, чтобы просмотреть все разрешения, предоставленные пользователем **sys** и предоставленные пользователю **sys**.</span><span class="sxs-lookup"><span data-stu-id="118a2-114">Use the following statements to display all permissions that are granted by user **sys** and granted to user **sys**.</span></span>  
  
    ```  
    -- Return permissions granted by user sys.  
    SELECT * FROM sysprotects WHERE grantor = USER_ID('sys')  
    -- Return permissions granted to user sys.  
    SELECT * FROM sysprotects WHERE uid = USER_ID('sys')  
    ```  
  
3.  <span data-ttu-id="118a2-115">Чтобы передать права владения для всех объектов, принадлежащих пользователю **sys** , новому пользователю, воспользуйтесь процедурой **sp_changeobjectowner**.</span><span class="sxs-lookup"><span data-stu-id="118a2-115">To transfer ownership of all objects owned by **sys** to the new user, use **sp_changeobjectowner**.</span></span>  
  
4.  <span data-ttu-id="118a2-116">Удалите пользователя **sys**.</span><span class="sxs-lookup"><span data-stu-id="118a2-116">Drop user **sys**.</span></span>  
  
5.  <span data-ttu-id="118a2-117">Чтобы восстановить первоначальные разрешения, записанные на шаге 2, используйте предложение AS *new_user* инструкции GRANT.</span><span class="sxs-lookup"><span data-stu-id="118a2-117">To restore the original permissions captured in step 2, use the AS *new_user* clause of the GRANT statement.</span></span>  
  
6.  <span data-ttu-id="118a2-118">Измените скрипты, чтобы они ссылались на нового пользователя.</span><span class="sxs-lookup"><span data-stu-id="118a2-118">Modify scripts to reference the new user.</span></span> <span data-ttu-id="118a2-119">Например, в скриптах необходимо изменить все инструкции, подобные `SELECT * FROM sys.my`_`table` , на `SELECT * FROM new_user.my_table`.</span><span class="sxs-lookup"><span data-stu-id="118a2-119">For example, scripts that contain statements such as `SELECT * FROM sys.my`_`table` must be changed to `SELECT * FROM new_user.my_table`.</span></span>  
  
### <a name="after-upgrade-procedure"></a><span data-ttu-id="118a2-120">Процедура после обновления</span><span class="sxs-lookup"><span data-stu-id="118a2-120">After Upgrade Procedure</span></span>  
 <span data-ttu-id="118a2-121">Если пользователь **sys** не был переименован перед обновлением, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="118a2-121">If the user **sys** was not renamed prior to upgrading, do the following:</span></span>  
  
1.  <span data-ttu-id="118a2-122">Выполните инструкцию `ALTER DATABASE db_name SET ONLINE`.</span><span class="sxs-lookup"><span data-stu-id="118a2-122">Execute the statement `ALTER DATABASE db_name SET ONLINE`.</span></span> <span data-ttu-id="118a2-123">База данных перейдет в режим SINGLE_USER.</span><span class="sxs-lookup"><span data-stu-id="118a2-123">The database will be in SINGLE_USER mode.</span></span>  
  
2.  <span data-ttu-id="118a2-124">Выполните все шаги, описанные в разделе «Процедура перед началом обновления».</span><span class="sxs-lookup"><span data-stu-id="118a2-124">Follow all steps in the Before Upgrade Procedure section.</span></span>  
  
3.  <span data-ttu-id="118a2-125">Выполните инструкцию `ALTER DATABASE db_name SET MULTI_USER`.</span><span class="sxs-lookup"><span data-stu-id="118a2-125">Execute the statement `ALTER DATABASE db_name SET MULTI_USER`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="118a2-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="118a2-126">See Also</span></span>  
 <span data-ttu-id="118a2-127">[Проблемы обновления ядро СУБД](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="118a2-127">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="118a2-128">Советник по переходу SQL Server 2014 &#91;New&#93;</span><span class="sxs-lookup"><span data-stu-id="118a2-128">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
