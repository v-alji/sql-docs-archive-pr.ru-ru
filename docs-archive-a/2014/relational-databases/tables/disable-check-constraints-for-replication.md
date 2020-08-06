---
title: Отключение проверочных ограничений для репликации | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- CHECK constraints, disabling
- constraints [SQL Server], disabling
- disabling constraints
- constraints [SQL Server], check
ms.assetid: af98fc70-24dd-4bd3-a0a3-f701dfa67b2c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 98b6ca7c3525edeffdb47f294db568d3c115b2c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654120"
---
# <a name="disable-check-constraints-for-replication"></a><span data-ttu-id="b9cb4-102">Отключение проверочных ограничений для репликации</span><span class="sxs-lookup"><span data-stu-id="b9cb4-102">Disable Check Constraints for Replication</span></span>
  <span data-ttu-id="b9cb4-103">Отключить проверочные ограничения в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] можно при помощи среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b9cb4-103">You can disable check constraints in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="b9cb4-104">Также можно явно отключить проверочные ограничения при репликации, что может оказаться полезным при публикации данных от более ранней версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b9cb4-104">You can also explicitly disable check constraints for replication, which can be useful if you are publishing data from a previous version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b9cb4-105">Если таблица опубликована с использованием репликации, то проверочные ограничения для операций, выполняемых агентами репликации, автоматически отключаются.</span><span class="sxs-lookup"><span data-stu-id="b9cb4-105">If a table is published using replication, check constraints are automatically disabled for operations performed by replication agents.</span></span> <span data-ttu-id="b9cb4-106">Когда агент репликации на подписчике выполняет вставку, обновление или удаление, ограничение не проверяется. Если эту же операцию выполняет пользователь, ограничение проверяется.</span><span class="sxs-lookup"><span data-stu-id="b9cb4-106">When a replication agent performs an insert, update, or delete at a Subscriber, the constraint is not checked; if a user performs an insert, update, or delete, the constraint is checked.</span></span> <span data-ttu-id="b9cb4-107">Ограничение отключено для агента репликации по той причине, что оно уже проверено на издателе при выполнении исходной операции вставки, обновления или удаления данных.</span><span class="sxs-lookup"><span data-stu-id="b9cb4-107">The constraint is disabled for the replication agent because the constraint was already checked at the Publisher when the data was originally inserted, updated, or deleted.</span></span> <span data-ttu-id="b9cb4-108">Дополнительные сведения см. в разделе [Указание параметров схемы](../replication/publish/specify-schema-options.md).</span><span class="sxs-lookup"><span data-stu-id="b9cb4-108">For more information, see [Specify Schema Options](../replication/publish/specify-schema-options.md).</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b9cb4-109">Перед началом</span><span class="sxs-lookup"><span data-stu-id="b9cb4-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b9cb4-110">безопасность</span><span class="sxs-lookup"><span data-stu-id="b9cb4-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b9cb4-111">Permissions</span><span class="sxs-lookup"><span data-stu-id="b9cb4-111">Permissions</span></span>  
 <span data-ttu-id="b9cb4-112">Требуется разрешение ALTER на таблицу.</span><span class="sxs-lookup"><span data-stu-id="b9cb4-112">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b9cb4-113">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b9cb4-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-a-check-constraint-for-replication"></a><span data-ttu-id="b9cb4-114">Отключение проверочных ограничений при репликации</span><span class="sxs-lookup"><span data-stu-id="b9cb4-114">To disable a check constraint for replication</span></span>  
  
1.  <span data-ttu-id="b9cb4-115">Разверните в **обозревателе объектов**таблицу с проверочным ограничением, которое нужно изменить, а затем разверните папку **Ограничения** .</span><span class="sxs-lookup"><span data-stu-id="b9cb4-115">In **Object Explorer**, expand the table with the check constraint you want to modify, and then expand the **Constraints** folder.</span></span>  
  
2.  <span data-ttu-id="b9cb4-116">Щелкните правой кнопкой мыши проверочное ограничение, которое нужно изменить, и выберите пункт **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="b9cb4-116">Right-click the check constraint you wish to modify and then click **Modify**.</span></span>  
  
3.  <span data-ttu-id="b9cb4-117">В диалоговом окне **Проверочные ограничения** в разделе **Конструктор таблиц**выберите для параметра **Включить использование для репликации** значение **Нет**.</span><span class="sxs-lookup"><span data-stu-id="b9cb4-117">In the **Check Constraints** dialog box, under **Table Designer**, select a value of **No** for **Enforce For Replication**.</span></span>  
  
4.  <span data-ttu-id="b9cb4-118">Щелкните **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="b9cb4-118">Click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b9cb4-119">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b9cb4-119">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-a-check-constraint-for-replication"></a><span data-ttu-id="b9cb4-120">Отключение проверочных ограничений при репликации</span><span class="sxs-lookup"><span data-stu-id="b9cb4-120">To disable a check constraint for replication</span></span>  
  
1.  <span data-ttu-id="b9cb4-121">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b9cb4-121">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b9cb4-122">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="b9cb4-122">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b9cb4-123">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="b9cb4-123">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="b9cb4-124">В примере создается таблица со столбцом IDENTITY и ограничением CHECK.</span><span class="sxs-lookup"><span data-stu-id="b9cb4-124">The example creates a table with an IDENTITY column and a CHECK constraint on the table.</span></span> <span data-ttu-id="b9cb4-125">Затем в таблице удаляется это ограничение и снова создается с указанием предложения NOT FOR REPLICATION.</span><span class="sxs-lookup"><span data-stu-id="b9cb4-125">The example then drops the constraint and recreates it specifying the NOT FOR REPLICATION clause.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE TABLE dbo.doc_exd (column_a int IDENTITY (1,1)   
    CONSTRAINT exd_check CHECK (column_a > 1))   
  
    ALTER TABLE dbo.doc_exd   
    DROP CONSTRAINT exd_check;   
    GO  
    ALTER TABLE dbo.doc_exd    
    ADD CONSTRAINT exd_check CHECK NOT FOR REPLICATION (column_a > 1);  
    ```  
  
 <span data-ttu-id="b9cb4-126">Дополнительные сведения см. в разделе [ALTER TABLE (Transact-SQL)](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b9cb4-126">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>   
## <a name="see-also"></a><span data-ttu-id="b9cb4-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="b9cb4-127">See Also</span></span>  
 [<span data-ttu-id="b9cb4-128">Specify Schema Options (Указание параметров схемы)</span><span class="sxs-lookup"><span data-stu-id="b9cb4-128">Specify Schema Options</span></span>](../replication/publish/specify-schema-options.md)  
  
  
