---
title: Просмотр свойств внешнего ключа | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- foreign keys [SQL Server], attributes
- displaying foreign keys attributes
- viewing foreign keys attributes
ms.assetid: b0e57cb7-9b26-4b96-b76a-1f59f5f498c5
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5860a0cf26b983d75bab86862ee1e5fdd7737712
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655550"
---
# <a name="view-foreign-key-properties"></a><span data-ttu-id="e8869-102">Просмотр свойств внешнего ключа</span><span class="sxs-lookup"><span data-stu-id="e8869-102">View Foreign Key Properties</span></span>
  <span data-ttu-id="e8869-103">Просматривать атрибуты внешнего ключа связи в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] можно с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e8869-103">You can view the foreign key attributes of a relationship in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="e8869-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="e8869-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e8869-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="e8869-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e8869-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="e8869-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e8869-107">**Просмотр атрибутов внешнего ключа таблицы с помощью различных средств.**</span><span class="sxs-lookup"><span data-stu-id="e8869-107">**To view the foreign key attributes of a specific table, using:**</span></span>  
  
     [<span data-ttu-id="e8869-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e8869-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="e8869-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e8869-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e8869-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="e8869-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e8869-111">безопасность</span><span class="sxs-lookup"><span data-stu-id="e8869-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e8869-112">Permissions</span><span class="sxs-lookup"><span data-stu-id="e8869-112">Permissions</span></span>  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] <span data-ttu-id="e8869-113">Дополнительные сведения см. в разделе [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="e8869-113">For more information, see [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e8869-114">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e8869-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-foreign-key-attributes-of-a-relationship-in-a-specific-table"></a><span data-ttu-id="e8869-115">Просмотр атрибутов внешнего ключа связей в таблице</span><span class="sxs-lookup"><span data-stu-id="e8869-115">To view the foreign key attributes of a relationship in a specific table</span></span>  
  
1.  <span data-ttu-id="e8869-116">Откройте в конструкторе таблиц таблицу, содержащую внешний ключ, который нужно просмотреть. Щелкните правой кнопкой мыши конструктор таблиц и выберите в контекстном меню пункт **Связи** .</span><span class="sxs-lookup"><span data-stu-id="e8869-116">Open the Table Designer for the table containing the foreign key you want to view, right-click in the Table Designer, and choose **Relationships** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="e8869-117">В диалоговом окне **Связи внешних ключей** выберите связь, свойства которой нужно просмотреть.</span><span class="sxs-lookup"><span data-stu-id="e8869-117">In the **Foreign Key Relationships** dialog box, select the relationship with properties you want to view.</span></span>  
  
 <span data-ttu-id="e8869-118">Если внешние ключевые столбцы связаны с первичным ключом, столбцы первичных ключей можно идентифицировать в **конструкторе таблиц** по символу первичного ключа в селекторе строк.</span><span class="sxs-lookup"><span data-stu-id="e8869-118">If the foreign key columns are related to a primary key, the primary key columns are identified in **Table Designer** by a primary key symbol in the row selector.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e8869-119">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e8869-119">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-foreign-key-attributes-of-a-relationship-in-a-specific-table"></a><span data-ttu-id="e8869-120">Просмотр атрибутов внешнего ключа связей в таблице</span><span class="sxs-lookup"><span data-stu-id="e8869-120">To view the foreign key attributes of a relationship in a specific table</span></span>  
  
1.  <span data-ttu-id="e8869-121">В **обозревателе объектов**подключитесь к экземпляру компонента [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e8869-121">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e8869-122">На стандартной панели выберите пункт **Создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="e8869-122">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e8869-123">Скопируйте следующий пример в окно запроса и нажмите кнопку **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="e8869-123">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="e8869-124">В приведенном далее примере возвращаются сведения обо всех внешних ключах и их свойствах для таблицы `HumanResources.Employee` из образца базы данных.</span><span class="sxs-lookup"><span data-stu-id="e8869-124">The example returns all foreign keys and their properties for the table `HumanResources.Employee` in the sample database.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT   
        f.name AS foreign_key_name  
       ,OBJECT_NAME(f.parent_object_id) AS table_name  
       ,COL_NAME(fc.parent_object_id, fc.parent_column_id) AS constraint_column_name  
       ,OBJECT_NAME (f.referenced_object_id) AS referenced_object  
       ,COL_NAME(fc.referenced_object_id, fc.referenced_column_id) AS referenced_column_name  
       ,is_disabled  
       ,delete_referential_action_desc  
       ,update_referential_action_desc  
    FROM sys.foreign_keys AS f  
    INNER JOIN sys.foreign_key_columns AS fc   
       ON f.object_id = fc.constraint_object_id   
    WHERE f.parent_object_id = OBJECT_ID('HumanResources.Employee');  
    ```  
  
 <span data-ttu-id="e8869-125">Дополнительные сведения см. в разделе [sys.foreign_keys (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-foreign-keys-transact-sql) и [sys.foreign_key_columns (Transact-SQL)](/sql/relational-databases/system-catalog-views/sys-foreign-key-columns-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e8869-125">For more information, see [sys.foreign_keys &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-foreign-keys-transact-sql) and [sys.foreign_key_columns &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-foreign-key-columns-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
