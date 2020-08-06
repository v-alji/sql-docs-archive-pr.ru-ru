---
title: Предоставление доступа к объекту базы данных | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- granting access to database objects
ms.assetid: a44d9bbf-f58e-4734-b7f4-eb3b492b777b
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 22bd0bb1f01e59ec30f7cf1bbf128c890d3d5d64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667990"
---
# <a name="granting-access-to-a-database-object"></a><span data-ttu-id="de6ad-102">Предоставление доступа к объекту базы данных</span><span class="sxs-lookup"><span data-stu-id="de6ad-102">Granting Access to a Database Object</span></span>
  <span data-ttu-id="de6ad-103"> Будучи администратором, можно выполнять инструкцию SELECT из таблицы **Products** и представления **vw_Names**, а также выполнять процедуру **pr_Names**; однако Мэри всего этого не может.</span><span class="sxs-lookup"><span data-stu-id="de6ad-103">As an administrator, you can execute the SELECT from the **Products** table and the **vw_Names** view, and execute the **pr_Names** procedure; however, Mary cannot.</span></span> <span data-ttu-id="de6ad-104">Чтобы предоставить Mary необходимые разрешения, воспользуйтесь инструкцией GRANT.</span><span class="sxs-lookup"><span data-stu-id="de6ad-104">To grant Mary the necessary permissions, use the GRANT statement.</span></span>  
  
### <a name="procedure-title"></a><span data-ttu-id="de6ad-105">Описание процедуры</span><span class="sxs-lookup"><span data-stu-id="de6ad-105">Procedure Title</span></span>  
  
1.  <span data-ttu-id="de6ad-106">Выполните следующую инструкцию, чтобы предоставить `Mary` разрешение на `EXECUTE` для хранимой процедуры `pr_Names` .</span><span class="sxs-lookup"><span data-stu-id="de6ad-106">Execute the following statement to give `Mary` the `EXECUTE` permission for the `pr_Names` stored procedure.</span></span>  
  
    ```  
    GRANT EXECUTE ON pr_Names TO Mary;  
    GO  
    ```  
  
 <span data-ttu-id="de6ad-107">В данном сценарии Mary имеет доступ только к таблице **Products** посредством хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="de6ad-107">In this scenario, Mary can only access the **Products** table by using the stored procedure.</span></span> <span data-ttu-id="de6ad-108">Если Mary нужно выполнять инструкцию SELECT к представлению, нужно выполнить инструкцию `GRANT SELECT ON vw_Names TO Mary`.</span><span class="sxs-lookup"><span data-stu-id="de6ad-108">If you want Mary to be able to execute a SELECT statement against the view, then you must also execute `GRANT SELECT ON vw_Names TO Mary`.</span></span> <span data-ttu-id="de6ad-109">Чтобы удалить доступ к объектам базы данных, воспользуйтесь инструкцией REVOKE.</span><span class="sxs-lookup"><span data-stu-id="de6ad-109">To remove access to database objects, use the REVOKE statement.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="de6ad-110">Если таблицей, представлением или хранимой процедурой не владеет та же схема, процесс предоставления прав становится более сложным.</span><span class="sxs-lookup"><span data-stu-id="de6ad-110">If the table, the view, and the stored procedure are not owned by the same schema, granting permissions becomes more complex.</span></span>  
  
## <a name="about-grant"></a><span data-ttu-id="de6ad-111">Об инструкции GRANT</span><span class="sxs-lookup"><span data-stu-id="de6ad-111">About GRANT</span></span>  
 <span data-ttu-id="de6ad-112">Нужно иметь разрешение на EXECUTE, чтобы выполнить хранимую процедуру.</span><span class="sxs-lookup"><span data-stu-id="de6ad-112">You must have EXECUTE permission to execute a stored procedure.</span></span> <span data-ttu-id="de6ad-113">Нужно иметь разрешения на SELECT, INSERT, UPDATE и DELETE, чтобы получить доступ к данным и изменять их.</span><span class="sxs-lookup"><span data-stu-id="de6ad-113">You must have SELECT, INSERT, UPDATE, and DELETE permissions to access and change data.</span></span> <span data-ttu-id="de6ad-114">Инструкция GRANT также используется для других разрешений, например для разрешений на создание таблиц.</span><span class="sxs-lookup"><span data-stu-id="de6ad-114">The GRANT statement is also used for other permissions, such as permission to create tables.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="de6ad-115">Следующая задача занятия</span><span class="sxs-lookup"><span data-stu-id="de6ad-115">Next Task in Lesson</span></span>  
 [<span data-ttu-id="de6ad-116">Сводка. Настройка разрешений на объекты базы данных</span><span class="sxs-lookup"><span data-stu-id="de6ad-116">Summary: Configuring Permissions on Database Objects</span></span>](lesson-2-5-summary-configuring-permissions-on-database-objects.md)  
  
## <a name="see-also"></a><span data-ttu-id="de6ad-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="de6ad-117">See Also</span></span>  
 <span data-ttu-id="de6ad-118">[GRANT (Transact-SQL)](/sql/t-sql/statements/grant-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="de6ad-118">[GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) </span></span>  
 [<span data-ttu-id="de6ad-119">REVOKE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="de6ad-119">REVOKE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/revoke-transact-sql)  
  
  
