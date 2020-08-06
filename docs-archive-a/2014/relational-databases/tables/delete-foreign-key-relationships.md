---
title: Удаление связей по внешнему ключу | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- foreign keys [SQL Server], deleting
- removing foreign keys
- deleting foreign keys
ms.assetid: 9c9e9ae4-9e03-4137-acb6-b18928a0c4ca
author: stevestein
ms.author: sstein
ms.openlocfilehash: 86ae466b9fce53073bfc0645c753246023ff3269
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87664093"
---
# <a name="delete-foreign-key-relationships"></a><span data-ttu-id="c959c-102">Удаление связей по внешнему ключу</span><span class="sxs-lookup"><span data-stu-id="c959c-102">Delete Foreign Key Relationships</span></span>
  <span data-ttu-id="c959c-103">Можно удалить ограничение внешнего ключа в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] при помощи среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c959c-103">You can delete a foreign key constraint in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="c959c-104">При удалении ограничения внешнего ключа удаляется требование принудительного создания ссылочной целостности.</span><span class="sxs-lookup"><span data-stu-id="c959c-104">Deleting a foreign key constraint removes the requirement to enforce referential integrity.</span></span>  
  
 <span data-ttu-id="c959c-105">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="c959c-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c959c-106">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="c959c-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c959c-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="c959c-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c959c-108">**Удаление ограничения внешнего ключа при помощи различных средств**</span><span class="sxs-lookup"><span data-stu-id="c959c-108">**To delete a foreign key constraint, using:**</span></span>  
  
     [<span data-ttu-id="c959c-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c959c-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c959c-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c959c-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c959c-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="c959c-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c959c-112">безопасность</span><span class="sxs-lookup"><span data-stu-id="c959c-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c959c-113">Permissions</span><span class="sxs-lookup"><span data-stu-id="c959c-113">Permissions</span></span>  
 <span data-ttu-id="c959c-114">Требуется разрешение ALTER на таблицу.</span><span class="sxs-lookup"><span data-stu-id="c959c-114">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c959c-115">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c959c-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-foreign-key-constraint"></a><span data-ttu-id="c959c-116">Удаление ограничения внешнего ключа</span><span class="sxs-lookup"><span data-stu-id="c959c-116">To delete a foreign key constraint</span></span>  
  
1.  <span data-ttu-id="c959c-117">Разверните в **обозревателе объектов**таблицу с ограничением, после чего разверните узел **Ключи**.</span><span class="sxs-lookup"><span data-stu-id="c959c-117">In **Object Explorer**, expand the table with the constraint and then expand **Keys**.</span></span>  
  
2.  <span data-ttu-id="c959c-118">Щелкните правой кнопкой мыши ограничение и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="c959c-118">Right-click the constraint and then click **Delete**.</span></span>  
  
3.  <span data-ttu-id="c959c-119">В диалоговом окне **Удаление объекта** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c959c-119">In the **Delete Object** dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c959c-120">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c959c-120">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-foreign-key-constraint"></a><span data-ttu-id="c959c-121">Удаление ограничения внешнего ключа</span><span class="sxs-lookup"><span data-stu-id="c959c-121">To delete a foreign key constraint</span></span>  
  
1.  <span data-ttu-id="c959c-122">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c959c-122">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c959c-123">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="c959c-123">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c959c-124">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="c959c-124">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER TABLE dbo.DocExe   
    DROP CONSTRAINT FK_Column_B;   
    GO  
    ```  
  
 <span data-ttu-id="c959c-125">Дополнительные сведения см. в разделе [ALTER TABLE (Transact-SQL)](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c959c-125">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
  
