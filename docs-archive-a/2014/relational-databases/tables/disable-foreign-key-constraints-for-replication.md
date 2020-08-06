---
title: Отключение ограничений внешнего ключа для репликации | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- constraints [SQL Server], foreign keys
- foreign keys [SQL Server], disabling constraints
- disabling constraints
ms.assetid: 4211f2fd-d16a-4081-995c-43f1f0827f0b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4ee7f2fb7b0a27870a09a9d99b723b7faf739aeb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87658679"
---
# <a name="disable-foreign-key-constraints-for-replication"></a><span data-ttu-id="1210c-102">Отключение ограничений внешнего ключа для репликации</span><span class="sxs-lookup"><span data-stu-id="1210c-102">Disable Foreign Key Constraints for Replication</span></span>
  <span data-ttu-id="1210c-103">Отключить ограничения внешнего ключа для репликации можно в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] с помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1210c-103">You can disable foreign key constraints for replication in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="1210c-104">Это может потребоваться при публикации данных из предыдущей версии [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1210c-104">This can be useful if you are publishing data from a previous version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1210c-105">Если таблица публикуется для репликации, ограничения внешнего ключа для нее автоматически отключаются в случае операций, выполняемых агентами репликации.</span><span class="sxs-lookup"><span data-stu-id="1210c-105">If a table is published using replication, foreign key constraints are automatically disabled for operations performed by replication agents.</span></span> <span data-ttu-id="1210c-106">Когда агент репликации на подписчике выполняет вставку, обновление или удаление, ограничение не проверяется. Если эту же операцию выполняет пользователь, ограничение проверяется.</span><span class="sxs-lookup"><span data-stu-id="1210c-106">When a replication agent performs an insert, update, or delete at a Subscriber, the constraint is not checked; if a user performs an insert, update, or delete, the constraint is checked.</span></span> <span data-ttu-id="1210c-107">Ограничение отключено для агента репликации по той причине, что оно уже проверено на издателе при выполнении исходной операции вставки, обновления или удаления данных.</span><span class="sxs-lookup"><span data-stu-id="1210c-107">The constraint is disabled for the replication agent because the constraint was already checked at the Publisher when the data was originally inserted, updated, or deleted.</span></span>  
  
 <span data-ttu-id="1210c-108">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="1210c-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1210c-109">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="1210c-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1210c-110">Безопасность</span><span class="sxs-lookup"><span data-stu-id="1210c-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="1210c-111">**Отключение ограничения внешнего ключа для репликации с использованием следующих средств:**</span><span class="sxs-lookup"><span data-stu-id="1210c-111">**To disable a foreign key constraint for replication, using:**</span></span>  
  
     [<span data-ttu-id="1210c-112">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1210c-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="1210c-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1210c-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1210c-114">Перед началом</span><span class="sxs-lookup"><span data-stu-id="1210c-114">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1210c-115">безопасность</span><span class="sxs-lookup"><span data-stu-id="1210c-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1210c-116">Permissions</span><span class="sxs-lookup"><span data-stu-id="1210c-116">Permissions</span></span>  
 <span data-ttu-id="1210c-117">Требуется разрешение ALTER на таблицу.</span><span class="sxs-lookup"><span data-stu-id="1210c-117">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1210c-118">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1210c-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-a-foreign-key-constraint-for-replication"></a><span data-ttu-id="1210c-119">Отключение ограничения внешнего ключа для репликации</span><span class="sxs-lookup"><span data-stu-id="1210c-119">To disable a foreign key constraint for replication</span></span>  
  
1.  <span data-ttu-id="1210c-120">В **обозревателе объектов**раскройте таблицу, содержащую ограничение внешнего ключа, которое необходимо изменить, а затем разверните папку **Ключи** .</span><span class="sxs-lookup"><span data-stu-id="1210c-120">In **Object Explorer**, expand the table with the foreign key constraint you want to modify, and then expand the **Keys** folder.</span></span>  
  
2.  <span data-ttu-id="1210c-121">Правой кнопкой мыши щелкните ограничение, а затем выберите команду **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="1210c-121">Right-click the foreign key constraint and then click **Modify**.</span></span>  
  
3.  <span data-ttu-id="1210c-122">В диалоговом окне **Связи по внешнему ключу** выберите значение **Нет** для параметра **Включить использование для репликации**.</span><span class="sxs-lookup"><span data-stu-id="1210c-122">In the **Foreign Key Relationships** dialog box, select a value of **No** for **Enforce For Replication**.</span></span>  
  
4.  <span data-ttu-id="1210c-123">Щелкните **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="1210c-123">Click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1210c-124">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1210c-124">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-a-foreign-key-constraint-for-replication"></a><span data-ttu-id="1210c-125">Отключение ограничения внешнего ключа для репликации</span><span class="sxs-lookup"><span data-stu-id="1210c-125">To disable a foreign key constraint for replication</span></span>  
  
1.  <span data-ttu-id="1210c-126">Для выполнения этой задачи в [!INCLUDE[tsql](../../includes/tsql-md.md)]удалите ограничение внешнего ключа.</span><span class="sxs-lookup"><span data-stu-id="1210c-126">To perform this task in [!INCLUDE[tsql](../../includes/tsql-md.md)], drop the foreign key constraint.</span></span> <span data-ttu-id="1210c-127">Затем добавьте новое ограничение внешнего ключа и укажите параметр NOT FOR REPLICATION.</span><span class="sxs-lookup"><span data-stu-id="1210c-127">Then add a new foreign key constraint and specify the NOT FOR REPLICATION option.</span></span>  
  
 <span data-ttu-id="1210c-128">Дополнительные сведения см. в разделе [ALTER TABLE (Transact-SQL)](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1210c-128">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
