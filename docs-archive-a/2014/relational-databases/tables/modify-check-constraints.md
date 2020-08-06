---
title: Изменение проверочного ограничения | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- CHECK constraints, modifying
- modifying constraints
- constraints [SQL Server], check
- constraints [SQL Server], modifying
ms.assetid: f22daef8-e350-40ef-8ff0-b5f87d1d9e56
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8377c80590612c8b68c315f7c37823eb8f5c5093
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87665250"
---
# <a name="modify-check-constraints"></a><span data-ttu-id="47037-102">Изменение проверочного ограничения</span><span class="sxs-lookup"><span data-stu-id="47037-102">Modify Check Constraints</span></span>
  <span data-ttu-id="47037-103">Изменение проверочных ограничений в [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] осуществляется в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] или с помощью [!INCLUDE[tsql](../../includes/tsql-md.md)] , если необходимо изменить выражение ограничения или параметры, включающие или отключающие ограничение для конкретных условий.</span><span class="sxs-lookup"><span data-stu-id="47037-103">You can modify a check constraint in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)] when you want to change the constraint expression or the options that enable or disable the constraint for specific conditions.</span></span>  
  
 <span data-ttu-id="47037-104">**В этом разделе**</span><span class="sxs-lookup"><span data-stu-id="47037-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="47037-105">**Перед началом работы**</span><span class="sxs-lookup"><span data-stu-id="47037-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="47037-106">Безопасность</span><span class="sxs-lookup"><span data-stu-id="47037-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="47037-107">**Изменение проверочного ограничения с помощью:**</span><span class="sxs-lookup"><span data-stu-id="47037-107">**To modify a check constraint using:**</span></span>  
  
     [<span data-ttu-id="47037-108">Среда SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="47037-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="47037-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="47037-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="47037-110">Перед началом</span><span class="sxs-lookup"><span data-stu-id="47037-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="47037-111">безопасность</span><span class="sxs-lookup"><span data-stu-id="47037-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="47037-112">Permissions</span><span class="sxs-lookup"><span data-stu-id="47037-112">Permissions</span></span>  
 <span data-ttu-id="47037-113">Требуется разрешение ALTER на таблицу.</span><span class="sxs-lookup"><span data-stu-id="47037-113">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="47037-114">Использование среды SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="47037-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-check-constraint"></a><span data-ttu-id="47037-115">Изменение проверочного ограничения</span><span class="sxs-lookup"><span data-stu-id="47037-115">To modify a check constraint</span></span>  
  
1.  <span data-ttu-id="47037-116">В **обозревателе объектов**щелкните правой кнопкой мыши таблицу, содержащую проверочное ограничение, и выберите пункт **Конструктор**.</span><span class="sxs-lookup"><span data-stu-id="47037-116">In the **Object Explorer**, right-click the table containing the check constraint and select **Design**.</span></span>  
  
2.  <span data-ttu-id="47037-117">В меню **Конструктор таблиц** выберите **Проверочные ограничения...** .</span><span class="sxs-lookup"><span data-stu-id="47037-117">On the **Table Designer** menu, click **Check Constraints...**.</span></span>  
  
3.  <span data-ttu-id="47037-118">В диалоговом окне **Проверочные ограничения** выберите ограничение, которое нужно изменить, из списка **Выбранное проверочное ограничение**.</span><span class="sxs-lookup"><span data-stu-id="47037-118">In the **Check Constraints** dialog box, under **Selected Check Constraint**, select the constraint you wish to edit.</span></span>  
  
4.  <span data-ttu-id="47037-119">Выполните действие из следующей таблицы.</span><span class="sxs-lookup"><span data-stu-id="47037-119">Complete an action from the following table:</span></span>  
  
    |<span data-ttu-id="47037-120">Чтобы</span><span class="sxs-lookup"><span data-stu-id="47037-120">To</span></span>|<span data-ttu-id="47037-121">Выполните следующее</span><span class="sxs-lookup"><span data-stu-id="47037-121">Follow these steps</span></span>|  
    |--------|------------------------|  
    |<span data-ttu-id="47037-122">Изменить выражение ограничения</span><span class="sxs-lookup"><span data-stu-id="47037-122">Edit the constraint expression</span></span>|<span data-ttu-id="47037-123">Введите новое выражение в поле **Выражение** .</span><span class="sxs-lookup"><span data-stu-id="47037-123">Type the new expression in the **Expression** field.</span></span>|  
    |<span data-ttu-id="47037-124">Переименуйте ограничение</span><span class="sxs-lookup"><span data-stu-id="47037-124">Rename the constraint</span></span>|<span data-ttu-id="47037-125">Введите новое имя в поле **Имя** .</span><span class="sxs-lookup"><span data-stu-id="47037-125">Type a new name in the **Name** field.</span></span>|  
    |<span data-ttu-id="47037-126">Применить ограничение к существующим данным</span><span class="sxs-lookup"><span data-stu-id="47037-126">Apply the constraint to existing data</span></span>|<span data-ttu-id="47037-127">Установите флажок **Проверить существующие данные при создании или включении** .</span><span class="sxs-lookup"><span data-stu-id="47037-127">Select the **Check Existing Data on Creation or Enabling** option.</span></span>|  
    |<span data-ttu-id="47037-128">Отключить ограничение при добавлении в таблицу новых данных или обновлении существующих данных таблицы.</span><span class="sxs-lookup"><span data-stu-id="47037-128">Disable the constraint when new data is added to the table or when existing data is updated in the table.</span></span>|<span data-ttu-id="47037-129">Снимите флажок **Принудительное ограничение для инструкций INSERT и UPDATE** .</span><span class="sxs-lookup"><span data-stu-id="47037-129">Clear the **Enforce Constraint for INSERTs and UPDATEs** option.</span></span>|  
    |<span data-ttu-id="47037-130">Отключить ограничение при вставке или обновлении данных в таблице агентом репликации.</span><span class="sxs-lookup"><span data-stu-id="47037-130">Disable the constraint when a replication agent inserts or updates data in your table.</span></span>|<span data-ttu-id="47037-131">Снимите флажок **Включить использование для репликации** .</span><span class="sxs-lookup"><span data-stu-id="47037-131">Clear the **Enforce For Replication** option.</span></span>|  
  
    > [!NOTE]  
    >  <span data-ttu-id="47037-132">В некоторых базах данных проверочные ограничения различаются по функциональности.</span><span class="sxs-lookup"><span data-stu-id="47037-132">Some databases have different functionality for check constraints.</span></span>  
  
5.  <span data-ttu-id="47037-133">Щелкните **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="47037-133">Click **Close**.</span></span>  
  
6.  <span data-ttu-id="47037-134">В меню **Файл** выберите пункт **Сохранить**_table name_.</span><span class="sxs-lookup"><span data-stu-id="47037-134">On the **File** menu, click **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="47037-135">Использование Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="47037-135">Using Transact-SQL</span></span>  
 <span data-ttu-id="47037-136">**Изменение проверочного ограничения**</span><span class="sxs-lookup"><span data-stu-id="47037-136">**To modify a check constraint**</span></span>  
  
 <span data-ttu-id="47037-137">Чтобы изменить ограничение `CHECK` с помощью [!INCLUDE[tsql](../../includes/tsql-md.md)], нужно удалить существующее ограничение `CHECK` и повторно создать его с новым определением.</span><span class="sxs-lookup"><span data-stu-id="47037-137">To modify a `CHECK` constraint using [!INCLUDE[tsql](../../includes/tsql-md.md)], you must first delete the existing `CHECK` constraint and then re-create it with the new definition.</span></span> <span data-ttu-id="47037-138">Дополнительные сведения см. в разделах [Удаление проверочного ограничения](delete-check-constraints.md) и [Создание ограничений CHECK](create-check-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="47037-138">For more information, see [Delete Check Constraints](delete-check-constraints.md) and [Create Check Constraints](create-check-constraints.md).</span></span>  
  
###  <a name="TsqlExample"></a>  
