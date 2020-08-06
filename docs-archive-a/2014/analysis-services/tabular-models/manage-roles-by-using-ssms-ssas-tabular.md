---
title: Управление ролями с помощью SSMS (табличные службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 652faac0-1cfc-438b-8119-2f4b090a2381
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4ee34d5e75d5d4ce3679d46d29af3215852d2bbe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728805"
---
# <a name="manage-roles-by-using-ssms-ssas-tabular"></a><span data-ttu-id="d61c0-102">Управление ролями с помощью среды SSMS (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="d61c0-102">Manage Roles by using SSMS (SSAS Tabular)</span></span>
  <span data-ttu-id="d61c0-103">С помощью [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]можно создавать, изменять роли развернутой табличной модели или управлять ими.</span><span class="sxs-lookup"><span data-stu-id="d61c0-103">You can create, edit, and manage roles for a deployed tabular model by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="d61c0-104">Задачи данной темы:</span><span class="sxs-lookup"><span data-stu-id="d61c0-104">Tasks in this topic:</span></span>  
  
-   [<span data-ttu-id="d61c0-105">Создание новой роли</span><span class="sxs-lookup"><span data-stu-id="d61c0-105">To create a new role</span></span>](#bkmk_new_role)  
  
-   [<span data-ttu-id="d61c0-106">Копирование роли</span><span class="sxs-lookup"><span data-stu-id="d61c0-106">To copy a role</span></span>](#bkmk_copy_role)  
  
-   [<span data-ttu-id="d61c0-107">Изменение роли</span><span class="sxs-lookup"><span data-stu-id="d61c0-107">To edit a role</span></span>](#bkmk_edit_role)  
  
-   [<span data-ttu-id="d61c0-108">Удаление роли</span><span class="sxs-lookup"><span data-stu-id="d61c0-108">To delete a role</span></span>](#bkmk_deletet_role)  
  
> [!CAUTION]  
>  <span data-ttu-id="d61c0-109">Повторное развертывание проекта табличной модели с ролями, определенными с помощью диспетчера ролей в среде [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] , приводит к перезаписи ролей, определенных в развернутой табличной модели.</span><span class="sxs-lookup"><span data-stu-id="d61c0-109">Re-deploying a tabular model project with roles defined by using Role Manager in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] will overwrite roles defined in a deployed tabular model.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="d61c0-110">Использование среды [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] для управления базой данных рабочей области табличной модели, когда проект открыт в среде [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] , может привести к повреждению файла Model.bim.</span><span class="sxs-lookup"><span data-stu-id="d61c0-110">Using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to manage a tabular model workspace database while the model project is open in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] may cause the Model.bim file to become corrupted.</span></span> <span data-ttu-id="d61c0-111">При создании ролей и управлении ими в базе данных рабочей области табличной модели пользуйтесь диспетчером ролей среды [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d61c0-111">When creating and managing roles for a tabular model workspace database, use Role Manager in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span>  
  
###  <a name="to-create-a-new-role"></a><a name="bkmk_new_role"></a> <span data-ttu-id="d61c0-112">Создание новой роли</span><span class="sxs-lookup"><span data-stu-id="d61c0-112">To create a new role</span></span>  
  
1.  <span data-ttu-id="d61c0-113">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]разверните табличный шаблон баз данных, для которого требуется создать новую роль, щелкните правой кнопкой мыши **Роли**и выберите пункт **Создать роль**.</span><span class="sxs-lookup"><span data-stu-id="d61c0-113">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the tabular model database for which you want to create a new role, then right click on **Roles**, and then click **New Role**.</span></span>  
  
2.  <span data-ttu-id="d61c0-114">В диалоговом окне **Создание роли** в окне «Выбор страницы» щелкните **Общие**.</span><span class="sxs-lookup"><span data-stu-id="d61c0-114">In the **Create Role** dialog box, in the Select a page window, click **General**.</span></span>  
  
3.  <span data-ttu-id="d61c0-115">В окне общих параметров введите имя роли в поле **Имя** .</span><span class="sxs-lookup"><span data-stu-id="d61c0-115">In the general settings window, in the **Name** field, type a name for the role.</span></span>  
  
     <span data-ttu-id="d61c0-116">По умолчанию к имени роли, заданному по умолчанию, будет добавляться номер, последовательно увеличивающийся для каждой новой роли.</span><span class="sxs-lookup"><span data-stu-id="d61c0-116">By default, the name of the default role will be incrementally numbered for each new role.</span></span> <span data-ttu-id="d61c0-117">Рекомендуется ввести имя, ясно определяющее тип члена, например «Финансовые менеджеры» или «Специалисты по кадрам».</span><span class="sxs-lookup"><span data-stu-id="d61c0-117">It is recommended you type a name that clearly identifies the member type, for example, Finance Managers or Human Resources Specialists.</span></span>  
  
4.  <span data-ttu-id="d61c0-118">В поле **Разрешения базы данных для этой роли**выберите один из следующих параметров разрешений.</span><span class="sxs-lookup"><span data-stu-id="d61c0-118">In **Set the database permissions for this role**, select one of the following permissions options:</span></span>  
  
    |<span data-ttu-id="d61c0-119">Разрешение</span><span class="sxs-lookup"><span data-stu-id="d61c0-119">Permission</span></span>|<span data-ttu-id="d61c0-120">Описание</span><span class="sxs-lookup"><span data-stu-id="d61c0-120">Description</span></span>|  
    |----------------|-----------------|  
    |<span data-ttu-id="d61c0-121">**Полный доступ (администратор)**</span><span class="sxs-lookup"><span data-stu-id="d61c0-121">**Full control (Administrator)**</span></span>|<span data-ttu-id="d61c0-122">Члены могут вносить изменения в схему модели, а также просматривать все данные.</span><span class="sxs-lookup"><span data-stu-id="d61c0-122">Members can make modifications to the model schema and can view all data.</span></span>|  
    |<span data-ttu-id="d61c0-123">**Process Database**</span><span class="sxs-lookup"><span data-stu-id="d61c0-123">**Process database**</span></span>|<span data-ttu-id="d61c0-124">Члены могут выполнять операции «Обработать» и «Обработать все».</span><span class="sxs-lookup"><span data-stu-id="d61c0-124">Members can run Process and Process All operations.</span></span> <span data-ttu-id="d61c0-125">Не могут изменять схему модели и просматривать данные.</span><span class="sxs-lookup"><span data-stu-id="d61c0-125">Cannot modify the model schema and cannot view data.</span></span>|  
    |<span data-ttu-id="d61c0-126">**Чтение**</span><span class="sxs-lookup"><span data-stu-id="d61c0-126">**Read**</span></span>|<span data-ttu-id="d61c0-127">Члены могут просматривать данные (с учетом фильтров строк), но не могут вносить изменения в схему модели.</span><span class="sxs-lookup"><span data-stu-id="d61c0-127">Members are allowed to view data (based on row filters) but cannot make any changes to the model schema.</span></span>|  
  
5.  <span data-ttu-id="d61c0-128">В диалоговом окне **Создание роли** в окне «Выбор страницы» щелкните **Членство**.</span><span class="sxs-lookup"><span data-stu-id="d61c0-128">In the **Create Role** dialog box, in the Select a page window, click **Membership**.</span></span>  
  
6.  <span data-ttu-id="d61c0-129">В окне параметров членства выберите **Добавить**и затем в диалоговом окне **Выбор пользователей или групп** добавьте нужных пользователей или группы Windows в качестве членов.</span><span class="sxs-lookup"><span data-stu-id="d61c0-129">In the membership settings window, click **Add**, and then in the **Select Users or Groups** dialog box, add the Windows users or groups you want to add as members.</span></span>  
  
7.  <span data-ttu-id="d61c0-130">Если у создаваемой роли есть разрешение «Чтение», добавлять фильтры строк для любой таблицы можно с помощью формулы DAX.</span><span class="sxs-lookup"><span data-stu-id="d61c0-130">If the role you are creating has Read permissions, you can add row filters for any table using a DAX formula.</span></span> <span data-ttu-id="d61c0-131">Чтобы добавить фильтры строк, в диалоговом окне **свойства \<rolename> роли —** на **странице Выбор страницы**щелкните элемент **фильтры строк**.</span><span class="sxs-lookup"><span data-stu-id="d61c0-131">To add row filters, in the **Role Properties - \<rolename>** dialog box, in **Select a page**, click on **Row Filters**.</span></span>  
  
8.  <span data-ttu-id="d61c0-132">В окне Фильтры строк выберите таблицу, а затем щелкните поле **Фильтр DAX** , а затем в поле \*\* \<tablename> Фильтр DAX\*\* введите формулу DAX.</span><span class="sxs-lookup"><span data-stu-id="d61c0-132">In the row filters window, select a table, then click on the **DAX Filter** field, and then in the **DAX Filter - \<tablename>** field, type a DAX formula.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d61c0-133">Поле фильтра DAX \<tablename> не содержит редактор запросов автозаполнения или функцию вставки функции.</span><span class="sxs-lookup"><span data-stu-id="d61c0-133">The DAX Filter - \<tablename> field does not contain an AutoComplete query editor or insert function feature.</span></span> <span data-ttu-id="d61c0-134">Чтобы использовать автозаполнение при написании DAX-формулы, следует использовать редактор DAX-формул в среде [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d61c0-134">To use AutoComplete when writing a DAX formula, you must use a DAX formula editor in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span>  
  
9. <span data-ttu-id="d61c0-135">Для сохранения роли нажмите кнопку **OК** .</span><span class="sxs-lookup"><span data-stu-id="d61c0-135">Click **Ok** to save the role.</span></span>  
  
###  <a name="to-copy-a-role"></a><a name="bkmk_copy_role"></a> <span data-ttu-id="d61c0-136">Копирование роли</span><span class="sxs-lookup"><span data-stu-id="d61c0-136">To copy a role</span></span>  
  
1.  <span data-ttu-id="d61c0-137">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]разверните шаблон базы данных, содержащий роль, которую нужно скопировать, разверните **Роли**, щелкните правой кнопкой мыши роль и выберите команду **Создать копию**.</span><span class="sxs-lookup"><span data-stu-id="d61c0-137">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the tabular model database that contains the role you want to copy, then expand **Roles**, then right click on the role, and then click **Duplicate**.</span></span>  
  
###  <a name="to-edit-a-role"></a><a name="bkmk_edit_role"></a><span data-ttu-id="d61c0-138">Изменение роли</span><span class="sxs-lookup"><span data-stu-id="d61c0-138">To edit a role</span></span>  
  
-   <span data-ttu-id="d61c0-139">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]разверните табличный шаблон базы данных, содержащий роль, которую нужно изменить, разверните **Роли**, щелкните правой кнопкой мыши роль и выберите команду **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="d61c0-139">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the tabular model database that contains the role you want to edit, then expand **Roles**, then right click on the role, and then click **Properties**.</span></span>  
  
     <span data-ttu-id="d61c0-140">В диалоговом окне **Свойства роли** \<rolename> можно изменить разрешения, добавить или удалить членов, а также добавить или изменить фильтры строк.</span><span class="sxs-lookup"><span data-stu-id="d61c0-140">In the **Role Properties** \<rolename> dialog box, you can change permissions, add or remove members, and add/edit row filters.</span></span>  
  
###  <a name="to-delete-a-role"></a><a name="bkmk_deletet_role"></a><span data-ttu-id="d61c0-141">Удаление роли</span><span class="sxs-lookup"><span data-stu-id="d61c0-141">To delete a role</span></span>  
  
-   <span data-ttu-id="d61c0-142">В среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]разверните шаблон базы данных, содержащий роль, которую нужно удалить, разверните **Роли**, щелкните правой кнопкой мыши роль и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="d61c0-142">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the tabular model database that contains the role you want to delete, then expand **Roles**, then right click on the role, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d61c0-143">См. также:</span><span class="sxs-lookup"><span data-stu-id="d61c0-143">See Also</span></span>  
 [<span data-ttu-id="d61c0-144">Роли (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="d61c0-144">Roles &#40;SSAS Tabular&#41;</span></span>](roles-ssas-tabular.md)  
  
  
