---
title: Атрибуты (службы Master Data Services) | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- free-form attributes [Master Data Services]
- attributes [Master Data Services], about attributes
- attributes [Master Data Services], file attributes
- file attributes [Master Data Services]
- attributes [Master Data Services], free-form attributes
- attributes [Master Data Services]
ms.assetid: 95ecb75f-c559-41c3-933c-40ae60a4c2fd
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 5a6fb01b47658f39e14c599ae88aa7ad3d29c69a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87667268"
---
# <a name="attributes-master-data-services"></a><span data-ttu-id="d3ad5-102">Атрибуты (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="d3ad5-102">Attributes (Master Data Services)</span></span>
  <span data-ttu-id="d3ad5-103">Атрибуты — это объекты, которые содержатся в сущностях [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d3ad5-103">Attributes are objects that are contained in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] entities.</span></span> <span data-ttu-id="d3ad5-104">Значения атрибутов описывают элементы сущности.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-104">Attribute values describe the members of the entity.</span></span> <span data-ttu-id="d3ad5-105">Атрибут может использоваться для описания конечного элемента, объединенного элемента или коллекции.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-105">An attribute can be used to describe a leaf member, a consolidated member, or a collection.</span></span>  
  
## <a name="how-attributes-relate-to-other-model-objects"></a><span data-ttu-id="d3ad5-106">Связь атрибутов с другими объектами модели</span><span class="sxs-lookup"><span data-stu-id="d3ad5-106">How Attributes Relate to Other Model Objects</span></span>  
 <span data-ttu-id="d3ad5-107">Атрибут можно представить как столбец таблицы сущности.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-107">You can think of an attribute as a column in an entity table.</span></span> <span data-ttu-id="d3ad5-108">Значение атрибута — это значение, описывающее определенный элемент.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-108">An attribute value is the value used to describe a specific member.</span></span>  
  
 <span data-ttu-id="d3ad5-109">![Сущность служб Master Data Services, представленная в виде таблицы](../../2014/master-data-services/media/mds-conc-entity-table.gif "Сущность служб Master Data Services, представленная в виде таблицы")</span><span class="sxs-lookup"><span data-stu-id="d3ad5-109">![Master Data Services Entity Represented as Table](../../2014/master-data-services/media/mds-conc-entity-table.gif "Master Data Services Entity Represented as Table")</span></span>  
  
 <span data-ttu-id="d3ad5-110">При создании сущности, содержащей множество атрибутов, можно организовать атрибуты в группы.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-110">When you create an entity that contains many attributes, you can organize the attributes into attribute groups.</span></span> <span data-ttu-id="d3ad5-111">Дополнительные сведения см. в разделе [Группы атрибутов (службы Master Data Services)](attribute-groups-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d3ad5-111">For more information, see [Attribute Groups &#40;Master Data Services&#41;](attribute-groups-master-data-services.md).</span></span>  
  
## <a name="required-attributes"></a><span data-ttu-id="d3ad5-112">Обязательные атрибуты</span><span class="sxs-lookup"><span data-stu-id="d3ad5-112">Required Attributes</span></span>  
 <span data-ttu-id="d3ad5-113">При создании сущности атрибуты «Имя» и «Код» создаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-113">When you create an entity, the Name and Code attributes are automatically created.</span></span> <span data-ttu-id="d3ad5-114">Атрибут «Код» должен иметь значение, уникальное внутри сущности.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-114">Code requires a value and must be unique within the entity.</span></span> <span data-ttu-id="d3ad5-115">Удалить атрибуты «Имя» и «Код» нельзя.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-115">You cannot remove the Name and Code attributes.</span></span>  
  
## <a name="attribute-types"></a><span data-ttu-id="d3ad5-116">Типы атрибутов</span><span class="sxs-lookup"><span data-stu-id="d3ad5-116">Attribute Types</span></span>  
 <span data-ttu-id="d3ad5-117">Существует три типа атрибутов.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-117">There are three types of attributes:</span></span>  
  
-   <span data-ttu-id="d3ad5-118">Атрибуты свободной формы, допускающие свободный ввод текста, чисел, дат или ссылок.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-118">Free-form attributes, which allow free-form input for text, numbers, dates, or links.</span></span>  
  
-   <span data-ttu-id="d3ad5-119">Атрибуты на основе домена, заполненные сущностями.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-119">Domain-based attributes, which are populated by entities.</span></span> <span data-ttu-id="d3ad5-120">Дополнительные сведения см. в разделе [Атрибуты на основе домена (службы Master Data Services)](../../2014/master-data-services/domain-based-attributes-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d3ad5-120">For more information, see [Domain-Based Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/domain-based-attributes-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="d3ad5-121">Файловые атрибуты, используемые для хранения файлов, документов или изображений.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-121">File attributes, which are used to store files, documents, or images.</span></span> <span data-ttu-id="d3ad5-122">Атрибуты файлов помогают обеспечивать согласованность данных, требуя наличия у файла определенного расширения.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-122">File attributes are intended to help with the consistency of your data by requiring files to have a specific extension.</span></span> <span data-ttu-id="d3ad5-123">Атрибуты файлов не могут гарантированно запретить злоумышленнику передать файл другого типа.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-123">File attributes cannot be guaranteed to prevent a malicious user from uploading a file of a different type.</span></span>  
  
### <a name="numeric-free-form-attributes"></a><span data-ttu-id="d3ad5-124">Числовые атрибуты в свободной форме</span><span class="sxs-lookup"><span data-stu-id="d3ad5-124">Numeric Free-Form Attributes</span></span>  
 <span data-ttu-id="d3ad5-125">Числовые атрибуты в свободной форме нуждаются в специальной обработке, так как они могут иметь значения только типа **SqlDouble** .</span><span class="sxs-lookup"><span data-stu-id="d3ad5-125">Numeric free-form attributes require special handling, because numeric free-form attribute values are limited to the **SqlDouble** value type.</span></span>  
  
 <span data-ttu-id="d3ad5-126">По умолчанию значение **SqlDouble** содержит 15 знаков после запятой, хотя для внутренних целей поддерживается до 17 знаков.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-126">By default, a **SqlDouble** value contains 15 decimal digits of precision, although a maximum of 17 digits is maintained internally.</span></span> <span data-ttu-id="d3ad5-127">Точность числа с плавающей запятой может иметь следующие эффекты.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-127">The precision of a floating-point number has several consequences:</span></span>  
  
-   <span data-ttu-id="d3ad5-128">Два числа с плавающей запятой, которые могут казаться равными при определенной точности, на самом деле отличаются, поскольку их менее значащие цифры различаются.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-128">Two floating-point numbers that appear equal for a particular precision might not compare equal because their least significant digits are different.</span></span>  
  
-   <span data-ttu-id="d3ad5-129">Математическая операция или сравнение, в которой используется число с плавающей запятой, может выдавать разные результаты при использовании десятичного числа, поскольку число с плавающей запятой может не совсем точно соответствовать десятичному числу.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-129">A mathematical or comparison operation that uses a floating-point number might not yield the same result if a decimal number is used because the floating-point number might not exactly approximate the decimal number.</span></span>  
  
-   <span data-ttu-id="d3ad5-130">Значение может не допускать *обратного преобразования* , если представлено числом с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-130">A value might not *roundtrip* if a floating-point number is involved.</span></span> <span data-ttu-id="d3ad5-131">Значение называется обратимым, если после некоторой операции, преобразующей исходное число с плавающей запятой в другой вид, и применения обратной операции, которая возвращает полученный результат обратно к числу с плавающей запятой, получившееся число равно исходному числу с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-131">A value is said to roundtrip if an operation converts an original floating-point number to another form, an inverse operation transforms the converted form back to a floating-point number, and the final floating-point number is equal to the original floating-point number.</span></span> <span data-ttu-id="d3ad5-132">Обратимость может нарушаться, если в результате преобразования теряются или меняются одна или несколько менее значащих цифр.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-132">The roundtrip might fail because one or more least significant digits are lost or changed in a conversion.</span></span>  
  
## <a name="attribute-examples"></a><span data-ttu-id="d3ad5-133">Примеры атрибутов</span><span class="sxs-lookup"><span data-stu-id="d3ad5-133">Attribute Examples</span></span>  
 <span data-ttu-id="d3ad5-134">В следующем примере сущность имеет атрибуты: Name, Code, Subcategory, StandardCost, ListPrice и FilePhoto.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-134">In the following example, the entity has the attributes: Name, Code, Subcategory, StandardCost, ListPrice, and FilePhoto.</span></span> <span data-ttu-id="d3ad5-135">Эти атрибуты описывают элементы.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-135">These attributes describe the members.</span></span> <span data-ttu-id="d3ad5-136">Каждый элемент представлен отдельной строкой значений атрибута.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-136">Each member is represented by a single row of attribute values.</span></span>  
  
 <span data-ttu-id="d3ad5-137">![Таблица продукта «Велосипед»](../../2014/master-data-services/media/mds-conc-entity-table-w-data.gif "Таблица продукта «Велосипед»")</span><span class="sxs-lookup"><span data-stu-id="d3ad5-137">![Bike Product Entity Table](../../2014/master-data-services/media/mds-conc-entity-table-w-data.gif "Bike Product Entity Table")</span></span>  
  
 <span data-ttu-id="d3ad5-138">В следующем примере сущность Product содержит:</span><span class="sxs-lookup"><span data-stu-id="d3ad5-138">In the following example, the Product entity contains:</span></span>  
  
-   <span data-ttu-id="d3ad5-139">атрибуты в свободной форме Name, Code, StandardCost и ListPrice;</span><span class="sxs-lookup"><span data-stu-id="d3ad5-139">The free-form attributes of Name, Code, StandardCost and ListPrice.</span></span>  
  
-   <span data-ttu-id="d3ad5-140">атрибут на основе домена Subcategory;</span><span class="sxs-lookup"><span data-stu-id="d3ad5-140">The domain-based attribute of Subcategory.</span></span>  
  
-   <span data-ttu-id="d3ad5-141">атрибут файла FilePhoto.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-141">The file attribute of FilePhoto.</span></span>  
  
 <span data-ttu-id="d3ad5-142">Сущность Subcategory используется в качестве атрибута на основе домена сущности Product.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-142">Subcategory is an entity that is used as a domain-based attribute of Product.</span></span> <span data-ttu-id="d3ad5-143">Сущность Category используется в качестве атрибута на основе домена сущности Subcategory.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-143">Category is an entity that is used as a domain-based attribute of Subcategory.</span></span> <span data-ttu-id="d3ad5-144">Как и сущность Product, сущности Category и Subcategory по умолчанию содержат атрибуты Name и Code.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-144">Like the Product entity, the Category and Subcategory entities each contain the default Name and Code attributes.</span></span>  
  
 <span data-ttu-id="d3ad5-145">![Древовидная структура сущности «Продукт»](../../2014/master-data-services/media/mds-conc-entity-ui.gif "Древовидная структура сущности «Продукт»")</span><span class="sxs-lookup"><span data-stu-id="d3ad5-145">![Product Entity Tree Structure](../../2014/master-data-services/media/mds-conc-entity-ui.gif "Product Entity Tree Structure")</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="d3ad5-146">Связанные задачи</span><span class="sxs-lookup"><span data-stu-id="d3ad5-146">Related Tasks</span></span>  
  
|<span data-ttu-id="d3ad5-147">Описание задачи</span><span class="sxs-lookup"><span data-stu-id="d3ad5-147">Task Description</span></span>|<span data-ttu-id="d3ad5-148">Раздел</span><span class="sxs-lookup"><span data-stu-id="d3ad5-148">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="d3ad5-149">Создание нового текстового атрибута в свободной форме.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-149">Create a new free-form text attribute.</span></span>|[<span data-ttu-id="d3ad5-150">Создание текстового атрибута (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="d3ad5-150">Create a Text Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-text-attribute-master-data-services.md)|  
|<span data-ttu-id="d3ad5-151">Создание нового числового атрибута в свободной форме.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-151">Create a new free-form numeric attribute.</span></span>|[<span data-ttu-id="d3ad5-152">Создание числового атрибута (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="d3ad5-152">Create a Numeric Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-numeric-attribute-master-data-services.md)|  
|<span data-ttu-id="d3ad5-153">Создание нового атрибута ссылки в свободной форме.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-153">Create a new free-form link attribute.</span></span>|[<span data-ttu-id="d3ad5-154">Создание атрибута ссылки (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="d3ad5-154">Create a Link Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-link-attribute-master-data-services.md)|  
|<span data-ttu-id="d3ad5-155">Создание нового файлового атрибута.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-155">Create a new file attribute.</span></span>|[<span data-ttu-id="d3ad5-156">Создание файлового атрибута (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="d3ad5-156">Create a File Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-file-attribute-master-data-services.md)|  
|<span data-ttu-id="d3ad5-157">Создание нового атрибута на основе домена.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-157">Create a new domain-based attribute.</span></span>|[<span data-ttu-id="d3ad5-158">Создание атрибута на основе домена (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="d3ad5-158">Create a Domain-Based Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md)|  
|<span data-ttu-id="d3ad5-159">Изменение имени существующего атрибута.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-159">Change the name of an existing attribute.</span></span>|[<span data-ttu-id="d3ad5-160">Измените имя атрибута &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d3ad5-160">Change an Attribute Name &#40;Master Data Services&#41;</span></span>](change-an-attribute-name-and-data-type-master-data-services.md)|  
|<span data-ttu-id="d3ad5-161">Добавление существующих атрибутов в группу отслеживания изменений.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-161">Add existing attributes to a change tracking group.</span></span>|[<span data-ttu-id="d3ad5-162">Добавление атрибутов в группу отслеживания изменений (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="d3ad5-162">Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md)|  
|<span data-ttu-id="d3ad5-163">Удаление существующего атрибута.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-163">Delete an existing attribute.</span></span>|[<span data-ttu-id="d3ad5-164">Удаление атрибута (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="d3ad5-164">Delete an Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-an-attribute-master-data-services.md)|  
|<span data-ttu-id="d3ad5-165">Изменение порядка атрибутов.</span><span class="sxs-lookup"><span data-stu-id="d3ad5-165">Change the order of attributes.</span></span>|[<span data-ttu-id="d3ad5-166">Изменение порядка атрибутов</span><span class="sxs-lookup"><span data-stu-id="d3ad5-166">Change the Order of Attributes</span></span>](../../2014/master-data-services/change-the-order-of-attributes.md)|  
  
## <a name="related-content"></a><span data-ttu-id="d3ad5-167">См. также</span><span class="sxs-lookup"><span data-stu-id="d3ad5-167">Related Content</span></span>  
  
-   [<span data-ttu-id="d3ad5-168">Атрибуты на основе домена (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="d3ad5-168">Domain-Based Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/domain-based-attributes-master-data-services.md)  
  
-   [<span data-ttu-id="d3ad5-169">Группы атрибутов (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="d3ad5-169">Attribute Groups &#40;Master Data Services&#41;</span></span>](attribute-groups-master-data-services.md)  
  
-   [<span data-ttu-id="d3ad5-170">Элементы (службы Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="d3ad5-170">Members &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/members-master-data-services.md)  
  
-   [<span data-ttu-id="d3ad5-171">Разрешения конечного элемента (службы основных данных)</span><span class="sxs-lookup"><span data-stu-id="d3ad5-171">Leaf Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/leaf-permissions-master-data-services.md)  
  
-   [<span data-ttu-id="d3ad5-172">Объединенные разрешения &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d3ad5-172">Consolidated Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/consolidated-permissions-master-data-services.md)  
  
  
