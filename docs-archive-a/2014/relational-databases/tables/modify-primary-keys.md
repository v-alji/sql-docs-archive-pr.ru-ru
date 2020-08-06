---
title: Изменение первичных ключей | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- modifying primary keys
- primary keys [SQL Server], modifying
ms.assetid: 8e2a15ba-1cd1-4408-b860-16c3ee37d635
author: stevestein
ms.author: sstein
ms.openlocfilehash: f24deeac45491f9097d90ee0407464f928a0713b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654107"
---
# <a name="modify-primary-keys"></a><span data-ttu-id="064b2-102">Изменение первичных ключей</span><span class="sxs-lookup"><span data-stu-id="064b2-102">Modify Primary Keys</span></span>
  <span data-ttu-id="064b2-103">Изменить первичный ключ в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] можно с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="064b2-103">You can modify a primary key in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="064b2-104">Изменить первичный ключ таблицы можно, изменив порядок столбцов, имя индекса, параметр кластеризации или коэффициент заполнения.</span><span class="sxs-lookup"><span data-stu-id="064b2-104">You can modify the primary key of a table by changing the column order, index name, clustered option, or fill factor.</span></span>  
  
 <span data-ttu-id="064b2-105">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="064b2-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="064b2-106">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="064b2-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="064b2-107">Безопасность</span><span class="sxs-lookup"><span data-stu-id="064b2-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="064b2-108">**Изменение первичного ключа с использованием:**</span><span class="sxs-lookup"><span data-stu-id="064b2-108">**To modify a primary key, using:**</span></span>  
  
     [<span data-ttu-id="064b2-109">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="064b2-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="064b2-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="064b2-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="064b2-111">Перед началом</span><span class="sxs-lookup"><span data-stu-id="064b2-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="064b2-112">безопасность</span><span class="sxs-lookup"><span data-stu-id="064b2-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="064b2-113">Permissions</span><span class="sxs-lookup"><span data-stu-id="064b2-113">Permissions</span></span>  
 <span data-ttu-id="064b2-114">Требуется разрешение ALTER на таблицу.</span><span class="sxs-lookup"><span data-stu-id="064b2-114">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="064b2-115">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="064b2-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-primary-key"></a><span data-ttu-id="064b2-116">Изменение первичного ключа</span><span class="sxs-lookup"><span data-stu-id="064b2-116">To modify a primary key</span></span>  
  
1.  <span data-ttu-id="064b2-117">Откройте в конструкторе таблиц таблицу, первичный ключ которой необходимо изменить, правой кнопкой мыши щелкните конструктор таблиц и выберите пункт **Индексы и ключи** в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="064b2-117">Open the Table Designer for the table whose primary key you want to modify, right-click in the Table Designer, and choose **Indexes/Keys** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="064b2-118">В диалоговом окне **Индексы/ключи** выберите индекс первичного ключа из списка **Выберите первичный/уникальный ключ или индекс** .</span><span class="sxs-lookup"><span data-stu-id="064b2-118">In the **Indexes/Keys** dialog box, select the primary key index from the **Selected Primary/Unique Key or Index** list.</span></span>  
  
3.  <span data-ttu-id="064b2-119">Выполните действие из следующей таблицы.</span><span class="sxs-lookup"><span data-stu-id="064b2-119">Complete an action from the following table:</span></span>  
  
    |<span data-ttu-id="064b2-120">Чтобы</span><span class="sxs-lookup"><span data-stu-id="064b2-120">To</span></span>|<span data-ttu-id="064b2-121">Выполните следующее</span><span class="sxs-lookup"><span data-stu-id="064b2-121">Follow these steps</span></span>|  
    |--------|------------------------|  
    |<span data-ttu-id="064b2-122">Переименование первичного ключа</span><span class="sxs-lookup"><span data-stu-id="064b2-122">Rename the primary key</span></span>|<span data-ttu-id="064b2-123">Введите новое имя в поле **Имя** .</span><span class="sxs-lookup"><span data-stu-id="064b2-123">Type a new name in the **Name** box.</span></span> <span data-ttu-id="064b2-124">Убедитесь, что новое имя не совпадает с именами в списке **Выбранный первичный/уникальный ключ или индекс** .</span><span class="sxs-lookup"><span data-stu-id="064b2-124">Make sure that your new name does not duplicate a name in the **Selected Primary/Unique Key or Index** list.</span></span>|  
    |<span data-ttu-id="064b2-125">Установка параметра кластеризации</span><span class="sxs-lookup"><span data-stu-id="064b2-125">Set the clustered option</span></span>|<span data-ttu-id="064b2-126">Для создания кластеризованного индекса для первичного ключа укажите **Создать как CLUSTERED**и выберите нужный параметр из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="064b2-126">To create a clustered index for the primary key, select **Create as CLUSTERED**, and select the option from the drop-down list box.</span></span> <span data-ttu-id="064b2-127">Таблица может содержать только один кластеризованный индекс.</span><span class="sxs-lookup"><span data-stu-id="064b2-127">Only one clustered index can exist per table.</span></span> <span data-ttu-id="064b2-128">Если этот параметр недоступен для выбранного индекса, то сначала снимите этот флажок в существующем кластеризованном индексе.</span><span class="sxs-lookup"><span data-stu-id="064b2-128">If this option is not available for your index, you must first clear this setting on the existing clustered index.</span></span><br /><br /> <span data-ttu-id="064b2-129">Если этот параметр не выбран, создается уникальный некластеризованный индекс.</span><span class="sxs-lookup"><span data-stu-id="064b2-129">If this option is not selected, a unique nonclustered index is created.</span></span>|  
    |<span data-ttu-id="064b2-130">Установка коэффициента заполнения</span><span class="sxs-lookup"><span data-stu-id="064b2-130">Define a fill factor</span></span>|<span data-ttu-id="064b2-131">Разверните категорию **Характеристики заполнения** и введите целое число от 0 до 100 в поле **Коэффициент заполнения** .</span><span class="sxs-lookup"><span data-stu-id="064b2-131">Expand the **Fill Specification** category and type an integer from 0 to 100 in the **Fill factor** box.</span></span> <span data-ttu-id="064b2-132">Дополнительные сведения о коэффициентах заполнения и их использовании см. в разделе [Укажите коэффициент заполнения для индекса](../indexes/specify-fill-factor-for-an-index.md).</span><span class="sxs-lookup"><span data-stu-id="064b2-132">For more information about fill factors and their uses, see [Specify Fill Factor for an Index](../indexes/specify-fill-factor-for-an-index.md).</span></span>|  
    |<span data-ttu-id="064b2-133">Изменение порядка столбцов</span><span class="sxs-lookup"><span data-stu-id="064b2-133">Change the column order</span></span>|<span data-ttu-id="064b2-134">Выберите свойство **Столбцы**и нажмите кнопку с многоточием **(...)** справа от свойства.</span><span class="sxs-lookup"><span data-stu-id="064b2-134">Select **Columns**, and then click the ellipses **(...)** to the right of the property.</span></span> <span data-ttu-id="064b2-135">В диалоговом окне  **Столбцы индекса** удалите столбцы из первичного ключа.</span><span class="sxs-lookup"><span data-stu-id="064b2-135">In the  **Index Columns** dialog box, remove the columns from the primary key.</span></span> <span data-ttu-id="064b2-136">Затем снова добавьте эти столбцы в необходимом порядке.</span><span class="sxs-lookup"><span data-stu-id="064b2-136">Then add the columns back in the order you want.</span></span> <span data-ttu-id="064b2-137">Чтобы удалить столбец из ключа, просто удалите имя столбца из списка имен **Столбец** .</span><span class="sxs-lookup"><span data-stu-id="064b2-137">To remove a column from the key, simply remove the column name from the **Column** name list.</span></span>|  
  
4.  <span data-ttu-id="064b2-138">В меню **Файл** выберите пункт **Сохранить**_table name_.</span><span class="sxs-lookup"><span data-stu-id="064b2-138">On the **File** menu, click **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="064b2-139">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="064b2-139">Using Transact-SQL</span></span>  
 <span data-ttu-id="064b2-140">**Изменение первичного ключа**</span><span class="sxs-lookup"><span data-stu-id="064b2-140">**To modify a primary key**</span></span>  
  
 <span data-ttu-id="064b2-141">Чтобы изменить ограничение PRIMARY KEY с использованием Transact-SQL, необходимо сначала удалить существующее ограничение PRIMARY KEY, а затем создать новое с другим определением.</span><span class="sxs-lookup"><span data-stu-id="064b2-141">To modify a PRIMARY KEY constraint using Transact-SQL, you must first delete the existing PRIMARY KEY constraint and then re-create it with the new definition.</span></span> <span data-ttu-id="064b2-142">Дополнительные сведения см. в разделах [Delete Primary Keys](delete-primary-keys.md) и [Create Primary Keys](create-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="064b2-142">For more information, see [Delete Primary Keys](delete-primary-keys.md) and [Create Primary Keys](create-primary-keys.md).</span></span>  
  
###  <a name="TsqlExample"></a>  
