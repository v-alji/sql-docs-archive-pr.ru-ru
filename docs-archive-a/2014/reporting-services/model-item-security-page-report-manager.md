---
title: Страница «Безопасность элементов модели» (диспетчер отчетов) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.modelproperties.modelitemsecurity.f1
ms.assetid: 8c5b29ae-1f17-41f2-ab59-97899b8fb4fc
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 928572437990c7f7fe1117c086c65c939aa9c999
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654895"
---
# <a name="model-item-security-page-report-manager"></a><span data-ttu-id="4ecd2-102">Страница «Безопасность элементов модели» (диспетчер отчетов)</span><span class="sxs-lookup"><span data-stu-id="4ecd2-102">Model Item Security Page (Report Manager)</span></span>
  <span data-ttu-id="4ecd2-103">На этой странице можно защитить элементы модели, предоставляя или отменяя разрешения «только для чтения» в отношении определенных элементов.</span><span class="sxs-lookup"><span data-stu-id="4ecd2-103">Use this page to secure parts of a model by granting or revoking read-only permissions on particular items.</span></span> <span data-ttu-id="4ecd2-104">Безопасность элементов модели определяет порядок нерегламентированного просмотра данных во время выполнения и возможность использования элементов опубликованной модели при создании отчетов в построителе отчетов.</span><span class="sxs-lookup"><span data-stu-id="4ecd2-104">Model item security affects ad hoc data exploration at run time and the ability to use parts of a published model when creating reports in Report Builder.</span></span> <span data-ttu-id="4ecd2-105">Для использования этой функции необходимы разрешения диспетчера содержимого.</span><span class="sxs-lookup"><span data-stu-id="4ecd2-105">To use this feature, you must have Content Manager permissions.</span></span>  
  
 <span data-ttu-id="4ecd2-106">Безопасность элементов модели применяется к модели, которая обрабатывается на сервере отчетов, и не влияет на SMDL-файлы, изменяемые в конструкторе моделей или используемые в конструкторе отчетов.</span><span class="sxs-lookup"><span data-stu-id="4ecd2-106">Model item security is applied to a model that is processed on the report server and does not affect .smdl files that you edit in Model Designer or use in Report Designer.</span></span> <span data-ttu-id="4ecd2-107">Более того, она не применяется к пользователям, имеющим разрешения на изменение определения модели.</span><span class="sxs-lookup"><span data-stu-id="4ecd2-107">Furthermore, it has no effect on users who have permission to modify a model definition.</span></span> <span data-ttu-id="4ecd2-108">Любому пользователю, имеющему для модели разрешения &#0171;</ph>Диспетчер содержимого&#0187;</ph> или &#0171;</ph>Издатель&#0187;</ph>, доступны все ее части независимо от того, применяется ли безопасность элементов модели.</span><span class="sxs-lookup"><span data-stu-id="4ecd2-108">Any user who has Content Manager or Publisher permissions on a model can see all parts of it, regardless of whether you apply model item security.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4ecd2-109">Элементы модели могут иметь дополнительную защиту благодаря использованию фильтров безопасности.</span><span class="sxs-lookup"><span data-stu-id="4ecd2-109">Model items can be further secured through the use of security filters.</span></span>  
  
 <span data-ttu-id="4ecd2-110">Безопасность элементов модели можно определить для сущностей, папок и отдельных полей в рамках модели.</span><span class="sxs-lookup"><span data-stu-id="4ecd2-110">You can define model item security on entities, folders, and individual fields within a model.</span></span> <span data-ttu-id="4ecd2-111">Поскольку модель содержит большое количество защищаемых элементов, наследование разрешений встроено в модель, что позволяет обеспечить защиту большого количества элементов с помощью относительно небольшого количества назначений ролей.</span><span class="sxs-lookup"><span data-stu-id="4ecd2-111">Because a model presents such a large surface of securable items, permission inheritance is built into the model so that you can secure a large number of items through a relatively small number of role assignments.</span></span> <span data-ttu-id="4ecd2-112">Наследование разрешений основано на следующем.</span><span class="sxs-lookup"><span data-stu-id="4ecd2-112">Permission inheritance is based on the following:</span></span>  
  
-   <span data-ttu-id="4ecd2-113">Модель</span><span class="sxs-lookup"><span data-stu-id="4ecd2-113">Model</span></span>  
  
-   <span data-ttu-id="4ecd2-114">Корневой узел</span><span class="sxs-lookup"><span data-stu-id="4ecd2-114">Root node</span></span>  
  
-   <span data-ttu-id="4ecd2-115">Папки или сущности</span><span class="sxs-lookup"><span data-stu-id="4ecd2-115">Folders or entities</span></span>  
  
-   <span data-ttu-id="4ecd2-116">Поля</span><span class="sxs-lookup"><span data-stu-id="4ecd2-116">Fields</span></span>  
  
 <span data-ttu-id="4ecd2-117">Изначально разрешения на доступ к элементам модели наследуется через назначения ролей, задаваемые для самой модели.</span><span class="sxs-lookup"><span data-stu-id="4ecd2-117">Initially, permission to access to model items is inherited through role assignments that are set on the model itself.</span></span> <span data-ttu-id="4ecd2-118">Пользователь, имеющий разрешение просматривать модель в папке диспетчера отчетов, может просмотреть все элементы этой модели.</span><span class="sxs-lookup"><span data-stu-id="4ecd2-118">A user who has permission to view a model in a folder in Report Manager can view all of the items in the model.</span></span>  
  
 <span data-ttu-id="4ecd2-119">После включения защиты элементов модели необходимо создать, по крайней мере, одно назначение ролей для корневого узла.</span><span class="sxs-lookup"><span data-stu-id="4ecd2-119">If you apply model item security, you must create at least one role assignment on the root node.</span></span> <span data-ttu-id="4ecd2-120">Это исходное назначение ролей на корневом узле становится новым источником наследуемых разрешений.</span><span class="sxs-lookup"><span data-stu-id="4ecd2-120">This initial role assignment on the root node becomes the new source of inherited permissions.</span></span> <span data-ttu-id="4ecd2-121">Оно автоматически наследуется всеми элементами в иерархии модели.</span><span class="sxs-lookup"><span data-stu-id="4ecd2-121">The role assignment on the root node is automatically inherited by all items in the model hierarchy.</span></span>  
  
 <span data-ttu-id="4ecd2-122">Чтобы выполнить дальнейшую настройку разрешений на просмотр данных, можно изменять разрешения для папок и сущностей.</span><span class="sxs-lookup"><span data-stu-id="4ecd2-122">To further customize permissions on data exploration, you can vary permissions on folders and entities.</span></span> <span data-ttu-id="4ecd2-123">И наконец, можно установить разрешения для отдельных полей.</span><span class="sxs-lookup"><span data-stu-id="4ecd2-123">Finally, you can set permissions on individual fields.</span></span>  
  
 <span data-ttu-id="4ecd2-124">Чтобы упростить обслуживание, связанное с назначениями ролей, вместо отдельных полей разрешения следует создавать для папок и сущностей.</span><span class="sxs-lookup"><span data-stu-id="4ecd2-124">To make role assignments easier to maintain, set permissions only on folders or entities rather than individual fields.</span></span> <span data-ttu-id="4ecd2-125">Поиск созданных назначений ролей не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="4ecd2-125">You cannot search for role assignments that you create.</span></span> <span data-ttu-id="4ecd2-126">Если для конкретных полей установлены настройки безопасности и в дальнейшем необходимо обновить эти настройки, нужно будет прощелкать все пространство имен модели для поиска полей с примененными настройками безопасности.</span><span class="sxs-lookup"><span data-stu-id="4ecd2-126">If you set security on specific fields and you want to update the security settings later, you must click through the model namespace to find the fields you secured.</span></span>  
  
 <span data-ttu-id="4ecd2-127">Для начала создайте назначение роли на корневом узле, после чего создайте дополнительные назначения ролей для сущностей и папок.</span><span class="sxs-lookup"><span data-stu-id="4ecd2-127">To get started, create a role assignment on the root node and then create additional role assignments on entities and folders.</span></span> <span data-ttu-id="4ecd2-128">Чтобы отменить защиту элементов модели, снимите флажок **Обеспечивать индивидуальную безопасность отдельных элементов этой модели**.</span><span class="sxs-lookup"><span data-stu-id="4ecd2-128">To clear model item security, clear the check box for **Secure individual model items independently for this model**.</span></span> <span data-ttu-id="4ecd2-129">Снятие этого флажка восстанавливает исходные разрешения, унаследованные от модели.</span><span class="sxs-lookup"><span data-stu-id="4ecd2-129">Clearing the check box reverts back to the initial permissions that are inherited from the model.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="4ecd2-130">Навигация</span><span class="sxs-lookup"><span data-stu-id="4ecd2-130">Navigation</span></span>  
 <span data-ttu-id="4ecd2-131">Чтобы перейти к этому местоположению в пользовательском интерфейсе, используйте следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="4ecd2-131">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-general-properties-page-for-a-report"></a><span data-ttu-id="4ecd2-132">Открытие страницы свойств отчета «Общие»</span><span class="sxs-lookup"><span data-stu-id="4ecd2-132">To open the General properties page for a report</span></span>  
  
1.  <span data-ttu-id="4ecd2-133">Откройте диспетчер отчетов и найдите модель, для которой необходимо настроить защиту элементов модели.</span><span class="sxs-lookup"><span data-stu-id="4ecd2-133">Open Report Manager, and locate the model for which you want to configure security for model items.</span></span>  
  
2.  <span data-ttu-id="4ecd2-134">Подведите курсор к модели и щелкните стрелку раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="4ecd2-134">Hover over the model, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="4ecd2-135">В раскрывающемся меню выберите **Управление**.</span><span class="sxs-lookup"><span data-stu-id="4ecd2-135">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="4ecd2-136">Откроется страница свойств модели «Общие».</span><span class="sxs-lookup"><span data-stu-id="4ecd2-136">This opens the General properties page for the model.</span></span>  
  
4.  <span data-ttu-id="4ecd2-137">Перейдите на вкладку **Безопасность элементов модели** .</span><span class="sxs-lookup"><span data-stu-id="4ecd2-137">Select the **Model Item Security** tab.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4ecd2-138">Варианты</span><span class="sxs-lookup"><span data-stu-id="4ecd2-138">Options</span></span>  
 <span data-ttu-id="4ecd2-139">**Обеспечивать индивидуальную безопасность отдельных элементов этой модели**</span><span class="sxs-lookup"><span data-stu-id="4ecd2-139">**Secure individual model items independently for this model**</span></span>  
 <span data-ttu-id="4ecd2-140">Щелкните этот флажок, чтобы включить безопасность элемента модели.</span><span class="sxs-lookup"><span data-stu-id="4ecd2-140">Click this check box to enable model item security.</span></span>  
  
 <span data-ttu-id="4ecd2-141">**Задать настройки безопасности для отдельных элементов модели**</span><span class="sxs-lookup"><span data-stu-id="4ecd2-141">**Specify security for individual model items in the mode**</span></span>  
 <span data-ttu-id="4ecd2-142">Показывает все элементы модели.</span><span class="sxs-lookup"><span data-stu-id="4ecd2-142">Shows all of the items in a model.</span></span> <span data-ttu-id="4ecd2-143">Можно осуществлять навигацию по пространству имен модели для выбора элемента, безопасность которого требуется настроить.</span><span class="sxs-lookup"><span data-stu-id="4ecd2-143">You can navigate the model namespace to select the item you want to secure.</span></span> <span data-ttu-id="4ecd2-144">Одновременно можно выбрать только один элемент.</span><span class="sxs-lookup"><span data-stu-id="4ecd2-144">You can only select one item at a time.</span></span> <span data-ttu-id="4ecd2-145">Прежде чем переходить к другим сущностям и папкам, убедитесь в создании назначения ролей для корневого элемента.</span><span class="sxs-lookup"><span data-stu-id="4ecd2-145">Be sure to create the first role assignment on the root node before proceeding to other entities and folders.</span></span>  
  
 <span data-ttu-id="4ecd2-146">**Наследовать разрешения от родительского элемента**</span><span class="sxs-lookup"><span data-stu-id="4ecd2-146">**Inherit permissions from the parent item**</span></span>  
 <span data-ttu-id="4ecd2-147">Выберите этот параметр, чтобы унаследовать настройки безопасности родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="4ecd2-147">Click this option to inherit the security settings of the parent item.</span></span>  
  
 <span data-ttu-id="4ecd2-148">**Присвоить разрешение на чтение следующим пользователям и группам (разделенным точкой с запятой)**</span><span class="sxs-lookup"><span data-stu-id="4ecd2-148">**Assign read permission to the following users and groups (semi-colon separated)**</span></span>  
 <span data-ttu-id="4ecd2-149">Выберите этот параметр, чтобы указать учетную запись пользователя или группы, для которой определяется доступ.</span><span class="sxs-lookup"><span data-stu-id="4ecd2-149">Click this option to specify the user or group account for which you are defining access.</span></span> <span data-ttu-id="4ecd2-150">Если используются настройки безопасности по умолчанию, учетные записи пользователей и групп представляют собой учетные записи домена Windows.</span><span class="sxs-lookup"><span data-stu-id="4ecd2-150">If you are using default security, the user and group accounts are Windows domain accounts.</span></span> <span data-ttu-id="4ecd2-151">Укажите учетные записи в следующем формате: \* \<domain> \\<\> учетная запись\*.</span><span class="sxs-lookup"><span data-stu-id="4ecd2-151">Specify the accounts in this format: *\<domain>\\<account\>*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ecd2-152">См. также:</span><span class="sxs-lookup"><span data-stu-id="4ecd2-152">See Also</span></span>  
 [<span data-ttu-id="4ecd2-153">Справка F1 по использованию сервера отчетов среде Management Studio</span><span class="sxs-lookup"><span data-stu-id="4ecd2-153">Report Server in Management Studio F1 Help</span></span>](tools/report-server-in-management-studio-f1-help.md)  
  
  
