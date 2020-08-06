---
title: Удаление представлений | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- dropping views
- deleting views
- views [SQL Server], deleting
- removing views
ms.assetid: 6823c7f8-06ca-4bda-8482-7092f03d52a0
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3e05724f7d6384d0407e915207ad60a1cdfb01b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654979"
---
# <a name="delete-views"></a><span data-ttu-id="f1627-102">Удаление представлений</span><span class="sxs-lookup"><span data-stu-id="f1627-102">Delete Views</span></span>
  <span data-ttu-id="f1627-103">Представления можно удалить в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1627-103">You can delete (drop) views in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)]</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f1627-104">Перед началом</span><span class="sxs-lookup"><span data-stu-id="f1627-104">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f1627-105">Ограничения</span><span class="sxs-lookup"><span data-stu-id="f1627-105">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="f1627-106">При удалении представления из системного каталога удаляется его определение и другие сведения о нем.</span><span class="sxs-lookup"><span data-stu-id="f1627-106">When you drop a view, the definition of the view and other information about the view is deleted from the system catalog.</span></span> <span data-ttu-id="f1627-107">Все связанные с представлением разрешения также удаляются.</span><span class="sxs-lookup"><span data-stu-id="f1627-107">All permissions for the view are also deleted.</span></span>  
  
-   <span data-ttu-id="f1627-108">Любое представление таблицы, удаленной с помощью инструкции `DROP TABLE` , нужно удалять явно, с помощью инструкции `DROP VIEW`.</span><span class="sxs-lookup"><span data-stu-id="f1627-108">Any view on a table that is dropped by using `DROP TABLE` must be dropped explicitly by using `DROP VIEW`.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f1627-109">безопасность</span><span class="sxs-lookup"><span data-stu-id="f1627-109">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f1627-110">Permissions</span><span class="sxs-lookup"><span data-stu-id="f1627-110">Permissions</span></span>  
 <span data-ttu-id="f1627-111">Требует либо разрешения CONTROL для схемы SCHEMA, либо разрешения CONTROL для объекта OBJECT.</span><span class="sxs-lookup"><span data-stu-id="f1627-111">Requires ALTER permission on SCHEMA or CONTROL permission on OBJECT.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f1627-112">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f1627-112">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-view-from-a-database"></a><span data-ttu-id="f1627-113">Удаление представления из базы данных</span><span class="sxs-lookup"><span data-stu-id="f1627-113">To delete a view from a database</span></span>  
  
1.  <span data-ttu-id="f1627-114">В **обозревателе объектов**разверните базу данных, в которой содержится представление, подлежащее удалению, а затем разверните папку **Представления** .</span><span class="sxs-lookup"><span data-stu-id="f1627-114">In **Object Explorer**, expand the database that contains the view you want to delete, and then expand the **Views** folder.</span></span>  
  
2.  <span data-ttu-id="f1627-115">Щелкните правой кнопкой мыши представление, которое требуется удалить, и выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="f1627-115">Right-click the view you want to delete and click **Delete**.</span></span>  
  
3.  <span data-ttu-id="f1627-116">В диалоговом окне **Удаление объекта** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f1627-116">In the **Delete Object** dialog box, click **OK**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="f1627-117">Щелкните **Показать зависимости** в диалоговом окне **Удаление объекта** , чтобы открыть диалоговое окно _имя_представления_**Зависимости** .</span><span class="sxs-lookup"><span data-stu-id="f1627-117">Click **Show Dependencies** in the **Delete Object** dialog box to open the _view_name_**Dependencies** dialog box.</span></span> <span data-ttu-id="f1627-118">При этом будут отображены все объекты, зависящие от представления, и все объекты, от которых зависит представление.</span><span class="sxs-lookup"><span data-stu-id="f1627-118">This will show all of the objects that depend on the view and all of the objects on which the view depends.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f1627-119">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f1627-119">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-view-from-a-database"></a><span data-ttu-id="f1627-120">Удаление представления из базы данных</span><span class="sxs-lookup"><span data-stu-id="f1627-120">To delete a view from a database</span></span>  
  
1.  <span data-ttu-id="f1627-121">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f1627-121">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f1627-122">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="f1627-122">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f1627-123">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="f1627-123">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="f1627-124">В примере указанное представление удаляется только в том случае, если оно существует.</span><span class="sxs-lookup"><span data-stu-id="f1627-124">The example deletes the specified view only if the view already exists.</span></span>  
  
    ```  
    USE AdventureWorks2012 ;  
    GO  
    IF OBJECT_ID ('HumanResources.EmployeeHireDate', 'V') IS NOT NULL  
    DROP VIEW HumanResources.EmployeeHireDate;  
    GO  
    ```  
  
 <span data-ttu-id="f1627-125">Дополнительные сведения см. в разделе [DROP VIEW (Transact-SQL)](/sql/t-sql/statements/drop-view-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f1627-125">For more information, see [DROP VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-view-transact-sql).</span></span>  
  
  
