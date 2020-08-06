---
title: Создание перспектив и управление ими (табличные службы SSAS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.perspectivedb.f1
ms.assetid: 2a411c2b-2820-4086-ad7f-ce6a941fefc7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6d0029ff61aa05e2e83f34833c3d0af17ddb3beb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87656011"
---
# <a name="create-and-manage-perspectives-ssas-tabular"></a><span data-ttu-id="5e46a-102">Создание перспектив и управление ими (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="5e46a-102">Create and Manage Perspectives (SSAS Tabular)</span></span>
  <span data-ttu-id="5e46a-103">Перспективы определяют просматриваемые подмножества модели, реализующие точки наблюдения модели, которые сосредоточены на определенном аспекте либо предназначены для конкретных деловых целей или использования в конкретном приложении.</span><span class="sxs-lookup"><span data-stu-id="5e46a-103">Perspectives define viewable subsets of a model that provide focused, business-specific, or application-specific viewpoints of the model.</span></span> <span data-ttu-id="5e46a-104">Приведенные в этом разделе задачи описывают создание и управление перспективами с помощью диалогового окна **Перспективы** конструктора моделей.</span><span class="sxs-lookup"><span data-stu-id="5e46a-104">The tasks in this topic describe how to create and manage perspectives by using the **Perspectives** dialog box in the model designer.</span></span>  
  
 <span data-ttu-id="5e46a-105">В этот раздел включены следующее задачи:</span><span class="sxs-lookup"><span data-stu-id="5e46a-105">This topic includes the following tasks:</span></span>  
  
-   [<span data-ttu-id="5e46a-106">Добавление перспективы</span><span class="sxs-lookup"><span data-stu-id="5e46a-106">To add a perspective</span></span>](#bkmk_add)  
  
-   [<span data-ttu-id="5e46a-107">Изменение перспективы</span><span class="sxs-lookup"><span data-stu-id="5e46a-107">To edit a perspective</span></span>](#bkmk_edit)  
  
-   [<span data-ttu-id="5e46a-108">Переименование перспективы</span><span class="sxs-lookup"><span data-stu-id="5e46a-108">To rename a perspective</span></span>](#bkmk_rename)  
  
-   [<span data-ttu-id="5e46a-109">Удаление перспективы</span><span class="sxs-lookup"><span data-stu-id="5e46a-109">To delete a perspective</span></span>](#bkmk_delete)  
  
-   [<span data-ttu-id="5e46a-110">Копирование перспективы</span><span class="sxs-lookup"><span data-stu-id="5e46a-110">To copy a perspective</span></span>](#bkmk_copy)  
  
## <a name="tasks"></a><span data-ttu-id="5e46a-111">Задания</span><span class="sxs-lookup"><span data-stu-id="5e46a-111">Tasks</span></span>  
 <span data-ttu-id="5e46a-112">Для создания перспектив используется диалоговое окно **Перспективы** , которое позволяет добавлять, изменять, удалять, копировать и просматривать перспективы.</span><span class="sxs-lookup"><span data-stu-id="5e46a-112">To create perspectives, you will use the **Perspectives** dialog box, where you can add, edit, delete, copy, and view perspectives.</span></span> <span data-ttu-id="5e46a-113">Чтобы открыть диалоговое окно **Перспективы** , в [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]в меню **Модель** выберите пункт **Перспективы**.</span><span class="sxs-lookup"><span data-stu-id="5e46a-113">To view the **Perspectives** dialog box, in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click on the **Model** menu, and then click **Perspectives**.</span></span>  
  
###  <a name="to-add-a-perspective"></a><a name="bkmk_add"></a> <span data-ttu-id="5e46a-114">Добавление перспективы</span><span class="sxs-lookup"><span data-stu-id="5e46a-114">To add a perspective</span></span>  
  
-   <span data-ttu-id="5e46a-115">Чтобы добавить перспективу, нажмите кнопку **Создать перспективу**.</span><span class="sxs-lookup"><span data-stu-id="5e46a-115">To add a new perspective, click **New Perspective**.</span></span> <span data-ttu-id="5e46a-116">После этого можно установить или снять флажки включаемых в перспективу объектов полей. Также можно указать имя создаваемой перспективы.</span><span class="sxs-lookup"><span data-stu-id="5e46a-116">You can then check and uncheck field objects to be included and provide a name for the new perspective.</span></span>  
  
     <span data-ttu-id="5e46a-117">Если создать пустую перспективу, содержащую все поля объектов полей, то работающий с этой перспективой пользователь увидит пустой список полей.</span><span class="sxs-lookup"><span data-stu-id="5e46a-117">If you create an empty perspective with all of the field object fields, then a user using this perspective will see an empty Field List.</span></span> <span data-ttu-id="5e46a-118">Перспектива должна содержать как минимум одну таблицу и столбец.</span><span class="sxs-lookup"><span data-stu-id="5e46a-118">Perspectives should contain at least one table and column.</span></span>  
  
###  <a name="to-edit-a-perspective"></a><a name="bkmk_edit"></a><span data-ttu-id="5e46a-119">Изменение перспективы</span><span class="sxs-lookup"><span data-stu-id="5e46a-119">To edit a perspective</span></span>  
  
-   <span data-ttu-id="5e46a-120">Чтобы изменить перспективу, установите флажки и снимите флажки в столбцах перспективы, которые добавляют и удаляют объекты полей с точки зрения.</span><span class="sxs-lookup"><span data-stu-id="5e46a-120">To modify a perspective, check and uncheck fields in the perspective's column, which adds and removes field objects from the perspective.</span></span>  
  
###  <a name="to-rename-a-perspective"></a><a name="bkmk_rename"></a><span data-ttu-id="5e46a-121">Переименование перспективы</span><span class="sxs-lookup"><span data-stu-id="5e46a-121">To rename a perspective</span></span>  
  
-   <span data-ttu-id="5e46a-122">При наведении указателя мыши на заголовок столбца перспективы (имя перспективы) появляется кнопка **Переименовать** .</span><span class="sxs-lookup"><span data-stu-id="5e46a-122">When you hover over a perspective's column header (the name of the perspective), the **Rename** button appears.</span></span> <span data-ttu-id="5e46a-123">Для переименования перспективы нажмите кнопку **Переименовать**и введите новое имя или измените существующее.</span><span class="sxs-lookup"><span data-stu-id="5e46a-123">To rename the perspective, click **Rename**, and then enter a new name or edit the existing name.</span></span>  
  
###  <a name="to-delete-a-perspective"></a><a name="bkmk_delete"></a><span data-ttu-id="5e46a-124">Удаление перспективы</span><span class="sxs-lookup"><span data-stu-id="5e46a-124">To delete a perspective</span></span>  
  
-   <span data-ttu-id="5e46a-125">При наведении указателя мыши на заголовок столбца перспективы (имя перспективы) появляется кнопка **Удалить** .</span><span class="sxs-lookup"><span data-stu-id="5e46a-125">When you hover over a perspective's column header (the name of the perspective), the **Delete** button appears.</span></span> <span data-ttu-id="5e46a-126">Для удаления перспективы нажмите кнопку **Удалить** и затем нажмите кнопку **Да** в окне подтверждения.</span><span class="sxs-lookup"><span data-stu-id="5e46a-126">To delete the perspective, click the **Delete** button, and then click **Yes** in the confirmation window.</span></span>  
  
###  <a name="to-copy-a-perspective"></a><a name="bkmk_copy"></a><span data-ttu-id="5e46a-127">Копирование перспективы</span><span class="sxs-lookup"><span data-stu-id="5e46a-127">To copy a perspective</span></span>  
  
-   <span data-ttu-id="5e46a-128">При наведении указателя мыши на заголовок столбца перспективы появляется кнопка **Копировать** .</span><span class="sxs-lookup"><span data-stu-id="5e46a-128">When you hover over a perspective's column header, the **Copy** button appears.</span></span> <span data-ttu-id="5e46a-129">Для создания копии этой перспективы нажмите кнопку **Копировать** .</span><span class="sxs-lookup"><span data-stu-id="5e46a-129">To create a copy of that perspective, click the **Copy** button.</span></span> <span data-ttu-id="5e46a-130">Копия выбранной перспективы будет добавлена в качестве новой перспективы справа от существующих перспектив.</span><span class="sxs-lookup"><span data-stu-id="5e46a-130">A copy of the selected perspective is added as a new perspective to the right of existing perspectives.</span></span> <span data-ttu-id="5e46a-131">Новая перспектива наследует имя скопированной перспективы, при этом к концу имени добавляется слово *копия* .</span><span class="sxs-lookup"><span data-stu-id="5e46a-131">The new perspective inherits the name of the copied perspective and a *- Copy* annotation is appended to the end of the name.</span></span> <span data-ttu-id="5e46a-132">Например, при создании копии перспективы « *Sales* » новая перспектива называется *Sales-Copy*.</span><span class="sxs-lookup"><span data-stu-id="5e46a-132">For example, if a copy of the *Sales* perspective is created, the new perspective is called *Sales - Copy*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e46a-133">См. также</span><span class="sxs-lookup"><span data-stu-id="5e46a-133">See Also</span></span>  
 <span data-ttu-id="5e46a-134">[Перспективы &#40;табличные&#41;SSAS](perspectives-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="5e46a-134">[Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="5e46a-135">Иерархии (табличные службы SSAS)</span><span class="sxs-lookup"><span data-stu-id="5e46a-135">Hierarchies &#40;SSAS Tabular&#41;</span></span>](hierarchies-ssas-tabular.md)  
  
  
