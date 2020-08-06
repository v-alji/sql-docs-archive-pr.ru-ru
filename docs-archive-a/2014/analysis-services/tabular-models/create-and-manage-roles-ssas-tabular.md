---
title: Создание ролей и управление ими (табличные службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.rolemanager.f1
- sql12.asvs.bidtoolset.roledb.f1
ms.assetid: e23d27a8-e968-4082-9dbe-963fc724b5d9
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 335e0e311d97ea452449cd0c5d6550f6dbcca4f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656009"
---
# <a name="create-and-manage-roles-ssas-tabular"></a><span data-ttu-id="9e173-102">Создание ролей и управление ими (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="9e173-102">Create and Manage Roles (SSAS Tabular)</span></span>
  <span data-ttu-id="9e173-103">В табличной модели роли определяют разрешения члена для модели.</span><span class="sxs-lookup"><span data-stu-id="9e173-103">Roles, in tabular models, define member permissions for a model.</span></span> <span data-ttu-id="9e173-104">Роли определяются для проекта модели с помощью диалогового окна «Диспетчер ролей» в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9e173-104">Roles are defined for a model project by using the Role Manager dialog box in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="9e173-105">В развернутой модели администраторы баз данных могут управлять ролями с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9e173-105">When a model is deployed, database administrators can manage roles by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="9e173-106">Задачи в этом разделе описывают создание ролей и управление ролями во время создания модели с помощью диалогового окна «Диспетчер ролей» в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9e173-106">The tasks in this topic describe how to create and manage roles during model authoring by using the Role Manager dialog box in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="9e173-107">Сведения об управлении ролями в развернутой базе данных модели см. в разделе [Роли табличных моделей (табличные службы SSAS)](roles-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="9e173-107">For information about managing roles in a deployed model database, see [Tabular Model Roles &#40;SSAS Tabular&#41;](roles-ssas-tabular.md).</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="9e173-108">Задания</span><span class="sxs-lookup"><span data-stu-id="9e173-108">Tasks</span></span>  
 <span data-ttu-id="9e173-109">Создавать, изменять, копировать и удалять роли можно в диалоговом окне **Диспетчер ролей** .</span><span class="sxs-lookup"><span data-stu-id="9e173-109">To create, edit, copy, and delete roles, you will use the **Role Manager** dialog box.</span></span> <span data-ttu-id="9e173-110">Чтобы открыть диалоговое окно **Диспетчер ролей** в среде [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], выберите в меню **Модель** пункт **Диспетчер ролей**.</span><span class="sxs-lookup"><span data-stu-id="9e173-110">To view the **Role Manager** dialog box, in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Model** menu, and then click **Role Manager**.</span></span>  
  
###  <a name="to-create-a-new-role"></a><a name="bkmk_new_role"></a> <span data-ttu-id="9e173-111">Создание новой роли</span><span class="sxs-lookup"><span data-stu-id="9e173-111">To create a new role</span></span>  
  
1.  <span data-ttu-id="9e173-112">В среде [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]откройте меню **Модель** и выберите команду **Диспетчер ролей**.</span><span class="sxs-lookup"><span data-stu-id="9e173-112">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Model** menu, and then click **Role Manager**.</span></span>  
  
2.  <span data-ttu-id="9e173-113">В диалоговом окне **Диспетчер ролей** выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="9e173-113">In the **Role Manager** dialog box, click **New**.</span></span>  
  
     <span data-ttu-id="9e173-114">В список ролей будет добавлена новая выделенная роль.</span><span class="sxs-lookup"><span data-stu-id="9e173-114">A new highlighted role is added to the Roles list.</span></span>  
  
3.  <span data-ttu-id="9e173-115">В списке **Роли** в поле **Имя** введите имя роли.</span><span class="sxs-lookup"><span data-stu-id="9e173-115">In the **Roles** list, in the **Name** field, type a name for the role.</span></span>  
  
     <span data-ttu-id="9e173-116">По умолчанию к имени роли, заданному по умолчанию, будет добавляться номер, последовательно увеличивающийся для каждой новой роли.</span><span class="sxs-lookup"><span data-stu-id="9e173-116">By default, the name of the default role will be incrementally numbered for each new role.</span></span> <span data-ttu-id="9e173-117">Рекомендуется ввести имя, ясно определяющее тип члена, например «Финансовые менеджеры» или «Специалисты по кадрам».</span><span class="sxs-lookup"><span data-stu-id="9e173-117">It is recommended you type a name that clearly identifies the member type, for example, Finance Managers or Human Resources Specialists.</span></span>  
  
4.  <span data-ttu-id="9e173-118">В поле **Разрешения** щелкните стрелку вниз и выберите один из следующих типов разрешения.</span><span class="sxs-lookup"><span data-stu-id="9e173-118">In the **Permissions** field, click the down arrow and then select one of the following permission types:</span></span>  
  
    |<span data-ttu-id="9e173-119">Разрешение</span><span class="sxs-lookup"><span data-stu-id="9e173-119">Permission</span></span>|<span data-ttu-id="9e173-120">Описание</span><span class="sxs-lookup"><span data-stu-id="9e173-120">Description</span></span>|  
    |----------------|-----------------|  
    |<span data-ttu-id="9e173-121">**None**</span><span class="sxs-lookup"><span data-stu-id="9e173-121">**None**</span></span>|<span data-ttu-id="9e173-122">Члены не могут вносить изменения в схему модели и просматривать данные.</span><span class="sxs-lookup"><span data-stu-id="9e173-122">Members cannot make any modifications to the model schema and cannot query data.</span></span>|  
    |<span data-ttu-id="9e173-123">**Чтение**</span><span class="sxs-lookup"><span data-stu-id="9e173-123">**Read**</span></span>|<span data-ttu-id="9e173-124">Члены могут просматривать данные (с учетом фильтров строк), но не могут вносить изменения в схему модели.</span><span class="sxs-lookup"><span data-stu-id="9e173-124">Members are allowed to query data (based on row filters) but cannot make any changes to the model schema.</span></span>|  
    |<span data-ttu-id="9e173-125">**Чтение и обработка**</span><span class="sxs-lookup"><span data-stu-id="9e173-125">**Read and Process**</span></span>|<span data-ttu-id="9e173-126">Члены могут просматривать данные (с учетом фильтров строк), а также выполнять операции «Обработать» и «Обработать все», но не могут вносить изменения в схему модели.</span><span class="sxs-lookup"><span data-stu-id="9e173-126">Members are allowed to query data (based on row-level filters) and run Process and Process All operations, but cannot make any changes to the model schema.</span></span>|  
    |<span data-ttu-id="9e173-127">**Process**</span><span class="sxs-lookup"><span data-stu-id="9e173-127">**Process**</span></span>|<span data-ttu-id="9e173-128">Члены могут выполнять операции «Обработать» и «Обработать все».</span><span class="sxs-lookup"><span data-stu-id="9e173-128">Members can run Process and Process All operations.</span></span> <span data-ttu-id="9e173-129">Не могут изменять схему модели и просматривать данные.</span><span class="sxs-lookup"><span data-stu-id="9e173-129">Cannot modify the model schema and cannot query data.</span></span>|  
    |<span data-ttu-id="9e173-130">**Администратор**</span><span class="sxs-lookup"><span data-stu-id="9e173-130">**Administrator**</span></span>|<span data-ttu-id="9e173-131">Члены могут вносить изменения в схему модели и просматривать все данные.</span><span class="sxs-lookup"><span data-stu-id="9e173-131">Members can make modifications to the model schema and can query all data.</span></span>|  
  
5.  <span data-ttu-id="9e173-132">Чтобы ввести описание роли, щелкните поле **Описание** и введите описание.</span><span class="sxs-lookup"><span data-stu-id="9e173-132">To enter a description for the role, click the **Description** field, and then type a description.</span></span>  
  
6.  <span data-ttu-id="9e173-133">Если у создаваемой роли есть разрешение «Чтение» или «Чтение и обработка», можно добавить фильтры строк с помощью формулы DAX.</span><span class="sxs-lookup"><span data-stu-id="9e173-133">If the role you are creating has Read or Read and Process permission, you can add row filters using a DAX formula.</span></span> <span data-ttu-id="9e173-134">Чтобы добавить фильтры строк, перейдите на вкладку **Фильтры строк** , выберите таблицу, щелкните поле **Фильтр DAX** и введите формулу DAX.</span><span class="sxs-lookup"><span data-stu-id="9e173-134">To add row filters, click the **Row Filters** tab, then select a table, then click the **DAX Filter** field, and then type a DAX formula.</span></span>  
  
7.  <span data-ttu-id="9e173-135">Чтобы добавить членов роли, перейдите на вкладку **Члены** и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="9e173-135">To add members to the role, click the **Members** tab, and then click **Add**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9e173-136">Членов роли также можно добавлять в развернутую модель с помощью среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9e173-136">Role members can also be added to a deployed model by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="9e173-137">Дополнительные сведения см. в разделе [Управление ролями с помощью среды SSMS (табличные службы SSAS)](manage-roles-by-using-ssms-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="9e173-137">For more information, see [Manage Roles by using SSMS &#40;SSAS Tabular&#41;](manage-roles-by-using-ssms-ssas-tabular.md).</span></span>  
  
8.  <span data-ttu-id="9e173-138">В диалоговом окне **Выбор пользователей или групп** введите объекты пользователя или группы Windows в качестве членов.</span><span class="sxs-lookup"><span data-stu-id="9e173-138">In the **Select Users or Groups** dialog box, enter Windows user or Windows group objects as members.</span></span>  
  
9. <span data-ttu-id="9e173-139">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9e173-139">Click **Ok**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e173-140">См. также</span><span class="sxs-lookup"><span data-stu-id="9e173-140">See Also</span></span>  
 <span data-ttu-id="9e173-141">[Роли &#40;табличные&#41;SSAS](roles-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="9e173-141">[Roles &#40;SSAS Tabular&#41;](roles-ssas-tabular.md) </span></span>  
 <span data-ttu-id="9e173-142">[Перспективы &#40;табличные&#41;SSAS](perspectives-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="9e173-142">[Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md) </span></span>  
 <span data-ttu-id="9e173-143">[Анализ в Excel &#40;табличные&#41;SSAS](analyze-in-excel-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="9e173-143">[Analyze in Excel &#40;SSAS Tabular&#41;](analyze-in-excel-ssas-tabular.md) </span></span>  
 <span data-ttu-id="9e173-144">[Функция USERNAME &#40;DAX&#41;](/dax/username-function-dax) </span><span class="sxs-lookup"><span data-stu-id="9e173-144">[USERNAME Function &#40;DAX&#41;](/dax/username-function-dax) </span></span>  
 [<span data-ttu-id="9e173-145">CUSTOMDATA &#40;DAX&#41;</span><span class="sxs-lookup"><span data-stu-id="9e173-145">CUSTOMDATA Function &#40;DAX&#41;</span></span>](/dax/customdata-function-dax)  
  
  
