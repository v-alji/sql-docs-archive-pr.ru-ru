---
title: Переименование статистики | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- renaming statistics
- statistics [SQL Server], renaming
ms.assetid: a3bed7b7-3dc5-4b33-b1c6-67c27f573764
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 1528dcec50a662524531065d597b004fe7f59e5f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667631"
---
# <a name="rename-statistics"></a><span data-ttu-id="b8a8e-102">Переименование статистики</span><span class="sxs-lookup"><span data-stu-id="b8a8e-102">Rename Statistics</span></span>
  <span data-ttu-id="b8a8e-103">Объект статистики в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] можно переименовать с помощью [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8a8e-103">You can rename a statistics object in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)]</span></span>  
  
 <span data-ttu-id="b8a8e-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="b8a8e-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b8a8e-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="b8a8e-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b8a8e-106">Ограничения</span><span class="sxs-lookup"><span data-stu-id="b8a8e-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="b8a8e-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="b8a8e-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b8a8e-108">**Для переименования объекта статистики используются:**</span><span class="sxs-lookup"><span data-stu-id="b8a8e-108">**To rename a statistics object, using:**</span></span>  
  
     [<span data-ttu-id="b8a8e-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b8a8e-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b8a8e-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="b8a8e-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b8a8e-111">Ограничения</span><span class="sxs-lookup"><span data-stu-id="b8a8e-111">Limitations and Restrictions</span></span>  
 <span data-ttu-id="b8a8e-112">По умолчанию при создании индекса создается статистика по ключевому столбцу этого индекса.</span><span class="sxs-lookup"><span data-stu-id="b8a8e-112">By default, creating an index creates a statistic on the key columns of that index.</span></span> <span data-ttu-id="b8a8e-113">Таким образом, переименование индекса автоматически вызывает переименование объекта статистики и наоборот.</span><span class="sxs-lookup"><span data-stu-id="b8a8e-113">Therefore, renaming the index automatically renames the statistics object, and vice versa.</span></span>  
  
 <span data-ttu-id="b8a8e-114">Изменение любой части имени объекта может разрушить скрипты и хранимые процедуры.</span><span class="sxs-lookup"><span data-stu-id="b8a8e-114">Changing any part of an object name can break scripts and stored procedures.</span></span> <span data-ttu-id="b8a8e-115">Вместо переименования рекомендуется удалить объект статистики и создать его повторно с новым именем.</span><span class="sxs-lookup"><span data-stu-id="b8a8e-115">Instead of renaming, we recommend that you drop the statistics object and re-create it with the new name.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b8a8e-116">безопасность</span><span class="sxs-lookup"><span data-stu-id="b8a8e-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b8a8e-117">Permissions</span><span class="sxs-lookup"><span data-stu-id="b8a8e-117">Permissions</span></span>  
 <span data-ttu-id="b8a8e-118">Необходимо разрешение ALTER для таблицы или представления.</span><span class="sxs-lookup"><span data-stu-id="b8a8e-118">Requires ALTER permission on the table or view.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b8a8e-119">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b8a8e-119">Using Transact-SQL</span></span>  
  
#### <a name="to-rename-a-statistics-object"></a><span data-ttu-id="b8a8e-120">Переименование объекта статистики</span><span class="sxs-lookup"><span data-stu-id="b8a8e-120">To rename a statistics object</span></span>  
  
1.  <span data-ttu-id="b8a8e-121">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8a8e-121">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b8a8e-122">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="b8a8e-122">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b8a8e-123">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="b8a8e-123">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    EXEC sp_rename N'AK_Employee_LoginID', N'AK_Emp_Login', N'STATISTICS';   
    GO  
    ```  
  
 <span data-ttu-id="b8a8e-124">Дополнительные сведения см. в разделе [sp_rename (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b8a8e-124">For more information, see [sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql).</span></span>  
  
  
