---
title: Изменение ограничения уникальности | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- modifying constraints
- UNIQUE constraints [SQL Server], modifying
- constraints [SQL Server], modifying
- constraints [SQL Server], unique
ms.assetid: fddbdc9e-958b-4614-8e88-6ca205d64a4e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 74b044202f7e8e9bc762f025833cf2d0ff84c4c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669347"
---
# <a name="modify-unique-constraints"></a><span data-ttu-id="c703e-102">Изменение ограничения уникальности</span><span class="sxs-lookup"><span data-stu-id="c703e-102">Modify Unique Constraints</span></span>
  <span data-ttu-id="c703e-103">Изменить ограничение уникальности в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] можно в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или с помощью [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c703e-103">You can modify a unique constraint in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="c703e-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="c703e-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c703e-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="c703e-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c703e-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="c703e-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c703e-107">**Изменение ограничения уникальности с помощью:**</span><span class="sxs-lookup"><span data-stu-id="c703e-107">**To modify a unique constraint using:**</span></span>  
  
     [<span data-ttu-id="c703e-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c703e-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c703e-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c703e-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c703e-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="c703e-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c703e-111">безопасность</span><span class="sxs-lookup"><span data-stu-id="c703e-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c703e-112">Permissions</span><span class="sxs-lookup"><span data-stu-id="c703e-112">Permissions</span></span>  
 <span data-ttu-id="c703e-113">Требуется разрешение ALTER на таблицу.</span><span class="sxs-lookup"><span data-stu-id="c703e-113">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c703e-114">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c703e-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-unique-constraint"></a><span data-ttu-id="c703e-115">Изменение ограничения уникальности</span><span class="sxs-lookup"><span data-stu-id="c703e-115">To modify a unique constraint</span></span>  
  
1.  <span data-ttu-id="c703e-116">В **обозревателе объектов**щелкните правой кнопкой мыши таблицу, содержащую ограничение уникальности, и выберите пункт **Конструктор**.</span><span class="sxs-lookup"><span data-stu-id="c703e-116">In the **Object Explorer**, right-click the table containing the unique constraint and select **Design**.</span></span>  
  
2.  <span data-ttu-id="c703e-117">В меню **Конструктор таблиц** выберите пункт **Индексы и ключи...** .</span><span class="sxs-lookup"><span data-stu-id="c703e-117">On the **Table Designer** menu, click **Indexes/Keys...**.</span></span>  
  
3.  <span data-ttu-id="c703e-118">В диалоговом окне **Индексы и Ключи** в списке **Выбранный первичный/уникальный ключ или индекс**выберите ограничение, которое нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="c703e-118">In the **Indexes/Keys** dialog box, under **Selected Primary/Unique Key or Index**, select the constraint you wish to edit.</span></span>  
  
4.  <span data-ttu-id="c703e-119">Выполните действие из следующей таблицы.</span><span class="sxs-lookup"><span data-stu-id="c703e-119">Complete an action from the following table:</span></span>  
  
    |<span data-ttu-id="c703e-120">Чтобы</span><span class="sxs-lookup"><span data-stu-id="c703e-120">To</span></span>|<span data-ttu-id="c703e-121">Выполните следующее</span><span class="sxs-lookup"><span data-stu-id="c703e-121">Follow these steps</span></span>|  
    |--------|------------------------|  
    |<span data-ttu-id="c703e-122">Изменение столбца, с которым связано ограничение</span><span class="sxs-lookup"><span data-stu-id="c703e-122">Change the columns that the constraint is associated with</span></span>|<span data-ttu-id="c703e-123">1) В сетке в области **(Общие)** щелкните элемент **Столбцы**, затем нажмите кнопку с многоточием **(...)** справа от свойства.</span><span class="sxs-lookup"><span data-stu-id="c703e-123">1) In the grid under **(General)**, click **Columns** and then click the ellipses **(...)** to the right of the property.</span></span><br /><br /> <span data-ttu-id="c703e-124">2) В диалоговом окне **Столбцы индекса** укажите для индекса новый столбец и (или) порядок сортировки.</span><span class="sxs-lookup"><span data-stu-id="c703e-124">2) In the **Index Columns** dialog box, specify the new column or sort order or both for the index.</span></span>|  
    |<span data-ttu-id="c703e-125">Переименуйте ограничение</span><span class="sxs-lookup"><span data-stu-id="c703e-125">Rename the constraint</span></span>|<span data-ttu-id="c703e-126">В сетке в области **Идентификатор**введите новое имя в поле **Имя** .</span><span class="sxs-lookup"><span data-stu-id="c703e-126">In the grid under **Identity**, type a new name in the **Name** box.</span></span> <span data-ttu-id="c703e-127">Убедитесь, что новое имя не совпадает с именами в списке **Выбранный первичный/уникальный ключ или индекс** .</span><span class="sxs-lookup"><span data-stu-id="c703e-127">Make sure that your new name does not duplicate a name in the **Selected Primary/Unique Key or Index** list.</span></span>|  
    |<span data-ttu-id="c703e-128">Установка параметра кластеризации</span><span class="sxs-lookup"><span data-stu-id="c703e-128">Set the clustered option</span></span>|<span data-ttu-id="c703e-129">В сетке в области **Конструктор таблиц** выберите **Создать как кластеризованный**, а затем выберите в раскрывающемся списке пункт "Да". Будет создан кластеризованный индекс, а в противном случае — некластеризованный.</span><span class="sxs-lookup"><span data-stu-id="c703e-129">In the grid under **Table Designer**, select **Create As Clustered** and from the dropdown choose Yes to create a clustered index and No to create a nonclustered one.</span></span> <span data-ttu-id="c703e-130">Таблица может содержать только один кластеризованный индекс.</span><span class="sxs-lookup"><span data-stu-id="c703e-130">Only one clustered index can exist per table.</span></span> <span data-ttu-id="c703e-131">Если кластеризованный индекс уже существует в этой таблице, то необходимо сначала отменить данный параметр в исходном индексе.</span><span class="sxs-lookup"><span data-stu-id="c703e-131">If a clustered index already exists in this table, you must clear this setting on the original index.</span></span>|  
    |<span data-ttu-id="c703e-132">Установка коэффициента заполнения</span><span class="sxs-lookup"><span data-stu-id="c703e-132">Define a fill factor</span></span>|<span data-ttu-id="c703e-133">В сетке в области **Конструктор таблиц**разверните категорию **Характеристики заполнения** и введите целое число от 0 до 100 в поле **Коэффициент заполнения** .</span><span class="sxs-lookup"><span data-stu-id="c703e-133">In the grid under **Table Designer**, expand the **Fill Specification** category and type an integer from 0 to 100 in the **Fill Factor** box.</span></span>|  
  
5.  <span data-ttu-id="c703e-134">В меню **Файл** выберите пункт **Сохранить**_table name_.</span><span class="sxs-lookup"><span data-stu-id="c703e-134">On the **File** menu, click **Save**_table name_.</span></span>  
  
##  <a name="to-modify-a-unique-constraint"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c703e-135">**Изменение ограничения уникальности**</span><span class="sxs-lookup"><span data-stu-id="c703e-135">**To modify a unique constraint**</span></span>  
  
 <span data-ttu-id="c703e-136">Чтобы изменить ограничение UNIQUE с помощью Transact-SQL, необходимо сначала удалить существующее ограничение, а затем создать его повторно с помощью нового определения.</span><span class="sxs-lookup"><span data-stu-id="c703e-136">To modify a UNIQUE constraint using Transact-SQL, you must first delete the existing UNIQUE constraint and then re-create it with the new definition.</span></span> <span data-ttu-id="c703e-137">Дополнительные сведения см. в разделах [Delete Unique Constraints](delete-unique-constraints.md) и [Create Unique Constraints](create-unique-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="c703e-137">For more information, see [Delete Unique Constraints](delete-unique-constraints.md) and [Create Unique Constraints](create-unique-constraints.md).</span></span>  
  
###  <a name="TsqlExample"></a>  
