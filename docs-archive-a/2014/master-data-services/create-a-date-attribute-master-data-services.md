---
title: Создание атрибута даты (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- creating date attributes [Master Data Services]
- attributes [Master Data Services], creating date attributes
ms.assetid: 22a8f1a3-b4f2-4cfa-8495-7daad5ce9d12
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 93797b90ff03c6a2b60ce8e015897a46a7448aad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87654394"
---
# <a name="create-a-date-attribute-master-data-services"></a><span data-ttu-id="79a83-102">Создание атрибута даты (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="79a83-102">Create a Date Attribute (Master Data Services)</span></span>
  <span data-ttu-id="79a83-103">В среде [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]атрибут даты создается, если нужно, чтобы пользователи вводили даты как значения атрибута.</span><span class="sxs-lookup"><span data-stu-id="79a83-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a date attribute when you want users to enter a date as an attribute value.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="79a83-104">Атрибут называется DateTime, но значения времени не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="79a83-104">The attribute is called DateTime, but time values are not supported.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="79a83-105">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="79a83-105">Prerequisites</span></span>  
 <span data-ttu-id="79a83-106">Для выполнения этой процедуры:</span><span class="sxs-lookup"><span data-stu-id="79a83-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="79a83-107">Необходимо иметь разрешение на доступ к функциональной области **Администрирование системы** .</span><span class="sxs-lookup"><span data-stu-id="79a83-107">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="79a83-108">необходимо быть администратором модели.</span><span class="sxs-lookup"><span data-stu-id="79a83-108">You must be a model administrator.</span></span> <span data-ttu-id="79a83-109">Дополнительные сведения см. в разделе [administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="79a83-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="79a83-110">Должна существовать сущность, для которой создается атрибут.</span><span class="sxs-lookup"><span data-stu-id="79a83-110">You must have an entity to create the attribute for.</span></span> <span data-ttu-id="79a83-111">Дополнительные сведения см. в разделе [Создание сущности (службы Master Data Services)](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="79a83-111">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
### <a name="to-create-a-date-attribute"></a><span data-ttu-id="79a83-112">Создание атрибута даты</span><span class="sxs-lookup"><span data-stu-id="79a83-112">To create a date attribute</span></span>  
  
1.  <span data-ttu-id="79a83-113">В [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]щелкните область **Администрирование системы**.</span><span class="sxs-lookup"><span data-stu-id="79a83-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="79a83-114">На странице **Представление модели** в строке меню наведите курсор на **Управление** и щелкните **Сущности**.</span><span class="sxs-lookup"><span data-stu-id="79a83-114">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="79a83-115">На странице **Обслуживание сущности** выберите модель из списка **Модель** .</span><span class="sxs-lookup"><span data-stu-id="79a83-115">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="79a83-116">Выберите строку сущности, для которой необходимо создать атрибут.</span><span class="sxs-lookup"><span data-stu-id="79a83-116">Select the row for the entity that you want to create an attribute for.</span></span>  
  
5.  <span data-ttu-id="79a83-117">Щелкните **Изменить выбранную сущность**.</span><span class="sxs-lookup"><span data-stu-id="79a83-117">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="79a83-118">На странице **Изменение сущности** :</span><span class="sxs-lookup"><span data-stu-id="79a83-118">On the **Edit Entity** page:</span></span>  
  
    -   <span data-ttu-id="79a83-119">если атрибут предназначен для конечных элементов, выберите команду **Добавить конечный атрибут** на панели **Атрибуты конечных элементов**;</span><span class="sxs-lookup"><span data-stu-id="79a83-119">If the attribute is for leaf members, in the **Leaf member attributes** pane, click **Add leaf attribute**.</span></span>  
  
    -   <span data-ttu-id="79a83-120">если атрибут предназначен для объединенных элементов, выберите команду **Добавить объединенный атрибут** на панели **Атрибуты консолидированных элементов**;</span><span class="sxs-lookup"><span data-stu-id="79a83-120">If the attribute is for consolidated members, in the **Consolidated member attributes** pane, click **Add consolidated attribute**.</span></span>  
  
    -   <span data-ttu-id="79a83-121">если атрибут предназначен для коллекций, выберите команду **Добавить атрибут коллекции** на панели **Атрибуты коллекций**.</span><span class="sxs-lookup"><span data-stu-id="79a83-121">If the attribute is for collections, in the **Collection attributes** pane, click **Add collection attribute**.</span></span>  
  
7.  <span data-ttu-id="79a83-122">Выберите параметр **В свободной форме** на странице **Добавить атрибут** .</span><span class="sxs-lookup"><span data-stu-id="79a83-122">On the **Add Attribute** page, select the **Free-form** option.</span></span>  
  
8.  <span data-ttu-id="79a83-123">Введите имя атрибута в поле **Имя** .</span><span class="sxs-lookup"><span data-stu-id="79a83-123">In the **Name** box, type a name for the attribute.</span></span> <span data-ttu-id="79a83-124">Список слов, которые не должны использоваться в качестве имен атрибутов, см. в разделе [зарезервированные слова &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="79a83-124">For a list of words that should not be used as attribute names, see [Reserved Words &#40;Master Data Services&#41;](../../2014/master-data-services/reserved-words-master-data-services.md).</span></span>  
  
9. <span data-ttu-id="79a83-125">В поле **Ширина отображаемой области (в пикселях)** введите ширину столбца атрибута для отображения в сетке **обозревателя** .</span><span class="sxs-lookup"><span data-stu-id="79a83-125">In the **Display pixel width** box, type the width of the attribute column to be displayed in the **Explorer** grid.</span></span>  
  
10. <span data-ttu-id="79a83-126">В списке **Тип данных** выберите **DateTime**.</span><span class="sxs-lookup"><span data-stu-id="79a83-126">From the **Data type** list, select **DateTime**.</span></span>  
  
11. <span data-ttu-id="79a83-127">Выберите из списка **Маска ввода** формат дат.</span><span class="sxs-lookup"><span data-stu-id="79a83-127">From the **Input mask** list, select a format for dates.</span></span>  
  
12. <span data-ttu-id="79a83-128">По желанию установите флажок **Включить отслеживание изменений** , чтобы отслеживать изменения в группах атрибутов.</span><span class="sxs-lookup"><span data-stu-id="79a83-128">Optionally, select **Enable change tracking** to track changes to groups of attributes.</span></span> <span data-ttu-id="79a83-129">Дополнительные сведения см. в разделе [Добавление атрибутов в группу отслеживания изменений (службы Master Data Services)](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="79a83-129">For more information, see [Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span></span>  
  
13. <span data-ttu-id="79a83-130">Нажмите кнопку **Сохранить атрибут**.</span><span class="sxs-lookup"><span data-stu-id="79a83-130">Click **Save attribute**.</span></span>  
  
14. <span data-ttu-id="79a83-131">На странице **Обслуживание сущности** нажмите кнопку **Сохранить сущность**.</span><span class="sxs-lookup"><span data-stu-id="79a83-131">On the **Entity Maintenance** page, click **Save entity**.</span></span>  
  
## <a name="to-display-the-time-portion-of-a-datetime-value"></a><span data-ttu-id="79a83-132">Отображение части времени значения типа datetime</span><span class="sxs-lookup"><span data-stu-id="79a83-132">To display the time portion of a datetime value</span></span>  
 <span data-ttu-id="79a83-133">Чтобы пользовательский интерфейс отображал время из значения типа datetime, необходимо выбрать подходящую маску ввода для этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="79a83-133">To have the user interface display the time portion of a datetime value, you must select an appropriate input mask for the attribute.</span></span> <span data-ttu-id="79a83-134">Для этого не подходит ни одна из встроенных масок для атрибутов значения типа Datetime, но вы можете добавить новую маску, которая позволит отобразить значение времени.</span><span class="sxs-lookup"><span data-stu-id="79a83-134">None of the built-in masks for Datetime attributes do this, but you can add a new mask that will allow you to display time.</span></span> <span data-ttu-id="79a83-135">Для этого добавьте строку в таблицу mdm.tblList базы данных MDS, где будут храниться встроенные маски.</span><span class="sxs-lookup"><span data-stu-id="79a83-135">To do so, add a row in the mdm.tblList table of the MDS database, where the built-in masks are stored.</span></span> <span data-ttu-id="79a83-136">Строка должна иметь следующие значения:</span><span class="sxs-lookup"><span data-stu-id="79a83-136">The row should have the following values:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="79a83-137">ListCode</span><span class="sxs-lookup"><span data-stu-id="79a83-137">ListCode</span></span>|<span data-ttu-id="79a83-138">lstInputMask</span><span class="sxs-lookup"><span data-stu-id="79a83-138">lstInputMask</span></span>|  
|<span data-ttu-id="79a83-139">ListName</span><span class="sxs-lookup"><span data-stu-id="79a83-139">ListName</span></span>|<span data-ttu-id="79a83-140">Маска ввода</span><span class="sxs-lookup"><span data-stu-id="79a83-140">Input Mask</span></span>|  
|<span data-ttu-id="79a83-141">Seq</span><span class="sxs-lookup"><span data-stu-id="79a83-141">Seq</span></span>|<span data-ttu-id="79a83-142">19</span><span class="sxs-lookup"><span data-stu-id="79a83-142">19</span></span>|  
|<span data-ttu-id="79a83-143">List Option</span><span class="sxs-lookup"><span data-stu-id="79a83-143">List Option</span></span>|<span data-ttu-id="79a83-144">dd/MM/yyyy hh:mm:ss tt</span><span class="sxs-lookup"><span data-stu-id="79a83-144">dd/MM/yyyy hh:mm:ss tt</span></span>|  
|<span data-ttu-id="79a83-145">Option ID</span><span class="sxs-lookup"><span data-stu-id="79a83-145">Option ID</span></span>|<span data-ttu-id="79a83-146">19</span><span class="sxs-lookup"><span data-stu-id="79a83-146">19</span></span>|  
|<span data-ttu-id="79a83-147">IsVisible</span><span class="sxs-lookup"><span data-stu-id="79a83-147">IsVisible</span></span>|<span data-ttu-id="79a83-148">1</span><span class="sxs-lookup"><span data-stu-id="79a83-148">1</span></span>|  
|<span data-ttu-id="79a83-149">Group_ID</span><span class="sxs-lookup"><span data-stu-id="79a83-149">Group_ID</span></span>|<span data-ttu-id="79a83-150">3</span><span class="sxs-lookup"><span data-stu-id="79a83-150">3</span></span>|  
  
 <span data-ttu-id="79a83-151">После ввода строки с приведенными выше значениями в таблицу mdm.tblList маска dd/MM/yyyy hh:mm:ss tt становится доступной в списке масок ввода.</span><span class="sxs-lookup"><span data-stu-id="79a83-151">After you enter a row with the above values in the mdm.tblList table, the "dd/MM/yyyy hh:mm:ss tt" mask will be available in the Input mask list box.</span></span> <span data-ttu-id="79a83-152">Теперь вы можете выбрать эту маску для отображения даты и времени в столбце атрибутов datetime сущности в обозревателе MDS.</span><span class="sxs-lookup"><span data-stu-id="79a83-152">You can then select that mask to display the date and time in a datetime attribute column of an entity in the MDS Explorer.</span></span>  
  
 <span data-ttu-id="79a83-153">Маска ввода — это настраиваемая строка форматирования даты и времени .NET.</span><span class="sxs-lookup"><span data-stu-id="79a83-153">The Input Mask is a custom .NET DateTime format string.</span></span> <span data-ttu-id="79a83-154">Дополнительную информацию см. в разделе [Настраиваемые строки формата даты и времени](https://msdn.microsoft.com/library/8kb3ddd4\(v=vs.110\).aspx)</span><span class="sxs-lookup"><span data-stu-id="79a83-154">For more information, see [Custom Date and Time Format Strings](https://msdn.microsoft.com/library/8kb3ddd4\(v=vs.110\).aspx)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79a83-155">См. также:</span><span class="sxs-lookup"><span data-stu-id="79a83-155">See Also</span></span>  
 <span data-ttu-id="79a83-156">[Master Data Services &#40;атрибутов&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="79a83-156">[Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="79a83-157">[Измените имя атрибута &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="79a83-157">[Change an Attribute Name &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span></span>  
 <span data-ttu-id="79a83-158">[Создание атрибута на основе домена &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="79a83-158">[Create a Domain-Based Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md) </span></span>  
 [<span data-ttu-id="79a83-159">Создание файлового атрибута (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="79a83-159">Create a File Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-file-attribute-master-data-services.md)  
  
  
