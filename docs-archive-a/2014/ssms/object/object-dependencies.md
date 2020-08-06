---
title: Зависимости между объектами | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.common.objectdependencies.f1
ms.assetid: c63d1160-3f3d-45df-99be-6fe081125fb5
author: stevestein
ms.author: sstein
ms.openlocfilehash: 13d1775f1e4e6885fe56a43ce40c4ac155c5b361
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750436"
---
# <a name="object-dependencies"></a><span data-ttu-id="9082d-102">Зависимости между объектами</span><span class="sxs-lookup"><span data-stu-id="9082d-102">Object Dependencies</span></span>
  <span data-ttu-id="9082d-103">Некоторые объекты базы данных имеют зависимости от других объектов базы данных.</span><span class="sxs-lookup"><span data-stu-id="9082d-103">Some database objects have dependencies upon other database objects.</span></span> <span data-ttu-id="9082d-104">Например, представления и хранимые процедуры зависят от существования таблиц, содержащих данные, которые возвращаются этими таблицами и процедурами.</span><span class="sxs-lookup"><span data-stu-id="9082d-104">For example, views and stored procedures depend upon the existence of tables that contain the data returned by the view or procedure.</span></span> <span data-ttu-id="9082d-105">В диалоговом окне **Зависимости объекта (страница "Общие")** для текущего объекта перечислены как объекты базы данных, которые необходимы для правильной работы объекта, так и объекты, зависящие от выбранного объекта.</span><span class="sxs-lookup"><span data-stu-id="9082d-105">The **Object Dependencies (General Page)** for the current object lists both the database objects that must be present for the object to function properly and the objects that depend upon the selected object.</span></span> <span data-ttu-id="9082d-106">Объект, определение которого содержит ссылку на другой объект и хранится в системном каталоге, называется *ссылающейся сущностью*.</span><span class="sxs-lookup"><span data-stu-id="9082d-106">An object that references another object in its definition and that definition is stored in the system catalog is called a *referencing entity*.</span></span> <span data-ttu-id="9082d-107">Объект, на который ссылается другой объект, называется *упоминаемой сущностью*.</span><span class="sxs-lookup"><span data-stu-id="9082d-107">An object that is referred to by another object is called a *referenced entity*.</span></span>  
  
 <span data-ttu-id="9082d-108">В диалоговом окне **Зависимости объектов (страница "Дополнительно")** перечисляются для текущего объекта объекты базы данных [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и объекты служб [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , зависящие от этого объекта.</span><span class="sxs-lookup"><span data-stu-id="9082d-108">The **Object Dependencies (Advanced Page)** for the current object lists the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database objects and [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] objects that depend on the object.</span></span> <span data-ttu-id="9082d-109">Объекты могут храниться на разных серверах.</span><span class="sxs-lookup"><span data-stu-id="9082d-109">The objects may be stored on different servers.</span></span>  
  
 <span data-ttu-id="9082d-110">С помощью этого диалогового окна можно проанализировать зависимости перед изменением или удалением выбранного объекта.</span><span class="sxs-lookup"><span data-stu-id="9082d-110">Use this dialog box to understand the dependencies before changing or deleting the selected object.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="9082d-111">Список элементов пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="9082d-111">UI element list</span></span>  
 <span data-ttu-id="9082d-112">**Объекты, зависящие от**  _\<selected object>_</span><span class="sxs-lookup"><span data-stu-id="9082d-112">**Objects that depend on**  _\<selected object>_</span></span>  
 <span data-ttu-id="9082d-113">После нажатия этой кнопки на экран выводится список объектов, которые отслеживаются по зависимостям и зависят от выбранного объекта.</span><span class="sxs-lookup"><span data-stu-id="9082d-113">Clicking this button displays a list of those objects that are dependency-tracked and that depend on the selected object.</span></span>  
  
 <span data-ttu-id="9082d-114">**Объекты, для которых** _\<selected object>_ **зависит от**    </span><span class="sxs-lookup"><span data-stu-id="9082d-114">**Objects on which**  _\<selected object>_  **depends**</span></span>  
 <span data-ttu-id="9082d-115">После нажатия этой кнопки на экран выводится список объектов, которые отслеживаются по зависимостям и зависят от выбранного объекта.</span><span class="sxs-lookup"><span data-stu-id="9082d-115">Clicking this button displays a list of those objects that are dependency-tracked, on which the selected object depends.</span></span>  
  
 <span data-ttu-id="9082d-116">**Зависимости**</span><span class="sxs-lookup"><span data-stu-id="9082d-116">**Dependencies**</span></span>  
 <span data-ttu-id="9082d-117">Если щелкнуть **Объекты, которые зависят от** _\<selected object>_ , на экране отобразится иерархическое представление объектов, которые зависят от выделенного объекта.</span><span class="sxs-lookup"><span data-stu-id="9082d-117">If **Objects that depend on** _\<selected object>_ is clicked, this displays an hierarchical view of objects that depend on the selected object.</span></span> <span data-ttu-id="9082d-118">Если щелкнуть **Объекты, от которых** **зависит** _\<selected object>_ , на экране отобразиться иерархическое представление объектов, от которых зависит выбранный объект.</span><span class="sxs-lookup"><span data-stu-id="9082d-118">If **Objects on which** _\<selected object>_ **depends** is clicked, this displays an hierarchical view of objects on which the selected object depends.</span></span>  
  
 <span data-ttu-id="9082d-119">**имя**;</span><span class="sxs-lookup"><span data-stu-id="9082d-119">**Name**</span></span>  
 <span data-ttu-id="9082d-120">Имя объекта, выбранного в описанном выше иерархическом представлении **Зависимости** .</span><span class="sxs-lookup"><span data-stu-id="9082d-120">Displays the name of the object selected in the **Dependencies** tree view above.</span></span>  
  
 <span data-ttu-id="9082d-121">**Тип**</span><span class="sxs-lookup"><span data-stu-id="9082d-121">**Type**</span></span>  
 <span data-ttu-id="9082d-122">Имя объекта, выбранного в описанном выше представлении **Зависимости** в виде дерева.</span><span class="sxs-lookup"><span data-stu-id="9082d-122">Displays the type of the object selected in the **Dependencies** tree view above.</span></span>  
  
 <span data-ttu-id="9082d-123">**Last Sync Time**</span><span class="sxs-lookup"><span data-stu-id="9082d-123">**Last Sync Time**</span></span>  
 > [!NOTE]  
>  <span data-ttu-id="9082d-124">Этот параметр доступен только на странице **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="9082d-124">This option is available only on the **Advanced** page.</span></span>  
  
 <span data-ttu-id="9082d-125">Задает дату и время последнего обновления сведений о зависимостях.</span><span class="sxs-lookup"><span data-stu-id="9082d-125">Specifies the time and date when the dependency information was last updated.</span></span>  
  
 <span data-ttu-id="9082d-126">**Тип зависимости**</span><span class="sxs-lookup"><span data-stu-id="9082d-126">**Dependency type**</span></span>  
 > [!NOTE]  
>  <span data-ttu-id="9082d-127">Этот параметр доступен только на странице **Общие** .</span><span class="sxs-lookup"><span data-stu-id="9082d-127">This option is available only on the **General** page.</span></span>  
  
 <span data-ttu-id="9082d-128">Отображает тип зависимости между двумя объектами.</span><span class="sxs-lookup"><span data-stu-id="9082d-128">Displays the type of dependency between two objects.</span></span> <span data-ttu-id="9082d-129">Может применяться один из перечисленных ниже типов.</span><span class="sxs-lookup"><span data-stu-id="9082d-129">Can be one of the following:</span></span>  
  
-   <span data-ttu-id="9082d-130">Зависимость, привязанная к схеме</span><span class="sxs-lookup"><span data-stu-id="9082d-130">Schema-bound dependency</span></span>  
  
     <span data-ttu-id="9082d-131">Связь между двумя объектами, которая не позволяет удалить или изменить объект ссылки, если существует ссылающийся объект.</span><span class="sxs-lookup"><span data-stu-id="9082d-131">Is a relationship between two objects that prevents the referenced object from being dropped or modified as long as the referencing object exists.</span></span> <span data-ttu-id="9082d-132">Привязанная к схеме зависимость создается, когда с помощью предложения WITH SCHEMABINDING создается представление или определяемая пользователем функция, или когда таблица ссылается на другой объект в ограничении CHECK или DEFAULT либо в определении вычисляемого столбца.</span><span class="sxs-lookup"><span data-stu-id="9082d-132">A schema-bound dependency is created when a view or user-defined function is created by using the WITH SCHEMABINDING clause, or when a table references another object through a CHECK or DEFAULT constraint or in the definition of a computed column.</span></span>  
  
-   <span data-ttu-id="9082d-133">Зависимость без привязки к схеме</span><span class="sxs-lookup"><span data-stu-id="9082d-133">Non-schema-bound dependency</span></span>  
  
     <span data-ttu-id="9082d-134">Связь между двумя объектами, которая не мешает удалить или изменить объект ссылки.</span><span class="sxs-lookup"><span data-stu-id="9082d-134">Is a relationship between two objects that does not prevent the referenced object from being dropped or modified.</span></span>  
  
-   <span data-ttu-id="9082d-135">Сущность недоступна или не разрешена</span><span class="sxs-lookup"><span data-stu-id="9082d-135">Not available or Unresolved Entity</span></span>  
  
     <span data-ttu-id="9082d-136">Указывает, что тип зависимости определить невозможно.</span><span class="sxs-lookup"><span data-stu-id="9082d-136">Indicates the dependency type cannot be determined.</span></span> <span data-ttu-id="9082d-137">Это происходит, если выбранный объект находится в экземпляре [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , имеющем более раннюю версию, чем [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9082d-137">This occurs only when the selected object is on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is earlier than [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
  
