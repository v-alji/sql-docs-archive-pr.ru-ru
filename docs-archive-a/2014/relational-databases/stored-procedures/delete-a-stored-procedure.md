---
title: Удаление хранимой процедуры | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- removing stored procedures
- stored procedures [SQL Server], deleting
- deleting stored procedures
ms.assetid: 232dbf4d-392a-406f-af3a-579518cd8e46
author: stevestein
ms.author: sstein
ms.openlocfilehash: 418e68d4bb7c6ba6632767a554aea72e85726840
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667617"
---
# <a name="delete-a-stored-procedure"></a><span data-ttu-id="f14e8-102">Удаление хранимой процедуры</span><span class="sxs-lookup"><span data-stu-id="f14e8-102">Delete a Stored Procedure</span></span>
    
##  <a name="this-topic-describes-how-to-delete-a-stored-procedure-in-sscurrent-by-using-ssmanstudiofull-or-tsql"></a><a name="Top"></a> <span data-ttu-id="f14e8-103">В этом разделе описывается, как удалить хранимую процедуру [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] при помощи среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f14e8-103">This topic describes how to delete a stored procedure in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
-   <span data-ttu-id="f14e8-104">**Перед началом работы**  [Ограничения](#Restrictions), [Безопасность](#Security)</span><span class="sxs-lookup"><span data-stu-id="f14e8-104">**Before you begin:**  [Limitations and Restrictions](#Restrictions), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="f14e8-105">**Удаление хранимой процедуры с использованием:**  [среды SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="f14e8-105">**To delete a procedure, using:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f14e8-106">Перед началом</span><span class="sxs-lookup"><span data-stu-id="f14e8-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f14e8-107">Ограничения</span><span class="sxs-lookup"><span data-stu-id="f14e8-107">Limitations and Restrictions</span></span>  
 <span data-ttu-id="f14e8-108">Удаление процедуры может вызвать ошибку в зависимых объектах и в скриптах, если эти объекты и скрипты не обновляются для отражения удаления процедуры.</span><span class="sxs-lookup"><span data-stu-id="f14e8-108">Deleting a procedure can cause dependent objects and scripts to fail when the objects and scripts are not updated to reflect the removal of the procedure.</span></span> <span data-ttu-id="f14e8-109">Тем не менее, если вместо удаленной создать другую хранимую процедуру с тем же именем и параметрами, хранимые процедуры, которые на нее ссылаются, будут обрабатываться успешно.</span><span class="sxs-lookup"><span data-stu-id="f14e8-109">However, if a new procedure of the same name and the same parameters is created to replace the one that was deleted, other objects that reference it will still process successfully.</span></span> <span data-ttu-id="f14e8-110">Дополнительные сведения см. в разделе [Просмотр зависимостей хранимой процедуры](view-the-dependencies-of-a-stored-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="f14e8-110">For more information, see [View the Dependencies of a Stored Procedure](view-the-dependencies-of-a-stored-procedure.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f14e8-111">безопасность</span><span class="sxs-lookup"><span data-stu-id="f14e8-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f14e8-112">Permissions</span><span class="sxs-lookup"><span data-stu-id="f14e8-112">Permissions</span></span>  
 <span data-ttu-id="f14e8-113">Необходимо разрешение ALTER на схему, которой принадлежит процедура, или разрешение CONTROL на процедуру.</span><span class="sxs-lookup"><span data-stu-id="f14e8-113">Requires ALTER permission on the schema to which the procedure belongs, or CONTROL permission on the procedure.</span></span>  
  
##  <a name="how-to-delete-a-stored-procedure"></a><a name="Procedures"></a> <span data-ttu-id="f14e8-114">Удаление хранимой процедуры</span><span class="sxs-lookup"><span data-stu-id="f14e8-114">How to Delete a Stored Procedure</span></span>  
 <span data-ttu-id="f14e8-115">Можно использовать один из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="f14e8-115">You can use one of the following:</span></span>  
  
-   [<span data-ttu-id="f14e8-116">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f14e8-116">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="f14e8-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f14e8-117">Transact-SQL</span></span>](#TsqlProcedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f14e8-118">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f14e8-118">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="f14e8-119">**Удаление процедуры в обозревателе объектов**</span><span class="sxs-lookup"><span data-stu-id="f14e8-119">**To delete a procedure in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="f14e8-120">В обозревателе объектов подключитесь к экземпляру [!INCLUDE[ssDE](../../includes/ssde-md.md)] и разверните его.</span><span class="sxs-lookup"><span data-stu-id="f14e8-120">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="f14e8-121">Последовательно разверните узел **Базы данных**, базу данных, которой принадлежит процедура, и узел **Программирование**.</span><span class="sxs-lookup"><span data-stu-id="f14e8-121">Expand **Databases**, expand the database in which the procedure belongs, and then expand **Programmability**.</span></span>  
  
3.  <span data-ttu-id="f14e8-122">Разверните **Хранимые процедуры**, щелкните правой кнопкой мыши удаляемую процедуру, затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="f14e8-122">Expand **Stored Procedures**, right-click the procedure to remove, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="f14e8-123">Для просмотра объектов, зависящих от хранимой процедуры, нажмите **Показать зависимости**.</span><span class="sxs-lookup"><span data-stu-id="f14e8-123">To view objects that depend on the procedure, click **Show Dependencies**.</span></span>  
  
5.  <span data-ttu-id="f14e8-124">Подтвердите, что выбрана нужная процедура, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f14e8-124">Confirm the correct procedure is selected, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="f14e8-125">Удалите ссылки на процедуру из зависимых объектов и скриптов.</span><span class="sxs-lookup"><span data-stu-id="f14e8-125">Remove references to the procedure from any dependent objects and scripts.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f14e8-126">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f14e8-126">Using Transact-SQL</span></span>  
 <span data-ttu-id="f14e8-127">**Удаление процедуры в редакторе запросов**</span><span class="sxs-lookup"><span data-stu-id="f14e8-127">**To delete a procedure in Query Editor**</span></span>  
  
1.  <span data-ttu-id="f14e8-128">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)] и разверните его.</span><span class="sxs-lookup"><span data-stu-id="f14e8-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="f14e8-129">Разверните **Базы данных**, разверните базу данных, к которой относится процедура, или с помощью панели инструментов выберите базу данных из списка доступных.</span><span class="sxs-lookup"><span data-stu-id="f14e8-129">Expand **Databases**, expand the database in which the procedure belongs, or, from the tool bar, select the database from the list of available databases.</span></span>  
  
3.  <span data-ttu-id="f14e8-130">В меню «Файл» выберите команду **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="f14e8-130">On the File menu, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="f14e8-131">Получите имя хранимой процедуры для удаления из текущей базы данных.</span><span class="sxs-lookup"><span data-stu-id="f14e8-131">Obtain the name of stored procedure to remove in the current database.</span></span> <span data-ttu-id="f14e8-132">В обозревателе объектов разверните узел **Программирование** , затем **Хранимые процедуры**.</span><span class="sxs-lookup"><span data-stu-id="f14e8-132">From Object Explorer, expand **Programmability** and then expand **Stored Procedures**.</span></span> <span data-ttu-id="f14e8-133">Также можно выполнить следующую инструкцию в редакторе запросов.</span><span class="sxs-lookup"><span data-stu-id="f14e8-133">Alternatively, in the query editor, run the following statement.</span></span>  
  
    ```sql  
    SELECT name AS procedure_name   
        ,SCHEMA_NAME(schema_id) AS schema_name  
        ,type_desc  
        ,create_date  
        ,modify_date  
    FROM sys.procedures;  
    ```  
  
5.  <span data-ttu-id="f14e8-134">Скопируйте и вставьте следующий пример в редактор запросов и введите имя хранимой процедуры, которую нужно удалить из текущей базы данных.</span><span class="sxs-lookup"><span data-stu-id="f14e8-134">Copy and paste the following example into the query editor and insert a stored procedure name to delete from the current database.</span></span>  
  
    ```sql  
    DROP PROCEDURE <stored procedure name>;  
    GO  
    ```  
  
6.  <span data-ttu-id="f14e8-135">Удалите ссылки на процедуру из зависимых объектов и скриптов.</span><span class="sxs-lookup"><span data-stu-id="f14e8-135">Remove references to the procedure from any dependent objects and scripts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f14e8-136">См. также:</span><span class="sxs-lookup"><span data-stu-id="f14e8-136">See Also</span></span>  
 <span data-ttu-id="f14e8-137">[Создание хранимой процедуры](create-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="f14e8-137">[Create a Stored Procedure](create-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="f14e8-138">[Изменение хранимой процедуры](modify-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="f14e8-138">[Modify a Stored Procedure](modify-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="f14e8-139">[Изменение имени хранимой процедуры](rename-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="f14e8-139">[Rename a Stored Procedure](rename-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="f14e8-140">[Просмотр определения хранимой процедуры](view-the-definition-of-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="f14e8-140">[View the Definition of a Stored Procedure](view-the-definition-of-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="f14e8-141">[Просмотр зависимостей хранимой процедуры](view-the-dependencies-of-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="f14e8-141">[View the Dependencies of a Stored Procedure](view-the-dependencies-of-a-stored-procedure.md) </span></span>  
 [<span data-ttu-id="f14e8-142">DROP PROCEDURE (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f14e8-142">DROP PROCEDURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-procedure-transact-sql)  
  
  
